<template>
  <nav class="navbar">
    <!-- logo -->
    <div>
      <img src="/logo.png" alt="My Photo" class="hero-img" />
    </div>

    <!-- menu -->
    <div class="menu">
      <ul>
        <li><a href="#about">ABOUT</a></li>
        <li><a href="#projects">PROJECTS</a></li>
        <li><a href="#contact">CONTACT</a></li>
        <li><a href="#more">MORE</a></li>
      </ul>
    </div>

    <!-- icons -->
    <div class="social-icons">
      <a href="https://github.com/apriljavier" target="_blank" class="icon">
        <i class="fab fa-github"></i>
      </a>
      <a href="https://www.linkedin.com/in/april-kate-javier-991023260/" target="_blank" class="icon">
        <i class="fab fa-linkedin"></i>
      </a>
    </div>
  </nav>
</template>



<style scoped>
.navbar {
  display: grid;
  grid-template-columns: 1fr auto 1fr; /* left | center | right */
  align-items: center;
  background: #0DADA3;
  padding: 1rem 2rem;
}

.hero-img {
  width: 50px;
  height: 50px;
  object-fit: cover;
}

.menu ul {
  display: flex;
  list-style: none;
  gap: 1.5rem;
  margin: 0;
  padding: 0;
  justify-content: center;
}

.menu a {
  color: white;
  text-decoration: none;
  font-weight: 500;
}

.social-icons {
  display: flex;
  justify-content: flex-end;
  gap: 1rem;
}

.icon {
  font-size: 1.5rem;
  color: white;
  transition: color 0.3s;
}

.icon:hover {
  color: #0a66c2;
}

</style>