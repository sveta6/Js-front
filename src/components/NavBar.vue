<template>
    <div id = "nav">
        <div class="link-wrapper">
            <ul class="links">
            <div class="nav-links">
                <router-link tag="li" class="link" exact to="/">Список дел </router-link>
                <router-link tag="li" class="link" to="/info">Инфо </router-link>
            </div>   
            <a @click="onLogoutClicked" class="logout link"><li>
                Выйти
            </li>
            </a>
            </ul>
        </div>        
    </div>
</template>

<script>
import { doLogout } from '@/netClient/authService';
export default{
    name: 'NavBar',
    methods:{
        async onLogoutClicked(){
            try {
                await doLogout();
                this.$router.push('/login');
            } catch (error) {
                console.error({error});
            }
        }
    },
};
</script>

<style scoped>
a.router-link-active, li.router-link-active>a {
  color: #35C0CD;
}
.menu{
  float: right;
  margin: 0;
  padding: 0;
  display: flex;
}
.header {
  background: linear-gradient(#025167, #057D9F);
  box-shadow: 10px 5px 10px black;
  height: 100px;
  z-index: 3;
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
}
header ul li {
  list-style: none;
  padding: 16px 16px;
}
header ul li a {
  text-decoration: none;
  color: #dbebfa;
}
.logo {
  float: left;
  margin: 0 0 0 150px;
  height: 100px;
  width: 100px;
}
nav li:hover,
nav li:active{
  background-color: #63ADD0;
  cursor: pointer;
}
</style