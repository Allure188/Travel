<template>
	<div class="wrapper">
		<swiper :options="swiperOption">
			<!-- slides -->
      <!-- 和微信小程序一样需要绑定key -->
			<swiper-slide v-for="(item) in swiperList" :key="item.id">
				<img :src="item.imgUrl">
			</swiper-slide>
			<!-- Optional controls -->
			<div class="swiper-pagination" slot="pagination"></div>
		</swiper>
	</div>
</template>
<script>
	export default{
		data() {
			return {
				//定义轮播图属性
				swiperOption:{
					loop:true
				}
			}
		},
		props:{
			swiperList:{
				type:Array
			}
		}
	}
</script>
<!-- 约定俗成的内容 -->
<style lang="stylus" scoped>
	.wrapper
		width:100%
    height :0
		overflow:hidden
		padding-bottom:62%
</style>