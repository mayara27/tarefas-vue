<template>
  <div class="new-task">
      <input class="form-element" v-model="name" @keydown.enter="add" 
             type="text" placeholder="Adicione uma tarefa">
      <button @click="add" class="form-element">+</button>
  </div>
</template>

<script>
export default {
    data () {
        return {
            name: ''
        }
    },

    methods: {
        add() {
            this.$emit('taskAdded', { name: this.name })
            this.name = ''
        }
    }
}
</script>

<style>
    .new-task{
        margin: 35px;
    }

    .form-element{
        outline: none;
        font-size: 2rem;
        border: 1px solid white;
        padding: 5px 10px 8px;
    }

    input.form-element{
        width: 500px;
        border-top-left-radius: 8px;
        border-bottom-left-radius: 8px;
    }

    button.form-element{
        border-top-right-radius: 8px;
        border-bottom-right-radius: 8px;
        border-left: none;
        background-color: rgb(0, 179, 250);
        color: white;
    }
</style>