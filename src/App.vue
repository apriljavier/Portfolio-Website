<template>
  <div id="app">
    <Navbar />
    <section class="hero">
      <img src="/profile.png" alt="My Photo" class="hero-img" />
      <!-- floating circles -->
      <div class="floating-circle circle1">Web Developer</div>
      <div class="floating-circle circle2">Quality Assurance</div>
      <div class="floating-circle circle3">UI/UX</div>
    </section>
    <section class="about-section">
      <div class="content">
        <h2>About Me</h2>
        <p>
          insert about me here
        </p>
      </div>
    </section>
    <section class="projects-section">
      <div class="content">
        <h2>Projects</h2>
        <p>
          insert projects here
        </p>
      </div>
    </section>
    <section class="contact-section">
      <div class="content">
        <h2>Contact</h2>
        <p>
          insert contact here
        </p>
      </div>
    </section>
    <section class="more-section">
      <div class="content">
        <h2>More</h2>
        <p>
          insert more here
        </p>
      </div>
      <div class="footer">
        <p>© 2025 April Kate M Javier. All rights reserved.</p>
      </div>
    </section>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'

export default {
  components: { Navbar }
}
</script>

<style>
.hero {
  display: flex;
  flex-direction: column;  
  justify-content: center; 
  align-items: center;     
  height: calc(100vh - 80px); 
  text-align: center;
  position: relative;
  overflow: hidden;
}

.hero-img {
  width: 500px;
  height: 500px;
  object-fit: cover;
  transform: translateY(-10%);
}

/* floating circles base */
.floating-circle {
  position: absolute;
  padding: 1.5rem 4rem;
  border-radius: 9999px; /* pill shape */
  background: rgba(255, 255, 255, 0.1);
  border: 2px solid rgba(255, 255, 255, 0.3);
  color: white;
  font-size: 1.2rem;
  font-weight: bold;
  text-align: center;
  backdrop-filter: blur(6px);
  white-space: nowrap;
}

.circle1 {
  top: 40%;
  left: 35%;
  transform: translate(-50%, -50%);
  animation: float1 6s ease-in-out infinite;
}

.circle2 {
  top: 75%;
  left: 52%;
  transform: translate(-50%, -50%);
  animation: float2 7s ease-in-out infinite;
}

.circle3 {
  top: 50%;
  left: 65%;
  transform: translate(-50%, -50%);
  animation: float3 8s ease-in-out infinite;
}

/* Irregular Float Animations */
@keyframes float1 {
  0%, 100% { transform: translate(-50%, -50%) translateY(0); }
  50% { transform: translate(-50%, -50%) translateY(-6px); }
}

@keyframes float2 {
  0%, 100% { transform: translate(-50%, -50%) translateY(0); }
  50% { transform: translate(-50%, -50%) translateY(6px); }
}

@keyframes float3 {
  0%, 100% { transform: translate(-50%, -50%) translate(0, 0); }
  50% { transform: translate(-50%, -50%) translate(6px, -6px); }
}

/* ABOUT SECTION */
.about-section {
  background-color: #00302D; /* dark teal */
  color: white;
  padding: 4rem 2rem;
  text-align: center;
  border-top-right-radius: 100px;
  border: 2px solid white;
  border-left: none;
  border-bottom: none;
}

.about-section .content {
  max-width: 800px;
  height: 800px;
  margin: 0 auto;
}
/* PROJECTS SECTION */
.projects-section {
  background-color: #00302D;
  color: white;
  padding: 4rem 2rem;
  text-align: center;
  border-top-left-radius: 100px;
  border: 2px solid white;
  border-right: none;
  border-bottom: none;
}

.projects-section .content {
  max-width: 800px;
  height: 800px;
  margin: 0 auto;
}
/* CONTACT SECTION */
.contact-section {
  background-color: #00302D;
  color: white;
  padding: 4rem 2rem;
  text-align: center;
  border-top-right-radius: 100px;
  border: 2px solid white;
  border-left: none;
  border-bottom: none;
}

.contact-section .content {
  max-width: 800px;
  height: 800px;
  margin: 0 auto;
}
/* MORE SECTION */
.more-section {
  background-color: #00302D;
  color: white;
  padding: 4rem 2rem;
  text-align: center;
  border-top-left-radius: 100px;
  border: 2px solid white;
  border-right: none;
  border-bottom: none;
}

.more-section .content {
  max-width: 800px;
  height: 800px;
  margin: 0 auto;
}
section {
  position: sticky;
  top: 0;
  min-height: 100vh;
}

/* layer order */
.hero {
  z-index: 1;
}

.about-section {
  z-index: 2;
}

.projects-section {
  z-index: 3;
}
.contact-section {
  z-index: 4;
}
.more-section {
  z-index: 5;
}

</style>
