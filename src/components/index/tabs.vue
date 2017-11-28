<template>
  <b-card no-body class="container">
    <b-tabs card v-model="tabIndex">
      <b-tab title="促销商品" :title-link-class="linkClass(0)" :title-item-class="itemClass()">
        <swiper :options="swiperOption" ref="mySwiper">
          <!-- 这部分放你要渲染的那些内容 -->
          <swiper-slide v-for="item in discountItems" :key="item.id">
            <img class="swiper-image item.src" src="item.src" alt="swiper-image"/>
          </swiper-slide>
        </swiper>
      </b-tab>
      <b-tab title="新品尝鲜" :title-link-class="linkClass(1)" :title-item-class="itemClass()">
        <swiper :options="swiperOption" ref="mySwiper">
          <!-- 这部分放你要渲染的那些内容 -->
          <swiper-slide v-for="item in newItems" :key="item.id">
            <img class="swiper-image" src="item.src" alt="swiper-image">
          </swiper-slide>
        </swiper>
      </b-tab>
      <b-tab title="特色商品" :title-link-class="linkClass(2)" :title-item-class="itemClass()">
        <!--<swiper :options="swiperOption" ref="mySwiper">
          &lt;!&ndash; 这部分放你要渲染的那些内容 &ndash;&gt;
          <swiper-slide v-for="item in fetureItems">
            <img class="swiper-image" src="item.src" alt="swiper-image">
          </swiper-slide>
        </swiper>-->
      </b-tab>
    </b-tabs>
  </b-card>
</template>

<script>
  import Vue from 'vue'
  import BootstrapVue from 'bootstrap-vue'
  import 'bootstrap/dist/css/bootstrap.css'
  import 'bootstrap-vue/dist/bootstrap-vue.css'
  import 'swiper/dist/css/swiper.css'
  import VueAwesomeSwiper from 'vue-awesome-swiper'
  Vue.use(VueAwesomeSwiper);
  export default {
    name: 'tabs',
    component: 'tabs',
    data() {
      return {
        tabIndex: 0,
        swiperOption: {
          notNextTick: true,
//          pagination: '.swiper-pagination',
          slidesPerView: 'auto',
          centeredSlides: true,
          paginationClickable: true,
          spaceBetween: 30,
          onSlideChangeEnd: swiper => {
            //这个位置放swiper的回调方法
            this.page = swiper.realIndex + 1;
            this.index = swiper.realIndex;
          }
        },
        discountItems: [
          {"src":'../../assets/c1.jpg'},
          {"src":'../../assets/c2.jpg'},
          {"src":'../../assets/c3.jpg'}
        ],
        newItems: [
          {"src":'../../assets/c4.jpg'},
          {"src":'../../assets/c5.jpg'},
          {"src":'../../assets/c6.jpg'}
        ],
        fetureItems: [
          {"src":'../../assets/c7.jpg'},
          {"src":'../../assets/c8.jpg'},
          {"src":'../../assets/c9.jpg'}
        ]
      }
    },
    methods: {
      linkClass(idx) {
        if (this.tabIndex === idx) {
          return ['bg-success', 'text-light']
        } else {
          return ['bg-info', 'text-light']
        }
      },
      itemClass() {
        return ['col-4', 'text-center']
      }
    },
    computed: {
      swiper() {
        return this.$refs.mySwiper.swiper;
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  .card-header-tabs {
    margin: 0;
  }
</style>
