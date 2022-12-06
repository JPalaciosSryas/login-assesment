<template>
    <div class="login">
      <div class="main-container">
        <div class="branding">
          <h1>Registering zone</h1>
        </div>
        <div class="form">
            <el-form ref="form" :model="form">
              <el-form-item label="First name">
                <el-input id="name" v-model="form.name"></el-input>
              </el-form-item>
              <el-form-item label="Last name">
                <el-input id="lastName" v-model="form.lastName"></el-input>
              </el-form-item>
              <el-form-item label="Date of birth">
                <el-date-picker id="dateOfBirth" type="date" v-model="form.dateOfBirth" placeholder="Select your date of birth"></el-date-picker>
              </el-form-item>
              <el-form-item label="E-mail">
                <el-input id="email" type="email" v-model="form.email"></el-input>
              </el-form-item>
              <el-form-item label="Your new password">
                <el-input id="password" type="password" v-model="form.password" auto-complete="off"></el-input>
              </el-form-item>
              <el-form-item>
                <el-button type="primary" @click="onSubmit">Create</el-button>
                <el-button @click="$router.push('/')">Cancel</el-button>
              </el-form-item>
            </el-form>
            <div class="login">
              <p>Already having an account? <a type="primary" @click="$router.push('/')">Log In</a></p> 
            </div>
          </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'Register',
    data() {
      return {
        form: {
          name: '',
          lastName: '',
          dateOfBirth: '',
          email: '',
          password: ''
        }
      }
    },
    methods: {
      onSubmit() {
        const regex = new RegExp('[a-z0-9]+@[a-z]+\.[a-z]{2,3}');
        console.log(this.form.name);
        console.log<(this.form.lastName);
        console.log(this.form.dateOfBirth)
        regex.test(this.form.email) ? console.log(this.form.email) : console.log('Invalid email address');
        console.log(this.form.password);
        this.$router.push('/');
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
      background-color: #ddd;
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

    .el-date-editor.el-input {
      width: 280px !important;
    }
  
    #dateOfBirth {
      justify-self: flex-start;
    }

    .login {
      margin: 4px auto;
    }
  
    .login p {
      font-size: 14px;
    }
  
    .login a {
      color: teal;
      cursor: pointer;
    }

    .login a:hover {
      color: rgb(0, 100, 100);
      text-decoration: underline;
    }
  
  </style>