<template>
  <h1>UsersList</h1>

  {{ users }}

  <!-- <div v-if="isLoading">
    ...loading
  </div>
  <div v-else> -->
    <!-- <UserItem v-for="user in users" :key="user.id" :user="user"/> -->
  <!-- </div> -->
</template>

<script>
import UserItem from '@/components/UserItem.vue'

// COMP -> STORE -> SERVICE -> 


// 1
export default {
    name: 'UsersList',
    components: {
        UserItem
    },
    // свойства и методы
    data: () => ({
        // users: []

        // // users: [],
        isLoading: false
    }),
    // mounted, created, updated <---- lifeCycle events on component
    // 2
    mounted(){
        // console.log(this)

        // this.loadUsers()
        // 2 -> 3
        this.$store.dispatch('loadUsers')
    },
    computed: {
        // 6
        users(){
            return this.$store.state.users
        }
    },
    methods: {
        // loadUsers(){
        //    loadUsers().then(json => {
        //         this.users = json
        //         this.isLoading = false
        //     })
        // }
    }
}
</script>

<style>

</style>
