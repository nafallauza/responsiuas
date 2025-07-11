<script setup>
import SectionTitle from './SectionTitle.vue';

function openGmail() {
  const email = 'nafallauza@gmail.com';
  const subject = 'Kontak dari Website';
  const body = 'Halo, saya tertarik untuk menghubungi Anda...';

  const gmailUrl = `https://mail.google.com/mail/?view=cm&fs=1&to=${email}&su=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
  window.open(gmailUrl, '_blank');
}
</script>

<template>
  <footer id="kontak" class="py-20 bg-gray-900 text-white">
    <div class="container mx-auto px-6 text-center">
      <SectionTitle title="Hubungi Saya" />
      <p class="text-lg text-gray-400 mb-8">
        Jangan ragu untuk terhubung atau bertanya. Saya akan dengan senang hati merespons pesan Anda!
      </p>

      <button
        @click="openGmail"
        class="bg-gradient-to-r from-blue-600 to-blue-500 text-white font-semibold py-3 px-6 rounded-lg hover:from-blue-700 hover:to-blue-600 transition duration-300 shadow-md mb-10"
      >
        ✉️ Kirim Email
      </button>

      <div class="flex justify-center gap-6 mb-8 text-xl">
        <a
          href="https://github.com/nafallauza"
          target="_blank"
          class="text-gray-400 hover:text-white transition duration-300"
        >
          <i class="fab fa-github"></i> GitHub
        </a>
        <a
          href="https://www.linkedin.com/in/nafal-lauza-83a579275/"
          target="_blank"
          class="text-gray-400 hover:text-white transition duration-300"
        >
          <i class="fab fa-linkedin"></i> LinkedIn
        </a>
      </div>

      <p class="text-gray-500 text-sm">
        &copy; {{ new Date().getFullYear() }} Nafal Lauza Hafidh Adani. Dibuat dengan cinta dan secangkir teh hangat ☕
      </p>
    </div>
  </footer>
</template>

