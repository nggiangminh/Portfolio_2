<template>
  <nav class="navbar" :class="{ 'navbar-scrolled': isScrolled }">
    <div class="container">
      <div class="navbar-content">
        <div class="navbar-brand">
          <h2 class="brand-text">MN</h2>
        </div>
        
        <div class="navbar-menu" :class="{ 'navbar-menu-open': isMenuOpen }">
          <a href="#about" class="nav-link" @click="closeMenu">About</a>
          <a href="#projects" class="nav-link" @click="closeMenu">Projects</a>
          <a href="#certificates" class="nav-link" @click="closeMenu">Certificates</a>
          <a href="#contact" class="nav-link" @click="closeMenu">Contact</a>
        </div>
        
        <div class="navbar-toggle" @click="toggleMenu">
          <span class="hamburger-line"></span>
          <span class="hamburger-line"></span>
          <span class="hamburger-line"></span>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      isScrolled: false,
      isMenuOpen: false
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll() {
      this.isScrolled = window.scrollY > 50
    },
    toggleMenu() {
      this.isMenuOpen = !this.isMenuOpen
    },
    closeMenu() {
      this.isMenuOpen = false
    }
  }
}
</script>

<style scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background-color: var(--color-secondary);
  border-bottom: 2px solid var(--color-border);
  z-index: 1000;
  transition: all var(--transition-medium);
}

.navbar-scrolled {
  background-color: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  box-shadow: var(--shadow-medium);
}

.navbar-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: var(--spacing-sm) 0;
}

.navbar-brand {
  display: flex;
  align-items: center;
}

.brand-text {
  font-family: var(--font-primary);
  font-size: 1.8rem;
  font-weight: 700;
  color: var(--color-primary);
  margin: 0;
  border: 3px solid var(--color-primary);
  padding: var(--spacing-xs) var(--spacing-sm);
  border-radius: var(--border-radius-sm);
  transition: all var(--transition-medium);
}

.brand-text:hover {
  background-color: var(--color-primary);
  color: var(--color-secondary);
  transform: scale(1.05);
}

.navbar-menu {
  display: flex;
  gap: var(--spacing-md);
  align-items: center;
}

.nav-link {
  color: var(--color-primary);
  text-decoration: none;
  font-family: var(--font-primary);
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1px;
  padding: var(--spacing-xs) var(--spacing-sm);
  border-radius: var(--border-radius-sm);
  transition: all var(--transition-medium);
  position: relative;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 50%;
  width: 0;
  height: 2px;
  background-color: var(--color-primary);
  transition: all var(--transition-medium);
  transform: translateX(-50%);
}

.nav-link:hover::after {
  width: 100%;
}

.nav-link:hover {
  color: var(--color-accent);
  transform: translateY(-2px);
}

.navbar-toggle {
  display: none;
  flex-direction: column;
  cursor: pointer;
  padding: var(--spacing-xs);
}

.hamburger-line {
  width: 25px;
  height: 3px;
  background-color: var(--color-primary);
  margin: 3px 0;
  border-radius: var(--border-radius-sm);
  transition: all var(--transition-medium);
}

/* Mobile Responsive */
@media (max-width: 768px) {
  .navbar-menu {
    position: fixed;
    top: 100%;
    left: 0;
    right: 0;
    background-color: var(--color-secondary);
    flex-direction: column;
    padding: var(--spacing-md);
    border-top: 2px solid var(--color-border);
    transform: translateY(-100%);
    opacity: 0;
    visibility: hidden;
    transition: all var(--transition-medium);
  }
  
  .navbar-menu-open {
    transform: translateY(0);
    opacity: 1;
    visibility: visible;
  }
  
  .navbar-toggle {
    display: flex;
  }
  
  .navbar-menu-open .hamburger-line:nth-child(1) {
    transform: rotate(45deg) translate(5px, 5px);
  }
  
  .navbar-menu-open .hamburger-line:nth-child(2) {
    opacity: 0;
  }
  
  .navbar-menu-open .hamburger-line:nth-child(3) {
    transform: rotate(-45deg) translate(7px, -6px);
  }
}
</style>
