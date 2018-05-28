<template lang="html">
  <div class="">
    <input type="text" name="" v-model="titleText" value="" placeholder="Task to be done" ref="name">
    <input type="text" name="" v-model="projectText" value="" placeholder="Project" ref="project">
    <input type="button" v-on:click="sendForm" value="Enviar">
      </div>
</template>

<script>
export default {
data(){
  return {
    titleText: '',
    projectText: '',
  }
},
methods: {
  sendForm() {
      const title = this.titleText;
      const project = this.projectText;
      this.$emit('create-todo', {
        title,
        project,
        done: false
      });
      this.newTodoText = '';
      console.log("Clicado");
    }
},
};
</script>

<style lang="css">
</style>
