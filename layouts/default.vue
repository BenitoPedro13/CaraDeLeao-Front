<template>
  <div class="default-layout">
    <FooterBottom :cor="backgroundColor" :somos="marca" />
  </div>
</template>

<script>
import FooterBottom from '@/components/FooterBottom.vue'
export default {
  components: {
    FooterBottom,
  },
  data() {
    return {
      backgroundColor: '#F0892E',
      marca: 'cara de leao',
    }
  },
}
</script>

<style scoped>
@import url('http://fonts.cdnfonts.com/css/axiforma');

@import url('http://fonts.cdnfonts.com/css/nexa-bold');

.default-layout {
  font-family: 'Axiforma', sans-serif;
}

font-size: 18px;
line-height: 18px;

font-size: 18px;
font-weight: bold;
line-height: 20px;

font-family: Nexa;
font-size: 18px;
font-style: normal;
font-weight: 300;
line-height: 14px;
letter-spacing: 0em;
text-align: left;
</style>
