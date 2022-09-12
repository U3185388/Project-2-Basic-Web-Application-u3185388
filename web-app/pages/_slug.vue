<template>
    <main>
        <pre>
            {{ $data }}
        </pre>
     <div>
        <Nuxtlink to="/">Back to home page</Nuxtlink>
       <h3>Created by u3185388</h3>
     </div>
   </main>
  </template>
  
  
  <script>
    export default {
      async asyncData({ params, $axios }) {
        const event = await $axios.$get(`https://api.nuxtjs.dev/mountains/${params.id}`)
        return { event }
      }
    }
  </script>