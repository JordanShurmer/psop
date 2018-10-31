<h1>Personal Solid Pod</h1>
<Login loggedIn="{user.loggedIn}"></Login>

<script>
export default {
    data() {
        return {
            user: {}
        }
    },
    components: {
        Login: './Login.svelte',
    }
}
</script>

<style>
	h1 {
		color: purple;
	}
</style>
