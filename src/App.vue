<template>
  <div id="app">
    <div class="h-90">
      <Header :title='app.title'/>
      <ListOptions :subTitle='app.subTitle'/>
    </div>
    <Footer/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import ListOptions from './components/List-options'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  
  data(){
    return {
      app : {
        title: 'What should I play?',
        subTitle: 'Have too many options? I can help you!'
      }
    }
  },

  components: {
    Header,
    ListOptions,
    Footer
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
    background-color: #EEEEEE;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    letter-spacing: 1px;
    text-align: center;
    font-size: 1.2em;
    min-height: 100vh;
  }
  .h-90{
    min-height: 90vh;
  }
</style>
