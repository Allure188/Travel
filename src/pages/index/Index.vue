<template>
    <div>
        <home-header :city="city"></home-header>
        <home-swiper :swiperList="swiperList"></home-swiper>
        <home-icons :iconList="iconList"></home-icons>
        <home-recommend :recommendList="recommendList"></home-recommend>
    </div>
</template>

<script>
    import HomeHeader from './components/Header'
    import HomeSwiper from './components/Swiper'
    import HomeIcons from './components/Icons'
    import HomeRecommend from './components/Recommend'
    import axios from 'axios'
    export default {
        name: "Home",
        data(){
            return{
                city:'',
                swiperList:[],
                iconList:[],
                recommendList:[]
            }
        },
        components:{
            HomeHeader,
            HomeSwiper,
            HomeIcons,
            HomeRecommend
        },
        methods:{
            getInfo(){
                axios.get('/static/moni/index.json').then((res)=>{
                    this.city=res.data.city;
                    this.swiperList=res.data.data.swiperList;
                    this.iconList=res.data.data.iconList;
                    this.recommendList=res.data.data.recommendList;
                })
            }
        },
        mounted:function(){
            this.getInfo();
        }
    }
</script>