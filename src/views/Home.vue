<template>
  <div class="home">
    <div class="tp-main_img">
      <img alt="" src="../assets/top_illust.svg">
    </div>
    <HelloWorld msg="PWAサンプルアプリ"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  components: {
    HelloWorld
  }
}
</script>

<style scoped lang="scss">
.tp-main_img {
  width: 80%;
  margin: 4rem auto;
  img {
    width: 100%;
    height: auto;
  }
}
</style>
