<template>
  <nav
    class="navbar is-black is-fixed-top"
    role="navigation"
    aria-label="main navigation"
  >
    <div class="container">
      <div class="navbar-brand">
        <a class="navbar-item" href="/">
          <img
            src="https://img.icons8.com/color/50/000000/rick-sanchez.png"
            width="28"
            height="28"
          />
        </a>

        <a
          v-on:click="dropdown"
          role="button"
          class="navbar-burger burger"
          aria-label="menu"
          aria-expanded="false"
          data-target="navbarBasicExample"
        >
          <span aria-hidden="true" />
          <span aria-hidden="true" />
          <span aria-hidden="true" />
        </a>
      </div>

      <div id="navbarBasicExample" class="navbar-menu">
        <div class="navbar-start">
          <div class="navbar-item has-dropdown is-hoverable">
            <a class="navbar-link">
              API
            </a>
            <div class="navbar-dropdown is-black">
              <p class="navbar-item item-dropdown">
                The below links are external urls<br />
                To return to this page, click back button
              </p>
              <hr class="navbar-divider" />
              <a
                class="navbar-item item-dropdown"
                href="https://rickandmortyapi.com/documentation"
              >
                Documentation
              </a>
              <a
                class="navbar-item item-dropdown"
                href="https://rickandmortyapi.com/about"
              >
                About
              </a>
              <a
                class="navbar-item item-dropdown"
                href="https://rickandmortyapi.com/help-us"
              >
                Help Us
              </a>
            </div>
          </div>
        </div>
        <div class="navbar-end">
          <div class="navbar-item">
            <div class="buttons">
              <a
                class="button-green"
                href="https://github.com/jdsmith022/RickAndMorty"
              >
                <strong>Git Repo</strong>
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  methods: {
    dropdown() {
      this.$el.querySelector(".navbar-burger").classList.toggle("is-active");
      document.querySelector(".navbar-menu").classList.toggle("is-active");
    }
  }
};
</script>
