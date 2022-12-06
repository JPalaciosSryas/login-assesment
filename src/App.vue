<template>
  <div id="app">
      <el-header class="header">
        <div class="branding">
          <h1>Holamundo</h1>
        </div>
        <el-breadcrumb class="nav-links" separator="|">
          <el-breadcrumb-item :to="{ path: '/' }">Home</el-breadcrumb-item>
          <el-breadcrumb-item :to="{ path: '/register' }">Register</el-breadcrumb-item>
        </el-breadcrumb>
      </el-header>
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <div class="view">
      <router-view/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #eee;
  color: #666;
}

.el-breadcrumb__inner, .is-link {
  color: #eee;
}

.header {
  background-color: #fff;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.header h1 {
  font-size: 1.5em;
  color: #333;
}

.nav-links el-link {
  color: #eee;
}

.view {
  padding: 54px 0 54px;
  background-image: url('@/assets/background.jpg');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  min-height: 74.5vh;
}

</style>
