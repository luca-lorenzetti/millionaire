<template>
  <div class="question">
   <p class="text">{{ask}}</p> 

  </div>
</template>

<script>

export default {
  created () {
  },
  name: "Question",
  props: {
    ask: String,
  },

};
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->

<style scoped lang="scss">
 
  .question{
    max-height: 100px;
    padding: 20px;
    height: auto;
    width: 700px;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 40px;
    border: 1px solid #fff;
  }


</style>
