<template>
    <div></div>
</template>

<script>
    import axios from 'axios'
    export default {
        name: "Axios",
        data(){
            return{}
        },
        methods:{
            getInfo(){
                axios.get('/static/moni/index.json').then(function(res){
                    console.log(res);
                })
            }
        },
        mounted(){
            this.getInfo();
        }
    }
</script>