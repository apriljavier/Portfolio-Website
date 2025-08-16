<template>
  <div id="app">
    <!-- normal navbar -->
     <Navbar v-show="!showFloatingNavbar" class="normal-navbar" />
    <!-- floating navbar -->
    <div v-show="showFloatingNavbar" class="floating-navbar">
      <ul>
        <li><a href="#about">ABOUT</a></li>
        <li><a href="#projects">PROJECTS</a></li>
        <li><a href="#contact">CONTACT</a></li>
        <li><a href="#more">MORE</a></li>
      </ul>
    </div> 
    <!-- <Navbar /> -->
    <section class="hero">
      <img src="/profile.png" alt="My Photo" class="hero-img" />
      <!-- floating circles -->
      <div class="floating-circle circle1">Web Developer</div>
      <div class="floating-circle circle2">Quality Assurance</div>
      <div class="floating-circle circle3">UI/UX</div>
    </section>
    <section id="about" class="about-section">
      <div class="content">
        <h2>About Me</h2>
        <p>
          insert about me here
        </p>
      </div>
    </section>
    <section id="projects" class="projects-section">
      <div class="content">
        <h2>Projects</h2>
        <p>
          insert projects here
        </p>
      </div>
    </section>
    <section id="contact" class="contact-section">
      <div class="content">
        <h2>Contact</h2>
        <p>
          insert contact here
        </p>
      </div>
    </section>
    <section id="more" class="more-section">
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
    <button 
      v-show="showTopButton" 
      @click="scrollToTop" 
      class="back-to-top"
    >
      ↑
    </button>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'

export default {
  components: { Navbar },
  data() {
    return {
      showTopButton: false,
      showFloatingNavbar: false
    }
  },
  methods: {
    scrollToTop() {
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }
  },
  mounted() {
    // section slide-up observer
    const sections = document.querySelectorAll("section");
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add("show-section");
        }
      });
    }, { threshold: 0.1 });

    sections.forEach(section => {
      observer.observe(section);
    });

    // back-to-top visibility
    window.addEventListener("scroll", () => {
      this.showTopButton = window.scrollY > 300;
      this.showFloatingNavbar = window.scrollY > 100;
    });
  }
}
</script>


<style>
section {
  opacity: 0;
  transform: translateY(50px);
  transition: all 0.8s ease-out;
}

section.show-section {
  opacity: 1;
  transform: translateY(0);
}

.hero {
  display: flex;
  flex-direction: column;  
  justify-content: center; 
  align-items: center;     
  height: calc(100vh - 80px); 
  text-align: center;
  position: relative;
  overflow: hidden;
  z-index: 1;
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
  border-radius: 9999px;
  background: rgba(255, 255, 255, 0.1);
  border: 2px solid rgba(255, 255, 255, 0.3);
  color: white;
  font-size: 1.2rem;
  font-weight: bold;
  text-align: center;
  backdrop-filter: blur(6px);
  white-space: nowrap;
}
.circle1 { top: 40%; left: 35%; transform: translate(-50%, -50%); animation: float1 6s ease-in-out infinite; }
.circle2 { top: 75%; left: 52%; transform: translate(-50%, -50%); animation: float2 7s ease-in-out infinite; }
.circle3 { top: 50%; left: 65%; transform: translate(-50%, -50%); animation: float3 8s ease-in-out infinite; }

/* float animations */
@keyframes float1 { 0%, 100% { transform: translate(-50%, -50%) translateY(0); } 50% { transform: translate(-50%, -50%) translateY(-6px); } }
@keyframes float2 { 0%, 100% { transform: translate(-50%, -50%) translateY(0); } 50% { transform: translate(-50%, -50%) translateY(6px); } }
@keyframes float3 { 0%, 100% { transform: translate(-50%, -50%) translate(0, 0); } 50% { transform: translate(-50%, -50%) translate(6px, -6px); } }

/* floating navbar */
.floating-navbar {
  position: fixed;
  top: 2rem;
  left: 50%;
  transform: translateX(-50%);
  z-index: 2000;
  display: flex;
  /* background: rgba(255, 255, 255, 0.1);
  border: 2px solid rgba(255, 255, 255, 0.3); */
  backdrop-filter: blur(6px);
  padding: 0.6rem 1.2rem;
  border-radius: 9999px;
  animation: floatNav 6s ease-in-out infinite;
}
.floating-navbar ul {
  display: flex;
  gap: 1rem;
  list-style: none;
  margin: 0;
  padding: 10px;
}
.floating-navbar a {
  padding: 0.6rem 1.2rem;
  border-radius: 9999px;
  background: rgba(255, 255, 255, 0.15);
  border: 1px solid rgba(255, 255, 255, 0.3);
  color: white;
  font-weight: bold;
  backdrop-filter: blur(6px);
  transition: background 0.3s;
  text-decoration: none;
}
.floating-navbar a:hover { background: rgba(255, 255, 255, 0.3); }
@keyframes floatNav {
  0%, 100% { transform: translateX(-50%) translateY(0); }
  50% { transform: translateX(-50%) translateY(-6px); }
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


.back-to-top {
  position: fixed;
  bottom: 2rem;
  right: 2rem;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: #0DADA3;
  color: white;
  border: none;
  font-size: 1.2rem;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0 4px 6px rgba(0,0,0,0.3);
  transition: opacity 0.3s, transform 0.3s;
  opacity: 0.8;
  z-index: 1000;
}

.back-to-top:hover {
  opacity: 1;
  transform: scale(1.1);
}

</style>
