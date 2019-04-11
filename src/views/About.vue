<template>
  <div class="about">
    <h1 class="ct-heading">シミュレーションページ</h1>
    <Simulation />
  </div>
</template>

<script>
// @ is an alias to /src
import Simulation from '@/components/Simulation.vue'

export default {
  name: 'about',
  components: {
    Simulation
  }
}
</script>

<!-- CSSカプセル化 -->
<style scoped lang="scss">
.ct-heading {
  font-size: 1.4rem;
}
</style>
