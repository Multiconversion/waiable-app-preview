# Rediseño UX — Waiable Clínicas (`clinicas.waiable.com`)

Rediseño de **evolución visual premium** de TODA la aplicación, pantalla por pantalla. Parte de la identidad real del producto (`apps/web/app/globals.css`: teal `#0f766e`, light mode) y la eleva con un sistema visual en capas, mejor jerarquía, navegación agrupada, accesibilidad AA, estados vacíos y microcopy en español.

**41 pantallas** (40 vistas de la app + el sistema visual), agrupadas en 8 áreas.

> **Revisión exhaustiva v2 (mejora de usabilidad orientada a conversión):** se auditaron y mejoraron las 41 pantallas. Resultado de la auditoría técnica: **de 44 a 0 problemas reales**. Principales arreglos: **legibilidad** (ningún texto por debajo de 12px — antes había hasta 8px), acción de negocio destacada en cada pantalla (confirmar cita, responder, recuperar llamada, aprobar campaña, reservar en 30s…), bloques "qué hacer ahora", estados vacíos útiles, microcopy orientado al beneficio, accesibilidad AA (foco visible, labels, color + icono + texto) y `lang="es"` en todas. La versión anterior se conserva en `.backup-v1/` por si quieres comparar.

---

## ▶️ Cómo validarlo (lo más fácil)

1. Abre en tu navegador:
   ```
   /Users/borja/waiable-selfhosted/app-redesign/index.html
   ```
2. Es un **prototipo navegable**:
   - **Menú izquierdo** con las 41 pantallas agrupadas por área → clica cualquiera y se carga **en vivo** (puedes interactuar: tabs, tooltips, acordeones).
   - Botón **Galería** → todas las pantallas en miniatura de un vistazo; clica una para abrirla en vivo.
   - Botón **Abrir aparte** → la pantalla actual a pantalla completa en otra pestaña.

> Truco: ábrelo con doble clic desde Finder, o en terminal:
> `open /Users/borja/waiable-selfhosted/app-redesign/index.html`

---

## 📁 Estructura de la carpeta

```
app-redesign/
├── index.html              ← PROTOTIPO NAVEGABLE (empieza por aquí)
├── _sistema/
│   └── sistema-visual.html ← Guía del sistema de diseño "Waiable Premium"
├── acceso/                 login · registro · invitación
├── whatsapp/               inbox · cuentas · flujos · widget · plantillas · campañas · audiencias · analítica · alertas
├── clinicas/               agenda · huecos-ia · solicitudes · informes · configuración · servicios · profesionales · sedes · google-calendar
├── crm/                    contactos · ficha-contacto · oportunidades · llamadas · empresas · actividades-tareas · atribución · campos
├── ajustes/                cuenta · agenda-horarios · contactos · usuarios · suscripción · ia
├── plataforma/             integraciones · ops · saas
├── publico/                widget-reserva · confirmación  (vistas del paciente)
├── _capturas/              PNG full-page de cada pantalla (alta resolución)
└── _capturas-jpg/          JPG optimizados (para compartir/revisar rápido)
```

Cada `.html` es **autocontenido** (sin dependencias salvo la fuente Inter): puedes abrirlo solo, exportarlo a imagen/PDF o pasárselo a quien quieras.

---

## 🗂️ Las 41 pantallas por área

**Sistema (1):** Guía visual "Waiable Premium" (tokens, componentes, navegación, accesibilidad).

**Acceso (3):** Login · Registro de organización · Aceptar invitación.

**WhatsApp (9):** Bandeja/Inbox (con sugerencia de IA y medidor de confianza) · Cuentas · Flujos (constructor visual) · Widget embebible · Plantillas · Campañas · Audiencias · Analítica · Alertas y SLA.

**Clínicas (9):** Agenda/Calendario · Huecos IA (Smart Gaps) · Solicitudes · Informes · Configurar clínica (onboarding) · Servicios · Profesionales · Sedes · Google Calendar.

**CRM (8):** Contactos · Ficha 360 del paciente · Oportunidades (Kanban) · Llamadas · Empresas/Aseguradoras · Actividades y tareas · Atribución y fuentes · Campos personalizados.

**Ajustes (6):** Cuenta · Agenda y horarios · Campos de contacto · Usuarios y equipo · Suscripción y facturación · IA operativa.

**Plataforma (3):** Integraciones · Operaciones del sistema · Resumen SaaS.

**Paciente / público (2):** Widget de reserva · Confirmación de cita.

---

## 🎨 Qué cambia respecto a la app actual

- **Legibilidad:** nada por debajo de 12px, cuerpo 14-15px, pesos normales (400-700). Más aire (grid de 8px), tarjetas con sombra suave.
- **Navegación agrupada** en la sidebar (Inicio · Agenda · Conversaciones · Pacientes · Crecimiento · Configuración) con item activo inequívoco; topbar con buscador ⌘K y chips de estado.
- **Jerarquía:** cada pantalla con título + contexto + una acción primaria clara.
- **Estado y feedback:** badges con color **+ icono + texto** (accesible a daltónicos), estados vacíos útiles, confirmaciones en acciones destructivas.
- **Microcopy** en español de España, llano y orientado a la acción; tooltips de ayuda en conceptos nuevos (Huecos IA, score de IA, SLA).
- **Accesibilidad AA** y diseño responsive (la sidebar colapsa en pantallas estrechas).

---

## 🔁 Regenerar capturas / prototipo

```bash
cd /Users/borja/waiable-selfhosted/app-redesign/.render
node shot.mjs            # re-renderiza las 41 capturas a _capturas/
python3 build-index.py   # reconstruye index.html desde las pantallas
```
