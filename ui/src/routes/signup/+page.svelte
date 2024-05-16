<script lang="ts">
  import { currentUser, pb } from "$lib/pocketbase";

  let email: string;
  let password: string;
  let confirmPassword: string;

  async function signup() {
    await pb.collection("users").create();
  }
</script>

<main class="columns">
  <section class="section column is-4 is-offset-4 is-large">
    <form on:submit|preventDefault>
      <div class="field">
        <input
          placeholder="email"
          class="input"
          type="text"
          bind:value={email}
        />
      </div>
      <div class="field">
        <input
          placeholder="password"
          class="input"
          type="password"
          bind:value={password}
        />
      </div>
      <div class="field">
        <input
          placeholder="confirm password"
          class="input"
          type="password"
          bind:value={confirmPassword}
        />
      </div>
    </form>
  </section>
</main>
