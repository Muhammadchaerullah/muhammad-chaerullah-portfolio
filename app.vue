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
      <div class="flex flex-col gap-20 md:flex-row">
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
              <p class="text-justify">
                <span class="font-poppins font-bold">Front End Developer</span> with over 3 years of experience specializing in building responsive, user-centric
                web applications using Vue.js, Nuxt.js, and Tailwind CSS. Skilled at translating UI/UX designs into
                high-quality, maintainable code. Passionate about optimizing user experience, integrating APIs, and
                collaborating with cross-functional teams to deliver impactful web solutions.
              </p>
            </div>
            <div class="flex flex-wrap justify-between">
              <div>
                <ThreeViewer/>
              </div>
              <div>
                <ThreeViewer/>
              </div>
              <div>
                <ThreeViewer/>
              </div>
              <div>
                <ThreeViewer/>
              </div>
              <div>
                <ThreeViewer/>
              </div>
              <div>
                <ThreeViewer/>
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
import ThreeViewer from '~/components/ThreeViewer.vue'

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
