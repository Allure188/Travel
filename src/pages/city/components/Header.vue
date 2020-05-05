<template>
    <div class="header">
        <router-link to="/index">
                    <span class="return"> 《 </span>
        </router-link>
        <span class="xuan">城市选择</span>
    </div>
</template>

<script>
    export default {
        name: "Header",
        data(){
            return{}
        }
    }
</script>

<style lang="stylus" scoped>
    .header
        width :100%
        height :3rem
        background-color :blue
        color :white
        line-height :3rem
        text-align :center
</style>