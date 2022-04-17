<template>
    <div>
     <h2 class="text-primary">Hello</h2>
      <div class="container">
          <div class="row my-4">
              <div class="col-md-4" v-for="Todo in MyTodos" :key="Todo.id">
                  <b-card bg-variant="primary" text-variant="white" class="text-center">
                     <b-card-text>{{ Todo.title }}</b-card-text>
                  </b-card>
              </div>
          </div>
      </div>

    </div>
</template>

<script>
import { mapGetters } from "vuex"
    export default {
        computed:mapGetters(["MyTodos"]),
    }
</script>

<style lang="scss" scoped>

</style>