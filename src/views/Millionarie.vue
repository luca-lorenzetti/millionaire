
<template>
  <div>
    <div class="header">
      <!-- <MillionarieIndex msg="" /> -->
      <img id="logo" alt="Vue logo" src="../assets/logo_mil.png" />
    </div>
        <main>
          <div class="container">
            <Question :ask="question.ask">
            </Question>

            <Answer :answers="answers">
            </Answer>
          </div>
        </main>
  </div>

</template>

<script>
// @ is an alias to /src
import Question from "@/components/Question.vue";
import Answer from "@/components/Answer.vue";


export default {
  name: "Millionarie",
  components: {
     Question,
     Answer
  },
  data(){
    return{
      questions:[
        [// Questions leve 1
          {
            ask: 'Chi è stato il primo insegnante Boolean?',
            answers: ['Michele', 'Luca', 'Chiara'],
            correct: 'Fabio'
          },
          {
            ask: 'Quale personaggio disney perde una scarpetta di vetro?',
            answers: ['La bella addormentata', 'Pocahontas', 'Elsa'],
            correct: 'Cenerentola'
          },
           {
            ask: 'Perchè il procione viene detto "orsetto lavotore"?',
            answers: ['Perchè si lava spesso', 'Perchè vive in acqua', 'Perchè lava i piccoli'],
            correct: 'Perchè lava i suoi cibi'
          },
          {
            ask: 'Quale personaggio dei cartoni animati ha reso famosi in tutto il mondo il "Donuts", le ciambelle fritte ricoperte di glassa o cioccolato?',
            answers: ['Bugs Bunny', 'Pippo', 'Fred Flinstone'],
            correct: 'Homer Simpson'
          }
        ]
      
      ],

      question:{},
      ask: '',
      answers:[],
      correct: '',
      randomQuestion: 0
    }
  },
  methods:{

    // Funzione che riordina l'Array
    sortAnswers(){
     let answersTmp = [];
     let index = 0;

      while( answersTmp.length != 4){

        index = Math.floor(Math.random()* this.answers.length)
          if(!answersTmp.includes(this.answers[index])){
              answersTmp.push(this.answers[index])
          }
      }

      this.answers = answersTmp;
    }
  },
  created(){
    this.randomQuestion = Math.floor(Math.random() * (this.questions[this.number-1].length) );
    this.question = this.questions[this.$route.params.number-1][this.randomQuestion];

    this.answers = this.question.answers;
    this.answers.push(this.question.correct);

    this.sortAnswers();
  },
  props:['number']


};
</script>

<style scoped lang="scss">
  .header{
    background-color: #11158d;
    padding-top: 50px;
    height: 49%;

    #logo{
      height: 350px;
    }
}

    main{

      background-color: #11093a;
      width: 100%;
      height: 51%;
      bottom: 0;
      color: #fff;
      font-weight: bold;

    .container{
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 70%;
      margin: 0 auto;
     }
    }

</style>
