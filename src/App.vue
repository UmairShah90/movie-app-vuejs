<template>
  <header>
    <router-link to="/">
    <h1>vue<span>movies</span></h1>
    
    </router-link> 
   
  </header>
  <main>
    
  <router-view/>
  </main>
</template>



<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  text-transform: capitalize;
  font-family: 'Fira Sans', sans-serif;
}
a{
  text-decoration: none;
}
body{
  background: #b8bbbd;
}
header{
  background: #2c3d4e;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 10px 16px;
  box-shadow: 0 0 0 6px rgba(0,0,0,0.1);
  h1{
    
    color: #428883;
    font-size: 28px;
    span{
      color:#fff;
    }

  }
}
</style>
