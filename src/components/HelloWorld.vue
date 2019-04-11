<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>これは仮想のシミュレーションサイトです。</p>
    <router-link class="sw-btn" to="/about">シミュレーションスタート</router-link>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- CSSカプセル化 -->
<style scoped lang="scss">
.sw-btn {
  display: inline-block;
  font-weight: bold;
  text-decoration: none;
  background: #42b983;
  color: #ffffff;
  border-radius: 2rem;
  padding: 1rem;
}
</style>
