<template>
  <div id="app">
    <InvoiceMain></InvoiceMain>
  </div>
</template>

<script>

import InvoiceMain from './components/InvoiceMain.vue'


export default {
  name: 'app',
  components: {
    InvoiceMain
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>