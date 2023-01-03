<style>
#container{
    display: grid;
    grid-template-columns: repeat(3, 400px);
    gap: 30px;
}
.card{
    border: 1px solid rgb(196, 186, 186);
    padding: 30px;
}
 img{
    height: 300px;
    width: 300px;
 }
</style>
<template>
    <h1>Home</h1>
    <div  id="container" >
        <div  @click="handleClick(prod.id)" class="card"  v-for="prod in ProdList"  >
       <!-- <router-link :to="'/product/' + prod.id"> -->
            <img :src="prod.image" />
        <h2>{{ prod.title }}</h2>
        <p>${{ prod.price }}</p><p>Category: {{ prod.category }}</p>
        <p> {{ prod.description }}</p>

       <!-- </router-link> -->
        
    </div>
    </div>
    
</template>

<script  >

import axios from 'axios'

 export default  {
    data(){
        return {
           ProdList :[]
         }
    },
    mounted(){
    axios("https://fakestoreapi.com/products")
        .then((res)=>{
            this.ProdList= res.data
           console.log(this.ProdList)
        })
    },
   methods:{
      handleClick (a) {
          this.$router.push({
            name : 'product',
            params :  {
              id  : a
            }
      })
   }
 }
}
</script>
