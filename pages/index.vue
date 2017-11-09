<template>
  <section class="container">
    <div>
      <div @click="click(1)">click1</div>
      <div @click="click(2)">click2</div>
      <nuxt-child/>
    </div>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'
import axios from 'axios'
export default {
  asyncData(context) {
    // console.log('11', context)
    return { name: 'posts', title: '123' }
  },
  // asyncData ({ params }) {
  //     return axios.get(`https://my-api/posts/${params.id}`)
  //     .then((res) => {
  //     return { title: res.data.title }
  //     })
  // },
  // async asyncData ({ params }) {
  //     let { data } = await axios.get(`https://my-api/posts/${params.id}`)
  //     return { title: data.title }
  // },
  fetch() {

  },
  head() {
    return {
      title: this.title,
      meta: [
        { hid: 'description', name: 'description', content: 'this is posts' }
      ]
    }
  },
  methods: {
    click(t) {
      if (t == 1) this.$router.push('test')
      else this.$router.push('testSecond')
    }
  },
  components: {
    Logo
  }
}
</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  /* 1 */
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
