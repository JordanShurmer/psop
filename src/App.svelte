<h1>Personal Solid Pod</h1>

<Login bind:user=user></Login>

<Acl></Acl>

<script>
export default {
    data() {
        return {
            user: {
                loggedIn: false,
                webId: ''
            }
        }
    },
    components: {
        Login: './Login.svelte',
        Acl: './Acl.svelte',
    }
}
</script>

<style>
	h1 {
		color: purple;
	}
</style>
