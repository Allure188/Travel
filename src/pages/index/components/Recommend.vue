<template>
    <div class="recommend">
        <div class="item"  v-for="(item) in recommendList" :key="item.id">
            <img class="pic" :src="item.imgUrl">
            <div class="info">
                <h3 class="title">{{item.title}}</h3>
                <p class="content">{{item.content}}</p>
                <router-link :to="'/detail/'+item.id">
                    <button class="btn">查看详情</button>
                </router-link>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Recommend",
        data(){
            return{}
        },
        props:{
            recommendList:{
                type:Array
            }
        }
    }
</script>

<style lang="stylus" scoped>
    .item
        width :100%
        height :9.375rem
        margin-bottom 0.625rem
        display :flex
        .pic 
            width :9.375rem
            height :9.375rem
        .info
            flex :1
            margin-left :0.9375rem
            display :flex
            flex-direction :column
            justify-content :space-around
            .btn
                width 6.25rem
                height :1.5rem
                border-radius :0.3125rem
                border:0
</style>