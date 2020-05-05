<template>
    <div class="header">
        <div class="header-left">搜索</div>
        <div class="header-center">222</div>
        <router-link to="/city">
            <div class="header-right">{{city}}</div>
        </router-link>
    </div>
</template>

<script>
    export default {
        name: "Header",
        data(){
            return{}
        },
        props:{
            city:{
                type:String
            }
        }
    }
</script>

<style lang="stylus" scoped>
    .header
        width :100%;
        height :3.125rem;
        background-color :red;
        display :flex;
        align-items :center;
        .header-left
            width :2.3125rem;
            height :3.125rem;
            text-align :center;
            line-height :3.125rem;
        .header-right
            width :2.3125rem;
            height :3.125rem;
            text-align :center;
            line-height :3.125rem;
        .header-center
            flex :1;  
            background-color :white;
            border-radius :0.3125rem;
</style>