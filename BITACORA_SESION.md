# 📓 Bitácora de Sesión: Instituto Sobre'Viver
**Fecha:** 23 de Abril de 2026
**Objetivo Principal:** Independización de Supabase, migración a Vercel (Local Assets) y estabilización del entorno de despliegue.

## 🚀 Resumen de Acciones Realizadas

### 1. Migración de Assets (Imágenes y Galería)
- Se detectó que el proyecto dependía de URLs absolutas apuntando al Storage de Supabase para las imágenes.
- Se descargaron en bloque **todas las imágenes `.webp`** y se almacenaron en la carpeta `public/images/` del repositorio `instituto-sobreviver-v2`.
- Se refactorizaron **13 componentes React** (`Hero.tsx`, `MetamorphosisDesktop.tsx`, etc.), reemplazando las URLs de Supabase por rutas relativas rápidas (`/images/...`).
- Se corrigió un bug en la sección de "Histórias de vida" (`HumanImpactGallery.tsx`), donde 22 imágenes dinámicas no cargaban. Se descargaron manualmente (`galeria1.webp` a `galeria22.webp`) y se aseguraron en el repositorio.
- Se resolvió un bug de rutas dinámicas ocultas en la versión móvil (`MetamorphosisMobile.tsx`), descargando e inyectando las 6 imágenes requeridas (`meta-movil-*.webp`) al repositorio.

### 2. Resolución de Errores (PDF 404)
- El botón "Baixar PDF completo" en `ImperativoDignidade.tsx` arrojaba error 404 en producción.
- Se identificó que el archivo físico `o-imperativo-da-dignidade.pdf` estaba fuera del directorio público.
- Se movió correctamente a `public/assets/brand/o-imperativo-da-dignidade.pdf`, garantizando su descarga estática a través de Vercel.

### 3. Limpieza de Infraestructura
- El directorio de trabajo raíz (`sitio-completo`) tenía repositorios redundantes y desactualizados (`instituto-sobreviver` Next.js y `proyecto-test`).
- Se eliminaron las carpetas obsoletas para evitar confusión en el código.
- **Repositorio canónico establecido:** Únicamente se conservó la carpeta `instituto-sobreviver-v2`, la cual está vinculada exitosamente al despliegue en Vercel.

### 4. Configuración Final para Entrega
- Todos los cambios se enviaron (`git push`) a la rama `main`.
- Vercel compiló y desplegó los cambios sin errores.
- El usuario reconfiguró el dominio en el Dashboard de Vercel.
- **URL Pública Final:** `https://instituto-sobreviver.vercel.app`

## 📌 Estado Actual
- **Infraestructura:** Vite + React + Tailwind + GSAP.
- **Hosting:** Vercel (Sin dependencias de bases de datos o buckets externos).
- **Estatus:** El sitio está optimizado, con assets empaquetados localmente y listo para ser entregado al cliente final.

---
*Nota para futuras sesiones: Cualquier modificación visual o de contenido debe realizarse exclusivamente sobre el directorio `instituto-sobreviver-v2` y hacer push a `main` para ver los cambios reflejados en Vercel.*
