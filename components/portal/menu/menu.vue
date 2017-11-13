<template>
    <div>
        <span v-for="(one, index) in menuConfig" :key="index">
            <router-link :to="one.path">{{one.name}}</router-link>
        </span>
    </div>
</template>

<script>
import con from './menu.js'
export default {
    fetch() {

    },
    head() {
        return {

        }
    },
    data() {
        return {
            menuConfig: con
        }
    },
    methods: {

    },
    components: {

    }
}
</script>

<style>

</style>
