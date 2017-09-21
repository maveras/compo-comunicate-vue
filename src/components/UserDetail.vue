<template>
  <div class="component">
    <h3>You may view the User Details here</h3>
    <p>Many Details</p>
    <p>name: {{ reverseName() }}</p>
    <p>age: {{userAge}}</p>
    <p><button @click="resetName">reset name</button></p>
  </div>
</template>

<script>
import {eventBus} from '../main'


export default {
data () {
    return {
  }
},
props: {
  name: {
    // type: Object,
    // default: function () {
    //   return {
    //     name: 'Susan'
    //   }
    // }
    type: String
  },
  userAge: Number
  
},
 methods: {
  reverseName() {
    return this.name.split("").reverse().join("")
  },
  resetName () {
    this.name = 'resetedNameGuy'
    this.$emit('nameWasReset',this.name)
  }
 },
 created () {
   eventBus.$on('ageWasEdited',(age)=>{
     console.log(age)
     this.userAge = age
   })
 }
}
</script>

<style scoped>
div {
  background-color: lightcoral;
}
</style>
