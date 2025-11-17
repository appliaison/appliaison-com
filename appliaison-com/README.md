# AppLiaison - Agency Portfolio Website

A modern, responsive agency portfolio website built with Svelte 5, SvelteKit, and Tailwind CSS. Showcasing AppLiaison's expertise in full-stack app development, mobile solutions, cloud services, AI/ML integration, and blockchain technology.

## 🚀 Features

- **Modern Stack**: Built with Svelte 5 (using new runes API), SvelteKit, and TypeScript
- **Responsive Design**: Fully responsive layout that works on all devices
- **Dark Theme**: Elegant dark theme with neural-inspired color palette
- **Smooth Animations**: Subtle animations and transitions for better UX
- **SEO Optimized**: Meta tags and semantic HTML for better search engine visibility
- **Performance Focused**: Optimized for fast loading and smooth interactions
- **Accessible**: ARIA labels and semantic HTML for better accessibility
- **Well Commented**: Comprehensive code comments for easy maintenance

## 📋 Prerequisites

- Node.js 18+ installed
- npm or pnpm package manager

## 🛠️ Installation

1. **Install Dependencies**
   ```bash
   npm install
   ```

2. **Run Development Server**
   ```bash
   npm run dev
   ```

   The site will be available at `http://localhost:5173`

3. **Build for Production**
   ```bash
   npm run build
   ```

4. **Preview Production Build**
   ```bash
   npm run preview
   ```

## 🌐 Deploying to Vercel

### Option 1: Vercel CLI (Recommended)

1. **Install Vercel CLI**
   ```bash
   npm install -g vercel
   ```

2. **Deploy**
   ```bash
   vercel
   ```

   Follow the prompts:
   - Set up and deploy: Yes
   - Which scope: Select your account
   - Link to existing project: No
   - Project name: arunabhdas-portfolio (or your preference)
   - Directory: ./ (press Enter)
   - Want to override settings: No

3. **Deploy to Production**
   ```bash
   vercel --prod
   ```

### Option 2: Vercel Dashboard

1. Push your code to a Git repository (GitHub, GitLab, or Bitbucket)

2. Go to [Vercel Dashboard](https://vercel.com/dashboard)

3. Click "Add New Project"

4. Import your Git repository

5. Vercel will auto-detect SvelteKit and configure:
   - Framework Preset: SvelteKit
   - Build Command: `npm run build`
   - Output Directory: `.svelte-kit`

6. Click "Deploy"

Your site will be live at `https://your-project.vercel.app`

### Custom Domain Setup

1. In Vercel Dashboard, go to your project settings
2. Navigate to "Domains"
3. Add your custom domain: `appliaison.com`
4. Follow Vercel's instructions to configure your DNS

## 🎨 Content Overview

### Current Content Structure

1. **Hero Section** (`src/lib/components/Hero.svelte`)
   - Company name and tagline
   - Full-stack app development agency positioning

2. **About Section** (`src/lib/components/About.svelte`)
   - Company overview and mission
   - Service areas and expertise
   - Key company metrics

3. **Services/Expertise** (`src/lib/components/Expertise.svelte`)
   - AI & Machine Learning solutions
   - Mobile app development
   - Cloud solutions (WCaaS)
   - Blockchain integration
   - Big Data analytics
   - Enterprise logistics

4. **Portfolio** (`src/lib/components/Projects.svelte`)
   - RealSmart (Blockchain real estate)
   - SmartStack & SmartSuite (Blockchain platforms)
   - Health+, SureServ, Vi Card, Rapicue (Mobile apps)
   - Propz.ai and Enterprise solutions

5. **Contact** (`src/lib/components/Contact.svelte`)
   - Contact form with email integration
   - Social media links (LinkedIn, Twitter, Email, Website)
   - Company contact information

### Form Submission

The contact form currently simulates submission. To make it functional:

1. **Using Email Service (e.g., EmailJS)**
   ```typescript
   // In Contact.svelte, replace the handleSubmit function
   import emailjs from '@emailjs/browser';

   async function handleSubmit(event: Event) {
     event.preventDefault();
     formStatus = 'submitting';

     try {
       await emailjs.send(
         'YOUR_SERVICE_ID',
         'YOUR_TEMPLATE_ID',
         formData,
         'YOUR_PUBLIC_KEY'
       );
       formStatus = 'success';
     } catch (error) {
       formStatus = 'error';
     }
   }
   ```

2. **Using API Endpoint**
   ```typescript
   async function handleSubmit(event: Event) {
     event.preventDefault();
     formStatus = 'submitting';

     try {
       const response = await fetch('/api/contact', {
         method: 'POST',
         headers: { 'Content-Type': 'application/json' },
         body: JSON.stringify(formData)
       });

       if (response.ok) {
         formStatus = 'success';
       } else {
         throw new Error('Failed to send');
       }
     } catch (error) {
       formStatus = 'error';
     }
   }
   ```

### Color Theme

Colors are defined in `tailwind.config.js`:
```javascript
colors: {
  neural: {
    dark: '#0a0e27',      // Main dark background
    darker: '#050812',    // Darker background
    blue: '#6b9bd1',      // Primary blue
    'blue-light': '#8fb5e0', // Light blue accent
    accent: '#4a90e2'     // Accent color
  }
}
```

### Add Company Logo

Add your company logo to the `static/` directory and update references in:
- `Header.svelte` - Navigation logo
- `About.svelte` - Company branding
- `app.html` - Favicon

### Portfolio Images

Add project screenshots and images to the `static/` directory and update image paths in `Projects.svelte`.

## 📁 Project Structure

```
appliaison-portfolio/
├── src/
│   ├── lib/
│   │   └── components/
│   │       ├── Header.svelte        # Navigation with company branding
│   │       ├── Hero.svelte          # Landing section with agency intro
│   │       ├── About.svelte         # About AppLiaison
│   │       ├── Expertise.svelte     # Services showcase
│   │       ├── Skills.svelte        # Technology stack
│   │       ├── Projects.svelte      # Portfolio projects
│   │       ├── Achievements.svelte  # Company impact & achievements
│   │       ├── OpenSource.svelte    # Company metrics & highlights
│   │       ├── Contact.svelte       # Contact form
│   │       └── Footer.svelte        # Footer with company info
│   ├── routes/
│   │   ├── +layout.svelte           # Root layout
│   │   ├── +page.svelte             # Main page
│   │   └── api/
│   │       └── contact/
│   │           └── +server.ts       # Contact form API endpoint
│   ├── app.css                      # Global styles
│   └── app.html                     # HTML template
├── static/
│   └── propz-ai/                    # Project screenshots
├── package.json
├── svelte.config.js
├── tailwind.config.js
├── tsconfig.json
└── vite.config.ts
```

## 🔧 Technologies Used

- **Svelte 5**: Latest version with runes API
- **SvelteKit**: Framework for building web applications
- **TypeScript**: Type-safe JavaScript
- **Tailwind CSS**: Utility-first CSS framework
- **Vercel**: Deployment platform

## 📝 Best Practices Implemented

- ✅ Semantic HTML for better SEO and accessibility
- ✅ Responsive design with mobile-first approach
- ✅ TypeScript for type safety
- ✅ Component-based architecture
- ✅ Smooth animations and transitions
- ✅ Optimized performance
- ✅ Clean, commented code
- ✅ Modern Svelte 5 patterns (runes, snippets)

## 🏢 About AppLiaison

AppLiaison Inc. is a full-stack app development agency specializing in:
- **Mobile App Development**: iOS, Android, and cross-platform solutions
- **Cloud Solutions**: Whitelabel-Cloud-as-a-Service (WCaaS) platform
- **AI & Machine Learning**: TensorFlow-powered intelligent solutions
- **Blockchain Technology**: Smart contracts and DeFi platforms
- **Big Data Analytics**: Real-time business intelligence
- **Enterprise Solutions**: ERP, CRM, and logistics automation

## 📧 Contact

- **Website**: [appliaison.com](https://appliaison.com)
- **Email**: info@appliaison.com
- **Services**: [appliaison.com/services](https://appliaison.com/services)
- **AI Solutions**: [appliaison.com/ai-home](https://appliaison.com/ai-home)

---

Built with cutting-edge technology to showcase AppLiaison's expertise in delivering transformative technology solutions.
