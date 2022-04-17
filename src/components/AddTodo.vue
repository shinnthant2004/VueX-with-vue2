<template>
    <div>
          <div class="input-group mb-3">
              <input type="text" class="form-control" v-model="newToDo.title">
                <div class="input-group-append">
                   <button class="btn btn-primary" @click="addTodo(newToDo)">Add Todo</button>
                </div>
         </div>  
    </div>
</template>

<script>
import { mapActions } from 'vuex'
    export default {
        methods:mapActions(['addTodo']),
        data() {
            return {
                newToDo:{
                    title:""
                }
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>