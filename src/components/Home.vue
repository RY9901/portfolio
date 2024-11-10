<template>
    <div class="home">
      <nav class="navbar">
        <ul class="nav-list">
          <li><a href="#home" @click.prevent="scrollToSection('home')">Home</a></li>
          <li><a href="#about" @click.prevent="scrollToSection('about')">About</a></li>
          <li><a href="#projects" @click.prevent="scrollToSection('projects')">Projects</a></li>
          <li><a href="#contact" @click.prevent="scrollToSection('contact')">Contact</a></li>
        </ul>
      </nav>
      <home-section></home-section>
      <about-section></about-section>
      <projects-section></projects-section>
      <contact-section></contact-section>
      <footer-section></footer-section>
    </div>
  </template>
  
  <script>
  import HomeSection from '@/components/HomeSection.vue'
  import AboutSection from '@/components/AboutSection.vue'
  import ProjectsSection from '@/components/ProjectsSection.vue'
  import ContactSection from '@/components/ContactSection.vue'
  import FooterSection from '@/components/footerSection.vue'

  
  export default {
    name: 'Home',
    components: {
      HomeSection,
      AboutSection,
      ProjectsSection,
      ContactSection,
      FooterSection,
    },
    methods: {
      scrollToSection(sectionId) {
        const section = document.getElementById(sectionId);
        if (section) {
          const navbarHeight = document.querySelector('.navbar').offsetHeight;
          const sectionTop = section.getBoundingClientRect().top + window.scrollY - navbarHeight;
          window.scrollTo({ top: sectionTop, behavior: 'smooth' });
        }
      }
    }
  }
  </script>
  
  <style scoped>
  .home {
    text-align: center;
    position: relative;
  }
  
  .navbar {
    position: sticky;
    width: 100%;     
    top: 0;
    background-color: #333;
    z-index: 1000;
    padding: 10px 20px;
  }
  
  .nav-list {
    list-style-type: none;
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: flex-end;
    width: 100%;
  }
  
  .nav-list li {
    display: inline;
  }
  
  .nav-list li a {
    display: block;
    color: white;
    text-align: center;
    padding: 14px 16px;
    text-decoration: none;
  }

  
  html {
    scroll-behavior: smooth;
  }
  </style>