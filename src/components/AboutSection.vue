<template>
    <section id="about" class="section">
      <h1 class="text-4xl font-bold">About Me</h1>
      <div class="marquee" data-speed="0.1">
        <div class="marquee__inner">
          <div class="icon-wrapper">
            <div class="d-flex flex-column">
                <font-awesome-icon :icon="['fab', 'angular']" class="icon angular" />
                ANGULAR
            </div>
            <div class="d-flex flex-column">
                <font-awesome-icon :icon="['fab', 'react']" class="icon react" />
                REACT
            </div>
            <div class="d-flex flex-column">
                <font-awesome-icon :icon="['fab', 'vuejs']" class="icon vue" />
                VUE
            </div>
            <div class="d-flex flex-column">
                <font-awesome-icon :icon="['fab', 'html5']" class="icon html" />
                HTML
            </div>
            <div class="d-flex flex-column">
                <font-awesome-icon :icon="['fab', 'css3-alt']" class="icon css" />
                CSS
            </div>
            <div class="d-flex flex-column">
                <font-awesome-icon :icon="['fab', 'js']" class="icon js" />
                JAVASCRIPT
            </div>
            <div class="d-flex flex-column">
                <font-awesome-icon :icon="['fab', 'java']" class="icon java" />
                JAVA
            </div>
          </div>
        </div>
      </div>
      <div>
        <p class="mt-4">This is the about page.</p>
      </div>
    </section>
  </template>
  
  <script>
  import { library } from '@fortawesome/fontawesome-svg-core'
  import { faAngular, faReact, faVuejs, faHtml5, faCss3Alt, faJs, faJava } from '@fortawesome/free-brands-svg-icons'
  import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
  
  library.add(faAngular, faReact, faVuejs, faHtml5, faCss3Alt, faJs, faJava)
  
  export default {
    name: 'AboutSection',
    components: {
      FontAwesomeIcon
    },
    mounted() {
      if (typeof Marquee3k !== 'undefined') {
        Marquee3k.init();
      } else {
        console.error('Marquee3k is not defined');
      }
    }
  }
  </script>
  
  <style scoped>
  .section {
    padding: 60px 20px 20px;
    height: 100vh;
    text-align: center;
    background-image: url('@/assets/img/background.jpg'); /* Replace with your background image path */
    background-size: cover;
    background-position: center;
  }
  
    .marquee {
    overflow: hidden;
    position: relative;
    width: 80%;
    margin: auto;
    }
  
    .marquee__inner {
    display: flex;
    animation: marquee 20s linear infinite;
    }
  
  @keyframes marquee {
    0% {
      transform: translateX(100%);
    }
    100% {
      transform: translateX(-100%);
    }
  }
  
  .icon-wrapper {
    display: flex;
    position: relative;
  }
  
  .icon {
    font-size: 10rem;
    margin: 20px;
  }
  
  .angular {
    color: #dd0031;
  }
  
  .react {
    color: #61dafb;
  }
  
  .vue {
    color: #42b883;
  }
  
  .html {
    color: #e34f26;
  }
  
  .css {
    color: #1572b6;
  }
  
  .js {
    color: #f7df1e;
  }
  
  .java {
    color: #007396;
  }
  </style>