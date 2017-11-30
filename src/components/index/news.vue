<template>
  <b-card no-body class="container">
    <swiper :options="swiperOption" ref="mySwiper">
      <swiper-slide v-for="item in newsItems" :key="item.id">
        <h6>{{item.title}}</h6>
        <p>{{item.content}}</p>
      </swiper-slide>
      <div class="swiper-button-prev" slot="button-prev"></div>
      <div class="swiper-button-next" slot="button-next"></div>
    </swiper>
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
    name: 'news',
    component: 'news',
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
          slidesPerView: 2,
          slidesPerGroup:2,
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
        newsItems: [
          {"title":'Title of the Latest News1',"content":"There's a voice that keeps on calling me. Down the road, that's where I'll al ways be. Every stop I make, I make a new friend. Lorem sown the road, that's where I'll always be. Every stop I make, I make a new friend."},
          {"title":'Title of the Latest News2',"content":"There's a voice that keeps on calling me. Down the road, that's where I'll al ways be. Every stop I make, I make a new friend. Lorem sown the road, that's where I'll always be. Every stop I make, I make a new friend."},
          {"title":'Title of the Latest News3',"content":"There's a voice that keeps on calling me. Down the road, that's where I'll al ways be. Every stop I make, I make a new friend. Lorem sown the road, that's where I'll always be. Every stop I make, I make a new friend."},
          {"title":'Title of the Latest News4',"content":"There's a voice that keeps on calling me. Down the road, that's where I'll al ways be. Every stop I make, I make a new friend. Lorem sown the road, that's where I'll always be. Every stop I make, I make a new friend."},
          {"title":'Title of the Latest News5',"content":"There's a voice that keeps on calling me. Down the road, that's where I'll al ways be. Every stop I make, I make a new friend. Lorem sown the road, that's where I'll always be. Every stop I make, I make a new friend."},
          {"title":'Title of the Latest News6',"content":"There's a voice that keeps on calling me. Down the road, that's where I'll al ways be. Every stop I make, I make a new friend. Lorem sown the road, that's where I'll always be. Every stop I make, I make a new friend."}
        ]
      }
    },
    methods: {


    },
    computed: {
      swiper() {
        return this.$refs.mySwiper.swiper;
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .swiper-container{
    height: 200px;
  }

</style>
