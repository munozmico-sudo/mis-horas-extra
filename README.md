# Mis Horas Extra

App para contar las horas extra del trabajo y lo que se gana con ellas.

- **Fichar**: apunta la entrada y la salida a mano o con "Fichar ahora".
- **Foto**: haz una foto al reloj y la app lee la hora de entrada o de salida.
- **Resumen**: horas trabajadas, horas extra y ganancias de cada mes.
- **PDF**: crea un PDF del mes con solo las horas extra o con el horario completo, para imprimir o compartir.
- **Ajustes**: horario de cada día, precio de la hora extra, precio en día libre, descanso no pagado y copia de seguridad.

Los datos se guardan en el propio teléfono. Usa la copia de seguridad de Ajustes para no perderlos.

## Lectura de la foto

- **Sin clave**: reconocimiento de texto gratuito (Tesseract). Va bien con relojes digitales y máquinas de fichar y necesita internet.
- **Con clave de la API de Claude** (Ajustes → Lectura de fotos): también lee relojes de agujas. Cada lectura gasta un poco de saldo de la API.

## Subirla a GitHub

1. Crea un repositorio nuevo, por ejemplo `horas-extra`, marcando **Add a README file**.
2. **Add file → Create new file**, nombre `.github/workflows/android.yml`, pega el contenido de ese archivo y **Commit changes**.
3. **Add file → Upload files**, arrastra `www`, `package.json`, `capacitor.config.json`, `README.md` y `.gitignore`, y **Commit changes**.

## Conseguir el APK para Android

1. En la pestaña **Actions**, el flujo **Compilar APK** arranca solo con cada subida y tarda unos 5 minutos.
2. Cuando salga en verde, ve a **Releases** y descarga `MisHorasExtra.apk` en el móvil.
3. Instálalo. Android pedirá permitir apps de origen desconocido.

Todas las versiones van firmadas con la misma llave (está dentro de `android.yml`), así que cada APK nuevo se instala encima sin perder los datos.

## Estructura

```
www/                 la app (index.html, manifest, icono, service worker)
capacitor.config.json  configuración para convertirla en app Android
package.json           dependencias de Capacitor
.github/workflows/     compilación del APK
```
