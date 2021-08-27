<template>
  <div id="app">
    <div id="nav">
      <router-link to="/"><h1>K<strong>3</strong>y Frame</h1></router-link>
    </div>
    <router-view/>
  </div>
</template>

<style>
*{
}
body{

  background-image: url('/kf.gif');
}
#app {
  font-family: "Roboto Mono", monospace;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
}
h1{
	font-weight: 200;
}
textarea{
	background-color: #333;
	color: white;
	width: 70%;
}

#nav {
  padding: 30px;
}

#nav a {
  color: #cfcf54;
}

#nav a.router-link-exact-active {
  color: #cfcf54;
  font-weight: 300;
  text-decoration: none;
}
button{
	margin: 20px;
	padding: 10px;
	border-radius: 5px;
	border: none;
	color: white;
	background-color: #333;
	transition: all .2s;
}
button:hover{
	background-color: #444;
}
button:active{
	background-color: #555;
}
</style>
