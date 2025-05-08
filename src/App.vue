
<template>
<div class="bg-[#111827] min-h-screen">
  <Navbar/>
  <HeroSection/>
  <AboutSection/>
  <SkillsSection/>
  <ProjectsSection/>
  <ContactSection/>
  <foot/>
</div>
</template>

<script setup>
import {defineAsyncComponent} from 'vue';
const Navbar = defineAsyncComponent(()=>import('@/components/Navbar.vue'));
const HeroSection = defineAsyncComponent(()=>import('@/components/HeroSection.vue'));
const AboutSection = defineAsyncComponent(()=>import('@/components/AboutSection.vue'));
const SkillsSection = defineAsyncComponent(()=>import('@/components/SkillsSection.vue'));
const ProjectsSection = defineAsyncComponent(()=>import('@/components/ProjectsSection.vue'));
const ContactSection = defineAsyncComponent(()=>import('@/components/ContactMe.vue'));
const foot = defineAsyncComponent(()=>import('@/components/footer.vue'));
</script>
