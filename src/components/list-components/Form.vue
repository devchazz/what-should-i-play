<template>
  <div id="form-container">
    <input type="text" @keyup.enter="addOptionChild" autocomplete="off" placeholder="Option name" id="input-add-option">
    <button id="btn-add-option" @click="addOptionChild">Add option</button>
  </div>
</template>

<script>
export default {
  methods:{
    addOptionChild(){
      let inputValue = document.getElementById("input-add-option").value
      inputValue && this.$emit('addOptionChild', inputValue)
    }
  }
}
</script>

<style scoped>
  #btn-add-option{
    font-size: 1.1em;
    margin: 10px 0;
  }
  #input-add-option{
    border: #777 2px solid;
    padding: 5px;
    border-radius: 5px;
    font-size: 1.1em;
    margin: 10px;
  }
</style>