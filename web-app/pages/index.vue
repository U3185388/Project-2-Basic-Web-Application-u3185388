<template>
    <main>
      <HomePage />
      <!-- <ul>
       <li v-for="page in pages" :key="page.id">
           <NuxtLink :to="'/pages/' + page.slug">
           {{  page.title.rendered  }}
           </NuxtLink>
           </li>
          </ul> -->
    <ul>
          <li><NuxtLink to="/about">About us</NuxtLink></li>
          <li><NuxtLink to="/events">The past Canberra Mordent Events</NuxtLink></li>
          <li><NuxtLink to="/buildings">The modern Canberra buildings</NuxtLink></li>    
          <li><NuxtLink to="/links">links</NuxtLink></li>
          <li><NuxtLink to="/videos">Videos</NuxtLink></li>
          <li><NuxtLink to="/top-20-mid-late-century-modern-buildings￼">Top 20 mid late century modern buildings</NuxtLink></li>
          <li><NuxtLink to="/partners">Partners</NuxtLink></li>
          <li><NuxtLink to="/error">Click here to see if error</NuxtLink></li>
    </ul>
     <div>
       <h5>Created by u3185388</h5>
     </div>
   </main>
  </template>
  
  
  <script>
import HomePage from '~/components/HomePage.vue';
   export default {
    data() {
        return {
            pages: [],
        };
    },
    async fetch() {
        this.pages = await fetch("http://cm.beneb.com/wp-json/wp/v2/pages/").then((res) => res.json());
    },
    components: { HomePage }
}
  </script>