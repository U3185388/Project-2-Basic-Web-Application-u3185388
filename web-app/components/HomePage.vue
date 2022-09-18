<template>
    <main>
        <!-- This is the navigation bar in home page -->

        <nav class="nav">
        <div class="logo"><img src="~assets/images/logo full.png"/></div>
        <!-- Logo on the left side -->>
        
        <div class="menubar"><h1>Welcome to Canberra Modern</h1></div>
        </nav>
        <!-- No need function in home page; So as welcome -->

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
   font-family: futura-pt, sans-serif;
   font-size: 1.5rem;
   display: flex;
   justify-content: space-between;
   color: white;
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
   font-size: 2.5rem;
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
   font-size: 1.1rem;
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
  font-size: 0.7rem;
 }

}

</style>