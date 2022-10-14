<template>
  <main>
    <SecPage />
    <section id="home">
    <!-- Select component -->

    <div class="b-header"><span>The modern Canberra buildings</span>
      <h3>Click any buildings to check details</h3>
    </div>
    <!-- This is the header in buildings page -->

    <div class="b-container">
      <h5 v-if="$fetchState.pending">Just a monent...</h5>
      <h5 v-else-if="$fetchState.error">Oops! Something went wrong...</h5>
      <!-- This is the error feedback -->

      <ul  v-for="building in buildings" :key="building.id" class="b-text">
        <li><a class="b-title"><NuxtLink :to="'/buildings/' + building.slug">
          {{  building.title.rendered  }}
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
            buildings: [],
        };
    },
  async fetch() {
    // This is how to fetch the API
    this.buildings = await fetch("http://cm.beneb.com/wp-json/wp/v2/buildings/").then((res) => res.json());
    },
    components: { SecPage }
}
</script>

<style>
  /* Home page standard */

  .b-header {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }
  
  .b-header span {
    font-family: futura-pt, sans-serif;
    font-size: 3rem;
    color: #2b2b2b;
  }
  
  .b-header h3 {
    font-family: futura-pt, sans-serif;
    font-size: 2rem;
    color: #2b2b2b;
  }
  
  .b-container {
    display: flex;
    margin: 3.7rem 5.6rem;
    flex-wrap: wrap;
  }
  
  .b-text {
    display: flex;
    flex-direction: column;
    margin: 5rem;
  }
  
  .b-text .b-title {
    font-family: futura-pt, sans-serif;
    font-size: 2rem;
    font-weight: 500;
    color: #272727;
  }

/* Responsive to over 1080p resolution */
@media (min-width:1920px) {
  .b-header span {
    font-size: 6rem;
  }
  
  .b-header h3 {
    font-size: 4rem;
  }
  
  .b-text {
    padding: 5rem;
  }
  
  .b-text .b-title {
    font-size: 5rem;
  }
}

/* Responsive to 720p resolution; can be responsive for tablet */
@media (min-width:800px) and (max-width:1280px){
  .b-header span {
    font-size: 2.5rem;
  }
  
  .b-header h3 {
    font-size: 1.6rem;
  }
  
}

/* Responsive to 720p lower resolution; can be responsive for mobile */
@media (max-width:799px){
  .b-header span {
    font-size: 1.8rem;
  }
  
  .b-header h3 {
    font-size: 1rem;
  }
  
  .b-text {
    padding: 5rem;
  }
  
  .b-text .b-title {
    font-size: 0.6rem;
  }
}
  </style>