<template>
  <div id="igLoginBox" class="wrapper">
    <div class="title">Login</div>
    <div id="igLogInForm" class="login-form">
      <div class="field">
        <input id="igLoginUsername" type="text" required />
        <label>Email Address</label>
      </div>
      <div class="field">
        <input id="igLoginPassword" type="password" required />
        <label>Password</label>
      </div>
      <div class="content">
        <div class="checkbox">
          <input type="checkbox" id="remember-me" />
          <label for="remember-me">Remember me</label>
        </div>
        <div class="pass-link">
          <a href="#">Forgot password?</a>
        </div>
      </div>
      <div id="igLogInMessage" class="login-message ig-hidden">
        Error message goes here
      </div>
      <div id="igLogInActions" class="actions">
        <div id="igLoginOK" class="field submit-btn" data-busy="0">
          <input type="submit" value="Login" />
        </div>
      </div>
      <div class="signup-link">Not a member? <a href="#">Signup now</a></div>
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 380px;
  background: #fff;
  border-radius: 8px;
  padding: 30px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.wrapper .title {
  font-size: 1.5em;
  font-weight: 600;
  text-align: center;
  margin-bottom: 25px;
}

.wrapper .field {
  position: relative;
  height: 50px;
  margin-top: 25px;
}

.wrapper .field input {
  height: 100%;
  width: 100%;
  padding-left: 15px;
  border: 1px solid lightgrey;
  border-radius: 5px;
  outline: none;
  transition: all 0.3s ease;
}

.field input:focus {
  border-color: #ffd33f;
}

.field input:focus ~ label,
.field input:valid ~ label {
  top: -10px;
  font-size: 14px;
  background: #fff;
  padding: 0 5px;
  color: #251d01;
}

.field label {
  position: absolute;
  top: 50%;
  left: 15px;
  color: #999;
  transform: translateY(-50%);
  font-size: 16px;
  pointer-events: none;
  transition: all 0.3s ease-in;
}

.field input[type="submit"] {
  background-color: #ffd33f;
  color: #fff;
  border: none;
  font-size: 18px;
  font-weight: 500;
  cursor: pointer;
}

.field input[type="submit"]:hover {
  background-color: #ffd33f;
}

.content {
  display: flex;
  justify-content: space-between;
  margin: 10px 0;
}

.checkbox {
  display: flex;
  align-items: center;
}

.checkbox input {
  margin-right: 5px;
}

.pass-link a,
.signup-link a {
  color: #ffd33f;
  text-decoration: none;
}

.pass-link a:hover,
.signup-link a:hover {
  text-decoration: underline;
}

.signup-link {
  margin-top: 20px;
  text-align: center;
}

.login-message {
  padding: 8px;
  font-size: 0.8em;
  color: #721c24;
  background-color: rgba(255, 0, 0, 0.1);
  border: 1px solid rgba(255, 0, 0, 0.3);
  border-radius: 3px;
  margin-top: 15px;
}

.ig-hidden {
  display: none;
}

.submit-btn[data-busy="1"] input {
  opacity: 0.7;
  cursor: not-allowed;
}
</style>

<script>
export default {
  name: "Login",
  emits: ["submit-login"],
  mounted() {
    const loginOK = document.getElementById("igLoginOK");
    const loginUsername = document.getElementById("igLoginUsername");
    const loginPassword = document.getElementById("igLoginPassword");

    if (loginOK && loginUsername && loginPassword) {
      // Handle button click
      loginOK.addEventListener("click", () => {
        if (loginOK.dataset.busy === "1") return;

        const username = loginUsername.value;
        const password = loginPassword.value;

        // Use the existing auth logic from the parent component
        this.$emit("submit-login", { username, password });
      });

      // Handle Enter key press in password field
      loginPassword.addEventListener("keyup", (e) => {
        if (e.key === "Enter") loginOK.click();
      });

      // Handle Enter key press in username field
      loginUsername.addEventListener("keyup", (e) => {
        if (e.key === "Enter" && loginUsername.value) {
          loginPassword.focus();
        }
      });
    }
  },
};
</script>
