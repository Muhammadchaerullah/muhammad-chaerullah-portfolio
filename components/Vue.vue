<template>
    <div class="w-[50px] h-[50px]" ref="threeContainerImg"></div>
  </template>
  
  <script setup lang="ts">
  import * as THREE from 'three'
  import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls.js'
  import { onMounted, ref, onBeforeUnmount } from 'vue'
  
  const threeContainerImg = ref<HTMLElement | null>(null)
  
  onMounted(() => {
    if (!threeContainerImg.value) return
  
    const width = threeContainerImg.value.clientWidth
    const height = threeContainerImg.value.clientHeight
  
    const scene = new THREE.Scene()
  
    const camera = new THREE.PerspectiveCamera(30, width / height, 0.1, 1000)
    camera.position.set(0, 0, 5)
  
    const renderer = new THREE.WebGLRenderer({ antialias: true, alpha: true })
    renderer.setSize(width, height)
    renderer.setClearColor(0x000000, 0)
    renderer.shadowMap.enabled = true
    threeContainerImg.value.appendChild(renderer.domElement)
  
    const controls = new OrbitControls(camera, renderer.domElement)
    controls.enableDamping = true
    controls.enableZoom = false
    controls.autoRotate = false
  
    // Lights
    const dirLight = new THREE.DirectionalLight(0xffffff, 10)
    dirLight.position.set(2, 4, 3)
    dirLight.castShadow = true
    scene.add(dirLight)
  
    const ambientLight = new THREE.AmbientLight(0xffffff, 0.6)
    scene.add(ambientLight)
  
    // Load texture
    const textureLoader = new THREE.TextureLoader()
    const texture = textureLoader.load(
      '/img/vue.png',
      () => {
        texture.minFilter = THREE.LinearFilter
        texture.magFilter = THREE.LinearFilter
        texture.anisotropy = renderer.capabilities.getMaxAnisotropy()
        texture.needsUpdate = true
        console.log('Texture loaded')
      },
      undefined,
      (err) => console.error('Texture error:', err)
    )
    renderer.setPixelRatio(window.devicePixelRatio)
    renderer.setSize(width, height)
  
    // Create Plane
    const geometry = new THREE.PlaneGeometry(2, 2)
    const material = new THREE.MeshStandardMaterial({
      map: texture,
      transparent: true,
      side: THREE.DoubleSide, // <--- penting!
    })
    const plane = new THREE.Mesh(geometry, material)
    plane.castShadow = true
    plane.receiveShadow = true
    scene.add(plane)
  
    // Floating variables
    let clock = new THREE.Clock()
  
    // Resize Handler
    function onWindowResize() {
      if (!threeContainerImg.value) return
      const width = threeContainerImg.value.clientWidth
      const height = threeContainerImg.value.clientHeight
      renderer.setSize(width, height)
      camera.aspect = width / height
      camera.updateProjectionMatrix()
    }
  
    window.addEventListener('resize', onWindowResize)
  
    function animate() {
      requestAnimationFrame(animate)
  
      const elapsed = clock.getElapsedTime()
  
      // Animasi rotasi dan floating
      plane.rotation.y += 0.01
      plane.rotation.x = Math.sin(elapsed * 0.5) * 0.1
      plane.position.y = Math.sin(elapsed) * 0.1
  
      controls.update()
      renderer.render(scene, camera)
    }
  
    animate()
  
    onBeforeUnmount(() => {
      window.removeEventListener('resize', onWindowResize)
    })
  })
  </script>
  