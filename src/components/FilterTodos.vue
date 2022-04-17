<template>
    <div>
     <select v-model="limit" class="form-control" @change="filterTodos(limit)">
         <option value="5" class="form-control">5</option>
         <option value="10" class="form-control">10</option>
         <option value="20" class="form-control">20</option>
         <option value="40" class="form-control">40</option>
     </select>
    </div>
</template>

<script>
import { mapActions } from 'vuex'
    export default {
        methods:mapActions(['filterTodos']),
        data() {
            return {
                limit: null
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>