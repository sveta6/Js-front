<template>
    <div class="form">
      <img src="../assets/incognito.jpg" width="200" height="280" />
      <h1 class="Second_Name">Who are you?</h1>
      <form action="" method="">
        <div class="Forms">
          <div class="Name">
            <label for="user_name">Enter your name: </label>

            <input
              type="text"
              placeholder="Your name"
              maxlenght="10"
              id="user_name"
            /><br /><br />
          </div>

          <div class="Email">
            <label for="user_email">Enter your email:</label>

            <input
              type="email"
              placeholder="Your email"
              id="user_email"
            /><br /><br />
          </div>

          <div class="Comment">
            <label for="user_comment">Enter your Comments:</label>

            <input
              type="text"
              placeholder="Your Commetns"
              id="user_comment"
            /><br /><br />
          </div>
        </div>

        <div class="Submit">
          <input type="submit" value="Submit" />
        </div>
      </form>
    </div>
</template>

<script>
export default {
  name: "FormCard",
};
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
</style>
