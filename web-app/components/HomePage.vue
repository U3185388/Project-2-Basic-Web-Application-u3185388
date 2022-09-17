<template>
    <main>
     <nav class="nav">
        <img class="logo" src="~assets/images/logo full.png"/>
        <div class="menubar"><h1>Welcome to Canberra Modern</h1></div>
     </nav>
   </main>
  </template>

<style>

    .nav{
    width: 100%;
    background-color: black;
    background-size: cover;
    background-position: center;
  }

  .nav .logo{
        max-width: 100px;
    }

  .menubar{
    margin-top: 25px;
  }

  h1{
      font-family: futura-pt, sans-serif;
      display: flex;
      margin-left: 500px;
      color: white;
  }

  @media screen and (min-width:720px) and (max-width: 1280px) {
    .logo{
      max-width: 70px;
    }
    
    .nav{
    width: 100%;
  }

  h1{
      margin-left: 230px;
      font-size: 25px;
  }

  }

  @media screen and (min-width:480px) and (max-width: 719px) {
    .logo{
      max-width: 50%;
    }

  h1{
      margin-left: 100px;
      font-size: 20px;
  }

  @media screen and (max-width: 479px) {
    .logo{
        max-width: 30%;
    }

    .nav{
    width: 100%;
    height: 10%;
  }

  .menubar{
    margin-top: 5px;
  }

  h1{
      font-size: 5px;
      font-family: futura-pt, sans-serif;
      display: flex;
      margin-left: 50px;
      color: white;
  }

}

}


  </style>