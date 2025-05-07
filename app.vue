<template>
  <div
    class="bg-slate-900 leading-relaxed text-slate-400 antialiased selection:bg-teal-300 selection:text-teal-900"
    @mousemove="updateCursorPosition"
  >
    <div
      class="fixed inset-0 pointer-events-none z-50"
      :style="{
        background: `radial-gradient(600px at ${position.x}px ${position.y}px, rgba(29, 78, 216, 0.15), transparent 80%)`,
        transition: 'background 0.15s ease'
      }"
    >
    </div>
    <div class="mx-auto md:max-w-10/12 md:p-20 px-5 py-10">
      <div class="flex flex-col gap-10 md:flex-row">
        <div class="flex flex-col gap-8 md:gap-96 md:w-6/12">
          <div class="flex flex-col gap-5">
            <div class="flex flex-col">
              <h1 class="text-3xl font-bold tracking-tight text-slate-200 md:text-5xl font-poppins">
                Muhammad Chaerullah
              </h1>
              <p class="text-2xl font-light tracking-tight text-slate-200 md:text-3xl">
                Front End Engineer
              </p>
            </div>
            <div>
              <p class="text-lg font-light tracking-tight text-slate-400 md:text-xl">
                Designing seamless digital experiences <br> accessible, beautiful, and fast.
              </p>
            </div>
          </div>
          <div class="flex gap-5">
            <Icon name="uil:github" class="text-slate-400 hover:text-slate-100 md:text-4xl text-3xl cursor-pointer" />
            <Icon name="uil:linkedin" class="text-slate-400 hover:text-slate-100 md:text-4xl text-3xl cursor-pointer" />
            <Icon name="uil:instagram" class="text-slate-400 hover:text-slate-100 md:text-4xl text-3xl cursor-pointer" />
          </div>
        </div>
        <div class="md:w-6/12">
          <div class="flex flex-col gap-10">
            <div>
              <p class="sm:text-justify">
                <span class="font-poppins font-bold">Front End Developer</span> with over 3 years of experience specializing in building responsive, user-centric
                web applications using Vue.js, Nuxt.js, and Tailwind CSS. Skilled at translating UI/UX designs into
                high-quality, maintainable code. Passionate about optimizing user experience, integrating APIs, and
                collaborating with cross-functional teams to deliver impactful web solutions.
              </p>
            </div>
            <div class="flex flex-wrap gap-5 sm:justify-between justify-start">
              <div class="flex flex-col gap-2 items-center grayscale transition-all duration-300 
            hover:grayscale-0 hover:rotate-2 hover:scale-105 
            focus:grayscale-0 focus:rotate-2 focus:scale-105 
            active:grayscale-0 active:rotate-2 active:scale-105 
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
              <div class="flex flex-col gap-2 items-center grayscale transition-all duration-300 
            hover:grayscale-0 hover:rotate-2 hover:scale-105 
            focus:grayscale-0 focus:rotate-2 focus:scale-105 
            active:grayscale-0 active:rotate-2 active:scale-105 
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
              <div class="flex flex-col gap-2 items-center grayscale transition-all duration-300 
            hover:grayscale-0 hover:rotate-2 hover:scale-105 
            focus:grayscale-0 focus:rotate-2 focus:scale-105 
            active:grayscale-0 active:rotate-2 active:scale-105 
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
              <div class="flex flex-col gap-2 items-center grayscale transition-all duration-300 
            hover:grayscale-0 hover:rotate-2 hover:scale-105 
            focus:grayscale-0 focus:rotate-2 focus:scale-105 
            active:grayscale-0 active:rotate-2 active:scale-105 
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
              <div class="flex flex-col gap-2 items-center grayscale transition-all duration-300 
            hover:grayscale-0 hover:rotate-2 hover:scale-105 
            focus:grayscale-0 focus:rotate-2 focus:scale-105 
            active:grayscale-0 active:rotate-2 active:scale-105 
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
              <div class="flex flex-col gap-2 items-center grayscale transition-all duration-300 
            hover:grayscale-0 hover:rotate-2 hover:scale-105 
            focus:grayscale-0 focus:rotate-2 focus:scale-105 
            active:grayscale-0 active:rotate-2 active:scale-105 
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
          </div>
        </div>
      </div>
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
