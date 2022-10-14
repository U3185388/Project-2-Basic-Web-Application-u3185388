<template>
    <main>
      <SecPage />
        <!-- Select component -->

      <section id="detail">
        <!-- This is the content in slug page -->

        <div class="header"><span><a class="title">{{page[0].title.rendered}}</a></span></div>
        <!-- Publish each title in API -->

        <!-- Use this to filt the content -->
        <div v-html="renderedContent" class="content"></div>

     </section>
   </main>
  </template>
  
  
  <script>
import SecPage from '~/components/SecPage.vue';
    export default {
      // This is how to fetch the API
    async asyncData({ params }) {
        const page = await fetch(`http://cm.beneb.com/wp-json/wp/v2/pages/?slug=${params.slug}`).then((res) => {
            if (res.ok) {
                return res.json();
            }
            throw new Error(res.status);
        });
        // This is the ways to use filter in content
        const renderedContent = page[0].content.rendered;
        return { renderedContent, page };
    },
    components: { SecPage }
}


  </script>

  <style>
    /* Same style slug sheet */

#detail {
    background: linear-gradient(#7187c1, #fae383, #f26f75);
    display: flex;
    flex-direction: column;
    padding: 2.5rem;
    border-bottom: 0.1rem solid black;
  }

  .header {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }

  .header span .title{
    font-family: futura-pt, sans-serif;
    font-size: 5rem;
    color: black;
  }

 .content {
    font-family: futura-pt, sans-serif;
    font-size: 2rem;
    color: black;
  }

  .content p{
    font-size: 1.7rem;
  }

  .content img{
    display: flex;
    text-align: center;
  }

  /* Responsive to over 1080p resolution */
@media (min-width:1920px) {
  .header span .title{
    font-size: 10rem;
  }

  .content {
    font-size: 5rem;
  }

  .content p{
    font-size: 3rem;
  }

}

/* Responsive to 720p resolution; can be responsive for tablet */
@media (min-width:800px) and (max-width:1280px){
  .header span .title{
    font-size: 3rem;
  }

  .content {
    font-size: 1.5rem;
  }

  .content p{
    font-size: 1.2rem;
  }

  .content img{
    max-width: 60%;
  }

}

/* Responsive to 720p lower resolution; can be responsive for mobile */
@media (max-width:799px){
  .header span .title{
    font-size: 2.5rem;
  }

  .content {
    font-size: 1rem;
  }

  .content p{
    font-size: 0.1rem;
  }

  .content img{
    max-width: 30%;
  }

}
  </style>