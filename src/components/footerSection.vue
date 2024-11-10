<template>
    <footer class="footer">
      <div class="container">
        <div class="row">
          <div class="col-md-6">
            <h5>About Me</h5>
            <p>This is a brief description about me. You can add more details here.</p>
          </div>
          <div class="col-md-6">
            <h5>Contact</h5>
            <ul class="list-unstyled">
              <li><a href="mailto:raziqyusri@example.com">raziqyusri@gmail.com</a></li>
              <li><a href="https://www.linkedin.com/in/muhammad-raziq-yusri-026995165" target="_blank">LinkedIn</a></li>
              <li><a href="https://github.com/RY9901" target="_blank">GitHub</a></li>
            </ul>
          </div>
        </div>
        <div class="text-center mt-4">
          <p>&copy; 2024 Raziq, All rights reserved.</p> 
        </div>
      </div>
    </footer>
  </template>
  
  <script>
  export default {
    name: 'FooterSection'
  }
  </script>
  
  <style scoped>
  .footer {
    background-color: #333;
    color: white;
    padding: 20px 0;
  }
  
  .footer h5 {
    font-size: 1.25rem;
    margin-bottom: 1rem;
  }
  
  .footer p {
    margin-bottom: 0.5rem;
  }
  
  .footer a {
    text-decoration: none;
  }
  
  .footer a:hover {
    text-decoration: underline;
  }
  
  .footer .container {
    max-width: 960px;
    margin: 0 auto;
  }
  
  .footer .row {
    display: flex;
    flex-wrap: wrap;
  }
  
  .footer .col-md-6 {
    flex: 0 0 50%;
    max-width: 50%;
    padding: 0 15px;
  }
  
  .footer .text-center {
    margin-top: 20px;
  }
  </style>