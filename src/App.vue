<template>
  <div id="app">
    <component :is="layout">
      <!-- <router-link class="link" to="/">
    to home
    </router-link>
    <a>|</a>
    <router-link class="link" to="/Info">
    to info
    </router-link>-->
      <router-view />
    </component>
  </div>
</template>

<script>
import AuthLayout from "@/layouts/AuthLayout";
import MainLayout from "@/layouts/MainLayout";
export default{
    name: 'App',
    components: { MainLayout, AuthLayout},
    computed:{
      layout(){
        return this.$route.meta?.layout || 'main-layout'
      }
    }
  }
</script>


<style>
/* .link {
  font-size: 18px;
  color: #ffffff;
}

a {
  color: #ffffff;
}

body {
  margin: 0;

  background-image: url(./assets/back.jpg);

  background-position: no-repeat center center;

  background-size: 100%;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;

  -webkit-font-smoothing: antialiased;

  -moz-osx-font-smoothing: grayscale;

  text-align: center;

  color: #2c3e50;

  margin: 0;
}

.cards {
  display: flex;
  flex-direction: row;
}

img {
  border-radius: 14px 14px 14px 14px;
  border: 4px solid #bd2b85;
} */
</style>
