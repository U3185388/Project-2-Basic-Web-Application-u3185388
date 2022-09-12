<template>
  <main>
    <img class="logo" src="~assets/images/logo full.png"/>
    <h1>The past Canberra Mordent Events</h1>
    <p>Click any events to see more information</p>
   <h5 v-if="$fetchState.pending">Just a monent...</h5>
   <h5 v-else-if="$fetchState.error">Oops! Something went wrong...</h5>
   <ul v-else>
     <li v-for="event in events" :key="event.id">
       <span>
         <NuxtLink :to="event.slug">
         {{  event.title.rendered  }}
         </NuxtLink>
     </span>
     </li>
   </ul>
   <div>
     <h3>Created by u3185388</h3>
   </div>
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
    max-width: 5%;
  }

</style>