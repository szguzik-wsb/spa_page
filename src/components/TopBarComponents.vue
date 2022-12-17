<template>
  <nav class="navbar" role="navigation" aria-label="main navigation">
    <div class="navbar-brand">
      <a class="navbar-item" href="https://bulma.io">
        <img src="https://www.wsb.pl/themes/custom/wsb/images/logos/logo_wsb.png" style="width:200px;">
      </a>

      <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false" data-target="navbarBasicExample" @click="showMenuBurger(!showMobileMenu)">
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>
    </div>

    <div id="navbarBasicExample" class="navbar-menu" :class="{ 'show-burger': showMobileMenu }">
      <div class="navbar-start">
        <RouterLink to="/" class="navbar-item">Witamy</RouterLink>
        <RouterLink to="/studia-i-szkolenia" class="navbar-item">Studia i szkolenia</RouterLink>
        <RouterLink to="/galeria" class="navbar-item">Galeria</RouterLink>
        <a class="navbar-item">
          Wspołpraca z biznesem
        </a>
        <a class="navbar-item">
          Badania i nauka
        </a>
      </div>

      <div class="navbar-end">
        <div class="navbar-item">
          <div class="buttons">
            <a class="button is-primary">
              <strong>Extranet</strong>
            </a>
            <a class="button is-light">
              Moodle
            </a>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "TopBarComponents",
  data() {
    return {
      showMobileMenu: false
    }
  },

  methods: {
    showMenuBurger(state) {
      this.showMobileMenu = state
    }
  }
}
</script>

<style scoped>
.navbar-item img {
  max-height: unset;
}

.show-burger {
  display: block;
}
</style>