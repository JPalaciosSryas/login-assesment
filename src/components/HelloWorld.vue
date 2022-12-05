<template>
  <div class="login">
    <div class="main-container">
      <div class="branding">
        <h1>Sign Up to continue</h1>
      </div>
      <div class="form">
          <el-form ref="form" :model="form">
            <el-form-item label="Username">
              <el-input v-model="form.username"></el-input>
            </el-form-item>
            <el-form-item label="Password">
              <el-input type="password" v-model="form.password" auto-complete="off"></el-input>
            </el-form-item>
            <el-form-item>
              <el-button type="primary" @click="onSubmit">Sign Up</el-button>
              <el-button>Cancel</el-button>
            </el-form-item>
          </el-form>
          <div class="register">
            <p>New over here? <a type="primary" href="/about">Register</a></p> 
          </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      form: {
        username: '',
        password: ''
      },
      username: 'juankapalacios97',
      password: 'jcpc8438'
    }
  },
  methods: {
    onSubmit() {
      
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .login {
    background-color: #eee;
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



</style>
