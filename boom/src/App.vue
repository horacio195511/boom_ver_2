<template>
<div>
  <component
    :is="present"
    @change-view="present = $event"
    ></component>
</div>
</template>

<script>
import Login from './components/Login.vue';
import Signup from './components/Signup.vue';
import Home from './components/Home.vue';
import ListAndForm from './components/ListAndForm.vue'
export default {
  name: 'App',
  components: {
    Login,
    Signup,
    Home,
    ListAndForm,
  },
  data(){
    return{
      present:'Home',
    };
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
  margin-top: 60px;
}
</style>
