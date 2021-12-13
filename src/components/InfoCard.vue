<template>
  <div class="info">
    <img src="../assets/1.jpg" width="200" height="280" />
    <h1 class="First_Name">
      SVeta Buzdalova</h1>
    <h2>BSBO-07-19</h2>
    <p class="mes">
      Hello, nice to meet you on my localhost. This page is under
      constuction. Hope you'll like my websource :3
    </p>
  </div>
</template>

<script>
export default {
  name:"InfoCard"
}
</script>


<style scoped>
.info {
  box-shadow: 3px 3px 3px #fcfcfc;
  margin: auto;
  background-color: #d485ba;
  font-family: "Didact Gothic";
  width: 500px;
  height: 500px;
  border-radius: 14px 14px 14px 14px;
  border: 4px solid  #bd2b85;
}

h2 {
  font-size: 24px;
  color: #ffffff;
  top: 140px;
  left: 280px;
  text-shadow: 2px 4px  #bd2b85;
}

.mes {
  font-size: 22px;
  left: 100px;
  text-align: left;
  color: #ffffff;
}

.First_Name {
  font-size: 26px;
  color: #ffffff;
  text-shadow: 2px 4px  #bd2b85;
}
</style>
