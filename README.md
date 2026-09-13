# Rock Click

Metrónomo 4/4 con sonido de batería acústica de hard rock para practicar guitarra, bajo, batería o ritmo.

Rock Click funciona directamente en el navegador y utiliza muestras reales del **Salamander Drumkit**. El motor combina diferentes tomas, capas de intensidad y pequeñas variaciones de interpretación para que el acompañamiento resulte más natural y menos repetitivo.

## Funciones

- Tempo entre **60 y 180 BPM**, en pasos de 5 BPM.
- Compás de **4/4**.
- Subdivisión en negras o corcheas.
- Cuenta de entrada opcional de uno o dos compases.
- Sonido de cuenta de entrada independiente, inspirado en golpes de baquetas.
- Muestras reales de bombo, caja, charles, toms, crash y ride.
- Selección round-robin y capas de intensidad.
- Variaciones naturales de volumen, afinación, panorama y tiempo.
- Saturación, compresión, compresión paralela y reverberación corta en la mezcla de batería.
- Rellenos automáticos cada cuatro compases.
- Varias familias de rellenos seleccionadas automáticamente para evitar repeticiones consecutivas.
- Crash ocasional al inicio de algunas frases, independiente de los rellenos.
- Golpes fantasma suaves de caja.
- Mezclador con controles de volumen general, batería, bombo, caja, toms y platos/charles.
- Guardado de preferencias en el almacenamiento local del navegador.
- Interfaz adaptada a teléfonos y pantallas pequeñas.
- Icono propio para el navegador y para añadir la aplicación a la pantalla de inicio.
- Soporte para foco de teclado, lectores de pantalla y reducción de animaciones.

## Uso

Abre la aplicación en un navegador y pulsa **Iniciar**. En teléfonos, esta primera pulsación permite al navegador activar el audio.

El panel principal muestra:

- El tempo actual.
- El estado de reproducción.
- El compás y el pulso actuales.
- El indicador visual de los cuatro pulsos.
- El progreso de la frase.
- El resumen de la configuración activa.

Los controles más habituales están disponibles en **Ajustes rápidos**. El mezclador y las opciones de interpretación se encuentran en **Más controles**.

## Controles

### Ajustes rápidos

- **Tempo:** entre 60 y 180 BPM, en pasos de 5.
- **Subdivisión:** negras o corcheas.
- **Cuenta de entrada:** desactivada, un compás o dos compases.

Los rellenos aparecen automáticamente cada cuatro compases y ocupan los pulsos 3 y 4 de la última barra de la frase. El motor escoge distintas variaciones para reducir la monotonía.

### Más controles

- Carácter sonoro: hard rock potente o rock clásico.
- Volumen general y volumen de batería.
- Volumen independiente de bombo, caja, toms y platos/charles.
- Variación natural de la interpretación.
- Crash ocasional al inicio de algunas frases.
- Golpes fantasma suaves de caja.

### Atajos de teclado

- `Espacio`: iniciar o detener el metrónomo.
- `↑`: subir 5 BPM.
- `↓`: bajar 5 BPM.

## Uso local

La aplicación no necesita dependencias para utilizarse en un navegador. Para probarla localmente con el servidor incluido, hace falta tener Node.js instalado:

```bash
npm.cmd run dev
```

Después, abre esta dirección:

```text
http://127.0.0.1:8000/index.html
```

El servidor local es recomendable porque permite cargar correctamente las muestras FLAC desde el navegador.

## Audio y muestras

La batería utiliza 39 muestras FLAC del **Salamander Drumkit**, correspondientes a bombo, caja, charles, toms, crash y ride.

El motor de audio incluye:

- Variación round-robin para alternar tomas.
- Selección de capas según la intensidad del golpe.
- Humanización opcional del tiempo, volumen, panorama y afinación.
- Procesamiento de saturación y compresión para conseguir un sonido más contundente.
- Reverb corta para integrar la batería.
- Carga progresiva de las muestras al iniciar la reproducción.

La atribución completa, las fuentes originales y las condiciones de uso están documentadas en:

- [`SAMPLES-LICENSES.md`](SAMPLES-LICENSES.md)
- [`assets/backing/salamander/SOURCES.md`](assets/backing/salamander/SOURCES.md)

## Uso desde un teléfono Android

La aplicación puede utilizarse desde el navegador del teléfono. Para añadirla a la pantalla de inicio:

1. Abre la aplicación en Chrome.
2. Abre el menú del navegador.
3. Selecciona **Añadir a pantalla de inicio** o **Instalar aplicación**, según la versión de Chrome.
4. Confirma la instalación.

El icono se define mediante `site.webmanifest` y `assets/rock-click-icon.svg`. Si el teléfono continúa mostrando el icono anterior después de una actualización, elimina el acceso directo antiguo y vuelve a añadir la aplicación desde la página actualizada.

## Accesibilidad

- Los controles tienen etiquetas y descripciones accesibles.
- El estado del metrónomo se anuncia mediante regiones para lectores de pantalla.
- El foco de teclado es visible.
- Los objetivos táctiles tienen un tamaño cómodo para teléfonos.
- La información importante no depende únicamente del color.
- Se respetan las preferencias del sistema para reducir animaciones.

## Preferencias

Los ajustes se guardan en el almacenamiento local del navegador. Esto permite conservar el tempo, la mezcla y las opciones de interpretación entre sesiones en el mismo dispositivo y navegador.

El botón **Restablecer** devuelve los valores principales a su configuración inicial.

## Licencias y atribución

El código de la aplicación y las muestras de batería son elementos independientes.

Las muestras proceden del **Salamander Drumkit** y se distribuyen bajo la licencia **Creative Commons Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0)**. La atribución completa y los enlaces de licencia están disponibles en los documentos de fuentes incluidos en el proyecto.

La aplicación está preparada para uso personal y no comercial. La licencia original de las muestras se mantiene y no cambia por incluirlas en este proyecto.

## Estructura principal

```text
.
├── index.html                         Aplicación completa
├── site.webmanifest                   Metadatos e icono para instalación móvil
├── assets/rock-click-icon.svg         Icono de la aplicación
├── assets/backing/salamander/         Muestras FLAC y fuentes
├── SAMPLES-LICENSES.md                Resumen de licencias y atribución
├── package.json                       Script opcional del servidor local
├── serve-preview.cjs                  Servidor estático para uso local
└── README.md                          Esta documentación
```
