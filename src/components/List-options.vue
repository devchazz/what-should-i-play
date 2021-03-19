<template>
  <div>
    <h3>Options:</h3>
    <div v-for="(e, i) in options" :key="i">
      <Option 
        :name="options[i]" 
        :index="i+1" 
        :functionClose="removeOption"
      />
    </div>

    <div>
      <input type="text" id="newOptionName">
      <button @click="addOption">+</button>
    </div>

    <button v-if="!answer" @click="draw">Ask the computer</button>
    <div v-if="answer">
      <p>{{answer}}</p>
      <button @click="reset">Try again</button>
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
      let newOptionValue = document.getElementById('newOptionName').value
      let newOption = newOptionValue
      this.options.push(newOption)
      //Clear the form
      document.getElementById('newOptionName').value = ''
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

</style>