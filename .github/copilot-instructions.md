# Instrucciones para agentes AI (Copilot)

Resumen rápido
- Repositorio mínimo: sitio estático con un solo archivo HTML: [login.html](login.html#L1-L15).
- Idioma del contenido: español (atributo `lang="es"`). Codificación: UTF-8.

Qué debe saber un agente antes de editar
- Este proyecto no tiene pipeline, dependencias ni tests; cambios son archivos estáticos.
- Evitar introducir dependencias externas sin pedirlo: el propietario espera HTML/CSS/JS simples.

Patrones y decisiones visibles
- Estructura actual: archivo raíz `login.html` contiene meta `charset` y `viewport`.
- Localización: todo el texto visible está en español — mantener `lang="es"` y textos en español.

Flujos de desarrollo (prácticos)
- Ver cambios localmente: abrir `login.html` en el navegador o servir el directorio:

```bash
python -m http.server 8000
# o (si tiene npm instalado)
npx http-server -c-1 .
```

- Edición rápida: pruebe en el navegador y haga commits pequeños y descriptivos.

Convenciones recomendadas para cambios (conservadoras)
- Si añade CSS, colóquelo en `css/` y enlace con `<link rel="stylesheet" href="css/main.css">`.
- Si añade JS, colóquelo en `js/` y use `defer` en el `script` para no bloquear el render:

```html
<script src="js/main.js" defer></script>
```

- Mantener la página en Español y UTF-8; no traduzca automáticamente textos.

Ejemplo pequeño — añadir un formulario de login (si se solicita):

```html
<!-- Añadir dentro del <body> de login.html -->
<form id="loginForm" action="/login" method="post">
  <label>Usuario<input name="username" required></label>
  <label>Contraseña<input name="password" type="password" required></label>
  <button type="submit">Ingresar</button>
</form>
```

Puntos de integración y limitaciones
- No hay backend ni rutas en este repo; cualquier integración con servidor o API debe especificarse explícitamente.
- No hay pruebas automatizadas; los cambios deben validarse manualmente en el navegador.

Solicita aclaraciones
- Si quieres que añada estilos, comportamiento JS o integración con un backend, dime el objetivo y el endpoint/stack esperado.

Contacto/Feedback
- Después de aplicar cambios, pídeme ejecutar pasos de validación o ajustar el documento si falta contexto.
