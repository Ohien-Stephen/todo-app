<template>
  <div id="app">
    <header>
      <div class="header-div">
            <a class="logo">
              <router-link to="/">{{msg}}</router-link>
            </a>
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

<script>
export default {
  data(){
    return{
      msg:"Todo App",
    }
  }
}
</script>

<style lang="scss">
*{
  margin:0;
  padding: 0;
}
body{
  box-sizing: border-box;
}
#app {
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: 1em;
}
header{
  background-color: rgb(125, 4, 238);
  color:white;
  width: 100%; 

    .header-div{
      width: 80%;   
      margin:0 auto; 
      padding: 20px;
      display: flex;
      justify-content: space-between;

      @media only screen and(max-width: 500px){
        width:90%;
      }
          a{    
              color:inherit;
              text-decoration: none;
          }
          .logo {
              font-weight: bold;
              font-size: 25px;
          }
  }
}
#wrapper{
  width:50%;
  margin: 1em auto;
  border: 1px solid gray;
  padding: 1em;
  height: 70vh;

  @media only screen and(max-width: 900px){
    width:80%;
  }

  @media only screen and(max-width: 500px){
    width:90%;
  }
}
</style>
