<template>
  <div id="app">
    <header class="st-header">
      <nav>
        <div id="nav">
          <router-link to="/">ホーム</router-link>
          <router-link to="/about">シミュレーション</router-link>
        </div>
      </nav>
    </header>
    <router-view/>
  </div>
</template>

<script>
import 'normalize.css'

export default {
  name: 'App'
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.st-header {
  background: #42b983;
}

#nav {
  padding: 1rem;
  a {
    font-weight: bold;
    display: inline-block;
    color: #ffffff;
    &:first-child {
      margin-right: 1rem;
    }
    &.router-link-exact-active {
      font-weight: bold;
      text-decoration: none;
    }
  }
}
</style>
