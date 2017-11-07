<template>
    <div>
        {{msg}}
    </div>
</template>

<script>
// import Vue from 'vue'

export default {
    name: 'test-one',
    transition: 'test',
//   beforeCreate () {
//     Vue.util.defineReactive(this, 'nuxt', this.$root.$options._nuxt)
//   },
    data() {
        return {
            msg: 'this is child1'
        }
    },
    computed: {
 
    },
    components: {
    }
}
</script>
