<template>
  <body class="bg-slate-900 leading-relaxed text-slate-400 antialiased selection:bg-teal-300 selection:text-teal-900"  @mousemove="updateCursorPosition" >
    <div class="font-display">
      <div
        class="fixed inset-0 pointer-events-none z-50"
        :style="{
          background: `radial-gradient(600px at ${position.x}px ${position.y}px, rgba(29, 78, 216, 0.15), transparent 80%)`,
          transition: 'background 0.15s ease'
        }"
      >
      </div>
      <div class="mx-auto md:max-w-10/12 md:p-20 py-10">
        <div class="flex flex-col gap-10 md:flex-row">
          <main class="flex flex-col gap-8 md:gap-96 md:w-6/12">
              <div class="flex flex-col gap-5 px-5">
                <div class="flex flex-col">
                  <h1 class="text-3xl font-bold tracking-tight text-slate-200 md:text-5xl">
                    Muhammad Chaerullah
                  </h1>
                  <p class="text-base font-light tracking-tight text-slate-200 md:text-3xl">
                    Front End Engineer
                  </p>
                </div>
                <div>
                  <p class="text-lg font-light tracking-tight text-slate-400 md:text-xl">
                    Designing seamless digital experiences <br> accessible, beautiful, and fast.
                  </p>
                </div>
              </div>
              <div class="flex gap-5 px-5">
                <Icon name="uil:github" class="text-slate-400 hover:text-slate-100 md:text-4xl text-3xl cursor-pointer" />
                <Icon name="uil:linkedin" class="text-slate-400 hover:text-slate-100 md:text-4xl text-3xl cursor-pointer" />
                <Icon name="uil:instagram" class="text-slate-400 hover:text-slate-100 md:text-4xl text-3xl cursor-pointer" />
              </div>
          </main>
          <main class="md:w-6/12 sm:max-h-screen sm:overflow-y-auto scroll-hide">
            <div class="flex flex-col gap-20 sm:gap-10">
              <section>
                <div class="p-5 sticky top-0 z-50 backdrop-blur-2xl block sm:hidden scroll-hide">
                  <p class="text-sm font-bold text-white">
                    ABOUT
                  </p>
                </div>
                <div class="px-5">
                  <div class="flex flex-col gap-5">
                    <p class="text-base/7 sm:text-sm">
                      <span class="text-white">Thank you for visiting this portfolio,</span> I’m a Front End Developer passionate about crafting accessible, visually precise user interfaces, combining thoughtful design with solid engineering.
                    </p>
                    <p class="text-base/7 sm:text-sm">
                      In the past, I worked as an <span class="text-white">IT Technician</span>, where I was responsible for maintaining office computers and troubleshooting user device issues. However, by the grace of <span class="text-white">Allah SWT</span>, I was given the opportunity to completely shift my career path and pursue my passion for web programming something I had already loved since my university days.
                    </p>
                    <p class="text-base/7 sm:text-sm">
                      I’ve had the chance to develop web-based applications in various environments, starting from small projects with fellow students to working in a <span class="text-white">startup company for about five years</span>. I'm proud of that journey, and it's fulfilling to see my dream come true.
                    </p>
                    <p class="text-base/7 sm:text-sm">
                      In my spare time, I enjoy learning new things—whether it's new technologies or evolving programming stacks. I also actively participate in religious and social activities. I'm currently the head of the youth mosque organization in my neighborhood and serve as the secretary of my local community council (RW). I often spend quality time with my wife, sharing stories about our daily lives.
                    </p>
                  </div>
                </div>
              </section>
              <!-- <section>
                <div class="flex flex-col gap-5">
                  <div class="p-5 sticky top-0 z-50 backdrop-blur-2xl block sm:hidden scroll-hide">
                    <p class="text-sm font-bold text-white">
                      EXPERIENCE
                    </p>
                  </div>
                  <ol class="group/list">
                    <li class="mb-12">
                      <div class="group relative grid pb-1 transition-all sm:grid-cols-8 sm:gap-8 md:gap-4 lg:hover:!opacity-100 lg:group-hover/list:opacity-50">
                        <div class="absolute -inset-x-4 -inset-y-4 z-0 hidden rounded-xl transition motion-reduce:transition-none lg:-inset-x-6 lg:block lg:group-hover:bg-slate-800/50 lg:group-hover:shadow-[inset_0_1px_0_0_rgba(148,163,184,0.1)] lg:group-hover:drop-shadow-lg o">
                        </div>
                        <header class="z-10 mb-2 mt-1 text-xs font-semibold uppercase tracking-wide text-slate-500 sm:col-span-2 px-5">
                          2019 - present
                        </header>
                      </div>
                    </li>
                  </ol>
                </div>
              </section> -->
              <section>
                <div class="flex flex-wrap gap-5 sm:justify-between justify-start px-5">
                    <div class="flex flex-col gap-2 items-center sm:grayscale transition-all duration-300 
                    sm:hover:grayscale-0 sm:hover:rotate-2 sm:hover:scale-105 
                    cursor-pointer">
                      <div>
                        <ThreeViewerImgHtml/>
                      </div>
                      <div>
                        <p class="font-bold text-sm sm:text-lg text-orange-300">
                          HTML
                        </p>
                      </div>
                    </div>
                    <div class="flex flex-col gap-2 items-center sm:grayscale transition-all duration-300 
                  sm:hover:grayscale-0 sm:hover:rotate-2 sm:hover:scale-105 
                  cursor-pointer">
                      <div>
                        <Css/>
                      </div>
                      <div>
                        <p class="font-bold text-sm sm:text-lg text-blue-400">
                          CSS 3
                        </p>
                      </div>
                    </div>
                    <div class="flex flex-col gap-2 items-center sm:grayscale transition-all duration-300 
                  sm:hover:grayscale-0 sm:hover:rotate-2 sm:hover:scale-105 
                  cursor-pointer">
                      <div>
                        <Js/>
                      </div>
                      <div>
                        <p class="font-bold text-sm sm:text-lg text-yellow-300">
                          JS
                        </p>
                      </div>
                    </div>
                    <div class="flex flex-col gap-2 items-center sm:grayscale transition-all duration-300 
                  sm:hover:grayscale-0 sm:hover:rotate-2 sm:hover:scale-105 
                  cursor-pointer">
                      <div>
                        <Tailwind/>
                      </div>
                      <div>
                        <p class="font-bold text-sm sm:text-lg text-cyan-300">
                          TAILWIND
                        </p>
                      </div>
                    </div>
                    <div class="flex flex-col gap-2 items-center sm:grayscale transition-all duration-300 
                  sm:hover:grayscale-0 sm:hover:rotate-2 sm:hover:scale-105 
                  cursor-pointer">
                      <div>
                        <Vue/>
                      </div>
                      <div>
                        <p class="font-bold text-sm sm:text-lg text-green-300">
                          VUE
                        </p>
                      </div>
                    </div>
                    <div class="flex flex-col gap-2 items-center sm:grayscale transition-all duration-300 
                  sm:hover:grayscale-0 sm:hover:rotate-2 sm:hover:scale-105 
                  cursor-pointer">
                      <div>
                        <Nuxt/>
                      </div>
                      <div>
                        <p class="font-bold text-sm sm:text-lg text-green-300">
                          NUXT
                        </p>
                      </div>
                    </div>
                  </div>
              </section>
            </div>
          </main>
        </div>
      </div>
    </div>
  </body>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import ThreeViewerImgHtml from '~/components/ThreeViewerImgHtml.vue'
import Css from '~/components/Css.vue'
import Vue from '~/components/Vue.vue'
import Js from '~/components/Js.vue'
import Tailwind from '~/components/Tailwind.vue'
import Nuxt from '~/components/Nuxt.vue'

const position = ref({ x: 0, y: 0 })

function updateCursorPosition(event) {
  position.value.x = event.clientX
  position.value.y = event.clientY
}

onMounted(() => {
  window.addEventListener('mousemove', updateCursorPosition)
})

onBeforeUnmount(() => {
  window.removeEventListener('mousemove', updateCursorPosition)
})
</script>

<style>
/* tambahkan di style global (misalnya di app.css) */
.scroll-hide::-webkit-scrollbar {
  display: none;
}
.scroll-hide {
  -ms-overflow-style: none;  /* IE and Edge */
  scrollbar-width: none;     /* Firefox */
}
</style>