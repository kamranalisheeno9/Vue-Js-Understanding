    <script>
    export default {
        data(){
            return{

                title:'Result',
                rank:null,
            }
        },
        methods:{
          
        },
        mounted(){
                console.log(this.score)
               if(this.score < 250){
                this.rank='You are faster...'
               }else if(this.score > 250 && this.score < 650){
                this.rank='You are slow...'

               }else{
                this.rank='You are slower...'

               }
        },
        props:['score']
    }
    </script>
<template>
    <h3>React Time is : {{ score }} ms</h3>
    <h4>{{ rank }}</h4>
    </template>
    <style>
    </style>