# Personal Portfolio Website

A modern, responsive personal portfolio website built with Vue.js 3 and Vite, featuring a retro-inspired design with black, white, and gray color scheme.

## 🎨 Design Features

- **Retro-inspired Design**: Clean, minimalist aesthetic with vintage typography
- **Color Scheme**: Black, white, and gray palette for professional appearance
- **Rounded Elements**: All buttons and interactive elements feature rounded corners
- **Smooth Animations**: Subtle hover effects and transitions throughout
- **Responsive Design**: Mobile-first approach with excellent mobile experience

## 🚀 Technologies Used

- **Frontend**: Vue.js 3 (Composition API)
- **Build Tool**: Vite
- **Styling**: CSS3 with CSS Variables
- **Typography**: Courier New (monospace) + Georgia (serif)
- **Icons**: Emoji-based icons for simplicity

## 📁 Project Structure

```
src/
├── components/
│   ├── Navbar.vue      # Navigation component with mobile menu
│   ├── About.vue       # Hero section, skills, and experience
│   ├── Projects.vue    # Portfolio projects showcase
│   ├── Certificate.vue # Professional certificates and achievements
│   └── Contact.vue     # Contact form and information
├── App.vue             # Main application component
├── main.js             # Application entry point
└── style.css           # Global styles and CSS variables
```

## 🎯 Key Components

### Navbar
- Fixed navigation with scroll effects
- Mobile-responsive hamburger menu
- Smooth transitions and hover effects

### About Section
- Hero section with animated profile frame
- Skills categorization with interactive tags
- Timeline-based experience display

### Projects
- Grid layout for project showcase
- Hover effects with project links
- Technology tags and feature lists

### Certificates
- Professional certifications display
- Verified badges and credential links
- Statistics dashboard
- Interactive tags and download options

### Contact
- Contact form with validation
- Social media links
- Contact information display

## 🎨 Design System

### Color Palette
- **Primary**: #000000 (Black)
- **Secondary**: #ffffff (White)
- **Accent**: #808080 (Gray)
- **Light Gray**: #f5f5f5
- **Medium Gray**: #666666
- **Dark Gray**: #333333

### Typography
- **Primary Font**: Courier New (monospace) - for technical elements
- **Secondary Font**: Georgia (serif) - for headings and content

### Spacing System
- **XS**: 0.5rem (8px)
- **SM**: 1rem (16px)
- **MD**: 2rem (32px)
- **LG**: 3rem (48px)
- **XL**: 4rem (64px)

### Border Radius
- **Small**: 8px
- **Medium**: 12px
- **Large**: 20px

## 🚀 Getting Started

### Prerequisites
- Node.js (version 16 or higher)
- npm or yarn package manager

### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd portfolio
```

2. Install dependencies:
```bash
npm install
```

3. Start development server:
```bash
npm run dev
```

4. Build for production:
```bash
npm run build
```

5. Preview production build:
```bash
npm run preview
```

## 📱 Responsive Design

The portfolio is fully responsive with breakpoints:
- **Desktop**: 1200px and above
- **Tablet**: 768px - 1199px
- **Mobile**: Below 768px

## 🎭 Customization

### Colors
Update CSS variables in `src/style.css`:
```css
:root {
  --color-primary: #000000;
  --color-secondary: #ffffff;
  --color-accent: #808080;
  /* ... other colors */
}
```

### Content
- Update personal information in component files
- Modify project data in `Projects.vue`
- Change contact details in `Contact.vue`
- Update skills and experience in `About.vue`

### Typography
Modify font families in CSS variables:
```css
:root {
  --font-primary: 'Your-Monospace-Font', monospace;
  --font-secondary: 'Your-Serif-Font', serif;
}
```

## 🔧 Development

### Code Style
- Follow Vue.js 3 Composition API best practices
- Use semantic HTML elements
- Maintain consistent CSS naming conventions
- Comment complex logic and animations

### Performance
- Optimized images and assets
- Lazy loading for components
- Efficient CSS animations
- Minimal JavaScript bundle

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📞 Support

For questions or support, please open an issue in the repository.

---

**Built with ❤️ using Vue.js 3 and modern web technologies**
