<template>
  <div class="component">
    <h1>The User Component</h1>
    <p>I'm an awesome User!</p>
    <p>{{name}}</p>
    <button @click='changeUserName'>Change my name </button>
    <hr>
    
    <div class="row">
      <div class="col-xs-12 col-sm-6">
        <app-user-detail :userAge='age' :name='name' @nameWasReset="name = $event"></app-user-detail>
      </div>
      <div class="col-xs-12 col-sm-6">
        <app-user-edit :userAge='age'></app-user-edit>
      </div>
    </div>
  </div>
</template>

<script>
  import UserDetail from './UserDetail.vue';
  import UserEdit from './UserEdit.vue';

  export default {
    data() {
      return {
        name:'anna',
        age: 27
      }
    },
    components: {
      appUserDetail: UserDetail,
      appUserEdit: UserEdit
    },
    methods:{
      changeUserName() {
        this.name = 'jhon'
      }
    }
  }
</script>

<style scoped>
  div {
    background-color: lightblue;
  }
</style>
