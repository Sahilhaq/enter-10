<template>
  <div id="app">
    <app-header></app-header>
    <router-view/>
  </div>
</template>

<script>
  import appHeader from './components/Header.vue'

  export default {
    name: 'App',
    components: {
      appHeader
    }
  }
</script>

<style>
#app {
  margin: 0;
  padding: 0;
}
</style>
