<template>
  <div id="app">
    <header class="st-header">
      <nav>
        <div id="nav">
          <router-link to="/"><font-awesome-icon icon="home" class="tp-heaer_icon" /> ホーム</router-link>
          <router-link to="/about"><font-awesome-icon icon="vial" class="tp-heaer_icon" /> シミュレーション</router-link>
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
  position: relative;
}

.st-header {
  background: #42b983;
}

.tp-heaer_icon {
  font-size: 1.2rem;
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
