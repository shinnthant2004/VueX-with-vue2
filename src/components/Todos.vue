<template>
    <div>
     <h2 class="text-primary">Hello</h2>
      <div class="container">
          <div class="row">
              <div class="col-md-4 my-4" v-for="Todo in MyTodos" :key="Todo.id">
                  <b-card bg-variant="primary" text-variant="white" class="text-center">
                     <b-card-text>{{ Todo.title }}</b-card-text>
                  </b-card>
              </div>
          </div>
      </div>

    </div>
</template>

<script>
import { mapActions, mapGetters } from "vuex"
    export default {
        computed:mapGetters(["MyTodos"]),
        methods:mapActions(['getTodos']),
        mounted(){
            this.getTodos()
        }
    }
</script>

<style lang="scss" scoped>

</style>