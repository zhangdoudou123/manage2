<template>
  <div id="app">
    <div class="nva ">
      <hr>
      <strong class="item">用户管理系统</strong>
      <router-link to="/" class="aaa">主页</router-link>|
      <router-link to="/About" class="aaa">关于</router-link>
      <router-link to="/Add" class="navbar-right">添加用户</router-link>
      <hr>
    </div>
    


    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #0099ff;
}
.nva{
  background: #2c3e50;
  width: 100%;
  height: 100px;
}
.item{
  color:whitesmoke;
  font-size: 30px;
  display: flex;
  float:inline-start;
  
}
.aaa{
  margin: 10px;
  font-size: 20px;
  color:white;
}
.navbar-right{
  margin-left: 100px;
  color:rgb(116, 105, 105);
}
</style>
 