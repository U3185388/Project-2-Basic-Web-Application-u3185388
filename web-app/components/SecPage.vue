<template>
    <main>
      <nav class="nav">
        <div><img class="logo" src="~assets/images/logo full.png"/></div>
      <div class="menubar"><ul class="bar">
        <li><NuxtLink to="/">Home</NuxtLink></li>
        <li><NuxtLink to="/about">About</NuxtLink></li>
        <li><NuxtLink to="/events">Events</NuxtLink></li>
        <li><NuxtLink to="/buildings">Buildings</NuxtLink></li>    
        <li><NuxtLink to="/links">links</NuxtLink></li>
        <li><NuxtLink to="/videos">Videos</NuxtLink></li>
        <li><NuxtLink to="/top-20-mid-late-century-modern-buildings￼">Top 20 mid late century modern buildings</NuxtLink></li>
        <li><NuxtLink to="/partners">Partners</NuxtLink></li>
     </ul></div>
    </nav>
   </main>
  </template>

<style>
  .logo{
      max-width: 100px;
  }

  .nav{
    width: 100%;
    background-color: black;
    background-size: cover;
    background-position: center;
  }

  .menubar{
    margin-top: 25px;
  }

  .bar{
      font-size: 20px;
      display: flex;
      justify-content: space-between;
  }

  nav ul li{
    list-style-type: none;
    padding: 15px 20px;
  }

  nav ul li a{
    color: white;
    text-decoration: none;
    font-weight: bold;
  }
</style>