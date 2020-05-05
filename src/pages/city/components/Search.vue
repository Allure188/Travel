<template>
    <div class="search">
        <input type="text" class="demo" v-model="key">
        <div class="content" v-for="(item) in content" :key="item.id">
            {{item.name}}
        </div>   
    </div>
</template>

<script>
    export default {
        name: "Search",
        data(){
            return{
                //获取用户输入内容
                key:"",
                content:[]
            }
        },
        //获取父元素的cities
        props:{
            cities:Object
        },
        //对用户输入内容进行监听
        watch:{
            key(){
                //存储存在的信息
                const res=[];
                //循环遍历cities
                for(let i in this.cities){
                    this.cities[i].forEach((value) => {
                        //判断用户输入的内容是否存在
                        if(value.name.indexOf(this.key)>-1){
                            //放到res中
                            res.push(value);
                        }
                    });
                }
                this.content=res;
                console.log(res);
            }
        }
    }
</script>

<style lang="stylus" scoped>
    .search
        width :100%
        height :3rem
        background-color :blue
        text-align:center
        vertical-align:middle
        .demo
            width :80%
            height :1.25rem
            outline:none
        .content
            width :100%
            position :absolute
            top :6rem
            left :0
            right :0
            bottom 0
            background-color :red
            z-index :1000
</style>