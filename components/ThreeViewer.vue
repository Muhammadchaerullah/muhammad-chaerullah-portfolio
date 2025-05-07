<template>
    <div class="w-[50px] h-[100px]" ref="threeContainer"></div>
  </template>
  
  <script setup lang="ts">
  import * as THREE from 'three'
  import { GLTFLoader } from 'three/examples/jsm/loaders/GLTFLoader.js'
  import type { GLTF } from 'three/examples/jsm/loaders/GLTFLoader.js'
  import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls.js'
  import { onMounted, ref } from 'vue'
  
  const threeContainer = ref<HTMLElement | null>(null)
  
  onMounted(() => {
    if (!threeContainer.value) return
  
    const width = threeContainer.value.clientWidth
    const height = threeContainer.value.clientHeight
  
    const scene = new THREE.Scene()
  
    const camera = new THREE.PerspectiveCamera(25, width / height, 0.1, 1000)
    camera.position.z = 3
  
    const renderer = new THREE.WebGLRenderer({ antialias: true, alpha: true })
    renderer.setSize(width, height)
    renderer.setClearColor(0x000000, 0)
    threeContainer.value.appendChild(renderer.domElement)
  
    const controls = new OrbitControls(camera, renderer.domElement)
    controls.enableDamping = true
  
    // Lighting (penting untuk melihat model)
    const light = new THREE.DirectionalLight(0xffffff, 1)
    light.position.set(0, 1, 2)
    scene.add(light)
  
    const ambientLight = new THREE.AmbientLight(0xffffff, 0.5)
    scene.add(ambientLight)
  
    const loader = new GLTFLoader()
    let model: THREE.Object3D | null = null
  
    loader.load(
      '/models/Avocado.glb',
      (gltf: GLTF) => {
        model = gltf.scene
        model.scale.set(8, 8, 8) // Sesuaikan skala sesuai kebutuhan
        scene.add(model)
        console.log('Model loaded successfully:', model)
      },
      undefined,
      (error: unknown) => {
        if (error instanceof Error) {
          console.error('Error loading model:', error.message)
        } else {
          console.error('Unknown error loading model:', error)
        }
      }
    )
  
    function animate() {
      requestAnimationFrame(animate)
      controls.update()
      if (model) {
        model.rotation.y += 0.01 // ← Putar model di sumbu Y
        }
      renderer.render(scene, camera)
    }
  
    animate() // Mulai loop animasi
  })
  </script>
  