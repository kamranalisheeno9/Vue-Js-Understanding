<script>
export default {
  data() {
    return {
      title: "Click Me To Play",
      showBlock: false,
      timer:null,
      reactionTime:0,
    };
  },
  props: ["delay"],
  methods: {
   
    startTimer(){
        this.timer = setInterval(() => {
            this.reactionTime += 10
        }, 10);
    },
    stopTimer(){
       clearInterval( this.timer)
        this.showBlock= false,
        this.$emit('end',this.reactionTime)

    }
  },
  mounted() {
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer()
    }, this.delay);
  },
};
</script>
<template>
  <div v-if="showBlock" @click="stopTimer" class="block">{{ title }}</div>
</template>
<style>
.block {
  width: 400px;
  height: 400px;
  background-color: cadetblue;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 10px;
  border-radius: 10px;
  font-size: 24px;
  font-weight: 700;
  cursor: pointer;
}
</style>
