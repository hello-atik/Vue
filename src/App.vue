<template>
  <div>
    <div id="nav">
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
      <router-link to="/counter">Counter</router-link>
      <router-link to="/contacts">Contacts</router-link>
    </div>
    <div class="view">
      <router-view />
    </div>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  text-align: center;
  color: #2c3e50;
  margin: 0px;
  padding: 0px;
}

#nav {
  padding: 30px;
  border-radius: 5px;
  background: rgb(222, 222, 222);
}

#nav a {
  margin: 0px 5px;
  padding: 10px 15px;
  border-radius: 5px;

  color: #2c3e50;
  background: #eeeeee;
  box-shadow: 0px 1px 2px 2px rgba(0, 0, 0, 0.3);

  font-size: 18px;
  font-weight: bold;
  text-decoration: none;
  font-family: "Arial Rounded MT";
}
#nav a:hover {
  background: #dddddd;
}

#nav a.router-link-exact-active {
  color: #42b983;
  background: #000;
}

.view {
  display: flex;
  justify-content: center;

  width: 100%;
  height: auto;
  min-height: 600px;
  padding: 10px;
  margin-top: 20px;

  border-radius: 5px;
  box-sizing: border-box;
  border: 2px solid grey;
}
</style>
