<template>
  <div id="app">
    <Navbar />
    <main>
      <About />
      <Projects />
      <Certificate />
      <Contact />
    </main>
    <footer class="footer">
      <div class="container">
        <p>&copy; 2025 Minh Nguyen. All rights reserved.</p>
      </div>
    </footer>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import About from './components/About.vue'
import Projects from './components/Projects.vue'
import Certificate from './components/Certificate.vue'
import Contact from './components/Contact.vue'

export default {
  name: 'App',
  components: { 
    Navbar, 
    About, 
    Projects, 
    Certificate,
    Contact 
  }
}
</script>

<style>
#app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

main {
  flex: 1;
}

.footer {
  background-color: var(--color-primary);
  color: var(--color-secondary);
  text-align: center;
  padding: var(--spacing-md) 0;
  margin-top: auto;
}

.footer p {
  color: var(--color-secondary);
  margin: 0;
  font-size: 0.9rem;
}
</style>
