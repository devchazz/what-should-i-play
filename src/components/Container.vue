<template>
  <main>
    <h2 v-if='subTitle'> {{subTitle}} </h2>
    <ListOptions/>
  </main>
</template>

<script>
import ListOptions from "./List-options"

export default {
  name: 'Main',
  props: {
    subTitle: String
  },
  components: {
    ListOptions
  }
}
</script>

<style>

</style>