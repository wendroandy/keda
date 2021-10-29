<template>
  <div class="container">
    <h1>Wendroandy Test</h1>
    <AddInput @add-input="addInput"/>
    <Inputs :inputs="inputData" />
  </div>
</template>

<script>
import Inputs from './components/Inputs.vue'
import AddInput from './components/AddInput.vue'

export default {
  name: 'App',
  components: {
    Inputs,
    AddInput
  },
  data() {
    return {
      inputData: []
    }
  },
  methods: {
    addInput(input) {
      this.inputData=[...this.inputData, input]
    }
  }
}
</script>

<style>

</style>
