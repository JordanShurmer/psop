
<p>
{#if user.loggedIn}
  You are logged in as {user.webId}.
  <button on:click="logout()">Logout</button>
{:else}
  You are not logged in.
  <button on:click="login()">Login</button>
{/if}
</p>

<script>
import auth from 'solid-auth-client';

export default {
    oncreate() {
        auth.trackSession(session => {
            this.set({user: {
                loggedIn: !!session,
                webId: session && session.webId || ''
            }});
        })
    },
    methods: {
        logout() {
            auth.logout();
        },
        async login() {
            console.log("%cLogging In", "color: mediumseagreen; font-weight: bolder");
            const session = await auth.currentSession();
            if (!session) {
                await auth.popupLogin({popupUri: "https://solid.github.io/solid-auth-client/dist/popup.html"});
            } else {
                this.set({user: {
                    loggedIn: true,
                    webId: session.webId
                }});
            }
        }
    }
}
</script>