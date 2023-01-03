<style>

</style>
<template>
<h1>Product Page </h1>
<img :src=this.prodDetails.image />
<h2>{{ this.prodDetails.title }}</h2>
<p>${{ this.prodDetails.price }}</p>
<p>{{ this.prodDetails.description }}</p>
</template>
<script > 
    import {useRoute} from "vue-router";
    import axios from "axios"
    
    export  default {
       data (){
        return {
            prodDetails:[]
        }
        
       },
        mounted(){
            const route = useRoute();
             console.log("Route:" ,route.params.id)  

             axios(`https://fakestoreapi.com/products/${route.params.id}`)
        .then((res)=>{
            this.prodDetails= res.data
           console.log(this.prodDetails)
        })



        },

        setup(){

        }

      
    }
    

</script>
