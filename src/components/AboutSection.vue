<template>
  <section id="about" class="about-me bg-gray-900 text-white py-12">
      <div class="container mx-auto px-4">
          <h2 class="text-4xl font-bold text-center mb-8">About Me</h2>
          <div class="introduction mb-8">
              <p class="text-gray-300 sm:text-center max-w-full ">
                  Halo, saya Suryo Nugroho, seorang pengembang perangkat lunak yang berdedikasi, dengan pengalaman dalam berbagai proyek dan keahlian di berbagai teknologi.
              </p>
          </div>

          <div class="education mb-8">
              <h3 class="text-2xl font-semibold mb-4 text-center">Education</h3>
              <div class="education-container flex justify-center space-y-4 md:space-y-0 md:flex md:gap-3">
                  <div
                      v-for="(education, index) in educationList"
                      :key="index"
                      class="bg-gray-800 p-4 rounded-lg shadow-md flex items-center text-center transition-transform transform hover:scale-105"
                  >
                      <img :src="education.logo" alt="Logo {{ education.school }}" class="w-16 h-16 mb-2" />
                      <h4 class="text-xl font-semibold text-primary">{{ education.degree }}</h4>
                      <p class="text-gray-300">{{ education.school }} ({{ education.year }})</p>
                  </div>
              </div>
          </div>
      </div>
  </section>
</template>

<script>
import logoPP from "@/assets/images/PP.png";
import logoUnindra from "@/assets/images/unindra.png";

export default {
  data() {
      return {
          educationList: [
              {
                  degree: "Rekayasa Perangkat Lunak (RPL)",
                  school: "SMK Prestasi Prima",
                  year: "2017 - 2020",
                  logo: logoPP
              },
              {
                  degree: "Bachelor of Informatics Engineering",
                  school: "Universitas Indraprastha PGRI",
                  year: "2020 - 2024",
                  logo: logoUnindra
              },
          ],
      };
  },
};
</script>

<style scoped>
.about-me {
  background: linear-gradient(135deg, #13131d 0%, #14143d 100%);
}


.education-container {
  display: flex;
  flex-direction: column; 
  gap: 1.3rem;
}

@media (min-width: 768px) { 
  .education-container {
      flex-direction: row;
      
  }
}

.bg-gray-800 {
  display: flex;
  flex-direction: column; 
  align-items: center;
  justify-content: space-between; 
  flex: 1; 
  max-width: 30rem;
  margin: 0;
  padding: 2rem;
  transition: transform 0.5s;

}
img {
    max-width: 100%; 
    height: auto; 
}
</style>
