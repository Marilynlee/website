<template>
  <b-card no-body  class="container">
    <b-tabs card v-model="tabIndex">
      <b-tab title="Tab 1" :title-link-class="linkClass(0)" :title-item-class="itemClass()">
        tab 1
      </b-tab>
      <b-tab title="Tab 2" :title-link-class="linkClass(1)" :title-item-class="itemClass()">
        Tab Contents 2
      </b-tab>
      <b-tab title="Tab 3" :title-link-class="linkClass(2)" :title-item-class="itemClass()">
        Tab Contents 3
      </b-tab>
    </b-tabs>
  </b-card>
</template>

<script>
  import Vue from 'vue'
  import BootstrapVue from 'bootstrap-vue'
  import 'bootstrap/dist/css/bootstrap.css'
  import 'bootstrap-vue/dist/bootstrap-vue.css'

  Vue.use(BootstrapVue);
  export default {
    name: 'tabs',
    component: 'tabs',
    data () {
      return {
        tabIndex: 0
      }
    },
    methods: {
      linkClass (idx) {
        if (this.tabIndex === idx) {
          return ['bg-success', 'text-light']
        } else {
          return ['bg-info', 'text-light']
        }
      },
      itemClass () {
        return ['col-4', 'text-center']
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  .card-header-tabs{
    margin:0;
  }
</style>
