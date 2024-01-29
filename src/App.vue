<script >
import Block from './components/Block.vue'
import Result from './components/Result.vue'

export default{
  data(){
    return{
      title:'Reaction Timer',
      isPlaying:false,
      delay:null,
      score:0,
      showResults:false

    }
  },
  methods:{
    start(){
      this.isPlaying=true,
      this.showResults=false,
      this.delay= 2000 + Math.random() * 5000

    },
    endFunc(reactionTime){
      this.isPlaying=false
      this.showResults=true
      this.score=reactionTime

    }
  },
components:{Block,Result}
}



</script>

<template>
  <div>
  <h1>{{title}}</h1>
  <button type="button" @click="start" :disabled="isPlaying" >Play</button>
  <Block v-if="isPlaying"  :delay="delay"   @end="endFunc" />
 
  <Result v-if="showResults" :score="score" />
  </div>
</template>

<style scoped>

</style>
