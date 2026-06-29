# Instrucciones del Workspace — Canal de Estoicismo

## Cómo arrancar los creadores (Servidor Local)

Para ejecutar `Creador_de_Carruseles.html` y `Creador_de_Videos.html` localmente sin problemas de CORS (requerido porque el creador de vídeos lee `./animations.jsx` mediante fetch):


1. **Levantar un servidor web local** en el directorio raíz del proyecto:
   `npx -y http-server -p 8080`
   *(Alternativa si no hay Node: `python -m http.server 8080`)*
2. **Acceder en el navegador Chrome** (necesario por soporte de `WebCodecs`/`VideoEncoder` al grabar vídeos):
   - Creador de Carruseles: http://localhost:8080/Creador_de_Carruseles.html
   - Creador de Vídeos: http://localhost:8080/Creador_de_Videos.html
