<template>
  <b-card no-body class="container">
    <b-tabs card v-model="tabIndex">
      <b-tab title="促销商品" :title-link-class="linkClass(0)" :title-item-class="itemClass()">
        <p class="tab-title"></p>
        <swiper :options="swiperOption" ref="mySwiper">
          <!-- 这部分放你要渲染的那些内容 -->
          <swiper-slide v-for="item in discountItems" :key="item.id">
            <img class="swiper-image" :src="item.src" alt="swiper-image"/>
            <h4 >discountItems name</h4>
            <p >59% Cotton Lorem Ipsum Dolor Sit Amet esed ultrices sapien nunc nam frignila</p>
          </swiper-slide>
          <div class="swiper-button-prev" slot="button-prev"></div>
          <div class="swiper-button-next" slot="button-next"></div>
        </swiper>
      </b-tab>
      <b-tab title="新品尝鲜" :title-link-class="linkClass(1)" :title-item-class="itemClass()">
        <swiper :options="swiperOption" ref="mySwiper">
          <!-- 这部分放你要渲染的那些内容 -->
          <swiper-slide v-for="item in newItems" :key="item.id">
            <img class="swiper-image" :src="item.src" alt="swiper-image">
            <h4 >newItems name</h4>
            <p >59% Cotton Lorem Ipsum Dolor Sit Amet esed ultrices sapien nunc nam frignila</p>
          </swiper-slide>
          <div class="swiper-button-prev" slot="button-prev"></div>
          <div class="swiper-button-next" slot="button-next"></div>
        </swiper>
      </b-tab>
      <b-tab title="特色商品" :title-link-class="linkClass(2)" :title-item-class="itemClass()">
        <swiper :options="swiperOption" ref="mySwiper">
          <!-- 这部分放你要渲染的那些内容 -->
          <swiper-slide v-for="item in fetureItems" :key="item.id">
            <img class="swiper-image" :src="item.src" alt="swiper-image">
            <h4 >fetureItems name</h4>
            <p >59% Cotton Lorem Ipsum Dolor Sit Amet esed ultrices sapien nunc nam frignila</p>
          </swiper-slide>
          <div class="swiper-button-prev" slot="button-prev"></div>
          <div class="swiper-button-next" slot="button-next"></div>
        </swiper>
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
          grabCursor: true,
          setWrapperSize: true,
          autoHeight: false,
          observeParents: true,
          loop:true,
          cssWidthAndHeight : {width:"100%",height:'300px'},
          updateOnImagesReady : true,
          slidesPerView: 3,
          slidesPerGroup:3,
          spaceBetween: 30,
          prevButton:'.swiper-button-prev',//上一张
          nextButton:'.swiper-button-next',//下一张
          preventClicks : false,//默认true
          onTransitionStart(swiper){
            console.log(swiper)
          },
          onSlideChangeEnd: swiper => {
            //这个位置放swiper的回调方法
            this.page = swiper.realIndex + 1;
            this.index = swiper.realIndex;
          }
        },
        discountItems: [
          {"src":'/static/c1.jpg'},
          {"src":'/static/c2.jpg'},
          {"src":'/static/c3.jpg'},
          {"src":'/static/c4.jpg'},
          {"src":'/static/c5.jpg'},
          {"src":'/static/c6.jpg'},
          {"src":'/static/c7.jpg'},
          {"src":'/static/c8.jpg'},
          {"src":'/static/c9.jpg'}
        ],
        newItems: [
          {"src":'/static/c4.jpg'},
          {"src":'/static/c5.jpg'},
          {"src":'/static/c6.jpg'}
        ],
        fetureItems: [
          {"src":'/static/c7.jpg'},
          {"src":'/static/c8.jpg'},
          {"src":'/static/c9.jpg'}
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
    padding: 5px;
  }
  .swiper-container{
    height: 400px;
  }
  img.swiper-image {
    width: 100%;
    height: 75%;
  }
</style>
