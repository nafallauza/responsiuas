<template>
  <section id="profil" class="container mx-auto px-6 py-20 flex flex-col md:flex-row items-center gap-10">
    <!-- Deskripsi Profil -->
    <div class="md:w-1/2 text-center md:text-left">
      <h1
        class="text-5xl font-extrabold text-gray-800 leading-tight mb-4 animate-slide-in-left"
        style="animation-delay: 200ms;"
      >
        Halo, Saya
        <span class="text-blue-600">Nafal Lauza Hafidh Adani</span>
      </h1>
      <p
        class="text-lg text-gray-600 leading-relaxed mb-6 animate-slide-in-left"
        style="animation-delay: 400ms;"
      >
        Mahasiswa Teknik Informatika dengan semangat tinggi dalam
        <span class="font-semibold text-blue-500">pengembangan web</span> dan
        <span class="font-semibold text-blue-500">desain antarmuka</span>. Saya percaya bahwa teknologi dan kreativitas bisa berjalan beriringan.
      </p>

      <a
        href="#kontak"
        class="bg-gradient-to-r from-blue-600 to-purple-600 text-white font-semibold py-3 px-8 rounded-full shadow-lg hover:shadow-xl hover:scale-105 transform transition-all duration-300 inline-block animate-slide-in-left"
        style="animation-delay: 600ms;"
      >
        ✉️ Hubungi Saya
      </a>
    </div>

    <!-- Gambar Profil + Badge -->
    <div class="md:w-1/2 flex justify-center animate-slide-in-right">
      <div class="relative w-80 h-80">
        <img
          src="/src/assets/img/logo.webp"
          alt="Foto Profil"
          class="w-full h-full rounded-full object-cover shadow-2xl border-4 border-blue-600"
        />

        <!-- Badge: Frontend Developer -->
        <div
          class="absolute -bottom-4 right-4 bg-white px-4 py-1 rounded-full shadow-md text-sm font-semibold text-gray-700 animate-float-slow"
        >
          💻 Frontend Developer
        </div>

        <!-- Badge: UI/UX Designer -->
        <div
          class="absolute -top-4 left-4 bg-white px-4 py-1 rounded-full shadow-md text-sm font-semibold text-gray-700 animate-float-fast"
        >
          🎨 UI/UX Designer
        </div>

        <!-- Badge: Desainer -->
        <div
          class="absolute top-1/2 -left-8 transform -translate-y-1/2 bg-white px-4 py-1 rounded-full shadow-md text-sm font-semibold text-gray-700 animate-float-mid"
        >
          ✏️ Desainer
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
@keyframes float-slow {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-8px); }
}
@keyframes float-fast {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-12px); }
}
@keyframes float-mid {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-10px); }
}
.animate-float-slow {
  animation: float-slow 3s ease-in-out infinite;
}
.animate-float-fast {
  animation: float-fast 2s ease-in-out infinite;
}
.animate-float-mid {
  animation: float-mid 2.5s ease-in-out infinite;
}
</style>
