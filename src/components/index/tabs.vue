<template>
  <b-card no-body>
    <b-tabs card v-model="tabIndex">
      <b-tab title="Tab 1" :title-link-class="linkClass(0)">
        Tab Contents 1
      </b-tab>
      <b-tab title="Tab 2" :title-link-class="linkClass(1)">
        Tab Contents 2
      </b-tab>
      <b-tab title="Tab 3" :title-link-class="linkClass(2)">
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
          return ['bg-primary', 'text-light']
        } else {
          return ['bg-light', 'text-info']
        }
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

</style>
