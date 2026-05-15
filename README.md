# CV_Generator

Frontend del generador de CV — SPA construida con **Angular 18 + TypeScript**, signals nativos, i18n en tiempo real (EN/ES) y exportación delegada al backend.

Todo el estado del CV vive en el navegador (Angular signals). No hay backend de sesiones, no hay cookies, no hay cuenta de usuario. El usuario rellena el formulario, pulsa exportar, y el archivo se descarga directamente.

---

## Stack

| Capa | Tecnología |
|---|---|
| Framework | Angular 18 (standalone components) |
| Lenguaje | TypeScript 5.x |
| Estilos | SCSS + CSS custom properties |
| Estado | Signals nativos de Angular (sin librerías externas) |
| i18n | @ngx-translate/core (cambio de idioma en caliente) |
| HTTP | HttpClient + interceptors |
| Tests | Jest + Angular Testing Library |
| Despliegue | GitHub Pages (gratis, 24/7) |

---

## Arquitectura: el front es el único dueño del estado

Si el usuario cierra el navegador, el CV desaparece (es la sesión). Puede exportarlo antes o, en una iteración futura, añadir "guardar como JSON" para importarlo de nuevo. No se necesita base de datos para esto.

---

## Signals — patrón central de estado

Todo el CV se guarda en un único signal en `cv.store.ts`. Los componentes leen y escriben desde ahí:

---

## Configuración local

### Requisitos

- Node.js 20+
- Angular CLI 18: `npm install -g @angular/cli`

### Arrancar el proyecto

```bash
git clone https://github.com/HectorJarque/CV_Generator_Frontend.git
cd Frontend
npm install
ng serve
```

La app estará en `http://localhost:4200`.  
El backend debe estar corriendo en `localhost:8080` para que el export funcione. La previsualización de las plantillas se renderiza íntegramente en el front y no necesita conexión al backend.

---


## Tests

```bash
npm test
```

---
