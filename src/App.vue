<template>
  <div id="app">
    <Header :title='app.title'/>
    <Container :subTitle='app.subTitle'/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Container from './components/Container.vue'

export default {
  name: 'App',
  
  data(){
    return {
      app : {
        title: 'What should I play?',
        subTitle: 'Have too many games to play? I can help you!'
      }
    }
  },

  components: {
    Header,
    Container
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Nunito&display=swap');
  *{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }
  #app{
    font-family: 'Nunito', sans-serif;
    letter-spacing: 1px;
    text-align: center;
    font-size: 1.2em;
    min-height: 100vh;
  }
</style>
