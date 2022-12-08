<template>
  <div class="login">
    <div class="main-container">
      <div class="branding">
        <h1>Sign Up to continue</h1>
      </div>
      <div class="form">
          <el-form ref="form" :model="form">
            <el-form-item label="E-mail">
              <el-input id="email" type="email" v-model="form.email"></el-input>
            </el-form-item>
            <el-form-item label="Password">
              <el-input type="password" id="password" v-model="form.password" auto-complete="off"></el-input>
            </el-form-item>
            <el-form-item>
              <el-button type="primary" @click="onSubmit">Sign Up</el-button>
            </el-form-item>
          </el-form>
          <div class="register">
            <p>New over here? <a @click="$router.push('/register')">Register</a></p> 
          </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data() {
    return {
      form: {
        email: '',
        password: ''
      },
      myEmail: 'jpalacios@example.com',
      myPassword: '123456',
      isValid: true
    }
  },
  methods: {
    onSubmit() {
      // console.log(this.newEmail);
      const regex = new RegExp('[a-z0-9]+@[a-z]+\.[a-z]{2,3}');
      if (!regex.test(this.form.email)) {
        // console.log('Invalid email address');
        this.$alert('Invalid email address. ', 'Error', {confirmButtonText: 'OK'});
        this.isValid = false;
        setTimeout(() => {this.isValid = true}, 1000);
      } else if (this.form.email !== this.myEmail) {
        // console.log('Email not found');
        this.$alert('Email not found. ', 'Error', {confirmButtonText: 'OK'});
        this.isValid = false;
        setTimeout(() => {this.isValid = true}, 1000);
      } else if (this.form.password !== this.myPassword) {
        // console.log('Invalid password');
        this.$alert('Invalid password. ', 'Error', {confirmButtonText: 'OK'});
        this.isValid = false;
        setTimeout(() => {this.isValid = true}, 1000);
      }
      // console.log('Welcome, Juan Carlos')
      // console.log(this.form.email);
      // console.log(this.form.password);
      // console.log(this.isValid);
      if (this.isValid) {
        this.ifValid()
      }
    },
    ifValid() {
      if (this.isValid) {
        this.$router.push('/home')
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .login {
    margin: 0;
  }

  .main-container {
    margin: 0 auto;
    border: 1px solid #bbb;
    width: 320px;
    min-height: 320px;
    border-radius: 12px;
    padding: 18px 12px;
    box-shadow: 0px 2px 20px 2px rgba(102,102,102,0.7);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: #ddd;
  }

  .branding {
    margin: 12px auto;
  }

  .branding h1 {
    font-size: 1.2em;
    color: #444;
  }

  .form {
    padding: 2px 6px;
    width: 280px;
  }

  .register {
    margin: 4px auto;
  }

  .register p {
    font-size: 14px;
  }

  .register a {
    color: teal;
    cursor: pointer;
  }

  .register a:hover {
    color: rgb(0, 100, 100);
    text-decoration: underline;
  }

</style>
