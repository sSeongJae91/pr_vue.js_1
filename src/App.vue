<template>
  <div id="app">
    <app-header/>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader'

export default {
  name: 'App',
  components: {
    AppHeader
  }
}
</script>

<style>
@import "./style/reset.css";
#app {
  width: 560px;
  margin: 0 auto;
}
</style>
