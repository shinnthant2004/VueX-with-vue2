<template>
    <div>
     <h2 class="text-primary">Hello</h2>
      <div class="container">
          <div class="row">
              <AddTodo></AddTodo>
              <FilterTodos></FilterTodos>
          </div>
          <div class="row">
              <div class="col-md-4 my-4" v-for="Todo in MyTodos" :key="Todo.id">
                  <b-card :bg-variant="dynamicBackground(Todo)" text-variant="white" class="text-center" @dblclick="toggleComplete(Todo)">
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
import FilterTodos from "./FilterTodos.vue"
    export default {
    computed: mapGetters(["MyTodos"]),
    methods: {
        ...mapActions(["getTodos","deleteTodo","updateTodo"]),
         dynamicBackground(Todo){
         return Todo.completed ? 'success' : 'primary'
        },
        toggleComplete(Todo){
          Todo.completed=!Todo.completed;
          this.updateTodo(Todo)
        }
    },
    mounted() {
        this.getTodos();
    },
    components: { AddTodo, FilterTodos }
}
</script>

<style lang="scss" scoped>

</style>