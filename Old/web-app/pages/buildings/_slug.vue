<template>
  <main>
    <SecPage />
    <!-- Select component -->

    <section id="detail">
    <!-- This is the content in slug page -->

      <div class="header"><span>{{building[0].title.rendered}}</span></div>
      <br>
      <!-- Publish the title in each slug -->
      <div class="text">
      <div class="content"><p>Located at {{building[0].acf.location}}
      <!-- Publish the location in each slug -->
      
      <br>Built in {{building[0].acf.year}}</p></div> 
      <!-- Publish the year in each slug -->

      <div class="arc">
      <p>Architect: {{building[0].acf.architect[0].name}}</p></div>
      <!-- Publish the Architect in each slug -->

    </div>
  </section>
 
  </main>
</template>


<script>
import SecPage from '~/components/SecPage.vue';
  export default {
  async asyncData({ params }) {
    // This is how to fetch the API
      const building = await fetch(`http://cm.beneb.com/wp-json/wp/v2/buildings/?slug=${params.slug}`).then((res) => {
          if (res.ok) {
              return res.json();
          }
          throw new Error(res.status);
      });
      // This is the ways to use filter in content
      const renderedContent = building[0].content.rendered;
      return { renderedContent, building };
  },
  components: { SecPage }
}

</script>

<style>

  .header span {
    font-family: futura-pt, sans-serif;
    font-size: 3rem;
    color: #2b2b2b;
  }

  .text .content {
    font-family: futura-pt, sans-serif;
    font-size: 1.5rem;
    font-weight: 300;
    color: black;
  }

  .text .arc {
    font-family: futura-pt, sans-serif;
    font-size: 1.7rem;
    font-weight: 300;
    color: black;
  }

  </style>