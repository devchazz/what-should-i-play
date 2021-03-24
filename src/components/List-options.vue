<template>
  <main>
    <h2 v-if='subTitle'> {{subTitle}}</h2>
    <div id="container-list">
      <!--Form:-->
      <Form @addOptionChild="addOption"/>

      <div class="d-flex-column">
        <!--Render the options:-->
        <div>
          <div v-for="(e, i) in options" :key="i">
            <Option 
              :name="options[i]" 
              :functionClose="()=>{removeOption(i)}"
            />
          </div>
        </div>
        <!--Result:-->
        <div id="container-result">
          <button v-if="!answer" id="btn-draw" @click="draw">Ask the computer</button>
          <div v-if="answer"  id="container-result-final">
            <p id="answer">{{answer}}</p>
            <button id="btn-reset" @click="reset">Try again</button>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import Form from './list-components/Form'
import Option from './list-components/Option'

export default {
  data(){
    return{
      options: [],
      answer: ''
    }
  },

  props: {
    subTitle: String
  },

  components: {
    Form,
    Option
  },

  methods: {
    //Pick a random option in the options array:
    draw(){
      this.answer = this.options[Math.floor(Math.random() * this.options.length)];
    },
    //Add a option in the options array
    addOption(value){
      if(value){
        this.options.push(value)
        //Clear the form
        document.getElementById('input-add-option').value = ''
      }
    },
    //Reset the answer and let the user try again:
    reset(){
      this.answer = ''
    },
    //To the components:
    removeOption(i){
      this.options.splice(i,1)
    }
  }
}

</script>

<style>
  h2{
    font-weight: inherit;
    margin: 20px 0;
  }
  main{
    overflow-x: hidden ;
  }
  /* Containers: */
  #form-container{
    border-bottom: 2px #707070 solid;
  }
  #container-list{
    border: 2px solid #707070;
    background-color: white;
    min-height: 300px;
    width: 80%;
    margin: auto auto 30px auto;
    border-radius: 10px;
  }
  #container-list p{
    font-size: 1.2em;
  }
  #container-result{
    border-top: 2px solid #707070;
    padding: 10px 20%;
  }
  #container-result-final{
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }
  .d-flex-column{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    min-height: 310px;
    overflow-x: hidden;
  }
  /* Inputs: */
  input:focus, input:active{
    outline: none;
  }
  /* Buttons: */
  button{
    padding: 5px;
    border-radius: 5px;
    border: #777 2px solid;
  }
  button:focus, button:active{
    outline: none;
  }
  #btn-draw{
    font-size: 1.1em;
    margin: 10px;
  }
  #btn-reset{
    font-size: 1.1em;
    margin: 10px;
  }
  #answer{
    font-weight: bold;
  }
  /* Responsive: */
  @media only screen and (max-width: 600px) {
    #container-list {
      width: 95%;
    }
    
  }
</style>