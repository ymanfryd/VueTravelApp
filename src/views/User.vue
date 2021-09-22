<template>
<div class="userPage">
    <h1>Welcome {{ user }} </h1>
    <router-link :to="{name: 'invoices'}">Invoices</router-link>
    <button @click="logOut" class="btn">Log out</button>
</div>
</template>   

<script>
import store from '@/store'

export default ({
    data() {
        return{
            user: store.user
        }
    },
    methods: {
        logOut() {
            store.user = null;
            this.$router.push("/");
        }
    }
})
</script>

<style scoped>
.userPage {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
</style>
