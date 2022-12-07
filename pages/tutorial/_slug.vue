<script>
  export default {
    async asyncData({ $content, params }) {
      const tutorial = await $content('tutorials', params.slug).fetch()
      return { tutorial }
    },
    methods: {
        formatDate(date) {
          const options = { year: 'numeric', month: 'long', day: 'numeric' }
          return new Date(date).toLocaleDateString('en', options)
        }
    },
    head() {
      return {
        title: this.tutorial.title,
        meta: [
          {
            hid: 'description',
            name: 'description',
            content: this.tutorial.description
          }
        ]
      }
    }
  }
</script>
<template>
  <div class="mx-auto">
    <div class="bg-gradient-to-r from-[#8a4fff] via-emerald-400 to-[#23c393] py-8 flex items-center justify-start">
      <div class="max-w-5xl flex flex-col items-center justify-start px-4 sm:px-12 mx-auto p-4 w-full">
        <h1 class="text-white text-4xl font-bold text-left self-start">{{ tutorial.title }}</h1>
      </div>
    </div>
    <div class="max-w-5xl px-4 sm:px-12 mx-auto p-4">
      <article class="pt-12">
        <nuxt-content class="" :document="tutorial" />
      </article>
      <!-- <a href="https://tailwindsites.com" target="_blank" class=" max-w-xl flex flex-col mt-16 p-6 justify-start w-full bg-blue-100 rounded-lg">
        <img class="w-full h-auto border-2 border-blue-500 rounded-lg self-start md:self-end" src="/tailwindsites.png" alt="Weston Walker">
        <h2 class="mt-4 leading-relaxed text-left text-base font-semibold md:leading-snug text-gray-900 uppercase tracking-widest">
          🔥 Free Tailwind CSS Site Templates
        </h2>
        <p class="text-lg font-light text-gray-600 text-left mt-4">
            Tailwindsites is a collection of <span class="font-bold">free Tailwind CSS + HTML5 sites templates</span>. 100% free. Use them to kickstart your next project or learn Tailwind CSS!
        </p>
      </a> -->
    </div>
  </div>
</template>