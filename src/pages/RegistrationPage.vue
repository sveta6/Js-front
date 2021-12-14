<template>
  <form @submit.prevent = "onFormSubmit" class="registration-form">
    <div class="form-field">
      <label form="login">Login</label>
      <input v-model="login" id="login" type="text" required />
    </div>
    <div class="form-field">
      <label form="passwd">Passoword</label>
      <input v-model="passwd" id="passwd" type="text" required />
    </div>
    <button calss="submit-btw" type="submit">Регистрация</button>
    <div class="action-link">
      <span>Уже есть аккаунт?</span>
      <a @class="redirect" class="link-btw">Войти</a>
    </div>
  </form>
</template>

<script>
import {doRegistration} from '@/netClient/dataService';

export default {
  name:"RegistrationPage",
  data: ()=>({
      login: '',
      //email: '',
      password: '',
  }),
  async mounted(){},
  methods:{
    async onFormSubmit(){
        try {
          const data = await doRegistration(
             this.login.trim(),
            //this.email.trim(),
            this.password.trim())
          console.warn({data});
        } catch (error) {
          console.error({error});
        }
          this.$router.push('/')
      },
    redirect(){
      this.$router.push('/login')
    }
  }
}
</script>


<style scoped>
.Forms input {
  float: right;
  outline: none;
  text-align: center;
  border-radius: 14px;
  border: 2px solid;
  clear: both;

}

.form {
  margin: auto;
  width: 500px;
  height: 500px;
  box-shadow: 3px 3px 3px #fcfcfc;
  background-color: #d485ba;
  font-family: "Didact Gothic";
  width: 500px;
  height: 500px;
  border-radius: 14px 14px 14px 14px;
  border: 4px solid  #bd2b85;
}

.Name input {
  float: center;
}

.Email input {
  float: center;
}

.Second_Name {
  font-size: 24px;
  color: #ffffff;
  text-shadow: 2px 4px #bd2b85;
  
}

.Submit input {
  margin: auto;
  height: 20px;
  width: 150px;
  border-radius: 16px;
  border: 4 px solid;

}
.Submit :hover{
  border-color: #bd2b85;
}

label input {
}
</style>

