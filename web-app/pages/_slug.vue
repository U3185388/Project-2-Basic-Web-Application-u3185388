<template>
    <main>
      <SlugPage />
        <div><h1>{{page[0].title.rendered}}</h1>
        <br>

        <!-- Use this to filt the content -->
        <div v-html="renderedContent"></div>


      </div>
     <div>
       <h5>Created by u3185388</h5>
     </div>
   </main>
  </template>
  
  
  <script>
import SlugPage from '~/components/SlugPage.vue';
    export default {
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
    components: { SlugPage }
}


  </script>