<template>
  <v-app>
    <protocol-builder
      exportButton
    />
  </v-app>
</template>

<style>

.primary {
  background-color: #005fa3 !important;
  border-color: #005fa3 !important;
}

</style>

<script>

import ProtocolBuilder from './components/ProtocolBuilder/ProtocolBuilder.vue';

export default {
  name: 'App',
  components: {
    ProtocolBuilder
  },
}
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css?family=IBM+Plex+Sans:300,400');
</style>

<style>

body, html, #app {
  font-family: 'IBM Plex Sans', sans-serif !important;
  width: 100%;
  height: 100%;
}

</style>
