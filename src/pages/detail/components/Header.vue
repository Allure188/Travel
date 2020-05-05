<template>
    <div class="header">
        <div class="box">
            <img  class="pic" :src="header">
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
            header:String
        }
    }
</script>

<style lang="stylus" scoped>
    .box
        .pic
            width :100%;
            height :14.375rem
</style>