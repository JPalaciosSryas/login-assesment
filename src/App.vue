<template>
  <div id="app">
      <el-header class="header">
        <div class="branding">
          <h1>Holamundo</h1>
        </div>
        <el-breadcrumb class="nav-links" separator="|">
          <el-breadcrumb-item :to="{ path: '/' }">Home</el-breadcrumb-item>
          <el-breadcrumb-item :to="{ path: '/about' }">About</el-breadcrumb-item>
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

.header {
  background-color: rgb(40, 95, 255);
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.header h1 {
  font-size: 1.5em;
  color: #eee;
}

.nav-links el-link {
  color: #eee;
}

.view {
  padding: 54px 0 54px;
}

.footer {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
  height: 18vh;
  margin: 0 auto;
  background-color: #666;
  color: #eee;
}

.footer h1 {
  font-size: 16px;
  margin-bottom: 6px;
}

.footer p {
  font-size: 12px;
  margin: 2px;
}

</style>
