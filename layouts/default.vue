<template>
  <div>
    <div :class="['leftMenu', showExPand? 'after_leftMenu' : '']">
      <div :class="['expand', showExPand? 'showExPand' : '']" ref="expand">
        <div :class="['expandTxt',showExPand? 'after_expandTxt' : '' ]">
          <left-menu :visible="showExPand"></left-menu>
        </div>
      </div>
      <div :class="['leftFixedMenu', showExPand? 'after_lfm' : '']" @click="clickleftFixedMenu" ref="leftFixedMenu">
        <div :class="['leftMenuTxt', showExPand? 'after_lmt' : '']">
          <!--left固定-->
          <!--<img :src="point" alt="" :class="animate? 'img_point' : ''" @mouseover="mouseOver" @mouseout="mouseOut">-->
          <img :src="point" alt="" class="img_point" @mouseover="mouseOver" @mouseout="mouseOut">
        </div>
      </div>
      <div style="clear: both"></div>
    </div>
    <div :class="['rightMenu', showExPand? 'after_rightmenu' : '']">
      <div class="banner">
        <banner :imgs="imgs"></banner>
      </div>
      <div class="menus">
        <menus></menus>
      </div>
      <div class="nuxt">
        <nuxt/>
      </div>
    </div>
  </div>
</template>

<script>
import leftMenu from '~/components/portal/menu/leftMenu'
import menus from '~/components/portal/menu/menu.vue';
import banner from '~/components/banner';
import lun1 from '~/assets/b1.jpg'; //看文档静态文件可直接引图片路径
import lun2 from '~/assets/b2.jpg';
import point from '~/assets/hand_point.png';
export default {
  components: {
    banner,
    menus,
    leftMenu
  },
  data() {
    return {
      imgs: [lun1, lun2],
      showExPand: false,
      point: point,
      animate: true, // point 动画是否起作用
    }
  },
  created() {
  },
  mounted: function() {
    this.$nextTick(() => {
      this.$refs.leftFixedMenu.style.height = window.screen.availHeight + 'px';
    })
  },
  methods: {
    clickleftFixedMenu() {
      if (this.showExPand) this.showExPand = false
      else {
        this.showExPand = true;
        this.$nextTick(() => {
          this.$refs.expand.style.height = window.screen.availHeight + 'px';
        })
      }
    },
    mouseOver() {
      this.animate = false;
    },
    mouseOut() {
      this.animate = true;
    }
  }
}
</script>

<style>
.banner {
  max-width: 1920px;
  margin: 0 auto
}

html {
  font-family: "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}


* {
  margin: 0;
  padding: 0;
}

a {
  color: inherit;
  text-decoration: none
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

.menus {
  width: 1500px;
  margin: 0 auto;
  height: 70px;
}

.nuxt {
  border-radius: 10px;
  width: 1280px;
  margin: 0 auto;
  border: 1px solid #ddd;
  box-shadow: 1px 1px 2px 2px#a3a3a3;
  min-height: 500px;
}

.leftMenu {
  width: 100px;
  float: left;
}

.after_leftMenu {
  width: 300px;
}

.rightMenu {
  float: right;
  width: calc(100% - 100px);
  transition: all 0.5s;
}

.after_rightmenu {
  width: calc(100% - 300px)
}

.expand {
  position: fixed;
  top: 0px;
  width: 0px;
  transition: all 0.5s;
  -moz-transition: all 0.5s;
  /* Firefox 4 */
  -webkit-transition: all 0.5s;
  /* Safari and Chrome */
  -o-transition: all 0.5s;
  /* Opera */
  background-color: #060606;
}

.showExPand {
  color: #fff;
  width: 200px;
}

.expandTxt {
  color: #000;
  /*font-size: 18px;*/
  transition: all 2s;
  -moz-transition: all 2s;
  -webkit-transition: all 2s;
  -o-transition: all 2s;
}

.after_expandTxt {
  color: #fff;
}

.leftFixedMenu {
  text-align: center;
  position: fixed;
  top: 0px;
  left: 0px;
  background-color: #212121;
  color: white;
  width: 100px;
  transition: all 0.5s;
  -webkit-transition: all 0.5s;
  -moz-transition: all 0.5s;
  -o-transition: all 0.5s;
  cursor: pointer;
}

.after_lfm {
  left: 200px;
}

.leftMenuTxt {
  position: fixed;
  top: 50%;
  left: 15px;
  transition: all 0.5s;
  -webkit-transition: all 0.5s;
  -moz-transition: all 0.5s;
  -o-transition: all 0.5s;
}

.after_lmt {
  transform: rotateY(360deg);
  left: 215px;
}

.img_point {
  animation: pointAnimate 4s infinite;
  -webkit-animation: pointAnimate 4s infinite;
  -o-animation: pointAnimate 4s infinite;
  -moz-animation: pointAnimate 4s infinite;
  ;
}

@keyframes pointAnimate {
  0% {
    width: 70px
  }
  50% {
    width: 80px
  }
  100% {
    width: 70px
  }
}

@-moz-keyframes pointAnimate {
  0% {
    width: 70px
  }
  50% {
    width: 80px
  }
  100% {
    width: 70px
  }
}

@-webkit-keyframes pointAnimate {
  0% {
    width: 70px
  }
  50% {
    width: 80px
  }
  100% {
    width: 70px
  }
}

@-o-keyframes pointAnimate {
  0% {
    width: 70px
  }
  50% {
    width: 80px
  }
  100% {
    width: 70px
  }
}
</style>
