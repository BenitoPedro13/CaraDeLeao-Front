<template>
  <div class="default-layout">
    <Navbar :title="marca"/>
    <Nuxt style="min-height: 100vh"/>
    <FooterBottom :cor="backgroundColor" :somos="marca" />
  </div>
</template>

<script>
import FooterBottom from '@/components/FooterBottom.vue'
import Navbar from '@/components/Navbar.vue'

export default {
  components: {
    FooterBottom,
    Navbar
  },
  data() {
    return {
      backgroundColor: '#F0892E',
      marca: 'cara de leao'
    }
  },
}
</script>

<style lang="scss" scoped>
@import url('http://fonts.cdnfonts.com/css/axiforma');
@import url('http://fonts.cdnfonts.com/css/nexa-bold');

$font-color-primary: white !important;
$font-color-secondary: black !important;

$bg-color-primary: #F2994A !important;
$bg-color-secondary: #219653 !important;

$font-stack-primary: 'Axiforma', sans-serif;
$font-stack-secondary: 'Nexa';

.default-layout {
  font-family: 'Axiforma', sans-serif;
  background-color: $bg-color-primary !important;
}

</style>
