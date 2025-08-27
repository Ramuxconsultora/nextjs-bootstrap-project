```markdown
# Detailed Implementation Plan for Ramux Website

This plan outlines all changes and new files required to build a responsive, modern, and minimalist website for Ramux – Consultora de Comunicación y Gestión that communicates professionalism, trust, and innovation.

---

## 1. Global and Layout Updates

### a. Update Global Styles (src/app/globals.css)
- **Base Styles:**  
  - Set a clean, light background, elegant typography, and use a primary color palette with dark blue and neutral grey.
  - Example: Define font-family (e.g., "Helvetica, Arial, sans-serif"), base font-sizes, and color variables.
- **Responsive Breakpoints:**  
  - Add media queries for mobile, tablet, and desktop to ensure responsiveness.
- **Animations:**  
  - Create common CSS classes (e.g., `.fade-in`, `.slide-up`) for smooth scroll animations.
- **Error Handling:**  
  - Set styles to ensure elements (like images) retain layout even if an image fails to load.

### b. Update Layout (src/app/layout.tsx)
- **SEO Meta Tags:**  
  - Add title tag “Ramux – Consultora de Comunicación y Gestión”, description meta tag, and viewport settings.
- **Global Components:**  
  - Import and render the new Header and Footer components.
- **WhatsApp Floating Button:**  
  - Include the WhatsAppButton component so it’s visible on every page.

---

## 2. New UI Components in src/components

### a. Header Component (src/components/Header.tsx)
- **Structure:**  
  - Create a responsive navigation bar featuring the “Ramux” logo (styled text) and links to sections: Inicio, Quiénes Somos, Servicios, Blog y Contacto.
- **Responsiveness:**  
  - For smaller screens, consider a simple collapsible menu (if needed) using basic CSS and state management.
  
### b. HeroSection Component (src/components/HeroSection.tsx)
- **Design:**  
  - Full-screen hero section with a background image set using an `<img>` tag:
    - `src="https://placehold.co/1920x1080?text=Abstract+background+corporate+communication"`
    - `alt="Abstract background for corporate communication with a modern, clean style"`
    - Add an `onError` handler to hide or replace the image if it fails.
  - Overlay text displaying:
    - The logo “Ramux”
    - Slogan: “Comunicación estratégica y gestión para un mundo en movimiento.”
  - A prominent CTA button “Conocé nuestros servicios” that scrolls to the Services section.

### c. AboutSection Component (src/components/AboutSection.tsx)
- **Content:**  
  - A brief paragraph about Ramux’s mission in political, corporate communication, and strategic management.
  - A representative image using:
    - `src="https://placehold.co/800x600?text=Professional+team+working+in+modern+office"`
    - Descriptive alt text and the same onError handler.
  - A display of key values (profesionalismo, cercanía, innovación) in a visually appealing format (e.g., cards or simple boxes).

### d. ServicesSection Component (src/components/ServicesSection.tsx)
- **Structure:**  
  - Create a grid layout to display service cards for:
    - Consultoría en comunicación política
    - Estrategias de comunicación corporativa
    - Gestión y posicionamiento digital
    - Análisis de opinión pública
    - Capacitaciones y talleres
- **Service Cards:**  
  - Each card includes:
    - A custom “icon” created with pure CSS (e.g., colored shape or initial letter), no external icon libraries.
    - Service title and brief description.
    - Animated hover effect (using CSS transitions) to elevate the card visually.
  
### e. BlogSection Component (src/components/BlogSection.tsx)
- **Layout:**  
  - Magazine-style grid that displays featured articles with titles, summaries, and category tags (Política, Comunicación, Innovación, Actualidad).
  - Each article card uses clean typography and spacing.
  - Include simple “Compartir” text links styled as buttons for social media sharing.
  
### f. ContactSection Component (src/components/ContactSection.tsx)
- **Features:**  
  - A simple contact form with fields: nombre, correo electrónico, asunto (opcional) y mensaje.
  - Client-side validation (required fields, correct email format) with error messages.
  - Use accessible and semantic form elements.
  - On submit, log the input (or integrate with an API endpoint later) and display success or error alerts.
  
### g. Footer Component (src/components/Footer.tsx)
- **Content:**  
  - Quick navigation links, copyright text “© Ramux. Derechos reservados.”
  - Links to política de privacidad and términos de uso.
  
### h. WhatsAppButton Component (src/components/WhatsappButton.tsx)
- **Design & Functionality:**  
  - A floating button positioned fixed at the bottom-right of the viewport.
  - Styled using minimal colors that complement the site (avoid using external image icons; use text such as “WhatsApp”).
  - On click, open a WhatsApp chat link (e.g., `https://wa.me/1234567890` where the number is later replaced with the actual contact).

---

## 3. Home Page Integration (src/app/page.tsx)
- **Layout Order:**  
  - Import and render components in this order:
    1. Header (if not already placed in layout)
    2. HeroSection
    3. AboutSection
    4. ServicesSection
    5. BlogSection (if content is available; otherwise as placeholders)
    6. ContactSection
    7. Footer
    8. WhatsAppButton (floating, overlaying other sections)
- **Smooth Scrolling:**  
  - Add anchor links and/or scroll behavior (using CSS `scroll-behavior: smooth` or a simple JavaScript function) for navigation.
- **Error Handling:**  
  - Verify that if any component errors (e.g., image load failures), the overall layout remains intact.

---

## 4. Additional Best Practices & Testing

- **Accessibility:**  
  - Ensure all images have detailed `alt` text and all interactive elements have ARIA labels.
- **Responsive Testing:**  
  - Use media queries and test across multiple device sizes.
- **Form Validation:**  
  - Implement client-side error handling in the ContactSection to notify users of missing or invalid inputs.
- **Animation & Performance:**  
  - Use lightweight CSS transitions for scroll animations and hover effects to maintain performance.
- **Documentation:**  
  - Update README.md with installation and testing instructions, and document the new component hierarchy and routing.
- **Version Control:**  
  - Commit changes in logical chunks (global styles, each component, layout, and page integration).

---

## Summary

- Updated globals.css and layout.tsx to set a modern, minimalist visual language and SEO meta data.  
- Created new components (Header, HeroSection, AboutSection, ServicesSection, BlogSection, ContactSection, Footer, WhatsAppButton) to structure the website.  
- Integrated a one-page layout in src/app/page.tsx with smooth scrolling and responsive design.  
- Built custom CSS “icon” elements and animations without relying on external libraries.  
- Implemented error handling for images (with onerror) and validated the contact form inputs.  
- Ensured all UI elements use semantic HTML, proper alt text, and accessibility features.  
- Followed best practices for responsive design, performance, and code modularity.  
- The design clearly reflects Ramux’s professional, trustworthy, and innovative brand identity.
