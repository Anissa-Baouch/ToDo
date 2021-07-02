<template>
  <form class="col-12 col-sm-12 col-md-6 cl-lg-12" @submit.prevent="addTodo()">
    <input
      v-model="newTodo"
      type="text"
      class="form-control text-white"
      placeholder="Créer un nouveau TODO"
    />
  </form>
</template>

<script>
export default {
  data() {
    return {
      newTodo: ""
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo.length > 0) {
        this.$emit("on-new-todo", this.newTodo);
      }
      this.newTodo = "";
    }
  }
};
</script>
