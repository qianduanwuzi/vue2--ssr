<template>
  <div>
    <div :class="['leftMenu', showExPand? 'after_leftMenu' : '']">
      <div :class="['expand', showExPand? 'showExPand' : '']" v-if="showExPand">
          this is expand
      </div>
      <div class="leftFixedMenu" @click="clickleftFixedMenu">
          left固定
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
import menus from '~/components/portal/menu/menu.vue';
import banner from '~/components/banner';
import lun1 from '~/assets/b1.jpg';
import lun2 from '~/assets/b2.jpg';
// import lun3 from '~/assets/lun3.jpg';
// import lun4 from '~/assets/lun4.jpg';
// import lun5 from '~/assets/lun5.jpg';
// import lun6 from '~/assets/lun6.jpg';
export default {
  components: {
    banner,
    menus
  },
  data() {
    return {
      imgs: [lun1, lun2],
      showExPand: false
    }
  },
  methods:{
    clickleftFixedMenu() {
      this.showExPand = true;
    }
  }
}
</script>

<style>
.banner {
  /*background: url('~assets/banner.png') no-repeat center 100%*/
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

*{
  margin: 0;
  padding: 0;
}

a{
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

.leftMenu{
  width: 100px;
  float: left;
  
}

.after_leftMenu{
  width: 300px;
}

.rightMenu{
  float: right;
  width: calc(100% - 100px)
}

.after_rightmenu{
  width: calc(100% - 300px)
}

.expand{
  /*display: none;*/
  float: left;
  width: 0px;
  transition: all 2s ;
  -moz-transition:all 2s; /* Firefox 4 */
  -webkit-transition:all 2s; /* Safari and Chrome */
  -o-transition:all 2s; /* Opera */
  background-color: #060606;
  color: white;
  height: calc(100% -0px);
}

.showExPand{
  /*display: block;*/
  width: 200px;
}

.leftFixedMenu{
  float: right;
  background-color: #212121;
  color: white;
  width: 100px;
  height: calc(100% -0px);
}


/*.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}*/
</style>
