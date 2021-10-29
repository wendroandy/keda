<template>
  <form @submit="onSubmit">
      <label>Radion Button Name</label> 
      <input type="text" name="name" v-model="name" placeholder="Name"/>
      <label>Choose Subcomponent</label>
      <select name="subcompo" v-model="subcompo">
        <option :key="option" v-for="option in options">{{option}}</option>
      </select><br><br>
      <button type="submit">Add new Radio</button>
  </form>
</template>
<script>
export default ({
 name: 'AddInput',
 data() {
   return {
     name: '',
     subcompo: '',
     options: ['password','month','number','time','week']
   }
 },
 methods: {
   onSubmit(e) {
     e.preventDefault();
     if(!this.name) {
       alert("please add a name")
       return
     }
     const newInput= {
       id: Math.floor(Math.random() *10000),
       name: this.name,
       subcompo: this.subcompo
     }
     this.$emit('add-input',newInput)
     this.name='';
     this.subcompo='';
   }
 }
})
</script>

<style scoped>
label {
  display: block;
  margin: 5px 0;
}
input {
  margin: 5px 0;
}
</style>