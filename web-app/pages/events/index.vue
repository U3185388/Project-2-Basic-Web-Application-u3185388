<template>
    <main>
      <SecPage />
      <section id="home">

      <div class="header"><span>The past Canberra Mordent Events</span>
      <h3>Click any events to see more information</h3>
    </div>

    <div class="container">
     <h5 v-if="$fetchState.pending">Just a monent...</h5>
     <h5 v-else-if="$fetchState.error">Oops! Something went wrong...</h5>
       <ul v-for="event in events" :key="event.id" class="text">
           <li><a class="title"><NuxtLink :to="'/events/' + event.slug">
           {{  event.title.rendered  }}
           </NuxtLink></a></li>
          </ul>
      </div>
  </section>

     <div>
      <h5>Created by u3185388</h5>
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