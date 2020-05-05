<template>
    <div class="project">
        <div class="box" v-for="(item) in categoryList" :key="item.id">
            <div class="left">
                <div class="title">{{item.title}}</div>
            </div>
            <div class="price">￥{{item.price}}</div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Header",
        data(){
            return{}
        },
        props:{
            categoryList:Array
        }
    }
</script>

<style lang="stylus" scoped>
    .project
        width :100%
        height 6.25rem
        .box
            width :100%
            height :3.125rem
            background-color :blue
            display :flex
            justify-content :space-between
            align-items :center  
</style>