# Radar de Licitaciones - Mercado Publico para Enel

Revisa Mercado Publico 2 veces al dia, filtra licitaciones de energia,
alumbrado publico, fotovoltaico y camaras/videovigilancia, las analiza
con Claude y te envia un correo estilo noticias con links directos.

## Paso 1: Sacar ticket de la API de Mercado Publico
1. Entra a https://www.mercadopublico.cl
2. 2. Busca la seccion API / Desarrolladores (o el portal de datos abiertos de ChileCompra).
   3. 3. Registrate y solicita un ticket para la API publica de licitaciones. Es gratis.
      4. 4. Guarda ese ticket, lo necesitas en el Paso 4.
        
         5. ## Paso 2: Crear una cuenta Gmail para enviar los correos
         6. 1. Puede ser una cuenta Gmail nueva o una que ya tengas (no uses tu correo Enel para ENVIAR, solo para RECIBIR).
            2. 2. Activa la verificacion en 2 pasos: https://myaccount.google.com/security
               3. 3. Genera una Contrasena de aplicacion: https://myaccount.google.com/apppasswords
                 
                  4. ## Paso 3: Conseguir una API key de Anthropic
                  5. 1. Entra a https://console.anthropic.com
                     2. 2. Crea una cuenta / inicia sesion y genera una API key.
                       
                        3. ## Paso 4: Configurar los secrets en GitHub
                        4. Ve a: Settings -> Secrets and variables -> Actions -> New repository secret, y agrega estos 5 secrets:
                        5. - MP_TICKET
                           - - ANTHROPIC_API_KEY
                             - - GMAIL_USER
                               - - GMAIL_APP_PASSWORD
                                 - - DEST_EMAIL
                                  
                                   - ## Paso 5: Probar
                                   - 1. Ve a la pestana Actions del repositorio.
                                     2. 2. Entra al workflow Radar Licitaciones Mercado Publico.
                                        3. 3. Click en Run workflow para probarlo manualmente.
                                           4. 4. Revisa tu correo Enel y los logs si algo falla.
                                             
                                              5. ## Ajustes
                                              6. - Horarios: en .github/workflows/licitaciones.yml, cambia los cron (estan en UTC).
                                                 - - Palabras clave: en buscar_licitaciones.py, la lista KEYWORD_MAP.
                                                   - - Limite por corrida: MAX_LICITACIONES_POR_CORRIDA.
                                                     - 
