<template>
    <div class="wrapper" ref="wrapper">
        <div>
            <!--当前城市-->
            <div class="list">
                <div class="title">当前城市</div>
                <div class="current-list">
                    <div class="current-one"> 
                        <div class="btn">{{city}}</div>
                    </div>
                </div>
            </div>
            <!--热门城市-->
            <div class="list">
                <div class="title">热门城市</div>
                <div class="city-list">
                    <div class="city-one" v-for="(item) in hotCities" :key="item.id"> 
                        <div class="btn">
                            {{item.name}}
                        </div>
                    </div>
                </div>
            </div>
            <!--区域-->
            <div class="list" v-for="(item,index) in cities" :key="item.id" :ref="index">
                <div class="title">{{index}}</div>
                <div class="item-list">
                    <div class="item" v-for="(value) in item" :key="value.id">
                        {{value.name}}
                    </div>
                </div>
            </div>    
        </div>    
    </div>
</template>

<script>
    import Bscroll from 'better-scroll'
    export default {
        name: "List",
        data(){
            return{}
        },
        props:{
            city:String,
            hotCities:Array,
            cities:Object,
            wordmsg:String
        },
        mounted:function(){
            //滑动菜单
            this.scroll = new Bscroll(this.$refs.wrapper) 
        },
        watch:{
            wordmsg(){
                //获取DOM元素
                var ok=this.$refs[this.wordmsg][0];
                //滚动到指定元素
                this.scroll.scrollToElement(ok);
            }
        }
    }
</script>

<style lang="stylus" scoped>
    .wrapper
        position: absolute
        top :6rem
        left: 0
        right :0
        bottom :0
        overflow: hidden
        .list
            .title
                width :100%
                height :1.875rem
                background-color :#ccc
                line-height :1.875rem
                padding-left :0.625rem
            .current-list
                .current-one
                    width :30%
                    height :1.875rem
                    background-color :red 
                    text-align :center
                    line-height :1.875rem
                    margin-top :0.625rem
                    margin-bottom :0.625rem
                    margin-left :0.625rem 
            .city-list
                width :100%
                display :flex   
                justify-content :space-around
                padding-bottom :0.625rem
                .city-one
                    width :30%
                    height :1.875rem
                    background-color :red
                    text-align :center
                    line-height :1.875rem
                    margin-top :0.625rem
            .item-list
                .item
                    width :100%
                    height :1.875rem
                    padding-top :0.3125rem              
</style>