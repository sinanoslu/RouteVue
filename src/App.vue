<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link :to="{name: 'about'}">About</router-link> |
    <router-link :to="{name: 'jobs'}">Jobs</router-link>
  </nav>

  <button @click="Redirect">Redirect</button>
  <button @click="Back">Go Back</button>
  <button @click="Forward">Go Forward</button>

  <router-view/>
</template>

<script>
export default {
    methods:{
      Redirect(){
        this.$router.push({name:'home'})
      },
      Back(){
        this.$router.go(-1)
      },
      Forward(){
        this.$router.go(1)
      }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  padding: 10px;
  border-radius: 4px;
}

nav a.router-link-exact-active {
  color: white;
  background: crimson;
}

button{
    margin: 0 10px;
    padding: 16px;
    border: none;
    border-radius: 4px;
}
</style>
