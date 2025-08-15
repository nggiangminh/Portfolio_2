<template>
  <section id="projects" class="section projects-section">
    <div class="container">
      <h2 class="section-title">Featured Projects</h2>
      <p class="section-subtitle">A showcase of my recent work and contributions</p>
      
      <div class="projects-grid">
        <div class="project-card" v-for="project in projects" :key="project.id">
          <div class="project-image">
            <div class="project-placeholder">
              <span class="project-icon">{{ project.icon }}</span>
            </div>
            <div class="project-overlay">
              <div class="project-links">
                <a :href="project.demo" target="_blank" class="project-link" v-if="project.demo">
                  <span class="link-icon">🌐</span>
                  Demo
                </a>
                <a :href="project.github" target="_blank" class="project-link" v-if="project.github">
                  <span class="link-icon">📁</span>
                  Code
                </a>
              </div>
            </div>
          </div>
          
          <div class="project-content">
            <h3 class="project-title">{{ project.title }}</h3>
            <p class="project-description">{{ project.description }}</p>
            
            <div class="project-tech">
              <span class="tech-tag" v-for="tech in project.technologies" :key="tech">
                {{ tech }}
              </span>
            </div>
            
            <div class="project-features">
              <ul>
                <li v-for="feature in project.features" :key="feature">{{ feature }}</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
      
      <div class="projects-cta">
        <p>Interested in working together?</p>
        <a href="#contact" class="btn">Let's Connect</a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Projects',
  data() {
    return {
      projects: [
        {
          id: 1,
          title: 'E-Commerce Platform',
          description: 'A full-stack e-commerce solution with modern UI/UX, payment integration, and admin dashboard.',
          icon: '🛒',
          technologies: ['Vue.js', 'Node.js', 'MongoDB', 'Stripe'],
          features: [
            'Responsive design with mobile-first approach',
            'Secure payment processing',
            'Real-time inventory management',
            'Admin analytics dashboard'
          ],
          demo: 'https://demo-ecommerce.com',
          github: 'https://github.com/username/ecommerce'
        },
        {
          id: 2,
          title: 'Task Management App',
          description: 'Collaborative task management application with real-time updates and team collaboration features.',
          icon: '📋',
          technologies: ['React', 'Spring Boot', 'PostgreSQL', 'WebSocket'],
          features: [
            'Real-time collaboration',
            'Task assignment and tracking',
            'Progress visualization',
            'Team performance metrics'
          ],
          demo: 'https://task-app-demo.com',
          github: 'https://github.com/username/taskapp'
        },
        {
          id: 3,
          title: 'Portfolio Website',
          description: 'Personal portfolio website built with modern web technologies and responsive design.',
          icon: '🎨',
          technologies: ['Vue.js', 'CSS3', 'JavaScript', 'Vite'],
          features: [
            'Responsive design',
            'Smooth animations',
            'SEO optimized',
            'Performance focused'
          ],
          demo: null,
          github: 'https://github.com/username/portfolio'
        },
        {
          id: 4,
          title: 'Weather Dashboard',
          description: 'Real-time weather application with location-based forecasts and interactive maps.',
          icon: '🌤️',
          technologies: ['JavaScript', 'OpenWeather API', 'Leaflet.js', 'CSS3'],
          features: [
            'Location-based weather',
            'Interactive maps',
            '5-day forecast',
            'Weather alerts'
          ],
          demo: 'https://weather-dashboard.com',
          github: 'https://github.com/username/weather'
        },
        {
          id: 5,
          title: 'Blog CMS',
          description: 'Content management system for blogs with markdown support and SEO optimization.',
          icon: '✍️',
          technologies: ['Next.js', 'Node.js', 'MySQL', 'Markdown'],
          features: [
            'Markdown editor',
            'SEO optimization',
            'Category management',
            'Comment system'
          ],
          demo: 'https://blog-cms-demo.com',
          github: 'https://github.com/username/blog-cms'
        },
        {
          id: 6,
          title: 'Chat Application',
          description: 'Real-time chat application with user authentication and file sharing capabilities.',
          icon: '💬',
          technologies: ['Vue.js', 'Socket.io', 'Express', 'MongoDB'],
          features: [
            'Real-time messaging',
            'File sharing',
            'User authentication',
            'Online status tracking'
          ],
          demo: 'https://chat-app-demo.com',
          github: 'https://github.com/username/chatapp'
        }
      ]
    }
  }
}
</script>

<style scoped>
.projects-section {
  background-color: var(--color-secondary);
  padding-top: calc(var(--spacing-xl) + 80px);
}

.section-subtitle {
  text-align: center;
  color: var(--color-medium-gray);
  font-size: 1.1rem;
  margin-bottom: var(--spacing-xl);
  max-width: 600px;
  margin-left: auto;
  margin-right: auto;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: var(--spacing-lg);
  margin-bottom: var(--spacing-xl);
}

.project-card {
  background-color: var(--color-secondary);
  border: 2px solid var(--color-border);
  border-radius: var(--border-radius-md);
  overflow: hidden;
  box-shadow: var(--shadow-light);
  transition: all var(--transition-medium);
  position: relative;
}

.project-card:hover {
  transform: translateY(-10px);
  box-shadow: var(--shadow-heavy);
  border-color: var(--color-primary);
}

.project-image {
  position: relative;
  height: 200px;
  background-color: var(--color-light-gray);
  overflow: hidden;
}

.project-placeholder {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
}

.project-icon {
  font-size: 4rem;
  opacity: 0.8;
}

.project-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.8);
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  transition: all var(--transition-medium);
}

.project-card:hover .project-overlay {
  opacity: 1;
}

.project-links {
  display: flex;
  gap: var(--spacing-sm);
}

.project-link {
  display: flex;
  align-items: center;
  gap: var(--spacing-xs);
  background-color: var(--color-secondary);
  color: var(--color-primary);
  text-decoration: none;
  padding: var(--spacing-sm) var(--spacing-md);
  border-radius: var(--border-radius-sm);
  font-weight: 600;
  transition: all var(--transition-fast);
}

.project-link:hover {
  background-color: var(--color-primary);
  color: var(--color-secondary);
  transform: scale(1.05);
}

.link-icon {
  font-size: 1.2rem;
}

.project-content {
  padding: var(--spacing-md);
}

.project-title {
  color: var(--color-primary);
  margin-bottom: var(--spacing-sm);
  font-size: 1.5rem;
}

.project-description {
  color: var(--color-medium-gray);
  margin-bottom: var(--spacing-md);
  line-height: 1.6;
}

.project-tech {
  display: flex;
  flex-wrap: wrap;
  gap: var(--spacing-xs);
  margin-bottom: var(--spacing-md);
}

.tech-tag {
  background-color: var(--color-light-gray);
  color: var(--color-primary);
  padding: var(--spacing-xs) var(--spacing-sm);
  border-radius: var(--border-radius-sm);
  font-size: 0.8rem;
  font-weight: 600;
  border: 1px solid var(--color-border);
}

.project-features {
  margin-top: var(--spacing-md);
}

.project-features ul {
  list-style: none;
  padding: 0;
}

.project-features li {
  color: var(--color-medium-gray);
  margin-bottom: var(--spacing-xs);
  padding-left: var(--spacing-sm);
  position: relative;
  font-size: 0.9rem;
}

.project-features li::before {
  content: '▶';
  position: absolute;
  left: 0;
  color: var(--color-primary);
  font-size: 0.8rem;
}

.projects-cta {
  text-align: center;
  padding: var(--spacing-lg);
  background-color: var(--color-light-gray);
  border-radius: var(--border-radius-md);
  border: 2px solid var(--color-border);
}

.projects-cta p {
  color: var(--color-medium-gray);
  margin-bottom: var(--spacing-md);
  font-size: 1.1rem;
}

/* Responsive Design */
@media (max-width: 768px) {
  .projects-grid {
    grid-template-columns: 1fr;
    gap: var(--spacing-md);
  }
  
  .project-card {
    margin-bottom: var(--spacing-md);
  }
  
  .project-links {
    flex-direction: column;
    gap: var(--spacing-xs);
  }
  
  .project-link {
    justify-content: center;
  }
}
</style>
