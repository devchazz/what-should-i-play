<template>
  <div>
    <p>{{index}}: {{name}}</p>
    <button @click="functionClose">
      Delete this option
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

</style>