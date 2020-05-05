<template>
    <div>
        <detail-header :header="header"></detail-header>
        <detail-info :fen="fen" :pinglun="pinglun"></detail-info>
        <detail-project :categoryList="categoryList"></detail-project>
    </div>
</template>

<script>
    import DetailHeader from './components/header'
    import DetailInfo from './components/info'
    import DetailProject from './components/project'
    import axios from 'axios'
    export default {
        name: "Detail",
        data(){
            return{
                header:"",
                fen:"",
                pinglun:"",
                categoryList:[]
            }
        },
        components:{
            DetailHeader,
            DetailInfo,
            DetailProject
        },
        methods:{
            getInfo(){
                //获取首页传来的ID
                var id=this.$route.params.id;
                axios.get('/static/moni/detail.json',{
                    params:{
                        id:id
                    }
                }).then((res)=>{
                    this.header=res.data.data.bannerImg
                    this.fen=res.data.data.fen
                    this.pinglun=res.data.data.pinglun
                    this.categoryList=res.data.data.categoryList
                    console.log(res.data.data.categoryList);
                })
            }
        },
         mounted:function(){
            this.getInfo();
        }
    }
</script>