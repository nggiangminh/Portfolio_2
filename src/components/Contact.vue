<template>
  <section id="contact" class="section contact-section">
    <div class="container">
      <h2 class="section-title">Get In Touch</h2>
      <p class="section-subtitle">Let's discuss your next project or just say hello!</p>
      
      <div class="contact-content">
        <div class="contact-info">
          <h3>Let's Connect</h3>
          <p>I'm always interested in hearing about new opportunities and exciting projects. Feel free to reach out!</p>
          
          <div class="contact-methods">
            <div class="contact-method">
              <div class="method-icon">📧</div>
              <div class="method-details">
                <h4>Email</h4>
                <a href="mailto:minh.nguyen@example.com" class="contact-link">minh.nguyen@example.com</a>
              </div>
            </div>
            
            <div class="contact-method">
              <div class="method-icon">📱</div>
              <div class="method-details">
                <h4>Phone</h4>
                <a href="tel:+1234567890" class="contact-link">+1 (234) 567-890</a>
              </div>
            </div>
            
            <div class="contact-method">
              <div class="method-icon">📍</div>
              <div class="method-details">
                <h4>Location</h4>
                <p>Ho Chi Minh City, Vietnam</p>
              </div>
            </div>
          </div>
          
          <div class="social-links">
            <h4>Follow Me</h4>
            <div class="social-icons">
              <a href="https://github.com/username" target="_blank" class="social-link" title="GitHub">
                <span class="social-icon">🐙</span>
              </a>
              <a href="https://linkedin.com/in/username" target="_blank" class="social-link" title="LinkedIn">
                <span class="social-icon">💼</span>
              </a>
              <a href="https://twitter.com/username" target="_blank" class="social-link" title="Twitter">
                <span class="social-icon">🐦</span>
              </a>
              <a href="https://dribbble.com/username" target="_blank" class="social-link" title="Dribbble">
                <span class="social-icon">🏀</span>
              </a>
            </div>
          </div>
        </div>
        
        <div class="contact-form-container">
          <form class="contact-form" @submit.prevent="handleSubmit">
            <div class="form-group">
              <label for="name" class="form-label">Name *</label>
              <input 
                type="text" 
                id="name" 
                v-model="formData.name" 
                class="form-input" 
                required
                placeholder="Your full name"
              >
            </div>
            
            <div class="form-group">
              <label for="email" class="form-label">Email *</label>
              <input 
                type="email" 
                id="email" 
                v-model="formData.email" 
                class="form-input" 
                required
                placeholder="your.email@example.com"
              >
            </div>
            
            <div class="form-group">
              <label for="subject" class="form-label">Subject</label>
              <input 
                type="text" 
                id="subject" 
                v-model="formData.subject" 
                class="form-input" 
                placeholder="What's this about?"
              >
            </div>
            
            <div class="form-group">
              <label for="message" class="form-label">Message *</label>
              <textarea 
                id="message" 
                v-model="formData.message" 
                class="form-textarea" 
                rows="5" 
                required
                placeholder="Tell me about your project or inquiry..."
              ></textarea>
            </div>
            
            <button type="submit" class="btn submit-btn" :disabled="isSubmitting">
              <span v-if="!isSubmitting">Send Message</span>
              <span v-else>Sending...</span>
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Contact',
  data() {
    return {
      formData: {
        name: '',
        email: '',
        subject: '',
        message: ''
      },
      isSubmitting: false
    }
  },
  methods: {
    async handleSubmit() {
      this.isSubmitting = true
      
      try {
        // Simulate form submission
        await new Promise(resolve => setTimeout(resolve, 2000))
        
        // Reset form
        this.formData = {
          name: '',
          email: '',
          subject: '',
          message: ''
        }
        
        // Show success message (you can implement a toast notification here)
        alert('Thank you for your message! I\'ll get back to you soon.')
        
      } catch (error) {
        console.error('Error submitting form:', error)
        alert('Sorry, there was an error sending your message. Please try again.')
      } finally {
        this.isSubmitting = false
      }
    }
  }
}
</script>

<style scoped>
.contact-section {
  background: linear-gradient(135deg, var(--color-light-gray) 0%, var(--color-secondary) 100%);
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

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: var(--spacing-xl);
  align-items: start;
}

.contact-info h3 {
  color: var(--color-primary);
  margin-bottom: var(--spacing-md);
  font-size: 1.8rem;
}

.contact-info > p {
  color: var(--color-medium-gray);
  margin-bottom: var(--spacing-lg);
  line-height: 1.7;
  font-size: 1.1rem;
}

.contact-methods {
  margin-bottom: var(--spacing-lg);
}

.contact-method {
  display: flex;
  align-items: center;
  gap: var(--spacing-md);
  margin-bottom: var(--spacing-md);
  padding: var(--spacing-md);
  background-color: var(--color-secondary);
  border-radius: var(--border-radius-md);
  border: 1px solid var(--color-border);
  transition: all var(--transition-medium);
}

.contact-method:hover {
  transform: translateX(10px);
  border-color: var(--color-primary);
  box-shadow: var(--shadow-light);
}

.method-icon {
  font-size: 2rem;
  opacity: 0.8;
}

.method-details h4 {
  color: var(--color-primary);
  margin-bottom: var(--spacing-xs);
  font-size: 1.1rem;
}

.contact-link {
  color: var(--color-accent);
  text-decoration: none;
  font-weight: 600;
  transition: color var(--transition-fast);
}

.contact-link:hover {
  color: var(--color-primary);
}

.method-details p {
  color: var(--color-medium-gray);
  margin: 0;
}

.social-links h4 {
  color: var(--color-primary);
  margin-bottom: var(--spacing-md);
  font-size: 1.1rem;
}

.social-icons {
  display: flex;
  gap: var(--spacing-md);
}

.social-link {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 50px;
  height: 50px;
  background-color: var(--color-secondary);
  border: 2px solid var(--color-border);
  border-radius: 50%;
  text-decoration: none;
  transition: all var(--transition-medium);
}

.social-link:hover {
  background-color: var(--color-primary);
  border-color: var(--color-primary);
  transform: translateY(-3px);
  box-shadow: var(--shadow-medium);
}

.social-icon {
  font-size: 1.5rem;
  color: var(--color-primary);
  transition: color var(--transition-fast);
}

.social-link:hover .social-icon {
  color: var(--color-secondary);
}

.contact-form-container {
  background-color: var(--color-secondary);
  padding: var(--spacing-lg);
  border-radius: var(--border-radius-md);
  border: 2px solid var(--color-border);
  box-shadow: var(--shadow-light);
}

.contact-form {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-md);
}

.form-group {
  display: flex;
  flex-direction: column;
}

.form-label {
  color: var(--color-primary);
  font-weight: 600;
  margin-bottom: var(--spacing-xs);
  font-family: var(--font-primary);
  text-transform: uppercase;
  letter-spacing: 1px;
  font-size: 0.9rem;
}

.form-input,
.form-textarea {
  padding: var(--spacing-sm);
  border: 2px solid var(--color-border);
  border-radius: var(--border-radius-sm);
  font-family: var(--font-primary);
  font-size: 1rem;
  transition: all var(--transition-medium);
  background-color: var(--color-secondary);
  color: var(--color-primary);
}

.form-input:focus,
.form-textarea:focus {
  outline: none;
  border-color: var(--color-primary);
  box-shadow: 0 0 0 3px rgba(0, 0, 0, 0.1);
}

.form-input::placeholder,
.form-textarea::placeholder {
  color: var(--color-medium-gray);
  opacity: 0.7;
}

.form-textarea {
  resize: vertical;
  min-height: 120px;
}

.submit-btn {
  margin-top: var(--spacing-sm);
  padding: var(--spacing-md) var(--spacing-lg);
  font-size: 1.1rem;
  position: relative;
  overflow: hidden;
}

.submit-btn:disabled {
  opacity: 0.7;
  cursor: not-allowed;
}

.submit-btn:not(:disabled):hover {
  transform: translateY(-3px);
  box-shadow: var(--shadow-medium);
}

/* Responsive Design */
@media (max-width: 768px) {
  .contact-content {
    grid-template-columns: 1fr;
    gap: var(--spacing-lg);
  }
  
  .contact-method {
    flex-direction: column;
    text-align: center;
    gap: var(--spacing-sm);
  }
  
  .contact-method:hover {
    transform: translateY(-5px);
  }
  
  .social-icons {
    justify-content: center;
  }
  
  .contact-form-container {
    padding: var(--spacing-md);
  }
}
</style>
