<template>
  <main>
    <SecPage />
    <section id="home">
    <!-- Select component -->

    <div class="e-header"><span>The past Canberra Mordent Events</span>
    <h3>Click any events to see more information</h3>
    </div>
    <!-- This is the header in events page -->

    <div class="e-container">
      <h5 v-if="$fetchState.pending">Just a monent...</h5>
      <h5 v-else-if="$fetchState.error">Oops! Something went wrong...</h5>
      <!-- This is the error feedback -->

      <ul v-for="event in events" :key="event.id" class="e-text">
         <li><a class="e-title"><NuxtLink :to="'/events/' + event.slug">
         {{  event.title.rendered  }}
         </NuxtLink></a></li>
        </ul>
    </div>
    <!-- This is the container for each slug page -->

</section>

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
      events: [],
    }
   },
  async fetch() {
    // This is how to fetch the API
    this.events = await fetch('http://cm.beneb.com/wp-json/wp/v2/events/').then((res) =>
      res.json()
    )
  },
  components: { SecPage }
  }
</script>

<style>
  /* Home page standard */

  .e-header {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }
  
  .e-header span {
    font-family: futura-pt, sans-serif;
    font-size: 3rem;
    color: #2b2b2b;
  }
  
  .e-header h3 {
    font-family: futura-pt, sans-serif;
    font-size: 2rem;
    color: #2b2b2b;
  }
  
  .e-container {
    display: flex;
    margin: 3.7rem 5.6rem;
    flex-wrap: wrap;
  }
  
  .e-text {
    padding: 2rem;
    display: flex;
    flex-direction: column;
    margin: 5rem;
  }
  
  .e-text .e-title {
    font-family: futura-pt, sans-serif;
    font-size: 2rem;
    font-weight: 500;
    color: #272727;
  }

/* Responsive to over 1080p resolution */
@media (min-width:1920px) {
  .e-header span {
    font-size: 6rem;
  }
  
  .e-header h3 {
    font-size: 4rem;
  }
  
  .e-text {
    padding: 5rem;
  }
  
  .e-text .e-title {
    font-size: 5rem;
  }
}

/* Responsive to 720p resolution; can be responsive for tablet */
@media (min-width:800px) and (max-width:1280px){
  .e-header span {
    font-size: 2.5rem;
  }
  
  .e-header h3 {
    font-size: 1.6rem;
  }
  
}

/* Responsive to 720p lower resolution; can be responsive for mobile */
@media (max-width:799px){
  .e-header span {
    font-size: 1.8rem;
  }
  
  .e-header h3 {
    font-size: 1rem;
  }
  
  .e-text {
    padding: 5rem;
  }
  
  .e-text .e-title {
    font-size: 0.6rem;
  }
}
  </style>