<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="header-content">
      <div class="logo">
        <img alt="Your Logo" src="@/assets/logo.svg" width="125" height="125" />
      </div>
      <nav>
        <ul>
          <li><RouterLink to="/">Home</RouterLink></li>
          <li><RouterLink to="/about">Demos</RouterLink></li>
          <li><RouterLink to="/example">Contact</RouterLink></li>
        </ul>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  background-color: #007BFF;
  color: white;
  padding: 1rem 0;
}

.header-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

.logo img {
  display: block;
  width: 125px;
  height: 125px;
}

nav ul {
  list-style: none;
  display: flex;
  gap: 1rem;
  font-size: 1.2rem;
}

nav ul li {
  margin: 0;
}

nav a {
  text-decoration: none;
  color: white;
  transition: color 0.3s ease-in-out;
}

nav a:hover {
  color: #0056b3;
}

@media (max-width: 768px) {
  .header-content {
    flex-direction: column;
    align-items: flex-start;
  }

  nav ul {
    flex-direction: column;
    gap: 0.5rem;
  }

  .logo {
    margin-bottom: 1rem;
  }
}
</style>
