<template>
    <table class="books">
        <tr>
          <th>图书ID</th>
          <th>书名</th>
          <th>作者</th>
          <th>出版</th>
          <th>出版社</th>
          <th>页数</th>
        </tr>
        <tr v-for="item in booksList " :key="item.id" id="mainConnent">
            <th>{{ item.id }}</th>
            <th>{{ item.title }}</th>
            <th> {{ item.author }}</th>
            <th>{{ item.publish }}</th>
            <th>{{ item.publisher }}</th>
            <th>{{ item.theNumberOfPage }}</th>
        </tr>
    </table>
    
</template>

<script>

import axios from 'axios'
export default {
    name: "BookTable",
    data(){
         return {
            booksList:[]
         }
    },
    mounted(){
        axios({
            url:"http://localhost:8443/library",
            params:{
                "getAll": "yes"
            }
        }).then(res=>{
            console.log(res);
            this.booksList = res.data

            
        }).catch(err=>{
            console.log(err);

            
        })


    },
    method:{
        
    }
}
</script>

<style scoped>
#mainConnent th{
    border: 1px solid black;

}
</style>