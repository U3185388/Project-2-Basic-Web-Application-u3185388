<!-- this component returns a list of all the buildings by year -->
<template>
	<div>
		<!-- these would show while the data loads or if an error -->
		<p v-if="$fetchState.pending">Just a monent...</p>
		<p v-else-if="$fetchState.error">Oops! Something went wrong...</p>

		<ul v-else>
			<!-- this is a for loop, it just loops through the list of buildings returned from the API -->
			<li v-for="building in buildings" :key="building.id">
				<!-- now make a link for each item -->
				<!-- <NuxtLink :to="building.slug"> -->
				<NuxtLink :to="'/buildings/' + building.slug">
					<!-- return the rendered title -->
					{{  building.title.rendered  }}
				</NuxtLink>
				<!-- now show me the building year -->
				: {{ building.acf.location }}
				: {{ building.acf.year }}
			</li>
		</ul>

	</div>
</template>


<script>
  export default {
    data() {
 		return {
 			buildings: [],
 		}
 	 },
 	async fetch() {
 		this.buildings = await fetch('http://cm.beneb.com/wp-json/wp/v2/buildings/').then((res) =>
 			res.json()
 		)
 	},
   }
</script>