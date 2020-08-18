<template>
  <div id="app">
    <header>
      <div class="header-div">
            <a class="logo">Todo App</a>
            <div id="nav">
              <router-link to="/">Home</router-link> |
              <router-link to="/about">About</router-link>
            </div>
      </div>
    </header>
    <div id="wrapper">
      <router-view/>
    </div>
  </div>
</template>

<style lang="scss">
body{
  box-sizing: border-box;
  margin:0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
header{
  background-color: rgb(125, 4, 238);
  color:white;
  padding: 20px;
  width: 100%; 

    .header-div{
      width: 90%;   
      margin:0 auto; 
      display: flex;
      justify-content: space-between;

        a{    
            color:inherit;
            text-decoration: none;
        }
      .logo {
          font-weight: bold;
      }
  }
}
#wrapper{
  width:90%;
  margin: 1em auto;
  height: 75vh;
  border: 1px solid gray;
}
</style>
