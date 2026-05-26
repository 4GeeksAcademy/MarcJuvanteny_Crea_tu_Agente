# Notas de Configuración - Agente de Telegram (Gmail & Drive)

## Decisiones de diseño
* **Interfaz unificada:** Se eligió Telegram como canal principal porque permite interactuar con el agente en tiempo real desde cualquier dispositivo mediante lenguaje natural.
* **Integración de herramientas:** Conectamos las APIs de Gmail y Google Drive para que el agente pueda leer/redactar correos y gestionar archivos directamente desde el chat.

## Problemas encontrados y soluciones
* **Conexión Telegram-IA:** El primer gran problema fue lograr que la IA respondiera en el chat. Costó configurar correctamente el webhook (o el bucle de escucha) para que los mensajes de Telegram llegaran al modelo de IA y este devolviera la respuesta al usuario.
* **Permisos de Google (OAuth2):** Al conectar Gmail y Drive, el agente no podía acceder a los datos. Se solucionó configurando las credenciales de Google y activando los permisos específicos (scopes) necesarios para leer y escribir.