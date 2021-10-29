<template>
  <div >
    <div :key="input.id" v-for="input in inputs" class="input-wrapper">
      <input type="radio" /><label>{{input.name}}</label><br>
      <input :type=input.subcompo :placeholder=input.subcompo />
    </div>
  </div>
</template>
<script>

export default ({
  name: 'Inputs',
  props: {
    inputs: Array
  }
})
</script>
<style scoped>
.input-wrapper {
  border: solid 1px #aaa;
  display: inline-block;
  padding: 20px;
  margin: 10px;
  border-radius: 4px;
}
</style>