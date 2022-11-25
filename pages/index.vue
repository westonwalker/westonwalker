<template>
  <div>
    <div class="flex flex-col-reverse md:flex-row-reverse max-w-5xl mx-auto">
      <div class="px-4 sm:px-12 mx-auto p-4 w-full md:w-1/3">
        <div class="flex flex-col pt-16 justify-start md:justify-end w-full">
          <img class="w-32 h-auto border-8 border-[#8a4fff] rounded-full self-start md:self-end" src="/avatar.png" alt="Weston Walker">
          <h2 class="mt-4 leading-relaxed text-left md:text-right text-base font-semibold md:leading-snug text-[#8a4fff] uppercase tracking-widest">
            👋 Hi, I'm Wes
          </h2>
          <p class="text-lg font-light text-gray-800 text-left md:text-right mt-4 max-w-md">I simplify complex topics - like development, design, and 1 person businesses - and help cure your imposter syndrome.</p>
        </div>
        <a href="https://tailwindsites.com" target="_blank" class="flex flex-col mt-16 p-6 md:p-2 justify-start md:justify-end w-full bg-blue-100 rounded-lg">
          <img class="w-full h-auto border-2 border-blue-500 rounded-lg self-start md:self-end" src="/tailwindsites.png" alt="Weston Walker">
          <h2 class="mt-4 leading-relaxed text-left md:text-right text-base font-semibold md:leading-snug text-gray-900 uppercase tracking-widest">
            🔥 Free Tailwind CSS Site Templates
          </h2>
          <p class="text-lg font-light text-gray-600 text-left md:text-right mt-4 max-w-md">
            Tailwindsites is a collection of <span class="font-bold">free Tailwind CSS + HTML5 sites templates</span>. 100% free. Use them to kickstart your next project or learn Tailwind CSS!
          </p>
        </a>
      </div>
      <div class="px-4 sm:px-12 mx-auto p-4 w-full md:w-2/3">
        <div id="articles" class="flex flex-col pt-16">
          <h2 class="leading-relaxed text-left text-base md:leading-snug text-pink-500 uppercase tracking-widest">
            Recently Published
          </h2>
          <div class="grid gap-6 grid-cols-1 text-center mt-6">
            <div class="flex flex-col justify-start max-w-xl mb-6" v-for="article of publishedArticles" :key="article.slug">
              <h2 class="text-xl font-bold text-left">
                {{ article.title }}
              </h2>
              <p class="text-lg font-light text-gray-800 text-left my-4">{{ article.description }}</p>
              <NuxtLink class="text-base font-bold text-left hover:text-violet-400" :to="{ name: 'article-slug', params: { slug: article.slug } }">
                Read More
              </NuxtLink>
            </div>
            <div class="flex flex-col justify-start max-w-xl mb-6" v-for="tutorial of publishedTutorials" :key="tutorial.slug">
              <h2 class="text-xl font-bold text-left">
                {{ tutorial.title }}
              </h2>
              <p class="text-lg font-light text-gray-800 text-left my-4">{{ tutorial.description }}</p>
              <NuxtLink class="text-base font-bold text-left hover:text-violet-400" :to="{ name: 'tutorial-slug', params: { slug: tutorial.slug } }">
                Read More
              </NuxtLink>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  async asyncData({ $content, params }) {
    const tutorials = await $content('tutorials')
      .where({ published: true })
      .only(['title', 'description', 'icon', 'slug', 'publishDate'])
      .sortBy('publishDate', 'desc')
      .fetch()

    const articles = await $content('articles')
      .where({ published: true })
      .only(['title', 'description', 'slug', 'img', 'alt', 'publishDate'])
      .sortBy('publishDate', 'desc')
      .fetch()

    const publishedTutorials = tutorials.filter(x => new Date(x.publishDate) <= new Date())
    
    const publishedArticles = articles.filter(x => new Date(x.publishDate) <= new Date())
    return {
      publishedTutorials,
      publishedArticles
    }
  }
}
</script>
