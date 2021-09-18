<template>
  <v-app-bar
    flat
    hide-on-scroll
    :collapse="!collapseOnScroll"
    :collapse-on-scroll="collapseOnScroll"
    color="transparent"
    height="144"
    app
  >
    <nuxt-link to="/">
      <img class="logo" src="../assets/img/logo.svg" alt="" />
      <v-toolbar-title v-text="title" />
    </nuxt-link>
    <v-spacer />
    <v-btn-toggle v-model="toggle_exclusive" mandatory group class="nav">
      <nuxt-link to="/sobre">
        <v-btn text class="nav-menu">sobre</v-btn>
      </nuxt-link>
      <nuxt-link to="/">
        <v-btn text class="nav-menu">home</v-btn>
      </nuxt-link>
      <nuxt-link to="/produtos">
        <v-btn text class="nav-menu">produtos</v-btn>
      </nuxt-link>
      <nuxt-link to="/contato">
        <v-btn text class="nav-menu">contato</v-btn>
      </nuxt-link>
    </v-btn-toggle>
  </v-app-bar>
</template>

<script>
export default {
  name: 'Navbar',
  props: {
    title: {
      type: String,
      default: 'cara de leao',
    }
  },
  data() {
    return {
      toggle_exclusive: undefined,
      collapseOnScroll: true,
      primaryColor: "transparent"
    }
  },
}
</script>

<style lang="scss" scoped>
$font-color-primary: white !important;
$font-color-secondary: black !important;

$bg-color-primary: #f2994a !important;
$bg-color-secondary: #219653 !important;

$font-stack-primary: 'Axiforma', sans-serif;
$font-stack-secondary: 'Nexa';

$font-size-header-logo: 24px;
$font-size-line: 24px;
$font-size-footer-big: 36px;
$font-size-footer-small: 14px;
$font-size-footer-cta-header: 20px;
$font-size-footer-cta-subheader: 28px;
$font-size-copyright: 14px;

a {
  text-decoration: none;
}

header {
  width: 100vw;
  padding: 0 23px;
}

.v-toolbar__content > a {
  display: flex;
  align-items: center;
}

.v-toolbar__title {
  margin-left: 16px;
  font-family: $font-stack-primary;
  font-weight: bold;
  color: $font-color-primary;
  font-size: $font-size-header-logo;
  line-height: 31px;
  letter-spacing: -0.5px;
}

.nav {
  width: 35%;
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
}

.theme--light.v-btn--active:hover::before,
.theme--light.v-btn--active::before {
  opacity: 0 !important;
}

.nav-menu {
  font-family: $font-stack-primary;
  margin: 0 auto;
  text-transform: lowercase !important;
  font-weight: thin;
  display: flex;
  position: relative;
  flex-direction: column;
  color: $font-color-primary;
}
.nuxt-link-exact-active {
  .nav-menu {
    font-weight: bold;
  }
}
</style>