<template>
  <div class="main-layout">
    <NavBar />
    <div class="page-title">
      {{ $route.meta.title }}
    </div>
    <ul class="page-container">
      <router-view />
    </ul>
  </div>
</template>

<script>
import NavBar from "@/components/NavBar";
export default {
  name: "MainLayout",
  components: { NavBar },
};
</script>

<style scoped>
/* .main-layout {
  width: 100%;
  display: grid;

   grid-template-rows: repeat(2, 1fr);

  grid-gap: 20px;

}  */
ul {
  
}
.page-container{
 grid-template-columns: 500px 20% min-content max-content 1fr 2fr auto;
  grid-template-rows: auto minmax(50px, 50vh) 2em;
}
 .main-layout {
  width: 100%;
  max-width: 1200px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
}
</style>
