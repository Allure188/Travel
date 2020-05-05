<template>
    <div class="info">
       <div class="boxes">
           <div class="box">
               <div>
                   <div class="fen">{{fen}}分</div>
                   <div>{{pinglun}}条评论</div>
               </div>
               <div class="btn"> > </div>
           </div>
           <div class="box">
               <div>
                   <div class="jianjie">景点简介</div>
                   <div>开放时间</div>
               </div>
               <div class="btn"> > </div>
           </div>
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
            fen:String,
            pinglun:String
        }
    }
</script>

<style lang="stylus" scoped>
    .boxes
        width :100%
        height :5rem
        display :flex
        justify-content :space-around
        .box
            width :47%
            height :5rem
            display :flex
            justify-content :space-between
            align-items :center
            .fen
                font-size :1.5rem
                margin-bottom :0.3125rem
                color :orange
            .jianjie
                font-size :1.5rem
                margin-bottom :0.3125rem
</style>