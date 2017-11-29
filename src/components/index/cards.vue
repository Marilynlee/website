<template>
  <div class="container card">
    <div class="titleBox">
      <h2 class="newItemList-title">New Products in the Shop</h2>
    </div>
    <b-card-group deck>
      <b-card title="$32"
              img-src="/static/c1.jpg"
              img-alt="Img"
              img-top>
        <p class="card-text">
          59% Cotton Lorem Ipsum Dolor Sit Amet esed ultrices sapien nunc nam frignila
        </p>
      </b-card>
      <b-card title="$32"
              img-src="/static/c2.jpg"
              img-alt="Img"
              img-top>
        <p class="card-text">
          59% Cotton Lorem Ipsum Dolor Sit Amet esed ultrices sapien nunc nam frignila
        </p>
      </b-card>
      <b-card title="$32"
              img-src="/static/c3.jpg"
              img-alt="Img"
              img-top>
        <p class="card-text">
          59% Cotton Lorem Ipsum Dolor Sit Amet esed ultrices sapien nunc nam frignila
        </p>
      </b-card>
    </b-card-group>
  </div>
</template>

<script>
  import Vue from 'vue'
  import BootstrapVue from 'bootstrap-vue'
  import 'bootstrap/dist/css/bootstrap.css'
  import 'bootstrap-vue/dist/bootstrap-vue.css'
  import 'swiper/dist/css/swiper.css'
  export default {
    name: 'cards',
    component: 'cards'
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  .newItemList-title {
    margin: 40px 0 20px;
  }
  .titleBox {
    position: relative;
    margin-bottom: 20px;
  }
  .titleBox:after {
    content: "";
    position: absolute;
    bottom: 0;
    width: 50px;
    height: 2px;
    background-color: #e0e0e0;
  }
</style>
