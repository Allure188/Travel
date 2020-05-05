<template>
    <div class="icons">
        <div class="icon" v-for="(item) in iconList" :key="item.id">
            <img class="icon-pic" :src="item.imgUrl">
            <p>{{item.content}}</p>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Icons",
        data(){
            return{}       
        },
        props:{
            iconList:{
                type:Array
            }
        }
    }
</script>

<style lang="stylus" scoped>
	.icons
		width:100%
		height:4.933333rem
		display:flex
		flex-wrap:wrap
		font-size:0.373333rem
		.icon	
			width:25%
			height:4.0rem
			display:flex
			flex-direction:column
			justify-content:space-around
			align-items:center
			.icon-pic
				width:2.0rem
				height:2.0rem
</style>
