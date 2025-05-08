<template>
    <section id="projects" class="about-me bg-gray-900 text-white py-12">
        <div class="container mx-auto px-4">
            <h2 class="text-4xl font-bold text-center mb-8">Projects</h2>
  
            <div class="project mb-8">
                
                <div class="project-container flex justify-center space-y-4 md:space-y-0 md:flex md:gap-3">
                    <component
  v-for="(project, index) in projectList"
  :key="index"
  :is="project.url ? 'a' : 'div'"
  :href="project.url || undefined"
  target="_blank"
  rel="noopener noreferrer"
  class="project-card relative rounded-lg shadow-md overflow-hidden transform transition-transform hover:scale-105"
>
  <div class="image-container w-full h-full">
    <img
      :src="project.logo"
      :alt="`Logo ${project.desc}`"
      class="w-full h-full object-cover"
    />
  </div>

  <div class="overlay absolute inset-0 bg-black bg-opacity-60 opacity-0 hover:opacity-100 transition-opacity duration-300 flex flex-col justify-center items-center text-center p-4 z-10">
    <h4 class="text-xl font-semibold text-white mb-2">{{ project.name }}</h4>
    <p class="text-gray-200">{{ project.desc }}</p>
  </div>
</component>




                </div>
            </div>
        </div>
    </section>
  </template>
  
  <script>
  import xyzHotel from "@/assets/images/XYZHotel.png";
  import dbWarga from "@/assets/images/DBWarga.png";
  import csw from "@/assets/images/CSW.png";
  export default {
    data() {
        return {
            projectList: [
                {
                    name: "XYZ Hotel",
                    desc: "Website booking hotel yang mudah dan cepat",
                    logo: xyzHotel
                },
                {
                    name: "cswservices.co.id",
                    desc: "Website resmi perusahaan Cakra Satria Wibawa",
                    logo: csw,
                    url :"https://cswservices.co.id/"
                },
                {
                    name: "DBDataWarga",
                    desc: "Website Pencatatan wargar desa",
                    logo: dbWarga
                },
            ],
        };
    },
  };
  </script>
  
  <style scoped>
        .project-card {
        width: 100%;
        max-width: 30rem;  
        height: 18rem;    
        position: relative;
        padding: 0; 
        transition: transform 0.3s ease-in-out; 
    }

        .image-container {
        width: 100%;
        height: 100%;
        position: relative;
        }

        .project-card img {
        object-fit: cover; 
        width: 100%;
        height: 100%;
        }

        .overlay {
        transition: opacity 0.3s ease-in-out;
        }

        .project-card:hover {
        transform: scale(1.05);
        }

        .project-container {
        display: flex;
        gap: 1rem;  
        flex-wrap: wrap; 
        }

  </style>
  