<script lang="ts">
    import { currentUser, pb} from "$lib/pocketbase";

    let username: string;
    let password: string;

    async function login() {
        await pb.collection('users').authWithPassword(username, password);
    }

    function logout() {
        pb.authStore.clear();
    }

</script>

{#if $currentUser}
    <p>
        Signed in as {$currentUser.username}
    </p>
    <button on:click={logout}>Logout</button>
{:else}
    <form on:submit|preventDefault>
        <input placeholder="username" type="text" bind:value={username} />
        <input placeholder="password" type="password" bind:value={password} />
    </form>
    <button on:click={login}>Login</button>
{/if}