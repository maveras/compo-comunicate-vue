<template>
  <div class="component">
    <h3>You may edit the User here</h3>
    <p>Edit me!</p>
    <p>User age: {{ userAge }}</p>
    <p><button @click='editAge'>edit Age</button></p>
  </div>
</template>

<script>
import {eventBus} from '../main'

export default {
  data () {
    return {
    }
  },
	props:['userAge'],
	methods: {
		editAge() {
      this.userAge = 30
      eventBus.$emit('ageWasEdited',this.userAge)
    }
	}
}
</script>

<style scoped>
div {
  background-color: lightgreen;
}
</style>
