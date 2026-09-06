# Rock Click

Metrónomo 4/4 con batería acústica de hard rock para practicar ritmo, guitarra, bajo o batería.

La aplicación funciona directamente en el navegador y utiliza muestras reales del **Salamander Drumkit**, con variaciones de interpretación para que el patrón resulte menos repetitivo.

## Funciones

- Tempo entre **60 y 180 BPM**, en pasos de 10 BPM.
- Compás actual de **4/4**.
- Subdivisión en negras o corcheas.
- Cuenta de entrada opcional de uno o dos compases.
- Sonido de cuenta de entrada independiente, inspirado en golpes de baquetas.
- Muestras reales de bombo, caja, charles, toms y platos.
- Selección round-robin y capas de intensidad.
- Variaciones sutiles de volumen, afinación, paneo y tiempo.
- Saturación, compresión, compresión paralela y reverb corta para el bus de batería.
- Rellenos automáticos cada cuatro compases.
- Varias familias de rellenos seleccionadas automáticamente para evitar repeticiones consecutivas.
- Crash ocasional al inicio de algunas frases, independiente de los rellenos.
- Golpes fantasma suaves de caja.
- Mezclador con controles de volumen general, batería, bombo, caja, toms y platos/charles.
- Guardado de preferencias en el almacenamiento local del navegador.
- Interfaz adaptada a móviles.
- Atajos de teclado:
  - `Espacio`: iniciar o detener.
  - `↑`: subir 10 BPM.
  - `↓`: bajar 10 BPM.
- Soporte para foco de teclado, lectores de pantalla y reducción de animaciones.

## Uso local

No necesita instalar dependencias para utilizar la aplicación.

La forma más sencilla es abrir `index.html` en un navegador. Sin embargo, para que todos los navegadores sirvan correctamente los archivos FLAC locales, es preferible usar el servidor estático incluido:

```bash
npm.cmd run dev
```

Después, abre:

```text
http://127.0.0.1:8000/index.html
```

También se puede utilizar `npm run dev` desde macOS o Linux si Node.js está instalado.

## Publicar en un repositorio personal de GitHub

### 1. Crear el repositorio

1. Entra en [GitHub](https://github.com/).
2. Crea un repositorio nuevo para tu cuenta personal.
3. Puedes llamarlo, por ejemplo, `rock-click` o `metronomo-hard-rock`.
4. No es necesario añadir un README desde GitHub, porque este proyecto ya incluye uno.

### 2. Subir los archivos

Desde la carpeta raíz del proyecto, ejecuta:

```bash
git init
git add index.html package.json serve-preview.cjs README.md SAMPLES-LICENSES.md .gitignore assets/backing/salamander
git commit -m "Preparar Rock Click para publicación personal"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/NOMBRE_DEL_REPOSITORIO.git
git push -u origin main
```

Sustituye `TU_USUARIO` y `NOMBRE_DEL_REPOSITORIO` por los valores de tu cuenta y repositorio.

> Si GitHub te pide autenticación, utiliza el método recomendado por GitHub, como GitHub CLI, un token personal o una clave SSH. No guardes contraseñas dentro de este proyecto.

### 3. Activar GitHub Pages

1. Abre el repositorio en GitHub.
2. Entra en **Configuración (Settings)**.
3. Abre la sección **Pages**.
4. En **Compilación y despliegue (Build and deployment)**, selecciona **Desplegar desde una rama (Deploy from a branch)**.
5. Selecciona la rama `main` y la carpeta `/ (raíz) (root)`.
6. Pulsa **Guardar (Save)**.
7. Espera a que GitHub Pages publique el sitio.

La dirección tendrá normalmente esta forma:

```text
https://TU_USUARIO.github.io/NOMBRE_DEL_REPOSITORIO/
```

GitHub Pages sirve `index.html` como página principal y conserva las rutas relativas de las muestras, por lo que la aplicación podrá cargar los archivos de:

```text
assets/backing/salamander/
```

## Usarlo desde el móvil

1. Abre la dirección de GitHub Pages desde el teléfono.
2. Pulsa **Iniciar** para permitir que el navegador active el audio.
3. Si quieres, añade la página a la pantalla de inicio del móvil.
4. Ajusta el volumen del teléfono antes de comenzar a practicar.

Los navegadores móviles bloquean el audio que intenta comenzar sin interacción del usuario; por eso la reproducción empieza al pulsar el botón **Iniciar**.

## Licencias y atribución

El código de esta aplicación y las muestras de batería deben considerarse por separado.

Las muestras proceden del **Salamander Drumkit** y se distribuyen bajo la licencia **Creative Commons Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0)**. La atribución completa, las fuentes y los enlaces de licencia están disponibles en:

- [`SAMPLES-LICENSES.md`](SAMPLES-LICENSES.md)
- [`assets/backing/salamander/SOURCES.md`](assets/backing/salamander/SOURCES.md)

La aplicación se ha preparado para uso personal y no comercial. La licencia de las muestras sigue siendo la licencia original y no se modifica por incluirlas en este repositorio.

Si en el futuro se distribuye públicamente una versión modificada, hay que conservar la atribución y respetar las condiciones de la licencia CC BY-SA 3.0.

## Estructura principal

```text
.
├── index.html                         Aplicación completa
├── package.json                       Script opcional del servidor local
├── serve-preview.cjs                  Servidor estático para desarrollo local
├── README.md                          Esta documentación
├── SAMPLES-LICENSES.md                Resumen de licencias y atribución
└── assets/
    └── backing/
        └── salamander/                Muestras FLAC y documentación de origen
```

## Notas para GitHub Pages

- No necesita Node.js para ejecutarse una vez publicado.
- No necesita base de datos, backend ni variables de entorno.
- No hay que subir la carpeta `.freebuff`; es configuración interna de Preview y queda excluida mediante `.gitignore`.
- No hay que subir `node_modules` si se crea localmente.
- Las rutas de las muestras deben conservarse exactamente.
- GitHub Pages debe publicar desde la raíz de la rama que contiene `index.html`.
- Si el audio no empieza en el móvil, pulsa primero **Iniciar** y comprueba que el dispositivo no esté en silencio.
