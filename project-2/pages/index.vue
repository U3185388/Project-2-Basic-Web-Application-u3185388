<template>
  <div class="Home page bar">
    <h1>This is Home page</h1>
    <p><NuxtLink to="/building">Click here to buildings page</NuxtLink></p>
    <p><NuxtLink to="/events">Click here to see more</NuxtLink></p>
		<p v-if="$fetchState.pending">Just a monent...</p>
		<p v-else-if="$fetchState.error">Oops! Something went wrong...</p>
		<ul v-else>
			<li v-for="page in pages" :key="page.id">
				<NuxtLink :to="'/pages/' + page.slug">
					{{  page.title.rendered  }}
				</NuxtLink>
				: {{ page.date }}
			</li>
		</ul>
	</div>
</template>

<script>
  export default {
    layout : 'intro',
    data() {
 		  return {
 			  pages: [],
 		}
 	 },
 	async fetch() {
 		this.pages = await fetch('http://cm.beneb.com/wp-json/wp/v2/pages/').then((res) =>
 			res.json()
 		)
 	},
    }
</script>