# Molinari Control Operativo — Android (.apk)

Esta carpeta es un proyecto completo para generar la app de Android. La compilación real del `.apk` no se puede hacer en este entorno (no tiene acceso a los servidores de Google necesarios), así que se hace gratis en la nube de GitHub, en unos 3-5 minutos, sin instalar nada pesado en tu computadora.

## Paso 1 — Crear cuenta en GitHub (si no tenés)

Andá a https://github.com/signup y creá una cuenta gratuita.

## Paso 2 — Crear un repositorio nuevo

1. Entrá a https://github.com/new
2. Nombre: `molinari-control-operativo` (o el que quieras)
3. Dejalo en **Private** (privado) — es tu código, no hace falta que sea público.
4. NO marques "Add a README" ni ninguna otra opción — dejalo vacío.
5. Hacé clic en "Create repository".

## Paso 3 — Subir esta carpeta al repositorio

GitHub te va a mostrar una página con comandos. La forma más simple sin usar la terminal:

1. En la página de tu repositorio recién creado, buscá el enlace **"uploading an existing file"**.
2. Arrastrá TODOS los archivos y carpetas que están dentro de esta carpeta (`molinari_android`) — incluida la carpeta `.github` y la carpeta `android` completas. Si GitHub no te deja arrastrar carpetas ocultas como `.github` desde el navegador, usá en su lugar GitHub Desktop (https://desktop.github.com) o pedime que te pase los comandos de `git` para hacerlo por línea de comandos.
3. Hacé "Commit changes" (confirmar cambios).

**Importante:** no hace falta subir la carpeta `node_modules` (si la ves) ni `android/.gradle` ni `android/app/build` — son archivos temporales que se generan solos.

## Paso 4 — Esperar la compilación automática

1. Andá a la pestaña **"Actions"** de tu repositorio en GitHub.
2. Vas a ver un flujo llamado "Build APK" corriendo (círculo amarillo girando).
3. Esperá unos 3-5 minutos hasta que se ponga verde (✓).
4. Si se pone rojo (✗), hacé clic para ver el error y pasámelo — lo reviso y te digo qué corregir.

## Paso 5 — Descargar el .apk

1. Con el flujo en verde, hacé clic sobre esa ejecución.
2. Abajo de todo vas a ver **"Artifacts"** → `Molinari-Control-Operativo-APK`.
3. Hacé clic para descargar — es un .zip que contiene el archivo `app-debug.apk`.

## Paso 6 — Instalar en la tablet

1. Pasá el archivo `app-debug.apk` a la tablet (por USB, por correo, por Google Drive, como prefieras).
2. En la tablet, tocá el archivo `.apk` para instalarlo.
3. Android va a pedir permiso para "instalar apps de orígenes desconocidos" (porque no viene de Google Play) — aceptalo solo para este archivo.
4. Listo — te va a quedar el ícono de "Molinari Control Operativo" en la tablet, como una app normal.

## Sobre los datos: tablet y PC son independientes

La tablet tiene su propia base de datos, separada de la del PC — no hay sincronización automática (armar eso es un proyecto de infraestructura mucho más grande, con un servidor propio). Lo que sí tiene la app es una sincronización **manual**:

- Botón **"⬇️ Exportar copia"**: genera un archivo `.json` con todos tus clientes, presupuestos y facturas.
- Botón **"⬆️ Importar copia"**: lee ese archivo en el otro dispositivo y agrega lo que falte (lo que ya existe — mismo cliente, mismo número de presupuesto/factura — se omite, así que podés importar el mismo archivo varias veces sin duplicar nada).

Flujo típico: trabajás en el taller del cliente con la tablet → "Exportar copia" → pasás el .json al PC (por correo, Drive, USB) → en el PC, "Importar copia". Y al revés si cargás algo primero en el PC.

## Actualizaciones futuras

Si más adelante querés otra mejora en la app, avisame y actualizo el archivo `www/index.html` de este mismo proyecto (y el de tu PC) — después solo hace falta volver a subir los cambios a GitHub para que se genere un `.apk` nuevo.
