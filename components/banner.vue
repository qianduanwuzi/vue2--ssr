<!-- The ref attr used to find the swiper instance -->
<template>
  <swiper :options="swiperOption" :not-next-tick="notNextTick" ref="mySwiper">
      <!--<span v-for="(one, index) in imgs" :key="index">
            <swiper-slide>
                <img :src="one" alt="">
            </swiper-slide>
      </span>-->
    <swiper-slide v-for="(one, index) in imgs" :key="index">
        <img :src="one" alt="" >
    </swiper-slide>
    <!--<div class="swiper-pagination"  slot="pagination"></div>
    <div class="swiper-button-prev" slot="button-prev"></div>
    <div class="swiper-button-next" slot="button-next"></div>
    <div class="swiper-scrollbar"   slot="scrollbar"></div>-->
  </swiper>
</template>

<script>
  // swiper options example:
  export default {
    name: 'carrousel',
    props: {
        imgs: {
            default:function() {
                return []
            },
            type: Array
        }
    },
    data() {
      return {
        // notNextTick是一个组件自有属性，如果notNextTick设置为true，组件则不会通过NextTick来实例化swiper，也就意味着你可以在第一时间获取到swiper对象，假如你需要刚加载遍使用获取swiper对象来做什么事，那么这个属性一定要是true
        notNextTick: true,
        swiperOption: {
          // swiper options 所有的配置同swiper官方api配置
          autoplay: 3000,
          direction: 'horizontal',
          grabCursor: true, // 手指形状
        //   height: 500,
        //   setWrapperSize: true, 
        //   autoHeight: true,
        //   pagination: '.swiper-pagination',
        // //   paginationClickable: true,
        //   prevButton: '.swiper-button-prev',
        //   nextButton: '.swiper-button-next',
        //   scrollbar: '.swiper-scrollbar',
        //   mousewheelControl: true,
        //   observeParents: true,
          // if you need use plugins in the swiper, you can config in here like this
          // 如果自行设计了插件，那么插件的一些配置相关参数，也应该出现在这个对象中，如下debugger
        //   debugger: true,
          // swiper callbacks
          // swiper的各种回调函数也可以出现在这个对象中，和swiper官方一样
        //   onTransitionStart (swiper) {
        //     console.log(swiper)
        //   }
          // more Swiper configs and callbacks...
          // ...
        }
      }
    },
    // you can find current swiper instance object like this, while the notNextTick property value must be true
    // 如果你需要得到当前的swiper对象来做一些事情，你可以像下面这样定义一个方法属性来获取当前的swiper对象，同时notNextTick必须为true
    computed: {
      swiper() {
        return this.$refs.mySwiper.swiper
      }
    },
    mounted() {
      // you can use current swiper instance object to do something(swiper methods)
      // 然后你就可以使用当前上下文内的swiper对象去做你想做的事了
    //   console.log('this is current swiper instance object', this.swiper)
    //   this.swiper.slideTo(1, 1000, false)
    }
  }
</script>