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
  margin-bottom: 2rem;
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
  top: 80%;
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
</style>
