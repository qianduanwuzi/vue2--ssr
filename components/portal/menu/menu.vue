<template>
    <div>
        <span v-for="(one, index) in menuConfig" :key="index" class="eachMenuBox" @mouseover="curIndex = index">
            <router-link :to="one.path" :class="['eachMenu', curIndex == index? 'curHover' : '']">{{one.name}}</router-link>
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
    .eachMenuBox{
        width: 25%;
        display: inline-block;
    }
    .eachMenu{
        border-radius: 5px;
        font-size: 18px;
        display: block;
        width: 100%;
        line-height: 50px;
        border: 1px solid #ddd;
        text-align: center;
        cursor: pointer;
        transition: all 1s;
        color: #a3a3a3;
        /*box-shadow: 2px 2px 1px #a3a3a3 ;*/
    }

    .curHover{
        box-shadow: 6px 6px 3px #a3a3a3 ;
        color: #2f2f2f;
        font-size: 20px;
    }




</style>
