<template>
  <div id="container-list">
    <h3>Add a Option:</h3>
    <hr/>
    <!--Form:-->
    <div>
      <input type="text" autocomplete="off" placeholder="Option name" id="input-add-option">
      <button id="btn-add-option" @click="addOption">Add option</button>
    </div>
    
    <hr/>

    <div class="flex-column">
      <!--List of options:-->
      <div>
        <h3>List of Options:</h3>
        <hr/>
        <div v-for="(e, i) in options" :key="i">
          <Option 
            :name="options[i]" 
            :index="i+1" 
            :functionClose="()=>{removeOption(i)}"
          />
        </div>
      </div>
      <!--Result:-->
      <div>
        <hr/>
        <button v-if="!answer" id="btn-draw" @click="draw">Ask the computer</button>
        <div v-if="answer">
          <p>{{answer}}</p>
          <button id="btn-reset" @click="reset">Try again</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Option from './Option'

export default {
  data(){
    return{
      options: [],
      answer: ''
    }
  },

  components: {
    Option
  },

  methods: {
    //Pick a random option in the options array:
    draw(){
      this.answer = this.options[Math.floor(Math.random() * this.options.length)];
    },
    //Add a option in the options array
    addOption(){
      let newOptionValue = document.getElementById('input-add-option').value
      let newOption = newOptionValue
      this.options.push(newOption)
      //Clear the form
      document.getElementById('input-add-option').value = ''
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

<style scoped>
  /* Containers: */
  #container-list{
    border: 1px solid black;
    min-height: 300px;
    width: 80%;
    margin: auto;
    border-radius: 10px;
  }
  #container-list p{
    font-size: 1.2em;
  }
  .flex-column{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    min-height: 300px;
  }
  /* Inputs: */
  #input-add-option{
    font-size: 1.1em;
    margin: 10px;
  }
  /* Buttons: */
  #btn-add-option{
    font-size: 1.1em;
  }
  #btn-draw{
    font-size: 1.1em;
    margin: 10px;
  }
  #btn-reset{
    font-size: 1.1em;
    margin: 10px;
  }
  /* Responsive: */
  @media only screen and (max-width: 600px) {
    #container-list {
      width: 95%;
    }
  }
</style>