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
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
</style>
