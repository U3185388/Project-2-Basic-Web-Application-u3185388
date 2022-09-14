<template>
    <main class="container">
        <ul class="list-inline">
          <li><img class="logo" src="~assets/images/logo full.png"/></li>
          <li><NuxtLink to="/">Home</NuxtLink></li>
       <li v-for="building in buildings" :key="building.id">
           <NuxtLink :to="'/buildings/' + building.slug">
           {{  building.title.rendered  }}
           </NuxtLink>
       </li>
     </ul>
   </main>
  </template>

<script>
  export default {
    data() {
     return {
       buildings: [],
     }
    },
   async fetch() {
     this.buildings = await fetch('http://cm.beneb.com/wp-json/wp/v2/buildings/').then((res) =>
       res.json()
     )
   },
   }
 </script>

<style>
    .logo{
        max-width: 100px;
    }
  </style>