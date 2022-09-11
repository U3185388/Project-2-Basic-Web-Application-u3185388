<template>
	<div>
		<p v-if="$fetchState.pending">Just a monent...</p>
		<p v-else-if="$fetchState.error">Oops! Something went wrong...</p>

		<ul v-else>
			<li v-for="event in events" :key="event.id">
				<NuxtLink :to="'/events/' + event.slug">
					{{  event.title.rendered  }}
				</NuxtLink>
				: {{ event.acf.year }}
			</li>
		</ul>

	</div>
</template>


<script>
  export default {
    data() {
 		return {
 			events: [],
 		}
 	 },
 	async fetch() {
 		this.events = await fetch('http://cm.beneb.com/wp-json/wp/v2/events/').then((res) =>
 			res.json()
 		)
 	},
   }
</script>