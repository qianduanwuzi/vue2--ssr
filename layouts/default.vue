<template>
  <div>
    <!--<div class="">
        <menus></menus>
    </div>-->
    <div class="banner">
        <banner :imgs="imgs"></banner>
    </div>
    <div class="">
        <menus></menus>
    </div>
    <nuxt/>
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
      imgs: [lun1, lun2]
    }
  }
}
</script>

<style>
.banner{
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

*, *:before, *:after {
  box-sizing: border-box;
  margin: 0;
}

.button--green {
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
}
</style>
