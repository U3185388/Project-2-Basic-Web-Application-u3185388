<template>
    <main>
      <HomePage />

      <section id="home">
      <div class="container"> 
        <div class="text">
          <span><a class="title"><NuxtLink to="/about">About us</NuxtLink></a></span>
          <p>What is so special about Canberra?
          <br>Who are Canberra Modern?
          <br>Our Patron</p>
          <a>Click to read more</a>
        </div>
      </div>

      <div class="container"> 
        <div class="text">
          <span><a class="title"><NuxtLink to="/events">Events</NuxtLink></a></span>
          <p>The past Canberra Mordent events.
          <br>The Other Moderns
          <br>The Cocktail Hour Lifestyle...</p>
          <a>Click to read more</a>
        </div>
      </div>

      <div class="container"> 
        <div class="text">
          <span><a class="title"><NuxtLink to="/buildings">Buildings</NuxtLink></a></span>
          <p>The Modern Canberra Buildings.
          <br>Swinger Hill Housing
          <br>High Court of Australia...</p>
          <a>Click to read more</a>
        </div>
      </div>

      <div class="container"> 
        <div class="text">
          <span><a class="title"><NuxtLink to="/links">links</NuxtLink></a></span>
          <p>Canberra House
          <br>Tim Ross
          <br>Darren Bradley Blog...</p>
          <a>Click to read more</a>
        </div>
      </div>

      <div class="container"> 
        <div class="text">
          <span><a class="title"><NuxtLink to="/videos">Videos</NuxtLink></a></span>
          <p>Manning Clark House Virtual Tour
          <br>Growing Up Modern Panel_Giralang Primary School
          <br>In Conversation with Ian Wong....</p>
          <a>Click to read more</a>
        </div>
      </div>

      <div class="container"> 
        <div class="text">
          <span><a class="title"><NuxtLink to="/top-20-mid-late-century-modern-buildings￼">Top 20</NuxtLink></a></span>
          <p>20 buildings might seem a lot, but in a city that grew up in the mid-century period that 
          <br>showcases work from some of Australia’s most renowned architects, it is almost impossible to
          <br>narrow the list to just 20! While many on the list are obvious and iconic, we also wanted to...</p>
          <a>Click to read more</a>
        </div>
      </div>

      <div class="container"> 
        <div class="text">
          <span><a class="title"><NuxtLink to="/partners">Partners</NuxtLink></a></span>
          <p>University House
          <br>Design Institute of Australia
          <br>Australia ICOMOS...</p>
          <a>Click to read more</a>
        </div>
      </div>

      <div>
        <h5>Create by u3185388</h5>
      </div>

    </section>
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

<style>
  /* blog styly sheet */

  #home {
    background: linear-gradient(#7187c1, #fae383, #f26f75);
    display: flex;
    flex-direction: column;
    padding: 40px;
    border-bottom: 1px solid black;
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

  .text p {
    font-family: futura-pt, sans-serif;
    color: #292929;
    font-size: 1.2rem;
    margin: 20px 5px;
  }

  .text a{
    color: #0f0f0f;
  }

</style>