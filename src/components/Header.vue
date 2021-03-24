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
    color: white;
    min-height: 10vh;
    width: 100%;
    padding: 13px 10%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: black 2px solid;
    background-color: #276fff;
  }
  header h1{
    font-weight: bold;
    font-size: 2em;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }
  nav a{
    font-size: 1.2em;
    color: white;
    text-decoration: none;
    padding: 5px 10px;
    border: 2px solid white;
    border-radius: 5px;
    transition: all 300ms;
  }
  nav a:hover{
    background-color: white;
    color: #276fff;
  }
  @media only screen and (max-width: 650px) {
    header{
      flex-direction: column;
      justify-content: space-between;
      margin-bottom: 12px;
      padding: 15px 0;
    }
    h1{
      margin-bottom: 12px;
    }
  }
</style>
