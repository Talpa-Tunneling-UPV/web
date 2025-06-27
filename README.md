# Talpa Tunneling UPV Web v0

## 💡 Visión
Plataforma dark-first que evangeliza sobre nuestra micro-tuneladora y recluta talento multidisciplinar para la Not-a-Boring Competition.

## 🚀 Tech Stack
- **Frontend:** Next.js 15 · React 19 · TypeScript
- **Styling:** Tailwind CSS · shadcn/ui
- **3D Graphics:** Canvas API (preparado para Three.js)
- **Forms:** React Hook Form · Zod validation
- **Animations:** CSS animations · Framer Motion ready
- **Deployment:** Vercel Edge Functions · UPV Plex ready

## 📁 Estructura del Proyecto

\`\`\`
talpa-tunneling-web/
├── app/                          # Next.js App Router
│   ├── layout.tsx               # Layout principal
│   ├── page.tsx                 # Landing page
│   ├── globals.css              # Estilos globales
│   ├── equipo/                  # Página del equipo
│   ├── tuneladora/              # Modelo 3D y specs
│   ├── unete/                   # Formulario inscripción
│   ├── contacto/                # Información contacto
│   ├── prensa/                  # Apariciones mediáticas
│   ├── eventos/                 # Próximos eventos
│   └── faq/                     # Preguntas frecuentes
├── components/                   # Componentes reutilizables
│   ├── ui/                      # shadcn/ui components
│   ├── layout/                  # Navegación y footer
│   ├── sections/                # Secciones de landing
│   └── forms/                   # Formularios
├── lib/                         # Utilidades y configuración
├── public/                      # Assets estáticos
└── styles/                      # Estilos adicionales
\`\`\`

## 🏗️ Setup y Desarrollo

### Prerrequisitos
- Node.js 18+ 
- pnpm (recomendado) o npm

### Instalación
\`\`\`bash
# Clonar el repositorio
git clone https://github.com/talpa-tunneling/web.git
cd talpa-tunneling-web

# Instalar dependencias
pnpm install

# Copiar variables de entorno
cp .env.example .env.local

# Iniciar servidor de desarrollo
pnpm dev
\`\`\`

### Scripts Disponibles
\`\`\`bash
pnpm dev          # Servidor de desarrollo
pnpm build        # Build de producción
pnpm start        # Servidor de producción
pnpm lint         # Linting con ESLint
pnpm type-check   # Verificación de tipos
pnpm test         # Tests con Jest
pnpm test:watch   # Tests en modo watch
\`\`\`

## 🎨 Sistema de Diseño

### Paleta de Colores
\`\`\`css
:root {
  --primary-black: #000000;
  --primary-white: #ffffff;
  --accent-blue: #00338d;
  --gradient-hero: linear-gradient(135deg, #000000 0%, #00338d 100%);
  --gradient-card: linear-gradient(145deg, #1a1a1a 0%, #2d2d2d 100%);
}
\`\`\`

### Tipografía
- **Títulos:** Overpass (ExtraBold, Bold, SemiBold)
- **Cuerpo:** Inter (Regular, Medium)
- **Código:** JetBrains Mono

### Componentes Clave
- **Glass Cards:** Efecto glassmorphism con `bg-white/5 backdrop-blur-sm`
- **Buttons:** Variantes primary (`btn-primary`) y secondary (`btn-secondary`)
- **Animations:** Float, glow, pulse para elementos interactivos

## 📱 Responsive Design

### Breakpoints
\`\`\`css
/* Mobile First Approach */
sm: 640px    /* Tablet pequeña */
md: 768px    /* Tablet */
lg: 1024px   /* Desktop pequeño */
xl: 1280px   # Desktop */
2xl: 1536px  /* Desktop grande */
\`\`\`

### Componentes Responsive
- **Navegación:** Hamburger menu en móvil, horizontal en desktop
- **Grid layouts:** Adaptación automática según breakpoint
- **Formularios:** Stack vertical en móvil, grid en desktop

## 🔧 Funcionalidades Principales

### Landing Page
- Hero section con animación 3D de tuneladora
- Secciones: About, Subsistemas, Estadísticas, CTA
- Animaciones suaves y micro-interacciones

### Formulario de Inscripción
- Validación en tiempo real con React Hook Form
- Subida de archivos (CV) con validación
- Selección múltiple de subsistemas
- Consentimientos GDPR

### Modelo 3D Interactivo
- Canvas API para renderizado 3D básico
- Controles de rotación y zoom
- Información contextual de componentes
- Preparado para integración con Three.js

### Sistema de Navegación
- Navegación sticky con backdrop blur
- Selector de idioma (ES/EN preparado)
- Enlaces activos con indicadores visuales

## 🌐 Internacionalización

### Configuración i18n
\`\`\`typescript
// Preparado para next-intl
const locales = ['es', 'en']
const defaultLocale = 'es'
\`\`\`

### Estructura de Traducciones
\`\`\`
locales/
├── es/
│   ├── common.json
│   ├── navigation.json
│   └── forms.json
└── en/
    ├── common.json
    ├── navigation.json
    └── forms.json
\`\`\`

## 📊 Performance y SEO

### Métricas Objetivo
- **LCP:** < 2.5s
- **FID:** < 100ms  
- **CLS:** < 0.1
- **Lighthouse Score:** > 90 en todas las métricas

### Optimizaciones Implementadas
- Lazy loading de imágenes
- Compresión de assets
- Meta tags optimizados
- Structured data (JSON-LD)
- Sitemap automático

## 🧪 Testing

### Estrategia de Testing
\`\`\`bash
# Unit tests
pnpm test

# E2E tests (preparado para Playwright)
pnpm test:e2e

# Visual regression tests (preparado para Percy)
pnpm test:visual
\`\`\`

### Cobertura de Tests
- Componentes UI críticos
- Formularios y validaciones
- Funciones de utilidad
- Hooks personalizados

## 🚀 Deployment

### Vercel (Recomendado)
\`\`\`bash
# Deploy automático desde main branch
git push origin main

# Preview deployments desde feature branches
git push origin feature/nueva-funcionalidad
\`\`\`

### UPV Plex
\`\`\`bash
# Build para producción
pnpm build

# Generar archivos estáticos
pnpm export

# Subir a servidor Plex
rsync -avz out/ usuario@plex.upv.es:/path/to/web/
\`\`\`

### Variables de Entorno
\`\`\`bash
# .env.local
NEXT_PUBLIC_SITE_URL=https://talpatunneling.upv.es
NEXT_PUBLIC_ANALYTICS_ID=your-analytics-id
CONTACT_EMAIL=info@talpatunneling.upv.es
\`\`\`

## 🤝 Contribuir

### Flujo de Trabajo
1. Fork del repositorio
2. Crear branch: `git checkout -b feature/nueva-funcionalidad`
3. Commit: `git commit -m 'feat: añadir nueva funcionalidad'`
4. Push: `git push origin feature/nueva-funcionalidad`
5. Crear Pull Request

### Convención de Commits
Seguimos [Conventional Commits](https://www.conventionalcommits.org/):
\`\`\`
feat: nueva funcionalidad
fix: corrección de bug
docs: actualización documentación
style: cambios de formato
refactor: refactorización de código
test: añadir o modificar tests
chore: tareas de mantenimiento
\`\`\`

### Code Review
- Todos los PRs requieren revisión de al menos 1 maintainer
- Tests automáticos deben pasar
- Lighthouse score debe mantenerse > 90
- Código debe seguir las convenciones del proyecto

## 📈 Roadmap

### v0.1 (Actual)
- ✅ Landing page completa
- ✅ Formulario de inscripción
- ✅ Páginas informativas
- ✅ Modelo 3D básico
- ✅ Responsive design

### v0.2 (Próximo)
- [ ] Integración Three.js avanzada
- [ ] CMS headless (Strapi/Contentful)
- [ ] Sistema de autenticación
- [ ] Dashboard administrativo
- [ ] Analytics avanzados

### v0.3 (Futuro)
- [ ] PWA capabilities
- [ ] Notificaciones push
- [ ] Chat en vivo
- [ ] Integración redes sociales
- [ ] Blog técnico

## 🐛 Issues Conocidos

### Limitaciones Actuales
- Modelo 3D básico (Canvas API) - migración a Three.js pendiente
- Formulario sin backend - integración con API pendiente
- Traducciones hardcodeadas - sistema i18n pendiente

### Workarounds
- Simulación de envío de formularios
- Contenido estático para demo
- Preparación para integraciones futuras

## 📞 Soporte

### Contacto del Equipo
- **Email:** dev@talpatunneling.upv.es
- **Slack:** #web-development
- **Issues:** GitHub Issues para bugs y features

### Documentación Adicional
- [Guía de Componentes](./docs/components.md)
- [API Reference](./docs/api.md)
- [Deployment Guide](./docs/deployment.md)

## 📜 Licencia

MIT © 2024 Talpa Tunneling UPV

---

**Desarrollado con ❤️ por el equipo de Talpa Tunneling UPV**

*Perforando el futuro, un commit a la vez.*
