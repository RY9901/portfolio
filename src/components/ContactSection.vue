<template>
    <section id="contact" class="section">
      <h1 class="text-4xl font-bold">Contact Me</h1>
      <form class="contact-form mt-4" @submit.prevent="sendEmail">
        <div class="mb-3">
          <label for="name" class="form-label">Name</label>
          <input type="text" class="form-control" id="name" v-model="form.name" placeholder="Your Name" required>
        </div>
        <div class="mb-3">
          <label for="email" class="form-label">Email</label>
          <input type="email" class="form-control" id="email" v-model="form.email" placeholder="Your Email" required>
        </div>
        <div class="mb-3">
          <label for="message" class="form-label">Message</label>
          <textarea class="form-control" id="message" v-model="form.message" rows="4" placeholder="Your Message" required></textarea>
        </div>
        <button type="submit" class="btn btn-primary">Submit</button>
      </form>
    </section>
  </template>
  
  <script>
  import emailjs from 'emailjs-com';
  
  export default {
    name: 'ContactSection',
    data() {
      return {
        form: {
          name: '',
          email: '',
          message: ''
        }
      };
    },
    methods: {
      sendEmail() {
        const serviceID = 'service_qxckkbd';
        const templateID = 'template_kya2utg';
        const userID = 'wy6Jcki1zuRV6ABPY';
  
        emailjs.send(serviceID, templateID, this.form, userID)
          .then((response) => {
            this.form.name = '';
            this.form.email = '';
            this.form.message = '';
            alert('Email sent successfully!');
          }, (error) => {
            alert('Failed to send email. Please try again later.');
          });
      }
    }
  }
  </script>
  
  <style scoped>
  .section {
    padding: 60px 20px 20px;
    height: 95vh;
    text-align: center;
    background-image: url('@/assets/img/background.jpg'); /* Replace with your background image path */
    background-size: cover;
    background-position: center;
  }
  
  .contact-form {
    background-color: rgba(255, 255, 255, 0.8);
    padding: 20px;
    border-radius: 10px;
    border: 1px solid #ccc;
  }
  
  /* Apply height for larger screens */
  @media (min-width: 768px) {
    .contact-form {
      height: 75%;
    }
    .section {
        padding: 60px 100px 20px 100px;

  }
  }
  </style>