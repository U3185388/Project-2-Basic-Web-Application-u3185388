<template>
    <main>
      <SecPage />
        <div><h1>{{event[0].title.rendered}}</h1>
        <br>
        <h3>{{event[0].acf.date}}</h3>

        <!-- Use this to filt the content -->
        <div class="text-center" v-html="renderedContent"></div>


      </div>
     <div>
       <h3>Created by u3185388</h3>
     </div>
   </main>
  </template>
  
  
  <script>
    export default {
	  async asyncData({ params }) {
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