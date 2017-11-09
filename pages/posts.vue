<template>
    <div>
        <div>this is post</div>
        <h1 class="red">Hello!{{name}}</h1>
    </div>
</template>
<script>
import axios from 'axios'
export default {
    // layout: 'blog',
    // 方法会在组件（限于页面组件）每次加载之前被调用。它可以在服务端或路由更新之前被调用, 拿不到this
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
    data() {
        return {
            msg: 'this is child1',
            title: 'this is posts',
            name: 'this is posts'
        }
    },
    mounted: function() {
    },
    created: function() {
    },
}
</script>

<style scoped>
.red {
    color: red;
}
</style>
