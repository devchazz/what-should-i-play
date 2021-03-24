<template>
  <div id="container-option">
    <p>{{name}}</p>
    <button @click="functionClose">
      &#10006;
    </button>
  </div>
</template>

<script>
export default {
  props:{
    name: String,
    index: Number,
    functionClose: Function
  }
}
</script>

<style scoped>
  #container-option{
    padding: 10px 15%;
    font-size: 1.2em;
    border-bottom: black 1px solid;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  button{
    border: none;
    background-color: white;
    padding: 1px 5px;
    font-weight: bold;
    font-size: 1.1em;
  }
  @media only screen and (max-width: 600px) {
    #container-option{
      padding: 10px 10%;
    }
  }
</style>