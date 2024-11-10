<template>
  <section id="home" class="section d-flex align-items-center">
    <div class="container-fluid">
      <div class="row w-100 mr-0 ml-0">
        <div class="col-xs-4 col-md-6 d-flex justify-content-center align-items-center">
          <img src="@/assets/img/raziq.jpg" alt="Your Picture" class="img-fluid profile-picture">
        </div>
        <div class="col-xs-6 col-md-6 d-flex flex-column justify-content-center align-items-center">
          <h1 class="font-bold">
            <span id="typed-output"></span>
          </h1>
          <p class="mt-4">A dedicated full-stack developer with a passion for continuous learning and growth in the tech world. I thrive on solving complex problems, building intuitive, user-centered applications, and expanding my skill set across front-end and back-end development. Driven by curiosity and a commitment to quality, I’m always seeking new challenges to elevate my expertise and make a positive impact through technology.</p>
          <div class="social-icons mt-4">
            <a href="https://www.linkedin.com/in/muhammad-raziq-yusri-026995165" target="_blank" class="me-3">
              <font-awesome-icon :icon="['fab', 'linkedin']" size="2x" />
            </a>
            <a href="https://github.com/RY9901" target="_blank">
              <font-awesome-icon :icon="['fab', 'github']" size="2x" />
            </a>
          </div>
          <a :href="cvLink" download class="btn btn-primary mt-4">Download CV</a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { library } from '@fortawesome/fontawesome-svg-core'
import { faLinkedin, faGithub } from '@fortawesome/free-brands-svg-icons'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import Typed from 'typed.js'

library.add(faLinkedin, faGithub)

export default {
  name: 'HomeSection',
  components: {
    FontAwesomeIcon
  },
  data() {
    return {
      cvLink: ''
    }
  },
  mounted() {
    import('@/assets/cv/Muhammad_Raziq_CV.pdf').then(module => {
      this.cvLink = module.default
    })

    const options = {
      strings: ["Hi, my name is Muhammad Raziq"],
      typeSpeed: 50,
      backSpeed: 25,
      loop: true
    };

    new Typed('#typed-output', options);
  }
}
</script>

<style scoped>
.section {
  height: 100vh;
  background-image: url('@/assets/img/background.jpg'); /* Replace with your background image path */
  background-size: cover;
  background-position: center;
  display: flex;
  justify-content: center;
  align-items: center;
}

h1 {
  font-size: 2rem;
}

@media (min-width: 768px) {
    .profile-picture {
    max-width: 800px;
    border-radius: 10%;
  }
  h1 {
    font-size: rem; 
  }
}

@media (min-width: 1024px) {
  h1 {
    font-size: 2rem;
  }
}

.profile-picture {
  border-radius: 10%;
}

.social-icons a {
  color: #333;
  transition: color 0.3s;
}

.social-icons a:hover {
  color: #0077b5;
}

.social-icons a.me-3:hover {
  color: #333;
}

.btn-primary {
  background-color: #007bff;
  border-color: #007bff;
}

.btn-primary:hover {
  background-color: #0056b3;
  border-color: #004085;
}
</style>