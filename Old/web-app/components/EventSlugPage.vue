<template>
    <main class="container">
        <ul class="list-inline">
          <li><img class="logo" src="~assets/images/logo full.png"/></li>
          <li><NuxtLink to="/">Home</NuxtLink></li>
       <li v-for="event in events" :key="event.id">
           <NuxtLink :to="'/events/' + event.slug">
           {{  event.title.rendered  }}
           </NuxtLink>
       </li>
     </ul>
   </main>
  </template>

<script>
    export default {
      data() {
       return {
         events: [],
       }
      },
     async fetch() {
       this.events = await fetch('http://cm.beneb.com/wp-json/wp/v2/events/').then((res) =>
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