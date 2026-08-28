# Molinari Control Operativo — versión tablet (sin app store, sin compilar)

Esta carpeta (`docs/`) es una app web instalable (PWA). GitHub la sirve por HTTPS y desde
la tablet se "instala" con un toque en Chrome — queda como un ícono normal, abre a
pantalla completa, sin barra de navegador, y funciona sin conexión después de la primera
vez. No hay .apk, no hay compilación, no hay Android Studio ni GitHub Actions de por medio.

## Publicar (una sola vez)

1. En GitHub Desktop, hacé "commit" de estos archivos (ya deberían aparecer en la lista de
   cambios) y "Push origin" para subirlos.
2. En github.com, dentro del repositorio → **Settings** → **Pages** (menú de la izquierda).
3. En "Build and deployment" → "Source": elegí **"Deploy from a branch"**.
4. Debajo, en "Branch": elegí **main** y la carpeta **/docs** → **Save**.
5. Esperá 1-2 minutos. GitHub te muestra la URL pública (algo como
   `https://TUUSUARIO.github.io/TUREPO/`).

## Instalar en la tablet

1. Abrí Chrome en la tablet y entrá a esa URL.
2. Menú de Chrome (⋮, arriba a la derecha) → **"Instalar app"** (o "Añadir a pantalla de
   inicio").
3. Listo — queda un ícono de Molinari en la tablet que abre la app sin mostrar el
   navegador, como cualquier otra app.

## Actualizaciones futuras

Si más adelante cambio algo del `index.html`, el proceso es: reemplazar los archivos
en esta carpeta → commit → push. La app en la tablet se actualiza sola la próxima vez que
tenga conexión (el service worker revisa cambios en segundo plano).

## Los datos NO se sincronizan solos

Cada dispositivo (PC, tablet) guarda sus datos por separado. Para pasar información de
uno a otro: **"⬇️ Exportar copia"** en el que tiene los datos nuevos → mandás el .json
por WhatsApp, correo o donde prefieras → **"⬆️ Importar copia"** en el otro. Se puede
importar el mismo archivo más de una vez sin duplicar nada (lo que ya existe se omite).
