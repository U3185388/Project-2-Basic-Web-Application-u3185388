<template>
    <main>
      <SlugPage />
      <h1>The modern Canberra buildings</h1>
      <p>Click any buildings to see more information</p>
     <h5 v-if="$fetchState.pending">Just a monent...</h5>
     <h5 v-else-if="$fetchState.error">Oops! Something went wrong...</h5>
     <ul v-else>
       <li v-for="building in buildings" :key="building.id">
         <span>
           <NuxtLink :to="'/buildings/' + building.slug">
           {{  building.title.rendered  }}
           </NuxtLink>
       </span>
       </li>
     </ul>
     <div>
      <h5>Created by u3185388</h5>
     </div>
   </main>
  </template>
  
  
  <script>
import SecPage from '~/components/SecPage.vue';
   export default {
    data() {
        return {
            buildings: [],
        };
    },
    async fetch() {
        this.buildings = await fetch("http://cm.beneb.com/wp-json/wp/v2/buildings/").then((res) => res.json());
    },
    components: { SecPage }
}
  </script>