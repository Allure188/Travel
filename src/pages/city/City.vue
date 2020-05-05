<template>
    <div>
        <city-header></city-header>
        <city-search :cities="cities"></city-search>
        <city-list :city="city" :hotCities="hotCities" :cities="cities" :wordmsg="wordmsg"></city-list>
        <city-words :cities="cities" @chuan="word"></city-words>
    </div>
</template>

<script>
    import CityHeader from './components/header'
    import CitySearch from './components/search'
    import CityList from './components/list'
    import CityWords from './components/words'
    import axios from 'axios'
    export default {
        name: "City",
        data(){
            return{
                city:"",
                hotCities:[],
                cities:{},
                wordmsg:""
            }
        },
        components:{
           CityHeader, 
           CitySearch,
           CityList,
           CityWords
        },
        methods:{
            getInfo(){
                axios.get('/static/moni/city.json').then((res)=>{
                    this.city=res.data.data.city;
                    this.hotCities=res.data.data.hotCities;
                    this.cities=res.data.data.cities;
                })
            },
            word(res){
                this.wordmsg=res
            }
        },
        mounted:function(){
            this.getInfo();
        }
    }
</script>