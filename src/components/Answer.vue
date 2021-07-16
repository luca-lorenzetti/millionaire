<template>
  <div class="answers">

    <p class="answer" v-for="(answer, index) in answers" :key="answer" ><span>{{letters[index]}}</span>{{answer}} </p>
  </div>
</template>

<script>

export default {

  created () {
  },
  name: "Answer",
 props: {
    answers: Array,
  },

  data(){
    return{
      correctAnswer: false,
      letters: ['A: ', 'B: ', 'C: ', 'D: ']
    }
  }


};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->


<style scoped lang="scss">
 
 .answers{
   position: relative;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    width: 100%;
    padding: 20px 0;

    .answer{
      max-height: 100px;
      position: relative;
      padding: 21px;
      height: auto;
      width: 40%;
      margin-top: 40px;
      border: 1px solid #fff;
      text-align: left;
      border-left: none;
      border-right: none;
      z-index: 10;
      background-color: #11093a;

      span{
        color: goldenrod;
      }


      &::before{
        position: absolute;
        z-index: -1;
        content: '';
        left: 0;
        max-height: 100px;
        height: 42px;
        width: 44px;
        transform: rotate(20deg);
        margin-top: 40px;
        border: 1px solid #fff;
        text-align: left;
        transform: translate(-50%, -123%) rotate(48deg);
        background-color: #11093a;
        border-right: none;
        border-top: none; 
      }

      &:hover{
        transition: background-color .5s;
        background-color: #fff;
        color:#11093a !important;
        cursor: pointer;
      }
       &:hover::before{
        transition: background-color .5s;
        background-color: #fff;
        color:#11093a !important;
        cursor: pointer;
      }
    }

  }

</style>