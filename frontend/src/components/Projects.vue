<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios'
import SectionTitle from './SectionTitle.vue'

const projects = ref([])

onMounted(async () => {
  try {
    const response = await axios.get('http://localhost:3000/api/projects')
    projects.value = response.data
  } catch (error) {
    console.error(error)
  }
})
</script>

<template>
  <section id="proyek" class="py-20 bg-gradient-to-b from-white to-gray-50">
    <div class="container mx-auto px-6">
      <SectionTitle title="Proyek Unggulan" />
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-10 mt-12">
        <div
          v-for="project in projects"
          :key="project.title"
          class="relative group bg-white rounded-2xl shadow-md overflow-hidden transform transition duration-300 hover:scale-[1.02] hover:shadow-xl"
        >
          <!-- Image -->
          <img
            :src="project.image"
            alt="Gambar Proyek"
            class="w-full h-48 object-cover group-hover:brightness-90 transition"
          />

          <!-- Content -->
          <div class="p-6 space-y-3">
            <h3 class="text-xl font-bold text-gray-800 group-hover:text-blue-600 transition">{{ project.title }}</h3>
            <p class="text-gray-600 text-sm leading-relaxed">
              {{ project.description }}
            </p>

            <!-- Tech Stack Tags -->
            <div class="flex flex-wrap gap-2 mt-2">
              <span
                v-for="t in project.tech"
                :key="t"
                class="bg-blue-100 text-blue-700 text-xs font-medium px-3 py-1 rounded-full shadow-sm"
              >
                {{ t }}
              </span>
            </div>

            <!-- Button -->
            <div class="pt-4">
              <a
                :href="project.link"
                target="_blank"
                rel="noopener noreferrer"
                class="inline-block text-sm font-semibold text-blue-600 hover:text-blue-800 transition duration-300"
              >
                🔗 Lihat Detail →
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
