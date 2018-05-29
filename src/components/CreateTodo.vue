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
  if (this.titleText.length > 0 && this.projectText.length > 0) {
    const title = this.titleText;
    const project = this.projectText;
    console.log("antes");
    this.$emit('create-todo', {
      title,
      project,
      done: false,
    });
    console.log("depois");
    this.titleText = '';
    this.projectText = '';
    this.isCreating = false;
  }
},
},
};
</script>

<style lang="css">
</style>
