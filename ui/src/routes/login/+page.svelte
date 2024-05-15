<script lang="ts">
  import { currentUser, pb } from "$lib/pocketbase";

  let username: string;
  let password: string;

  async function login() {
    await pb.collection("users").authWithPassword(username, password);
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
  <main class="columns">
    <section class="section column is-4 is-offset-4 is-large">
      <form on:submit|preventDefault>
        <div class="field">
          <input
            placeholder="username"
            class="input"
            type="text"
            bind:value={username}
          />
        </div>
        <div class="field">
          <input
            class="input"
            placeholder="password"
            type="password"
            bind:value={password}
          />
        </div>
        <div class="field">
          <div class="control">
            <input
              on:click={login}
              type="submit"
              value="Login"
              class="button is-primary is-fullwidth"
            />
          </div>
        </div>
      </form>
      <div class="is-flex is-justify-content-center p-4">
        <a class="has-text-dark" href="/auth/reset-password"
          >Trouble logging in?</a
        >
      </div>
    </section>
  </main>
{/if}
