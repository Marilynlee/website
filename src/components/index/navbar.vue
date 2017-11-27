<template>
  <div class="container">
    <b-navbar toggleable="lg" type="light" variant="light">
      <b-navbar-toggle target="nav_collapse"></b-navbar-toggle>
      <b-collapse is-nav id="nav_collapse">

        <b-navbar-brand href="#">Siknut</b-navbar-brand>

        <b-navbar-nav fill justify>
          <b-nav-item href="#">Linklink</b-nav-item>
          <b-nav-item-dropdown text="Lang" right @hover="expandDropdown(e)">
            <b-dropdown-item href="#">EN</b-dropdown-item>
            <b-dropdown-item href="#">ES</b-dropdown-item>
            <b-dropdown-item href="#">RU</b-dropdown-item>
            <b-dropdown-item href="#">FA</b-dropdown-item>
          </b-nav-item-dropdown>
          <b-nav-item-dropdown text="分类" right>
            <b-dropdown-item href="#">带壳坚果</b-dropdown-item>
            <b-dropdown-item href="#">带皮坚果</b-dropdown-item>
            <b-dropdown-item href="#">有核坚果</b-dropdown-item>
            <b-dropdown-item href="#">无核坚果</b-dropdown-item>
          </b-nav-item-dropdown>
          <b-nav-item-dropdown text="主题" right>
            <b-dropdown-item>one</b-dropdown-item>
            <b-dropdown-item>two</b-dropdown-item>
            <b-dropdown-divider></b-dropdown-divider>
            <b-dropdown-item>three</b-dropdown-item>
          </b-nav-item-dropdown>
          <b-nav-form>
            <b-form-input size="sm" class="mr-sm-2" type="text" placeholder="Search"/>
            <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
          </b-nav-form>

        </b-navbar-nav>

        <!-- Right aligned nav items -->
        <b-navbar-nav  class="ml-auto">
          <b-nav-item-dropdown text="语言" right>
            <b-dropdown-item href="#">中文</b-dropdown-item>
            <b-dropdown-item href="#">EN</b-dropdown-item>
          </b-nav-item-dropdown>
          <b-nav-item-dropdown text="用户中心" right>
            <b-dropdown-item href="#">Account</b-dropdown-item>
            <b-dropdown-item href="#">Settings</b-dropdown-item>
          </b-nav-item-dropdown>
        </b-navbar-nav>

      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
  import Vue from 'vue'
  import BootstrapVue from 'bootstrap-vue'
  import 'bootstrap/dist/css/bootstrap.css'
  import 'bootstrap-vue/dist/bootstrap-vue.css'

  Vue.use(BootstrapVue);
  export default {
    name: 'navbar',
    component: 'navbar',
    methods: {
      expandDropdown(e){
        debugger;
        this.dropup=true;
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  .alert {
    margin-bottom: 0;
  }

  .alert-dark {
    color: #f3eeee;
    background-color: #1b1e21;
    border-color: #1b1e21;
  }

  .navbar-light .navbar-nav .nav-link {
    color: #999;
    font-weight: bold;
  }
  .navbar {
    padding: 0 1rem;
  }
  .nav-fill .nav-item {
    padding: 0.5rem;
  }

</style>
