<template>
    <main>
      <SecPage />
      <section id="detail">
        <div class="header"><span>{{page[0].title.rendered}}</span>
        <br>

        <!-- Use this to filt the content -->
        <div class="text">
        <div v-html="renderedContent" class="content"></div>
        </div>
      </div>

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

#detail {
    background: linear-gradient(#7187c1, #fae383, #f26f75);
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
    font-family: futura-pt, sans-serif;
    font-size: 3rem;
    color: black;
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

  .text .content {
    font-family: futura-pt, sans-serif;
    font-size: 1.5rem;
    font-weight: 300;
    color: black;
  }

  </style>