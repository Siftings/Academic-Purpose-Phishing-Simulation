# Laboratorio 8 — Simulación de Phishing · Frontend

Proyecto frontend del Laboratorio 8 de la materia **Ciberseguridad** de la **Universidad de los Andes**. Implementa la interfaz de una simulación de phishing tipo *evil-twin* con fines exclusivamente académicos y pedagógicos.

El backend es desarrollado y mantenido en un repositorio externo por otro integrante del equipo. Este frontend se conecta a él a través de su API REST.

---

## Propósito

Demostrar de forma práctica y controlada el funcionamiento de un ataque de phishing institucional, registrando únicamente metadatos de interacción (sin capturar contraseñas), y redirigiendo al usuario a una página educativa que explica lo ocurrido.

---

## Páginas

| Archivo | Descripción |
|---|---|
| `index.html` | Página de login simulada que imita el portal institucional de Uniandes |
| `awareness.html` | Página educativa en español mostrada tras la interacción |
| `dashboard.html` | Panel de evidencias con estadísticas y logs de interacciones |
| `styles.css` | Estilos compartidos entre todas las páginas |

---

## Flujo de la simulación

```
Correo phishing ficticio
        ↓
Login simulado (index.html)
  → Registra click al enfocar el formulario
  → Registra submit al enviar (solo email, sin contraseña)
        ↓
Página educativa (awareness.html)
  → Informa que fue una prueba de phishing
  → Recursos educativos + enlace al sitio oficial
        ↓
Dashboard de evidencia (dashboard.html)
  → Estadísticas e historial de interacciones para el informe
```

---

## Requisitos

- El backend debe estar corriendo en `http://localhost:3000`
- Un servidor estático local en el puerto `4200` (para respetar la configuración CORS del backend)

---

## Cómo ejecutar

**1. Iniciar el backend** (repositorio externo):
```bash
npm run start:dev
```

**2. Servir el frontend en el puerto 4200:**
```bash
npx serve -p 4200 .
```

O con Python:
```bash
python3 -m http.server 4200
```

**3. Abrir en el navegador:**

| URL | Descripción |
|---|---|
| `http://localhost:4200` | Página de login simulada |
| `http://localhost:4200/awareness.html` | Página educativa |
| `http://localhost:4200/dashboard.html` | Dashboard de evidencias |

---

## Privacidad y datos

Este proyecto **nunca captura ni almacena contraseñas**. Los únicos datos registrados por el backend son:

- Correo electrónico ingresado en el formulario
- Tipo de interacción (`click` o `submit`)
- Timestamp generado por el servidor
- Dirección IP del request
- User-agent del navegador

---

## Contexto académico

> Este proyecto fue desarrollado como parte del **Laboratorio 8** de la materia **Ciberseguridad** de la **Universidad de los Andes**. Su uso está restringido al entorno controlado del laboratorio. Cualquier uso fuera de este contexto académico está estrictamente prohibido.
