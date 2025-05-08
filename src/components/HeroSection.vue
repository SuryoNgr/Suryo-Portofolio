<template>
    <section class="relative w-full">
      <!-- Gradient Background -->
      <div class="absolute top-0 inset-x-0 h-64 flex items-start">
        <div class="h-24 w-2/3 bg-gradient-to-br from-purple-500 blur-2xl invisible opacity-40"></div>
        <div class="h-20 w-3/5 bg-gradient-to-r from-primary opacity-40 blur-2xl"></div>
      </div>
  
      <!-- Container -->
      <div class="w-full px-4 sm:px-6 md:px-12 lg:px-8 max-w-screen-lg lg:max-w-screen-xl mx-auto relative">
        <div class="grid lg:grid-cols-2 gap-10 xl:gap-14 relative pt-16 lg:pt-24 lg:max-w-none max-w-full mx-auto">
  
          <!-- Text Content -->
          <div class="lg:py-6">
            <div class="text-center lg:text-left">
              <h1 class="pt-4 text-white font-bold text-3xl sm:text-4xl md:text-5xl lg:text-6xl whitespace-nowrap">
                Halo, Saya <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-purple-500">
                  Suryo Nugroho
                </span>
              </h1>
            </div>
            <p class="text-gray-300 pt-6 sm:pt-8 text-center lg:text-left mx-auto max-w-full sm:max-w-xl">
              Lulusan S1 Teknik Informatika Universitas Indraprasta yang memiliki
              minat dan dasar yang kuat dalam pengembangan web.
              Dengan keterampilan dalam HTML, CSS, PHP, dan JavaScript, serta
              framework modern seperti Laravel, Bootstrap, Tailwind CSS, dan
              Vue.js, saya telah belajar untuk merancang dan mengembangkan
              antarmuka web yang responsif dan interaktif.
            </p>
  
            <!-- Resume Button -->
            <div class="flex items-center gap-3 pt-6 sm:pt-9 flex-col sm:flex-row w-full sm:w-max sm:mx-auto lg:mx-0">
              <button
                @click="handleDownload"
                :disabled="isDownloading"
                class="border border-primary px-4 sm:px-6 py-3 rounded-full relative group w-full sm:w-auto flex justify-center"
              >
                <div class="flex items-center gap-2">
                  <div v-if="isDownloading" class="animate-spin rounded-full h-5 w-5 border-t-2 border-primary border-opacity-50"></div>
                  <svg
                    v-else
                    class="download-icon"
                    width="18"
                    height="22"
                    viewBox="0 0 18 22"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path d="M13 9L9 13M9 13L5 9M9 13V1" stroke="#f59e0b" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                    <path d="M1 17V18C1 18.8 1.3 19.6 1.9 20.1C2.4 20.7 3.2 21 4 21H14C14.8 21 15.6 20.7 16.1 20.1C16.7 19.6 17 18.8 17 18V17" stroke="#f59e0b" stroke-width="2" stroke-linecap="round"/>
                  </svg>
                  <span class="text-primary">
                    {{ isDownloading ? 'Downloading...' : 'Download Resume' }}
                  </span>
                </div>
              </button>
            </div>
          </div>
  
          <!-- Image Section (kosong untuk sekarang) -->
          <div class="lg:h-full md:flex">
            <div class="flex w-full h-96 min-h-[24rem] lg:min-h-[none] lg:w-full lg:h-full items-center relative">
              <div class="absolute z-0 top-1/2 w-5/6 right-0 h-[calc(80%+20px)] bg-gradient-to-tr opacity-25 from-[#570cac] to-primary blur-2xl"></div>
              <div class="absolute h-full z-10 p-2 translate-y-1/2 top-1/2 lg:right-3 md:right-40 sm:right-16 rounded-full shadow-lg border-primary">
                <img src="" alt="">
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  const isDownloading = ref(false)
  
  const handleDownload = () => {
    isDownloading.value = true
  
    // Simulasi download: buat <a> element lalu klik otomatis
    const link = document.createElement('a')
    link.href = '/documents/resume.pdf'
    link.download = 'SuryoNugroho(Resume).pdf'
    document.body.appendChild(link)
    link.click()
    document.body.removeChild(link)
  
    // Simulasikan animasi loading selama 2 detik
    setTimeout(() => {
      isDownloading.value = false
    }, 2000)
  }
  </script>
  