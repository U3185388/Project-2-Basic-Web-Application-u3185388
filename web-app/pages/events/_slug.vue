<template>
    <main>
      <SecPage />
      <section id="detail">
        <div class="header"><span>{{event[0].title.rendered}}</span>
        <h3>{{event[0].acf.date}}</h3></div>

        <div class="text">
        <div class="content" v-html="renderedContent"></div>
      </div>

    </section>
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

  .header span {
    font-family: futura-pt, sans-serif;
    font-size: 3rem;
    color: #2b2b2b;
  }

  .header h3 {
    font-family: futura-pt, sans-serif;
    font-size: 2rem;
    color: #2b2b2b;
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
