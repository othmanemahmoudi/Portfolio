<script setup lang="ts">
import { onMounted, ref } from 'vue'
import * as THREE from 'three'
import { OrbitControls } from 'three/examples/jsm/controls/OrbitControls.js'

const container = ref<HTMLDivElement | null>(null)

const skills = [
    { name: '', icon: '' },
    { name: 'JavaScript', icon: '🟨' },
    { name: 'TypeScript', icon: '🔷' },
    { name: 'Vue.js', icon: '🖖' },
    { name: 'React', icon: '⚛️' },
    { name: 'Node.js', icon: '🟩' },
    { name: 'Python', icon: '🐍' },
    { name: 'Django', icon: '🌿' },
    { name: 'HTML5', icon: '📄' },
    { name: 'CSS3', icon: '🎨' },
    { name: 'Tailwind', icon: '🌬️' },
    { name: 'Git', icon: '🔧' },
    { name: 'Docker', icon: '🐳' },
        { name: 'JavaScript', icon: '🟨' },
    { name: 'TypeScript', icon: '🔷' },
    { name: 'Vue.js', icon: '🖖' },
    { name: 'React', icon: '⚛️' },
    { name: 'Node.js', icon: '🟩' },
    { name: 'Python', icon: '🐍' },
    { name: 'Django', icon: '🌿' },
    { name: 'HTML5', icon: '📄' },
    { name: 'CSS3', icon: '🎨' },
    { name: 'Tailwind', icon: '🌬️' },
    { name: 'Git', icon: '🔧' },
    { name: 'Docker', icon: '🐳' },
]

onMounted(() => {
  if (!container.value) return

  const scene = new THREE.Scene()
  const camera = new THREE.PerspectiveCamera(75, container.value.clientWidth / container.value.clientHeight, 0.1, 1000)
  camera.position.z = 6

  const renderer = new THREE.WebGLRenderer({ antialias: true, alpha: true })
  renderer.setSize(container.value.clientWidth, container.value.clientHeight)
  container.value.appendChild(renderer.domElement)

  // Rayon pour les skills
  const radius = 3

  // Répartir les skills sur plusieurs latitudes
  skills.forEach((skill, i) => {
    const phi = Math.acos(-1 + (2 * i) / skills.length) // latitude
    const theta = Math.sqrt(skills.length * Math.PI) * phi // longitude

    const x = radius * Math.sin(phi) * Math.cos(theta)
    const y = radius * Math.cos(phi)
    const z = radius * Math.sin(phi) * Math.sin(theta)

    const canvas = document.createElement('canvas')
    const context = canvas.getContext('2d')!
    canvas.width = 128
    canvas.height = 128
    context.fillStyle = '#CFAF71'
    context.font = 'bold 24px sans-serif' 
    context.textAlign = 'center'
    context.textBaseline = 'middle'
    context.fillText(skill.icon, 64, 40)
    context.fillText(skill.name, 64, 90)

    const texture = new THREE.CanvasTexture(canvas)
    const spriteMaterial = new THREE.SpriteMaterial({ map: texture })
    const sprite = new THREE.Sprite(spriteMaterial)
    sprite.position.set(x, y, z)
    scene.add(sprite)
  })

  // Contrôles
  const controls = new OrbitControls(camera, renderer.domElement)
  controls.enableZoom = false
  controls.autoRotate = true
  controls.autoRotateSpeed = 3

  // Animation
  function animate() {
    requestAnimationFrame(animate)
    controls.update()
    renderer.render(scene, camera)
  }
  animate()

  // Resize
  window.addEventListener('resize', () => {
    if (!container.value) return
    camera.aspect = container.value.clientWidth / container.value.clientHeight
    camera.updateProjectionMatrix()
    renderer.setSize(container.value.clientWidth, container.value.clientHeight)
  })
})
</script>

<template>
    <div ref="container" class="w-full max-w-4xl h-[600px] mx-auto"></div>
</template>
