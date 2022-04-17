<template>
    <div>
     <h2 class="text-primary">Hello</h2>
      <div class="container">
          <div class="row">
              <AddTodo></AddTodo>
          </div>
          <div class="row">
              <div class="col-md-4 my-4" v-for="Todo in MyTodos" :key="Todo.id">
                  <b-card bg-variant="primary" text-variant="white" class="text-center">
                     <b-card-text class="d-flex justify-content-between">
                         <span>{{ Todo.title }}</span>
                         <span @click="deleteTodo(Todo.id)"><b-icon icon="trash-fill" variant="danger"></b-icon></span>
                     </b-card-text>
                  </b-card>
              </div>
          </div>
      </div>

    </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex"
import AddTodo from "./AddTodo.vue"
    export default {
    computed: mapGetters(["MyTodos"]),
    methods: mapActions(["getTodos","deleteTodo"]),
    mounted() {
        this.getTodos();
    },
    components: { AddTodo }
}
</script>

<style lang="scss" scoped>

</style>