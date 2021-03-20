<template>
  <header>
    <h1>{{ title }}</h1>
    <nav><a href="">GitHub</a></nav>
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    title: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  header{
    width: 100%;
    padding: 10px 2%;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  nav a{
    color: black;
    text-decoration: none;
    padding: 5px 10px;
    border: 1px solid black;
    border-radius: 5px;
    transition: all 300ms;
  }
  nav a:hover{
    background-color: black;
    color: white;
  }
  @media only screen and (max-width: 600px) {
    header{
      flex-direction: column;
      justify-content: space-between;
      margin-bottom: 12px;
    }
    h1{
      margin-bottom: 12px;
    }
  }
</style>
