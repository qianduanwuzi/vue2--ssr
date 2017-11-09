<template>
    <div>
        <div>this is nodes</div>
    </div>
</template>
<script>
import axios from 'axios'
export default {
    // layout: 'blog',
    // 方法会在组件（限于页面组件）每次加载之前被调用。它可以在服务端或路由更新之前被调用, 拿不到this
    asyncData(context) {
        return { name: 'posts', title: '123' }
    },
    fetch() {

    },
    // head() {
    //     return {
    //         title: this.title,
    //         meta: [
    //             { hid: 'description', name: 'description', content: 'this is posts' }
    //         ]
    //     }
    // },
    data() {
        return {
          
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
