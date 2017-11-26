<template>
  <div>
    <b-carousel id="carousel"
                style="text-shadow: 1px 1px 2px #333;"
                controls
                indicators
                background="#ababab"
                :interval="3000"
                v-model="slide"
                @sliding-start="onSlideStart"
                @sliding-end="onSlideEnd"
    >

      <!-- Text slides with image -->
      <b-carousel-slide caption="First slide"
                        text="Nulla vitae elit libero, a pharetra augue mollis interdum.">
        <img src="../../assets/c1.jpg"  slot="img" class="d-block img-fluid w-100">
      </b-carousel-slide>

      <!-- Slides with custom text -->
      <b-carousel-slide>
        <h1>Hello world!</h1>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse
          eros felis, tincidunt a tincidunt eget, convallis vel est. Ut pellentesque
          ut lacus vel interdum.
        </p>
        <img src="../../assets/c2.jpg"  slot="img" class="d-block img-fluid w-100">
      </b-carousel-slide>

      <!-- Slides with image only -->
      <b-carousel-slide>
        <img src="../../assets/c3.jpg"  slot="img" class="d-block img-fluid w-100">
      </b-carousel-slide>

      <!-- Slides with img slot -->
      <!-- Note the classes .d-block and .img-fluid to prevent browser default image alignment -->
      <b-carousel-slide>
        <img slot="img" class="d-block img-fluid w-100" src="../../assets/c4.jpg">
        <p>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse
        eros felis, tincidunt a tincidunt eget, convallis vel est. Ut pellentesque
        ut lacus vel interdum.
      </p>
      </b-carousel-slide>
    </b-carousel>
  </div>
</template>

<script>
  import Vue from 'vue'
  import BootstrapVue from 'bootstrap-vue'
  import 'bootstrap/dist/css/bootstrap.css'
  import 'bootstrap-vue/dist/bootstrap-vue.css'

  Vue.use(BootstrapVue);

  export default {
    name: 'carousel',
    component:'carousel',
    data () {
      return {
        slide: 0,
        sliding: null
      }
    },
    methods: {
      onSlideStart (slide) {
        this.sliding = true
      },
      onSlideEnd (slide) {
        this.sliding = false
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  .carousel-control-prev-icon, .carousel-control-next-icon {
    width: 40px;
    height: 40px;
  }
  .carousel-control-prev, .carousel-control-next {


  }
</style>
