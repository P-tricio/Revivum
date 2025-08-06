# Revivum

# ✅ Checklist de Proyecto Fullstack: Revivum (Bootcamp Review)

Este checklist te guiará paso a paso para desarrollar Revivum como proyecto completo repasando todas las áreas del bootcamp.

---

## 📁 FASE 1: Planificación & Setup inicial

- [ ] **Definir alcance MVP**  
      Establece qué funcionalidades mínimas vas a desarrollar: registro, login, selección de cualidades, visualización de acciones diarias, feedback visual tras completar, y seguimiento de progreso.

- [ ] **Dibujar flujo de usuario y pantallas**  
      Usa lápiz o Figma para diseñar el flujo: pantalla de bienvenida → registro/login → selección de cualidades → vista de acciones diarias → feedback → progreso.

- [ ] **Esquematizar base de datos (MySQL)**  
      Define tablas como `usuarios`, `acciones`, `acciones_completadas`, `tests`, `niveles` y sus relaciones.

- [ ] **Definir endpoints del backend**  
      Apunta las rutas necesarias: `/register`, `/login`, `/acciones`, `/acciones/completar`, `/progreso`, etc.

- [ ] **Crear repositorio Git**  
      Haz `git init`, conecta con GitHub, sube `README.md` y estructura básica del proyecto.

- [ ] **Elegir stack tecnológico**  
      Vite + React para el frontend. Express + MySQL para backend. Railway o Render para deploy.

---

## 🔧 FASE 2: Setup del entorno

- [ ] **Inicializar frontend con Vite**  
      `npm create vite@latest revivum-frontend --template react`, luego instala dependencias y estructura carpetas.

- [ ] **Inicializar backend con Express**  
      Crea carpeta `revivum-backend`, instala `express`, `cors`, `mysql2`, y crea archivo `index.js`.

- [ ] **Conectar con MySQL (local o Railway)**  
      Usa `mysql2` y `.env` para credenciales. Prueba conexión a DB con un `ping`.

- [ ] **Configurar `.env`**  
      Guarda claves y conexiones en archivos `.env` tanto en frontend como en backend.

- [ ] **Permitir comunicación frontend ↔ backend (CORS)**  
      Usa el middleware `cors()` en Express. Añade proxy en Vite si es necesario.

- [ ] **Crear estructura de carpetas base**  
      Backend: `/routes`, `/controllers`, `/models`, `/middlewares`. Frontend: `/pages`, `/components`, `/context`.

---

## 🗃️ FASE 3: Base de datos

- [ ] **Crear tabla `usuarios`**  
      Campos: `id`, `email`, `password_hash`, `nombre`, `nivel_fuerza`, `nivel_motricidad`, etc.

- [ ] **Crear tabla `acciones`**  
      Campos: `id`, `nombre`, `cualidad`, `nivel`, `descripcion`, `tempo`, `imagen_url`.

- [ ] **Crear tabla `acciones_completadas`**  
      Campos: `id`, `usuario_id`, `accion_id`, `fecha_completada`.

- [ ] **Crear tabla `tests` (opcional)**  
      Para validar si el usuario sube de nivel en cada cualidad.

- [ ] **Insertar ejemplos en todas las tablas**  
      Prueba con datos dummy y realiza consultas con SQL.

---

## 🔙 FASE 4: Backend – API funcional

- [ ] **Endpoint `POST /register`**  
      Recibe email y password, la hashea con bcrypt y guarda el usuario.

- [ ] **Endpoint `POST /login`**  
      Verifica email/password, genera token JWT y lo devuelve.

- [ ] **Middleware de autenticación JWT**  
      Protege rutas privadas comprobando el token en headers.

- [ ] **Endpoint `GET /acciones`**  
      Devuelve las acciones según cualidad y nivel del usuario.

- [ ] **Endpoint `POST /acciones/completar`**  
      Registra en la tabla de historial que el usuario ha completado una acción.

- [ ] **Endpoint `GET /progreso`**  
      Muestra acciones completadas, niveles y evolución.

---

## 🖥️ FASE 5: Frontend – Interfaz de usuario

- [ ] **Formulario de registro y login**  
      Inputs para email, password, nombre. Consume los endpoints.

- [ ] **Pantalla de selección de cualidades**  
      Permite al usuario elegir en qué cualidades quiere progresar.

- [ ] **Pantalla de acciones diarias**  
      Muestra lista filtrada por cualidad y nivel con botón "Hecho".

- [ ] **Botón de feedback inmediato al completar acción**  
      Cambia color, muestra mensaje o animación, y llama a `/acciones/completar`.

- [ ] **Vista de progreso visual (semilla → flor)**  
      Muestra evolución simbólica según número de acciones completadas.

- [ ] **Historial (opcional)**  
      Lista acciones anteriores del usuario con fechas.

---

## 🔐 FASE 6: Autenticación

- [ ] **Guardar JWT al hacer login**  
      Usa `localStorage` o `context` para guardar el token.

- [ ] **Mantener sesión activa**  
      Comprueba si hay token al recargar y úsalo en headers de fetch.

- [ ] **Proteger rutas privadas**  
      Redirige al login si no hay token válido.

- [ ] **Cerrar sesión (logout)**  
      Borra el token del almacenamiento local y redirige al login.

---

## 🎨 FASE 7: Diseño y experiencia de usuario

- [ ] **Aplicar estilos globales o CSS modular**  
      Define paleta de colores, tipografía y espaciado consistente.

- [ ] **Diseñar narrativa visual (planta en crecimiento)**  
      Usa SVGs o imágenes para representar: semilla → brote → planta → flor.

- [ ] **Mostrar progreso claramente**  
      Vincula el número de acciones completadas al estado visual de la planta.

- [ ] **Control de tempo (si se usa)**  
      Muestra metrónomo visual o cuenta atrás si la acción lo requiere.

---

## 🚀 FASE 8: Deploy

- [ ] **Deploy del frontend (Vercel/Netlify)**  
      Sube proyecto, configura build (`vite`) y variables de entorno.

- [ ] **Deploy del backend (Railway/Render)**  
      Sube proyecto Express y configura conexión DB en `.env`.

- [ ] **Configurar dominios y CORS en producción**

- [ ] **Verificar app completa online**

---

## ⭐ EXTRAS (opcional)

- [ ] **Sistema de rachas y logros**
- [ ] **Sistema de tests para subir de nivel**
- [ ] **Modo "nueva semilla" tras completar una flor**
- [ ] **Guía virtual o asistente**
- [ ] **Notificaciones y consejos desbloqueables**
