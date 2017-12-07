<template>
    <div class="leftMenuBox" v-if="visible">
        <span v-for="(one, index) in menuConfig" :key="index" class="eachLMenuBox" @mouseover="curIndex = index">
            <router-link :to="one.path" :class="['eachlMenu', curIndex == index? 'curLHover' : '']">{{one.name}}</router-link>
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
    props:{
        visible: {
            default: false,
            type: Boolean
        }
    },
    data() {
        return {
            menuConfig: con,
            curIndex: 0
        }
    },
    methods: {

    },
    components: {

    }
}
</script>

<style scoped>
    .leftMenuBox{
        position: fixed;
        top: 45%;
        left: 3%;
        
    }
    .eachLMenuBox{
        display: block;
    }
    .eachlMenu{
        font-size: 18px;
        line-height: 50px;
        text-align: center;
        cursor: pointer;
        /*transition: all 1s;*/
    }
    .curLHover{
        /*font-size: 20px;*/
    }




</style>
