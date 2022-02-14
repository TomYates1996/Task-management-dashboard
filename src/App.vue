<template>
  <div class="main-app-div">
    <Login @signIn="signIn" v-if="!signedIn" />
    <MyTaskApp v-if="signedIn" :email="user.email" :password="user.password" @sign-out="signOut"/>
    
  </div>
</template>

<script>
import Login from './components/Login'
import MyTaskApp from './components/MyTaskApp'

export default {
  name: 'App',
  components: {
    Login,
    MyTaskApp,
  },
  data() {
    return {
      user: '',
      signedIn: false,
    }
  },
  methods: {
    signIn(user) {
      this.user = user;
      this.signedIn = true;
    },
    signOut() {
      this.signedIn = false;
    }
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500;600;700;800;900&display=swap');
  *{
    box-sizing: border-box;
    padding: 0;
    margin: 0;
    font-family: 'Poppins', sans-serif;
  }
  .flex {
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>
