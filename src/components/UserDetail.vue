<template>
  <div class="component">
    <h3>You may view the User Details here</h3>
    <p>Many Details</p>
    <p>name: {{ reverseName() }}</p>
    <p><button @click="resetName">reset name</button></p>
  </div>
</template>

<script>
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
  }
  
},
 methods: {
  reverseName() {
    return this.name.split("").reverse().join("")
  },
  resetName () {
    this.name = 'resetedNameGuy'
    this.$emit('nameWasReset',this.name)
  }
 }
}
</script>

<style scoped>
div {
  background-color: lightcoral;
}
</style>
