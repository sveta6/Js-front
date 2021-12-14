<template>
  <form @submit.prevent="onFormSubmit" class="login-form">
    <div class="form-field">
      <label form="login">Login</label>
      <input id="login" type="text" required />
    </div>
    <div class="form-field">
      <label form="passwd">Password</label>
      <input id="passwd" type="text" required />
    </div>
    <button calss="submit-btw" type="submit">Войти</button>
    <div class="action-link">
      <span>Нет аккаунта?</span>
      <a @class="redirect" class="link-btw">Зарегистрируйтесь</a>
    </div>
  </form>
</template>

<script>
import { doLogin } from "@/netClient/todoService";
export default {
  name: "LoginPage",
   data: ()=> ({
      login: '',
      password: '',
  }),
  async mounted() {},
  methods: {
    async onFormSubmit() {
      try {
        const token = await doLogin(this.login.trim(), this.password.trim());
        console.warn({ token });
        if (token) {
          this.$router.push("/");
        }
      } catch (error) {
        console.error({ error });
      }
    },
    redirect() {
      this.$router.push("/registration");
    },
  },
};
</script>

<style scoped>
/* .Forms input {
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
  border: 4px solid #bd2b85;
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
.Submit :hover {
  border-color: #bd2b85;
}

label input {
} */
</style>
