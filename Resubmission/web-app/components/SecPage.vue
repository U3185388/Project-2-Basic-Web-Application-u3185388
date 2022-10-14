<template>
    <main>
    <!-- This is the navigation bar in slug page -->

        <nav class="nav">
        <div class="logo"><img src="~assets/images/logo full.png"/></div>
        <!-- Logo on the left side -->

        <div class="menubar">
            <ul class="bar">
                <li><NuxtLink to="/"><a>Home</a></NuxtLink></li>
                <li><NuxtLink to="/events"><a>Events</a></NuxtLink></li>
                <li><NuxtLink to="/buildings"><a>Buildings</a></NuxtLink></li>    
            </ul>
        </div>
        <!-- Lead users swtich to each page they wish; Homepage in condensed -->

        </nav>
   </main>
</template>

<style>

    /* Create based on 1080p resolution */
 
   .logo img{
     margin-bottom: 40%;
     max-width: 6rem;
   }
 
   .nav{
     height: 5rem;
     display: flex;
     align-items: center;
     justify-content: space-between;
     padding-top: 2.5rem;
     padding-left: 5%;
     padding-right: 40%;
     background-color: black;
     background-size: cover;
     background-position: center;
   }
 
   .menubar{
     margin-top: -5%;
     margin-right: -70%;
   }
 
   .bar{
      font-family: futura-pt, sans-serif;
      font-size: 1.5rem;
      display: flex;
      justify-content: space-between;
  }

  nav ul li{
    list-style-type: none;
    padding: 1rem 1.5rem;
  }

  nav ul li a{
    color: white;
    text-decoration: none;
    font-weight: bold;
  }
 
 /* Responsive to over 1080p resolution */
   @media (min-width:1920px) {
     .logo img{
     max-width: 10rem;
   }
 
   .nav{
     height: 10rem;
   }
 
     .menubar{
     margin-top: -3%;
   }
 
   .bar{
      font-family: futura-pt, sans-serif;
      font-size: 2.25rem;
      display: flex;
      justify-content: space-between;
  }

  nav ul li{
    list-style-type: none;
    padding: 2rem 3rem;
  }
     
 }
 
 /* Responsive to 720p resolution; can be responsive for tablet */
 @media (min-width:800px) and (max-width:1280px){
   .logo img{
     max-width: 6rem;
   }
 
   .nav{
     height: 6rem;
   }
 
   .menubar{
     margin-top: -7%;
     margin-right: -70%;
   }
 
   .bar{
      font-family: futura-pt, sans-serif;
      font-size: 1rem;
      display: flex;
      justify-content: space-between;
  }
 
 }
 
 /* Responsive to 720p lower resolution; can be responsive for mobile */
 @media (max-width:799px){
   .logo img{
     max-width: 5rem;
   }
 
   .nav{
     height: 3rem;
   }
 
   .menubar{
     margin-top: -10%;
     margin-right: -40%;
   }
 
   .bar{
      font-family: futura-pt, sans-serif;
      font-size: 0.5rem;
      display: flex;
      justify-content: space-between;
  }
 
 }
 
 </style>