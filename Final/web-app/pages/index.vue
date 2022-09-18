<template>
  <main>
    <HomePage />
    <!-- Select component -->

    <section id="home">
      <!-- This is the content in home page -->
      <!-- Each container carries links to each page -->
      
    <div class="container"> 
      <div class="text">
        <span><a class="title"><NuxtLink to="/about">About us</NuxtLink></a></span>
        <p>What is so special about Canberra?
        <br>Who are Canberra Modern?
        <br>Our Patron</p>
      </div>
    </div>

    <div class="container"> 
      <div class="text">
        <span><a class="title"><NuxtLink to="/events">Events</NuxtLink></a></span>
        <p>The past Canberra Mordent events.
        <br>The Other Moderns
        <br>The Cocktail Hour Lifestyle...</p>
      </div>
    </div>
       <!-- This container leads to Event API page -->

    <div class="container"> 
      <div class="text">
        <span><a class="title"><NuxtLink to="/buildings">Buildings</NuxtLink></a></span>
        <p>The Modern Canberra Buildings.
        <br>Swinger Hill Housing
        <br>High Court of Australia...</p>
      </div>
    </div>
       <!-- This container leads to Building API page -->

    <div class="container"> 
      <div class="text">
        <span><a class="title"><NuxtLink to="/links">links</NuxtLink></a></span>
        <p>Canberra House
        <br>Tim Ross
        <br>Darren Bradley Blog...</p>
      </div>
    </div>

    <div class="container"> 
      <div class="text">
        <span><a class="title"><NuxtLink to="/videos">Videos</NuxtLink></a></span>
        <p>Manning Clark House Virtual Tour
        <br>Growing Up Modern Panel_Giralang Primary School
        <br>In Conversation with Ian Wong....</p>
      </div>
    </div>

    <div class="container"> 
      <div class="text">
        <span><a class="title"><NuxtLink to="top-20-mid-late-century-modern-buildings￼">Top 20</NuxtLink></a></span>
        <p>20 buildings might seem a lot, but in a city that grew up in the mid-century period that 
        <br>showcases work from some of Australia’s most renowned architects, it is almost impossible to
        <br>narrow the list to just 20! While many on the list are obvious and iconic, we also wanted to...</p>
      </div>
    </div>

    <div class="container"> 
      <div class="text">
        <span><a class="title"><NuxtLink to="/partners">Partners</NuxtLink></a></span>
        <p>University House
        <br>Design Institute of Australia
        <br>Australia ICOMOS...</p>
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
      // This is how to fetch the API
      this.pages = await fetch("http://cm.beneb.com/wp-json/wp/v2/pages/").then((res) => res.json());
  },
  components: { HomePage }
}
</script>

<style>
/* blog style sheet in home page; This is used on 1080p resolution */
#home {
  background: linear-gradient(#7187c1, #fae383, #f26f75);
  display: flex;
  flex-direction: column;
  padding: 2.5rem;
  border-bottom: 0.1rem solid black;
}

.container {
  display: flex;
  margin: 3.75rem 5.6rem;
  flex-wrap: wrap;
}

.text {
  padding: 2rem;
  display: flex;
  flex-direction: column;
}

.text span .title {
  font-family: futura-pt, sans-serif;
  font-size: 3rem;
  color: #272727;
}

.text p {
  font-family: futura-pt, sans-serif;
  color: #292929;
  font-size: 2rem;
  margin: 1.25rem 0.3rem;
}

.text a{
  color: #0f0f0f;
}

/* Responsive to over 1080p resolution */
@media (min-width:1920px) {
.container {
  margin: 3.75rem 5.6rem;
  flex-wrap: wrap;
}

.text span .title {
  font-size: 5rem;
}

.text p {
  font-family: futura-pt, sans-serif;
  color: #292929;
  font-size: 4.5rem;
  margin: 1.5rem 0.5rem;
}

}

/* Responsive to 720p resolution; can be responsive for tablet */
@media (min-width:800px) and (max-width:1280px){
.container {
  margin: 3.75rem 5.6rem;
}

.text span .title {
  font-size: 2rem;
}

.text p {
  font-size: 1.2rem;
  margin: 1.25rem 0.3rem;
}

}

/* Responsive to 720p lower resolution; can be responsive for mobile */
@media (max-width:799px){
  #home {
  padding: 1rem;
}

.text span .title {
  font-size: 1.4rem;
  color: #272727;
}

.text p {
  font-size: 1.2rem;
  margin: 0.5rem 0.01rem;
}

}

</style>