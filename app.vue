<template>
  <div>
    <div
      class="fixed inset-0 pointer-events-none z-50"
      :style="{
        background: `radial-gradient(600px at ${position.x}px ${position.y}px, rgba(29, 78, 216, 0.15), transparent 80%)`,
        transition: 'background 0.15s ease'
      }"
      @mousemove="updateCursorPosition"
    >
    </div>
    <div class="mx-auto lg:max-w-10/12 lg:p-20 py-10 font-display">
      <div class="flex flex-col gap-10 lg:flex-row">
        <main class="flex flex-col gap-8 md:gap-96 lg:w-6/12">
            <div class="flex flex-col gap-5 px-5">
              <div class="flex flex-col">
                <h1 class="text-3xl font-bold tracking-tight text-slate-200 md:text-4xl">
                  Muhammad Chaerullah
                </h1>
                <p class="text-base tracking-tight text-slate-200 md:text-2xl">
                  Front End Engineer
                </p>
              </div>
              <div>
                <p class="text-sm font-light tracking-tight text-slate-400 md:text-base">
                  Stepping out of the comfort zone <br> never stopping the learning journey.
                </p>
              </div>
              <img
                src="/img/me.png"
                alt="This is me"
                class="hidden lg:block w-full object-cover rounded-lg shadow-lg transition-transform duration-300 hover:scale-105 hover:shadow-xl"
              />
              <div class="flex gap-5">
                <a href="https://github.com/Muhammadchaerullah">
                  <Icon name="uil:github" class="text-slate-400 hover:text-slate-100 md:text-4xl text-3xl cursor-pointer" />
                </a>
                <a href="https://www.linkedin.com/in/muhammad-chaerullah-752654191/">
                  <Icon name="uil:linkedin" class="text-slate-400 hover:text-slate-100 md:text-4xl text-3xl cursor-pointer" />
                </a>
                <a href="https://www.instagram.com/mchaerullah/">
                  <Icon name="uil:instagram" class="text-slate-400 hover:text-slate-100 md:text-4xl text-3xl cursor-pointer" />
                </a>
              </div>
            </div>
        </main>
        <main class="lg:w-6/12 sm:max-h-screen sm:overflow-y-auto scroll-hide">
          <div class="flex flex-col gap-5 sm:gap-10">
            <section id="about">
              <div class="p-5 sticky top-0 z-50 backdrop-blur-2xl block sm:hidden scroll-hide">
                <p class="text-sm font-bold text-white">
                  ABOUT
                </p>
              </div>
              <div class="px-5">
                <div class="flex flex-col gap-5">
                  <p class="text-sm/7 sm:text-sm/7">
                    <span class="text-white">I'm a Front-End Developer</span> who loves creating accessible and visually accurate user interfaces by combining design and solid code.
                    Previously, I worked as an IT Technician maintaining office computers, but by <span class="text-white">the grace of Allah SWT</span>, I was able to shift my career to web development—something I’ve been passionate about since university.
                  </p>
                  <p class="text-base/7 sm:text-sm/7">
                    Over the years, I’ve built web apps in various settings, from student projects to <span class="text-white">working at a startup for around five years.</span>
                  </p>
                  <p class="text-base/7 sm:text-sm/7">
                    <span class="text-white">Outside of work</span>, I enjoy learning new technologies and staying updated with the latest in programming.
                    I’m also active in my community, currently leading the local youth mosque organization and serving as secretary of the neighborhood council.
                    In my free time, I love spending time with my wife and sharing daily stories.
                  </p>
                </div>
              </div>
            </section>
            <section id="experience">
              <div class="flex flex-col gap-20 sm:gap-10">
                <div class="flex-col gap-5 sm:flex">
                  <div class="p-5 sticky top-0 z-50 backdrop-blur-2xl block sm:hidden scroll-hide">
                    <p class="text-sm font-bold text-white">
                      EXPERIENCE
                    </p>
                  </div>
                  <div>
                    <header class="z-10 mb-2 mt-1 text-xs font-semibold uppercase tracking-wide text-slate-500 sm:col-span-2 px-5">
                        2019 - 2025
                      </header>
                  </div>
                  <div>
                    <div class="text-lg font-semibold px-5 text-white hover:text-emerald-500 cursor-pointer transition duration-300 ease-in-out">
                        Middle Front End Developer · Travellergram
                      </div>
                  </div>
                  <div class="text-sm/7 px-5">
                    Build and optimize website or application interfaces using HTML, CSS, JavaScript, and frameworks like Vue.js or Nuxt.js, 
                    Translate UI/UX designs into functional code and work closely with backend developers to integrate APIs and server-side data,
                    Make sure the application is responsive across devices, loads quickly, and delivers a smooth user experience.
                  </div>
                  <div class="flex flex-row gap-2 px-5 mt-2">
                      <div class="font-medium px-3 py-1 bg-teal-500/10 rounded-full text-xs text-teal-300 text-center leading-5">
                        JavaScript
                      </div>
                      <div class="font-medium px-3 py-1 bg-teal-500/10 rounded-full text-xs text-teal-300 text-center leading-5">
                        Vue.js
                      </div>
                      <div class="font-medium px-3 py-1 bg-teal-500/10 rounded-full text-xs text-teal-300 text-center leading-5">
                        Nuxt.js
                      </div>
                      <div class="font-medium px-3 py-1 bg-teal-500/10 rounded-full text-xs text-teal-300 text-center leading-5">
                        Tailwind CSS
                      </div>
                    </div>
                </div>
                <div class="flex-col gap-5 sm:flex">
                  <div>
                    <header class="z-10 mb-2 mt-1 text-xs font-semibold uppercase tracking-wide text-slate-500 sm:col-span-2 px-5">
                        2018 - 2019
                      </header>
                  </div>
                  <div>
                    <div class="text-lg font-semibold px-5 text-white hover:text-emerald-500 cursor-pointer transition duration-300 ease-in-out">
                        IT Technician – Responsibilities · PT. Fastratabuana Kapal Api
                      </div>
                  </div>
                  <div class="text-sm/7 px-5">
                    <span class="text-white">Maintain and repair hardware components</span>
                    Ensure computers, printers, and other IT equipment function properly and perform necessary repairs when issues arise,
                    <span class="text-white">Install and configure software</span>
                    Install operating systems, work-related applications, antivirus programs, and carry out routine updates,
                    <span class="text-white">Troubleshoot technical issues</span>
                    Diagnose and resolve hardware, software, and basic network problems; provide user support for day-to-day technical issues.
                  </div>
                  <div class="flex flex-wrap gap-2 px-5 mt-2 justify-start">
                      <div class="font-medium px-3 py-1 bg-teal-500/10 rounded-full text-xs text-teal-300 text-center leading-5">
                        Hardware
                      </div>
                      <div class="font-medium px-3 py-1 bg-teal-500/10 rounded-full text-xs text-teal-300 text-center leading-5">
                        software knowledge
                      </div>
                      <div class="font-medium px-3 py-1 bg-teal-500/10 rounded-full text-xs text-teal-300 text-center leading-5">
                        Basic networking
                      </div>
                      <div class="font-medium px-3 py-1 bg-teal-500/10 rounded-full text-xs text-teal-300 text-center leading-5">
                        problem solving
                      </div>
                    </div>
                </div>
              </div>
            </section>
          </div>
        </main>
      </div>
      <main>
        <section id="skill" class="my-10 px-5">
          <div class="flex gap-2 lg:justify-between justify-start">
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
      </main>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'
import ThreeViewerImgHtml from '~/components/ThreeViewerImgHtml.vue'
import Css from '~/components/Css.vue'
import Vue from '~/components/Vue.vue'
import Js from '~/components/Js.vue'
import Tailwind from '~/components/Tailwind.vue'
import Nuxt from '~/components/Nuxt.vue'
import { LazyIcon } from '#components'

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