# 05-FESTIVAL-CONTROL-AMPLIFY

## FESTIVAL CONTROL · React Native + Expo Web

Demo para la charla de AWS Amplify. Mantiene la identidad visual del cuaderno 04-PILARES-SERVERLESS: fondo `#090909`, cards `#151515`, acento `#FF2F92`, confirmado `#39D98A` y retrasado `#F5C542`.

## Inicio rápido

```bash
npm install
npx expo install --fix
npm run web
```

## Backend Amplify Gen 2

El backend define una API de datos con el modelo `FestivalEvent` en `amplify/data/resource.ts`. Para probarlo en una cuenta AWS, configura credenciales de AWS y ejecuta:

```bash
npm run sandbox
```

El sandbox crea los recursos en tu cuenta y genera `amplify_outputs.json`. Ese archivo está ignorado por Git. En Amplify Hosting, conecta la rama `main` con el rol de servicio y las credenciales necesarias; `amplify.yml` despliega el backend por rama antes de construir la web.

La API usa una clave pública de 30 días para facilitar la demo. Permite acceso público al modelo y no debe usarse con datos reales ni en producción. La interfaz actual continúa trabajando con estado local; aún no está conectada a esta API.

## Exportación para AWS Amplify Hosting

```bash
npm run build:web
```

El resultado estático se genera en `dist/`. En Amplify: conectar GitHub, rama `main`, usar `amplify.yml` y publicar `dist/`.

## Prueba de alumno

1. Abrir **Eventos** y filtrar por escenario o artista.
2. Crear `TECHNO TITANS`, escenario `MAIN STAGE`, hora `21:45` y estado `CONFIRMED`.
3. Editar el evento y cambiar la hora a `23:00`.
4. Cambiar el estado a `DELAYED`.
5. Eliminar el evento.

**Datos de la interfaz:** los cambios se pierden al recargar la página; las operaciones de la interfaz todavía no realizan peticiones HTTP. Para probar el despliegue automático, cambiar el subtítulo de la aplicación, hacer commit y push y observar el nuevo build en Amplify.

## Referencia docente

https://github.com/albertohdezakkari/04-PILARES-SERVERLESS
