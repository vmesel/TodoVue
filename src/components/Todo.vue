<template>
<div>
  <h2>{{ todo.title }}</h2>
  <p>{{ todo.project }}</p>
  <p>{{ todo.done }}</p>
  <input type="button" value="Editar" v-on:click="showForm">
  <div v-show="isEditing">
    <input type="text" v-model="todo.title">
    <input type="text" v-model="todo.project">
    <input type="button" name="" value="fechar" v-on:click="hideForm">

  </div>
</div>
</template>

<script type="text/javascript">
  export default{
    props: ['todo'],
    data() {
      return {
        isEditing: false,
      };
  },
  methods: {
    showForm() {
      this.isEditing = true;
    },
    hideForm() {
      this.isEditing = false;
    },
  },
  };
</script>
