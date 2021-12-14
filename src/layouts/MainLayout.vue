<template>
  <div class="main-layout">
      <NavBar/>
    <div class="page-title">
         {{$route.meta.title}}
    </div>
    <div class="page-comtainer">
      <router-view />
    </div>
  </div>
</template>

<script>
import NavBar from "@/components/NavBar"
export default {
  name: "MainLayout",
  components:{NavBar}
};
</script>

<style scoped>
/* .main-layout {
  width: 100%;
  max-width: 800px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
} */
</style>
