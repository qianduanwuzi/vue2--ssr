<template>
    <div>
        111
        {{msg}}
    </div>
</template>

<script>
// import Vue from 'vue'

export default {
    name: 'test-second',
    transition: 'test',
//   beforeCreate () {
//     Vue.util.defineReactive(this, 'nuxt', this.$root.$options._nuxt)
//   },
    data() {
        return {
            msg: 'this is child2'
        }
    },
    computed: {
 
    },
    components: {
    }
}
</script>
