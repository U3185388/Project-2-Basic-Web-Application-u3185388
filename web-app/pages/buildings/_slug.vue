<template>
    <main>
      <SlugPage />
        <div><h1>{{building[0].title.rendered}}</h1>
        <br>
        <p>Located at {{building[0].acf.location}}
        <br>Built in {{building[0].acf.year}}</p>
        <br>
        <p>Architect: {{building[0].acf.architect[0].name}}</p>
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
    components: { SlugPage }
}


  </script>