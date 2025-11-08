# FokusCurso

Pequeña aplicación web de temporizador estilo Pomodoro para mejorar la concentración y gestionar descansos.

## Descripción

Esta aplicación permite alternar entre tres contextos de tiempo: enfoque (25 min), descanso corto (5 min) y descanso largo (15 min). Incluye controles para iniciar/pausar, activar música de fondo y reproduce sonidos para acciones como iniciar, pausar y finalizar.

Es un proyecto de práctica para aprender manipulación del DOM con JavaScript puro.

## Características

- Selección de contexto: `enfoque` (25 min), `descanso-corto` (5 min), `descanso-largo` (15 min).
- Mostrar el tiempo restante en pantalla en formato mm:ss.
- Iniciar / Pausar el temporizador.
- Música de ambiente opcional y sonidos para acciones y finalización.
- Cambio visual del banner y del título según el contexto.

## Estructura del proyecto

- `index.html`  — Página principal.
- `styles.css`  — Estilos.
- `script.js`   — Lógica principal (manipulación del DOM, temporizador, audio).
- `imagenes/`   — Imágenes usadas (banners, íconos, etc.).
- `sonidos/`    — Archivos de audio (.mp3, .wav) usados por la app.

Los archivos clave a revisar son `script.js` y `index.html`.

## Controles y comportamiento

- Botones de contexto: seleccionan el tiempo y actualizan la UI.
- Botón `Comenzar` / `Pausar`: inicia o detiene la cuenta regresiva.
- Switch de música: activa/desactiva la música de fondo.
- Cuando el tiempo llega a 0 se reproduce un sonido y se muestra una alerta.

En `script.js` verás variables como `botonEnfoque`, `botonCorto`, `botonLargo`, `botonIniciarPausar`, `inputMusicaEnfoque` y funciones como `cambiarContexto()`, `cuentaRegresiva()` y `mostrarTiempo()`.

## Cómo probar localmente

La app es estática; puedes simplemente abrir `index.html` en un navegador (doble clic o "Abrir con..." desde el explorador). Sin embargo, algunos navegadores pueden restringir la carga de ciertos recursos (audio, fetch, etc.) cuando se abre el archivo directamente, por lo que es conveniente usar un servidor local ligero.

Opciones recomendadas:


- Abrir directamente (rápido):

  - Desde el explorador de archivos, doble clic en `index.html` o abrirlo con el navegador.
  - Útil para pruebas rápidas; si notas problemas con audio o rutas, usa un servidor local.

- Con Node (http-server):

```powershell
# Instalar globalmente (una sola vez)
npm install -g http-server
# Servir la carpeta actual en el puerto 8000
http-server -p 8000
# Luego abrir http://localhost:8000 en el navegador
```

- Con npx (sin instalar globalmente):

```powershell
# Servir la carpeta actual con 'serve' rápidamente
npx serve -p 8000
# Luego abrir http://localhost:8000
```


- Extensión Live Server en VS Code (recomendada para desarrollo):

  - Instala la extensión "Live Server" y pulsa "Go Live" en la esquina inferior para servir la carpeta del proyecto.

Elige la opción que prefieras; para la mayoría de usos de desarrollo la extensión Live Server o `npx serve` son rápidas y simples.

## Capturas de pantalla

Las siguientes imágenes muestran la interfaz y distintos estados de la app. Los archivos están en la carpeta `screenshots/`.

### Vista de enfoque

![Enfoque](screenshots/Foco%20-%20Vazio%20(Desktop).png)

### Descanso corto

![Descanso corto](screenshots/Modo%20descanso%20curto%20(Desktop).png)

### Descanso largo

![Descanso largo](screenshots/Descanso%20longo%20(Desktop).png)

## Notas de desarrollo

- Los recursos de audio están en `sonidos/` y las imágenes en `imagenes/`. Asegúrate de que los nombres de archivo y las rutas coincidan con los referenciados en `script.js` (ej. `./sonidos/luna-rise-part-one.mp3`).
- El tiempo se formatea con `toLocaleTimeString('es-ES', {minute: '2-digit', second: '2-digit'})` en `mostrarTiempo()`.

## Posibles mejoras (sugerencias)

- Reemplazar `alert()` por un modal o notificación personalizada.
- Guardar el contexto y el estado (en curso/pausado) en localStorage para persistencia.
- Añadir ajustes personalizados para duración de sesiones.
- Mejores controles de accesibilidad (focus visible, labels ARIA, etc.).

## Autor

Proyecto de práctica — Daniel Rivera Alpízar.

## Licencia
Este proyecto está bajo la licencia MIT. Consulta el archivo `LICENSE` para el texto completo.
