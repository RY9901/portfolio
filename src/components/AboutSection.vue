<template>
  <section id="about" class="section">
    <h1 class="text-4xl font-bold mb-8">About Me</h1>
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
    <div id="timeline"></div>
    <div class="content-container">
      <div class="content-item">
        <img src="@/assets/img/raziq.jpg" alt="Description 1" class="content-image">
        <div class="content-description">
          <h2>Title 1</h2>
          <p>Description for the first item goes here.</p>
        </div>
      </div>
      <div class="content-item reverse">
        <div class="content-description">
          <h2>Title 2</h2>
          <p>Description for the second item goes here.</p>
        </div>
        <img src="@/assets/img/raziq.jpg" alt="Description 2" class="content-image">
      </div>
      <div class="content-item">
        <img src="@/assets/img/raziq.jpg" alt="Description 3" class="content-image">
        <div class="content-description">
          <h2>Title 3</h2>
          <p>Description for the third item goes here.</p>
        </div>
      </div>
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
    const events = [
      { date: '2020', content: 'Started new job' },
      { date: '2021', content: 'Promoted to senior developer' },
      { date: '2022', content: 'Started leading a team' },
      { date: '2023', content: 'Launched a major project' }
    ];
    $('#timeline').roadmap(events, {
      eventsPerSlide: 4,
      slide: 1,
      prevArrow: '<button type="button" class="roadmap-prev">Previous</button>',
      nextArrow: '<button type="button" class="roadmap-next">Next</button>'
    });


  }
}
</script>

<style scoped>
.section {
  padding: 60px 20px 20px;
  height: 300%;
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

.content-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.content-item {
  display: flex;
  align-items: center;
  margin: 20px 0;
  width: 80%;
}

.content-item .reverse {
  flex-direction: row-reverse;
}

.content-image {
  width: 40%;
  height: auto;
  border-radius: 8px;
  margin: 0 20px;
}

.content-description {
  width: 60%;
  text-align: left;
}

.content-description h2 {
  margin: 0 0 10px;
  font-size: 1.5rem;
  color: #333;
}

.content-description p {
  margin: 0;
  color: #666;
}
</style>