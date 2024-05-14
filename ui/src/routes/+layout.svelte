<script>
  import "../app.scss";
</script>

<header>
  <nav class="navbar">
    <a
      href="/"
      class="navbar-item is-size-3 has-text-weight-bold has-text-primary-invert"
    >
      towourney
    </a>
    <div class="navbar-end">
      <div class="navbar-item">
        <div class="buttons">
          <a href="/signup" class="button is-primary"
            ><strong>Sign up</strong></a
          >
          <a href="/login" class="button is-light">Log in</a>
        </div>
      </div>
    </div>
  </nav>
</header>

<slot></slot>
