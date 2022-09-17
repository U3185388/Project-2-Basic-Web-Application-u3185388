<template>
    <main>
      <SecPage />
      <section id="home">
      
      <div class="header"><span>The modern Canberra buildings</span>
      <h3>Click any buildings to check details</h3></div>  

      <div class="container">
     <h5 v-if="$fetchState.pending">Just a monent...</h5>
     <h5 v-else-if="$fetchState.error">Oops! Something went wrong...</h5>
     <ul v-else class="text">
       <li v-for="building in buildings" :key="building.id">
          <a class="title"><NuxtLink :to="'/buildings/' + building.slug">
           {{  building.title.rendered  }}
           </NuxtLink></a>
       </li>
     </ul>
    </div>

    <div>
      <h5>Create by u318533</h5>
    </div>

    </section>
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

<style>

#home {
    display: flex;
    flex-direction: column;
    padding: 40px;
    border-bottom: 1px solid black;
  }

  .header {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }

  .header span {
    font-family: futura-pt, sans-serif;
    font-size: 3rem;
    color: #2b2b2b;
  }

  .header h3 {
    font-family: futura-pt, sans-serif;
    font-size: 2rem;
    color: #2b2b2b;
  }

  .container {
    display: flex;
    margin: 60px 90px;
    flex-wrap: wrap;
  }

  .text {
    padding: 30px;
    display: flex;
    flex-direction: column;
  }

  .text .title {
    font-family: futura-pt, sans-serif;
    font-size: 2rem;
    font-weight: 500;
    color: #272727;
  }

</style>