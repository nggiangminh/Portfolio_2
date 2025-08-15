<template>
  <section id="certificates" class="section certificates-section">
    <div class="container">
      <h2 class="section-title">Certificates & Achievements</h2>
      <p class="section-subtitle">Professional certifications and educational achievements</p>
      
      <div class="certificates-grid">
        <div class="certificate-card" v-for="certificate in certificates" :key="certificate.id">
          <div class="certificate-header">
            <div class="certificate-icon">
              <span class="icon">{{ certificate.icon }}</span>
            </div>
            <div class="certificate-badge" v-if="certificate.isVerified">
              <span class="badge-text">✓ Verified</span>
            </div>
          </div>
          
          <div class="certificate-content">
            <h3 class="certificate-title">{{ certificate.title }}</h3>
            <p class="certificate-issuer">{{ certificate.issuer }}</p>
            <p class="certificate-date">{{ certificate.issueDate }}</p>
            <p class="certificate-description">{{ certificate.description }}</p>
            
            <div class="certificate-tags">
              <span class="tag" v-for="tag in certificate.tags" :key="tag">{{ tag }}</span>
            </div>
            
            <div class="certificate-actions">
              <a 
                :href="certificate.credentialUrl" 
                target="_blank" 
                class="btn btn-secondary certificate-btn"
                v-if="certificate.credentialUrl"
              >
                <span class="btn-icon">🔗</span>
                View Credential
              </a>
              <a 
                :href="certificate.certificateUrl" 
                target="_blank" 
                class="btn certificate-btn"
                v-if="certificate.certificateUrl"
              >
                <span class="btn-icon">📄</span>
                Download PDF
              </a>
            </div>
          </div>
        </div>
      </div>
      
      <div class="certificates-stats">
        <div class="stat-item">
          <div class="stat-number">{{ totalCertificates }}</div>
          <div class="stat-label">Total Certificates</div>
        </div>
        <div class="stat-item">
          <div class="stat-number">{{ verifiedCertificates }}</div>
          <div class="stat-label">Verified</div>
        </div>
        <div class="stat-item">
          <div class="stat-number">{{ currentYear }}</div>
          <div class="stat-label">This Year</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Certificate',
  data() {
    return {
      certificates: [
        {
          id: 1,
          title: 'AWS Certified Solutions Architect',
          issuer: 'Amazon Web Services',
          issueDate: 'December 2024',
          description: 'Professional level certification demonstrating expertise in designing distributed systems on AWS.',
          icon: '☁️',
          tags: ['AWS', 'Cloud Architecture', 'Professional'],
          isVerified: true,
          credentialUrl: 'https://aws.amazon.com/verification',
          certificateUrl: 'https://example.com/cert1.pdf'
        },
        {
          id: 2,
          title: 'Spring Boot Developer',
          issuer: 'Pivotal Software',
          issueDate: 'November 2024',
          description: 'Advanced certification for Spring Boot application development and microservices architecture.',
          icon: '🍃',
          tags: ['Spring Boot', 'Java', 'Microservices'],
          isVerified: true,
          credentialUrl: 'https://spring.io/certification',
          certificateUrl: 'https://example.com/cert2.pdf'
        },
        {
          id: 3,
          title: 'Vue.js Developer Certification',
          issuer: 'Vue.js Official',
          issueDate: 'October 2024',
          description: 'Comprehensive certification covering Vue.js 3, Composition API, and advanced patterns.',
          icon: '⚡',
          tags: ['Vue.js', 'Frontend', 'JavaScript'],
          isVerified: true,
          credentialUrl: 'https://vuejs.org/certification',
          certificateUrl: 'https://example.com/cert3.pdf'
        },
        {
          id: 4,
          title: 'MongoDB Database Administrator',
          issuer: 'MongoDB University',
          issueDate: 'September 2024',
          description: 'Professional certification for MongoDB database administration and optimization.',
          icon: '🍃',
          tags: ['MongoDB', 'Database', 'NoSQL'],
          isVerified: true,
          credentialUrl: 'https://university.mongodb.com',
          certificateUrl: 'https://example.com/cert4.pdf'
        },
        {
          id: 5,
          title: 'Docker Certified Associate',
          issuer: 'Docker Inc.',
          issueDate: 'August 2024',
          description: 'Certification demonstrating proficiency in containerization and Docker technologies.',
          icon: '🐳',
          tags: ['Docker', 'Containers', 'DevOps'],
          isVerified: true,
          credentialUrl: 'https://docker.com/certification',
          certificateUrl: 'https://example.com/cert5.pdf'
        },
        {
          id: 6,
          title: 'Google Cloud Professional Developer',
          issuer: 'Google Cloud',
          issueDate: 'July 2024',
          description: 'Professional certification for Google Cloud Platform development and deployment.',
          icon: '☁️',
          tags: ['Google Cloud', 'Cloud Development', 'Professional'],
          isVerified: true,
          credentialUrl: 'https://cloud.google.com/certification',
          certificateUrl: 'https://example.com/cert6.pdf'
        }
      ]
    }
  },
  computed: {
    totalCertificates() {
      return this.certificates.length
    },
    verifiedCertificates() {
      return this.certificates.filter(cert => cert.isVerified).length
    },
    currentYear() {
      const currentYear = new Date().getFullYear()
      return this.certificates.filter(cert => 
        new Date(cert.issueDate).getFullYear() === currentYear
      ).length
    }
  }
}
</script>

<style scoped>
.certificates-section {
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

.certificates-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  gap: var(--spacing-lg);
  margin-bottom: var(--spacing-xl);
}

.certificate-card {
  background-color: var(--color-secondary);
  border: 2px solid var(--color-border);
  border-radius: var(--border-radius-md);
  overflow: hidden;
  box-shadow: var(--shadow-light);
  transition: all var(--transition-medium);
  position: relative;
}

.certificate-card:hover {
  transform: translateY(-8px);
  box-shadow: var(--shadow-heavy);
  border-color: var(--color-primary);
}

.certificate-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: var(--spacing-md);
  background: linear-gradient(135deg, var(--color-light-gray) 0%, var(--color-secondary) 100%);
  border-bottom: 1px solid var(--color-border);
}

.certificate-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 60px;
  height: 60px;
  background-color: var(--color-secondary);
  border: 2px solid var(--color-primary);
  border-radius: 50%;
  box-shadow: var(--shadow-light);
}

.icon {
  font-size: 2rem;
  opacity: 0.9;
}

.certificate-badge {
  background-color: var(--color-primary);
  color: var(--color-secondary);
  padding: var(--spacing-xs) var(--spacing-sm);
  border-radius: var(--border-radius-sm);
  font-size: 0.8rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.badge-text {
  display: flex;
  align-items: center;
  gap: var(--spacing-xs);
}

.certificate-content {
  padding: var(--spacing-md);
}

.certificate-title {
  color: var(--color-primary);
  margin-bottom: var(--spacing-sm);
  font-size: 1.3rem;
  line-height: 1.3;
}

.certificate-issuer {
  color: var(--color-accent);
  font-weight: 600;
  margin-bottom: var(--spacing-xs);
  font-size: 1rem;
}

.certificate-date {
  color: var(--color-medium-gray);
  font-size: 0.9rem;
  margin-bottom: var(--spacing-sm);
  font-family: var(--font-primary);
}

.certificate-description {
  color: var(--color-medium-gray);
  line-height: 1.6;
  margin-bottom: var(--spacing-md);
  font-size: 0.95rem;
}

.certificate-tags {
  display: flex;
  flex-wrap: wrap;
  gap: var(--spacing-xs);
  margin-bottom: var(--spacing-md);
}

.tag {
  background-color: var(--color-light-gray);
  color: var(--color-primary);
  padding: var(--spacing-xs) var(--spacing-sm);
  border-radius: var(--border-radius-sm);
  font-size: 0.8rem;
  font-weight: 600;
  border: 1px solid var(--color-border);
  transition: all var(--transition-fast);
}

.tag:hover {
  background-color: var(--color-primary);
  color: var(--color-secondary);
  transform: scale(1.05);
}

.certificate-actions {
  display: flex;
  gap: var(--spacing-sm);
  flex-wrap: wrap;
}

.certificate-btn {
  display: flex;
  align-items: center;
  gap: var(--spacing-xs);
  font-size: 0.9rem;
  padding: var(--spacing-sm) var(--spacing-md);
  flex: 1;
  justify-content: center;
  min-width: 140px;
}

.btn-icon {
  font-size: 1rem;
}

.certificates-stats {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: var(--spacing-lg);
  padding: var(--spacing-lg);
  background-color: var(--color-light-gray);
  border-radius: var(--border-radius-md);
  border: 2px solid var(--color-border);
}

.stat-item {
  text-align: center;
  padding: var(--spacing-md);
}

.stat-number {
  font-size: 3rem;
  font-weight: 700;
  color: var(--color-primary);
  margin-bottom: var(--spacing-xs);
  font-family: var(--font-primary);
}

.stat-label {
  color: var(--color-medium-gray);
  font-size: 1rem;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 1px;
}

/* Responsive Design */
@media (max-width: 768px) {
  .certificates-grid {
    grid-template-columns: 1fr;
    gap: var(--spacing-md);
  }
  
  .certificate-card {
    margin-bottom: var(--spacing-md);
  }
  
  .certificate-header {
    flex-direction: column;
    gap: var(--spacing-sm);
    text-align: center;
  }
  
  .certificate-actions {
    flex-direction: column;
  }
  
  .certificate-btn {
    min-width: auto;
  }
  
  .certificates-stats {
    grid-template-columns: 1fr;
    gap: var(--spacing-md);
  }
  
  .stat-item {
    padding: var(--spacing-sm);
  }
  
  .stat-number {
    font-size: 2.5rem;
  }
}

@media (max-width: 480px) {
  .certificates-grid {
    grid-template-columns: 1fr;
  }
  
  .certificate-card {
    margin: 0 var(--spacing-sm) var(--spacing-md) var(--spacing-sm);
  }
}
</style>
