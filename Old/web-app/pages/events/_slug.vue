<template>
  <main>
    <SecPage />
    <!-- Select component -->
    
    <section id="detail">
    <!-- This is the content in slug page -->
      
      <div class="header"><span>{{event[0].title.rendered}}</span>
      <h3>{{event[0].acf.date}}</h3></div>
      <!-- Publish each title in API -->

      <!-- Use this to filt the content -->
      <div class="text">
      <div class="content" v-html="renderedContent"></div>
      </div>

  </section>
 </main>
</template>


<script>
  export default {
    async asyncData({ params }) {
    // This is how to fetch the API
    const event = await fetch(
      `http://cm.beneb.com/wp-json/wp/v2/events/?slug=${params.slug}`
    ).then((res) => {
      if (res.ok) {
        return res.json()
      }
      throw new Error(res.status)
    })
    // This is the ways to use filter in content
    const renderedContent = event[0].content.rendered;
    return {renderedContent, event}
  },
}

</script>