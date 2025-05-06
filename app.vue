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
    <div class="mx-auto max-w-6xl sm:p-20 px-5 py-10">
      <div class="flex flex-col gap-20 sm:flex-row">
        <div class="flex flex-col gap-8 sm:gap-96">
          <div class="flex flex-col gap-5">
            <div class="flex flex-col">
              <h1 class="text-3xl font-bold tracking-tight text-slate-200 sm:text-4xl font-poppins">
                Muhammad Chaerullah
              </h1>
              <p class="text-2xl font-light tracking-tight text-slate-200 sm:text-3xl">
                Front End Engineer
              </p>
            </div>
            <div>
              <p class="text-lg font-light tracking-tight text-slate-400 sm:text-xl">
                Designing seamless digital experiences — accessible, beautiful, and fast.
              </p>
            </div>
          </div>
          <div class="flex gap-5">
            <Icon name="uil:github" class="text-slate-400 hover:text-slate-100 sm:text-4xl text-3xl cursor-pointer" />
            <Icon name="uil:linkedin" class="text-slate-400 hover:text-slate-100 sm:text-4xl text-3xl cursor-pointer" />
            <Icon name="uil:instagram" class="text-slate-400 hover:text-slate-100 sm:text-4xl text-3xl cursor-pointer" />
          </div>
        </div>
        <div class="w-3/4">
          I’m a developer passionate about crafting accessible, pixel-perfect user interfaces that blend thoughtful design with robust engineering. My favorite work lies at the intersection of design and development, creating experiences that not only look great but are meticulously built for performance and usability.

          Currently, I'm a Senior Front-End Engineer at Klaviyo, specializing in accessibility. I contribute to the creation and maintenance of UI components that power Klaviyo’s frontend, ensuring our platform meets web accessibility standards and best practices to deliver an inclusive user experience.

          In the past, I've had the opportunity to develop software across a variety of settings — from advertising agencies and large corporations to start-ups and small digital product studios. Additionally, I also released a comprehensive video course a few years ago, guiding learners through building a web app with the Spotify API.

          In my spare time, I’m usually climbing, reading, hanging out with my wife and two cats, or running around Hyrule searching for Korok seeds
          K
          o
          r
          o
          k
          
          s
          e
          e
          d
          s
          .
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue'

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
