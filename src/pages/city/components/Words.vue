<template>
    <ul class="words">
        <li v-for="(item,index) in cities" :key="item.id" @click="click">{{index}}</li>
    </ul>
</template>

<script>
    export default {
        name: "Words",
        data(){
            return{}
        },
        props:{
            cities:Object
        },
        methods:{
            click(event){
                var res=event.target.innerText;
                this.$emit('chuan',res);
            }
        }
    }
</script>

<style lang="stylus" scoped>
    .words
        width :1.25rem
        position :absolute
        top :200px
        right :0
        bottom :0
        z-index :999
        display :flex
        flex-direction :column
        align-items :center
        justify-content :center
</style>
