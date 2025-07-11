<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios'
import SectionTitle from './SectionTitle.vue'

const skills = ref([])

onMounted(async () => {
  try {
    const response = await axios.get('http://localhost:3000/api/skills')
    skills.value = response.data
  } catch (error) {
    console.error(error)
  }
})
</script>

<template>
  <section id="skill" class="py-20 bg-gray-50">
    <div class="container mx-auto px-6">
      <SectionTitle title="Keahlian & Teknologi" />
      <div class="grid grid-cols-2 md:grid-cols-4 gap-8 mt-10">
        <div
          v-for="skill in skills"
          :key="skill.name"
          class="bg-white p-6 rounded-xl shadow-md hover:shadow-xl transition duration-300 transform hover:-translate-y-2 flex flex-col items-center text-center"
        >
          <!-- Logo -->
          <img
            v-if="skill.logo"
            :src="skill.logo"
            :alt="`Logo ${skill.name}`"
            class="w-12 h-12 mb-4 object-contain"
          />

          <!-- Nama Skill -->
          <h3 class="text-lg font-bold text-gray-800">{{ skill.name }}</h3>

          <!-- Badge Level -->
          <span
            class="mt-2 inline-block px-3 py-1 rounded-full text-xs font-medium"
            :class="{
              'bg-blue-100 text-blue-700': skill.level.toLowerCase() === 'pemula',
              'bg-yellow-100 text-yellow-800': skill.level.toLowerCase() === 'menengah',
              'bg-green-100 text-green-800': skill.level.toLowerCase() === 'ahli'
            }"
          >
            {{ skill.level }}
          </span>
        </div>
      </div>
    </div>
  </section>
</template>
