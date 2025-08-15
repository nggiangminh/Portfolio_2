<template>
  <section id="about" class="section about-section">
    <div class="container">
      <div class="about-content">
        <div class="hero-section">
          <div class="hero-text">
            <h1 class="hero-title">
              <span class="title-line">Hello, I'm</span>
              <span class="title-highlight">Minh Nguyen</span>
            </h1>
            <p class="hero-subtitle">Full-Stack Developer & Creative Problem Solver</p>
            <div class="hero-description">
              <p>Passionate about creating elegant solutions and building meaningful applications that make a difference.</p>
            </div>
            <div class="hero-actions">
              <a href="#projects" class="btn">View My Work</a>
              <a href="#contact" class="btn btn-secondary">Get In Touch</a>
            </div>
          </div>
          
          <div class="hero-visual">
            <div class="profile-frame">
              <div class="profile-placeholder">
                <span class="profile-icon">👨‍💻</span>
              </div>
            </div>
          </div>
        </div>
        
        <div class="skills-section">
          <h2 class="section-title">Skills & Expertise</h2>
          <div class="skills-grid">
            <div class="skill-category">
              <h3>Frontend</h3>
              <div class="skill-tags">
                <span class="skill-tag">Vue.js</span>
                <span class="skill-tag">React</span>
                <span class="skill-tag">JavaScript</span>
                <span class="skill-tag">CSS3</span>
                <span class="skill-tag">HTML5</span>
              </div>
            </div>
            
            <div class="skill-category">
              <h3>Backend</h3>
              <div class="skill-tags">
                <span class="skill-tag">Node.js</span>
                <span class="skill-tag">Python</span>
                <span class="skill-tag">Java</span>
                <span class="skill-tag">Spring Boot</span>
                <span class="skill-tag">Express</span>
              </div>
            </div>
            
            <div class="skill-category">
              <h3>Tools & Others</h3>
              <div class="skill-tags">
                <span class="skill-tag">Git</span>
                <span class="skill-tag">Docker</span>
                <span class="skill-tag">AWS</span>
                <span class="skill-tag">MongoDB</span>
                <span class="skill-tag">PostgreSQL</span>
              </div>
            </div>
          </div>
        </div>
        
        <div class="experience-section">
          <h2 class="section-title">Experience</h2>
          <div class="timeline">
            <div class="timeline-item">
              <div class="timeline-marker"></div>
              <div class="timeline-content">
                <h3>Senior Developer</h3>
                <p class="company">Tech Company</p>
                <p class="period">2023 - Present</p>
                <p>Leading development teams and architecting scalable solutions.</p>
              </div>
            </div>
            
            <div class="timeline-item">
              <div class="timeline-marker"></div>
              <div class="timeline-content">
                <h3>Full-Stack Developer</h3>
                <p class="company">Startup</p>
                <p class="period">2021 - 2023</p>
                <p>Built and maintained web applications using modern technologies.</p>
              </div>
            </div>
            
            <div class="timeline-item">
              <div class="timeline-marker"></div>
              <div class="timeline-content">
                <h3>Junior Developer</h3>
                <p class="company">Digital Agency</p>
                <p class="period">2020 - 2021</p>
                <p>Developed responsive websites and learned industry best practices.</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'About'
}
</script>

<style scoped>
.about-section {
  padding-top: calc(var(--spacing-xl) + 80px);
  background: linear-gradient(135deg, var(--color-light-gray) 0%, var(--color-secondary) 100%);
}

.hero-section {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--spacing-xl);
  align-items: center;
  margin-bottom: var(--spacing-xl);
}

.hero-title {
  font-size: 3.5rem;
  line-height: 1.1;
  margin-bottom: var(--spacing-md);
}

.title-line {
  display: block;
  color: var(--color-medium-gray);
  font-weight: 400;
}

.title-highlight {
  display: block;
  color: var(--color-primary);
  font-weight: 700;
  text-shadow: 2px 2px 0px var(--color-accent);
}

.hero-subtitle {
  font-size: 1.5rem;
  color: var(--color-accent);
  margin-bottom: var(--spacing-md);
  font-family: var(--font-primary);
  text-transform: uppercase;
  letter-spacing: 2px;
}

.hero-description {
  margin-bottom: var(--spacing-lg);
}

.hero-description p {
  font-size: 1.1rem;
  line-height: 1.7;
  color: var(--color-medium-gray);
}

.hero-actions {
  display: flex;
  gap: var(--spacing-md);
  flex-wrap: wrap;
}

.hero-visual {
  display: flex;
  justify-content: center;
  align-items: center;
}

.profile-frame {
  width: 300px;
  height: 300px;
  border: 4px solid var(--color-primary);
  border-radius: var(--border-radius-lg);
  background-color: var(--color-secondary);
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: var(--shadow-heavy);
  position: relative;
  overflow: hidden;
}

.profile-frame::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: linear-gradient(45deg, transparent, var(--color-light-gray), transparent);
  animation: shine 3s infinite;
}

.profile-placeholder {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100%;
}

.profile-icon {
  font-size: 8rem;
  opacity: 0.8;
}

@keyframes shine {
  0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
  100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
}

.skills-section {
  margin-bottom: var(--spacing-xl);
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: var(--spacing-lg);
}

.skill-category {
  background-color: var(--color-secondary);
  padding: var(--spacing-md);
  border-radius: var(--border-radius-md);
  border: 2px solid var(--color-border);
  box-shadow: var(--shadow-light);
  transition: all var(--transition-medium);
}

.skill-category:hover {
  transform: translateY(-5px);
  box-shadow: var(--shadow-medium);
  border-color: var(--color-primary);
}

.skill-category h3 {
  color: var(--color-primary);
  margin-bottom: var(--spacing-md);
  font-family: var(--font-primary);
  text-transform: uppercase;
  letter-spacing: 1px;
}

.skill-tags {
  display: flex;
  flex-wrap: wrap;
  gap: var(--spacing-xs);
}

.skill-tag {
  background-color: var(--color-light-gray);
  color: var(--color-primary);
  padding: var(--spacing-xs) var(--spacing-sm);
  border-radius: var(--border-radius-sm);
  font-size: 0.9rem;
  font-weight: 600;
  border: 1px solid var(--color-border);
  transition: all var(--transition-fast);
}

.skill-tag:hover {
  background-color: var(--color-primary);
  color: var(--color-secondary);
  transform: scale(1.05);
}

.experience-section {
  margin-bottom: var(--spacing-xl);
}

.timeline {
  position: relative;
  max-width: 800px;
  margin: 0 auto;
}

.timeline::before {
  content: '';
  position: absolute;
  left: 20px;
  top: 0;
  bottom: 0;
  width: 2px;
  background-color: var(--color-primary);
}

.timeline-item {
  position: relative;
  margin-bottom: var(--spacing-lg);
  padding-left: 60px;
}

.timeline-marker {
  position: absolute;
  left: 11px;
  top: 0;
  width: 20px;
  height: 20px;
  background-color: var(--color-secondary);
  border: 3px solid var(--color-primary);
  border-radius: 50%;
  z-index: 1;
}

.timeline-content {
  background-color: var(--color-secondary);
  padding: var(--spacing-md);
  border-radius: var(--border-radius-md);
  border: 1px solid var(--color-border);
  box-shadow: var(--shadow-light);
  transition: all var(--transition-medium);
}

.timeline-content:hover {
  transform: translateX(10px);
  box-shadow: var(--shadow-medium);
  border-color: var(--color-primary);
}

.timeline-content h3 {
  color: var(--color-primary);
  margin-bottom: var(--spacing-xs);
}

.company {
  color: var(--color-accent);
  font-weight: 600;
  margin-bottom: var(--spacing-xs);
}

.period {
  color: var(--color-medium-gray);
  font-size: 0.9rem;
  margin-bottom: var(--spacing-sm);
  font-family: var(--font-primary);
}

/* Responsive Design */
@media (max-width: 768px) {
  .hero-section {
    grid-template-columns: 1fr;
    text-align: center;
    gap: var(--spacing-lg);
  }
  
  .hero-title {
    font-size: 2.5rem;
  }
  
  .hero-actions {
    justify-content: center;
  }
  
  .profile-frame {
    width: 250px;
    height: 250px;
  }
  
  .profile-icon {
    font-size: 6rem;
  }
  
  .skills-grid {
    grid-template-columns: 1fr;
  }
  
  .timeline::before {
    left: 15px;
  }
  
  .timeline-item {
    padding-left: 50px;
  }
  
  .timeline-marker {
    left: 6px;
    width: 18px;
    height: 18px;
  }
}
</style>
