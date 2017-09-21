<template>
  <div class="component">
    <h3>You may view the User Details here</h3>
    <p>Many Details</p>
    <p>name: {{ reverseName()}}</p>
  </div>
</template>

<script>
export default {
  data () {
    return {
    }
 },
 props: ['name'],
 methods: {
  reverseName() {
    return this.name.split("").reverse().join("")
  }
 }
}
</script>

<style scoped>
div {
  background-color: lightcoral;
}
</style>
