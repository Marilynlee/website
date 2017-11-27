<template>
  <div>
    <b-alert show dismissible variant="dark">
      Dismissible Alert! Click the close button over there <b>&rArr;</b>
    </b-alert>
    <div id="app">
      <navbar></navbar>
      <carousel></carousel>
      <tabs></tabs>
    </div>
  </div>
</template>

<script>
import navbar from "./components/index/navbar";
import carousel from "./components/index/carousel";
import tabs from "./components/index/tabs";


export default {
  name: 'app',
  components:{navbar,carousel,tabs}
}
</script>

<style>
</style>
