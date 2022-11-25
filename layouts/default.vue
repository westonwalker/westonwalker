<template>
  <div>
    <div class="max-w-5xl flex flex-col items-start sm:items-start sm:flex-row sm:justify-between px-4 sm:px-12 mx-auto p-4">
      <NuxtLink class="inline-flex items-center font-semibold text-lg" to="/">
        <img class="h-10 w-auto mr-2" src="/logo.png" />
        <span>Weston Walker</span>
      </NuxtLink>
      <div class="text-base flex flex-col w-1/2 items-center">
        <div class="w-full flex flex-row items-center sm:justify-end">
          <NuxtLink class="md:px-4 py-2" to="/#articles">
            Articles
          </NuxtLink>
          <NuxtLink class="px-3 md:px-4 py-2" to="/projects">
            Projects
          </NuxtLink>
          <a target="_blank" href="https://twitter.com/wes_walke" class="pl-3 md:pl-4 py-2 inline-flex">
            <svg class="h-6 w-6 fill-[#39ADE8] m-0" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512">
              <path d="M459.37 151.716c.325 4.548.325 9.097.325 13.645 0 138.72-105.583 298.558-298.558 298.558-59.452 0-114.68-17.219-161.137-47.106 8.447.974 16.568 1.299 25.34 1.299 49.055 0 94.213-16.568 130.274-44.832-46.132-.975-84.792-31.188-98.112-72.772 6.498.974 12.995 1.624 19.818 1.624 9.421 0 18.843-1.3 27.614-3.573-48.081-9.747-84.143-51.98-84.143-102.985v-1.299c13.969 7.797 30.214 12.67 47.431 13.319-28.264-18.843-46.781-51.005-46.781-87.391 0-19.492 5.197-37.36 14.294-52.954 51.655 63.675 129.3 105.258 216.365 109.807-1.624-7.797-2.599-15.918-2.599-24.04 0-57.828 46.782-104.934 104.934-104.934 30.213 0 57.502 12.67 76.67 33.137 23.715-4.548 46.456-13.32 66.599-25.34-7.798 24.366-24.366 44.833-46.132 57.827 21.117-2.273 41.584-8.122 60.426-16.243-14.292 20.791-32.161 39.308-52.628 54.253z"/>
            </svg>
          </a>
        </div>
      </div>
    </div>
    <Nuxt />
    <div class="max-w-5xl px-4 sm:px-12 p-4 mx-auto my-12"> 
      <div class="h-12 bg-[#8a4fff] w-full"></div>
    </div>
    <div class="max-w-5xl px-4 sm:px-12 p-4 center-form mx-auto"> 
      <div class="flex flex-col justify-center max-w-xl mb-6 mx-auto">
        <div class="relative w-[350px] h-[550px] md:w-[450px] bg-gray-50 rounded-md shadow-2xl mt-6 mx-auto">
            <div class="h-28 bg-gradient-to-r from-[#8a4fff] to-[#23c393] border-b-2 border-black text-white text-2xl font-bold rounded-t-md flex justify-center items-center">
                <h3 class="text-xl text-white font-bold">The Full Stack Dev Newsletter</h3>
            </div>
            <nuxt-img format="webp" src="/avatar.png" alt="The Full Stack Dev Avatar" 
                    class="w-16 h-16 rounded-full border-2 border-black mx-auto -mt-8" sizes="sm:100vw md:50vw lg:400px" />
            <div class="px-6">
                <p class="font-light text-lg mb-4">Hey, I'm Wes. Every month I send a newsletter with articles on:</p>
                <ul class="font-semibold text-lg list-disc list-inside mb-4 ml-2">
                    <li>​🔥 Hot Web Dev tips</li>
                    <li>🎨 Web Design</li>
                    <li>🔨 Product Development</li>
                </ul>
                <p class="font-light text-lg mb-4">As seen at the top of Hacker News, Indie Hackers, and Hacker Noon.</p>
                <script async data-uid="9b73baf3e7" src="https://fabulous-inventor-6805.ck.page/9b73baf3e7/index.js"></script>
            </div>
        </div>
      </div> 
    </div>
    <EmailSlideIn></EmailSlideIn>
  </div>
</template>