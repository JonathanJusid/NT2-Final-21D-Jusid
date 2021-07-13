<template>
  <div id="app" class="container-fluid mt-3">
    <div class="jumbotron">
      <Codificacion />
    </div>
  </div>
</template>

<script>

import Codificacion from './components/Codificacion.vue'

export default {
  name: 'App',
  components: {
    Codificacion,
  }
}
</script>

<style>

h1 {
  color: black;
}

.jumbotron {
  padding: 32px !important;
}

</style>

