<template>
  <button>
    <img src="@/assets/img/wpp.svg" alt="whatsapp">
    <p>falar agora</p>
  </button>
</template>

<script>
export default {
    name: "WppCTA",
    props: {
        phone: {
            type: String,
            default: ''
        }
    }
}
</script>

<style lang="scss" scoped>
button {
    width: 240px;
    height: 78px;
    border-radius: 40px;
    color: white;
    background-color: #389653;
    padding: 23px 40px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-weight: bold;
    font-size: 20px;
    line-height: 33px;
}
</style>