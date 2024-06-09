# Syncplay All
![Syncplay-All](Syncplay-All_banner.png)
<br><br>
"Syncplay-All for Windows" es un proyecto para hacer accesible a una masa no capacitada en el ámbito informático el programa Syncplay junto a todas sus dependencias, como vc-redist, mpv, yt-dlp y ffmpeg.
Syncplay sirve para sincronizar multimedia como películas o canciones en una sala virtual. Más información, abajo.
<br><br>
**ATENCIÓN**: No soy el creador de los programas aquí presentados. Este repositorio es solo una compilación de los binarios finales de dichos programas; lo único que hago es agruparlos en un ejecutable ya preconfigurado por mí para aquellxs usuarixs que no sepan cómo instalar cada aplicativo. Se insta a descargarlos e instalarlos desde sus repositorios originales.

**Se recomienda leer todo antes de ejecutar el programa y/o de abrir un issue.**

## Instalar

Simplemente vaya a [releases](https://github.com/canqiro/Syncplay-All/releases) y descargue el ejecutable (.exe) según la versión de su sistema operativo (32 o 64 bits). Ejecute el archivo y se le pedirá derechos de administrador el cual tiene que aceptar. Automáticamente se extraerá en `C:\Syncplay\` y se abrirá una consola de comandos. Dejar que termine el proceso que tiene que hacer y seguir los pocos pasos respectivos en caso de existir. Esto último puede variar en existir o no dependiendo de la versión.

**¡Todo listo!**

Nota: También existirá en un futuro cercano una versión de pocos MB para mayor facilidad de descarga que descargará los ejecutables directamente desde este mismo repositorio.

## Cómo funciona

Se recomienda mucho ver los propios repositorios para más información de los mismos.

Microsoft Visual C++ Redistributable Version, Syncplay, mpv, yt-dlp y ffmepg están comprimidos a través de WinRar como archivo autoextraíble que se extrae directamente en el disco C creando una carpeta llamada “Syncplay” (`C:\Syncplay\`).

Dentro de ella se encuentran las carpetas correspondientes que son las de Syncplay, mpv y Multimedia. Esta última es necesaria para que Syncplay pueda saber en dónde buscar los archivos respectivos.

- **Syncplay** es el programa principal para sincronizar la multimedia.
- **Vc-redist** (Microsoft Visual C++ Redistributable Version) está por compatibilidad con Syncplay ya que en unos equipos parece no funcionar si no lo tienen instalado.
- **mpv** es el reproductor recomendado y mejor compatible con Syncplay.
- **yt-dlp** es un programa para descargar videos de distintas plataformas; mpv lo necesita para reproducir videos en línea con los que Syncplay también es compatible.
- **ffmepg** lo necesita yt-dlp para poder manejar los archivos que tiene que reproducir.

Una vez extraído se inicia el archivo “install.bat”. Este instala de manera silenciosa vc-redist y borra el/los instalador/es porque ya no es/son necesario/s (depende si se instala solo la versión de 32 bits o también la versión de 64 bits). Luego mueve los accesos directos de Syncplay.exe y de updater.bat al Inicio de Windows. A continuación ejecutará “updater.bat” que se encuentra dentro de la carpeta de mpv que busca y actualiza el reproductor mpv a su versión más reciente junto con ffmpeg y yt-dlp.

Se recomienda ejecutar “updater.bat” al menos una vez al mes para mantener la compatibilidad. Este ya se encuentra directamente en el menú de inicio como “Syncplay-Actualizar_mpv” así que solo tiene que hacer clic en el mismo y esperar a que actualice todo. Se debería cerrar la ventana de CMD automáticamente.

A partir de aquí ya no me hago responsable. Igualmente, en caso de abrirse Syncplay, puede reportar el error en este mismo proyecto y yo veré si es problema del ejecutable o del propio Syncplay; si es de Syncplay yo no puedo hacer nada y tendrá que referirse al propio repositorio de Syncplay.

## Opciones de configuración

En teoría, debería abrirse la ventana principal de Syncplay ya completamente configurada así que no es necesario realizar cambios. Las configuraciones seteadas pueden cambiarse a gusto del/la usuario/a. Se presentan ahora las configuraciones seteadas que vienen por defecto:

- Dirección del servidor: `syncplay.pl:8996`
- Nombre de usuario: `un.nombre`
- Ruta al reproductor: `C:\Syncplay\mpv\mpv.exe` (esto tiene que dejarse tal como está a menos que quiera cambiar de ruta a mpv o cambiar el reproductor; esto último no es recomendable).
- Es necesario especificar un nombre de sala para poder empezar a sincronizar.
- Se añadió a icedrive.io como dominio de confianza ya que esta nube ofrece la posibilidad de disponer de un enlace directo a algún video subido a sus servidores. El link se lo tiene que extraer del propio HTML.
- La información del nombre y tamaño del archivo se estableció como “no enviar”. Puede cambiarlo si gusta.
- Directorios para buscar medios: `C:\Syncplay\Multimedia\` (Solo cambiarlo si quiere poner alguna otra dirección o añadir otra. No puede estar vacío).

Revisar el [manual de usuario de Syncplay](https://syncplay.pl/guide/) para más información.

### También:

Dentro de la carpeta “mpv” se encuentra un archivo llamado “yt-dlp.conf”. Este será usado por `yt-dlp.exe` para que mpv pueda reproducir los videos en línea y en él se especifican las configuraciones que debe usar. Solo configuré la resolución máxima de los videos (si está disponible). Abrir con un editor de texto y reemplazar “720” por la resolución deseada. Visitar las [opciones de yt-dlp](https://github.com/yt-dlp/yt-dlp#usage-and-options) para más información.

Dentro de la carpeta “mpv” existe una carpeta llamada “mpv”. En ella hay un archivo “mpv.conf”; se establecieron los diferentes parámetros: `profile=fast; hwdec=auto-safe`. Pueden borrarse o cambiarse. Visitar las [configuraciones de mpv](https://mpv.io/manual/master/) para más información.

Estas 2 configuraciones por defectos están destinadas a equipos de gama baja o de una antigüedad considerable. Pueden modificarse o eliminarse para dejar las configuraciones por defecto.

## Consideraciones

Este repositorio es solo una muestra de los archivos que contiene cada ejecutable. No está hecho para compilarse ni mucho menos por ende las carpetas, subcarpetas y archivos son directamente extraídos de la versión final para usuarixs. Por ende, repito, no están hechos para compilarse ni hay código fuente. Si se quiere ir al código fuente debe dirigirse a los repositorios originales cuyos links se especifican más arriba.

En cuanto a este repositorio, las carpetas de mpv y el archivo install tienen en “main” puestos en los mismos nombres la versión para las que están hechas. Y dentro de la carpeta “mpv” los archivos “ffmpeg.exe”, “ffprobe.exe” y “mpv.exe” se encuentran comprimidos en 4 partes debido a que GitHub no me deja subir archivos más grandes que 25 MB.

Fuera de eso, no hay diferencias con respecto a las versiones ejecutables que pueden encontrarse en releases tanto de 32 como la de 64 bits. Syncplay solo tiene una versión por lo que se deduce que es universal; es la misma tanto para 32 bits como para 64 bits.

## Descargo de responsabilidad

Lo único que yo he hecho es agarrar los instaladores/ejecutables finales de los programas Microsoft Visual C++ Redistributable Version, Syncplay, mpv, yt-dlp y ffmepg y unirlos todos en un solo instalador. Yo solo me hago cargo de lo que sucede desde que inicia el ejecutable hasta que abre Syncplay lo que suceda después o antes de eso no es contemplado por el propio ejecutable.

En caso de tener problemas en ese período contactarme. Fuera de eso, contactar con los propios desarrolladores de los respectivos programas cuyos enlaces están más arriba.

Con todo puede extraer los ejecutables con WinRar, 7zip o con algún otro archivador de ficheros y revisar usted mismo que no contiene ningún archivo que no tengan los programas originales salvo los ya mencionados más arriba y que no contiene ningún tipo de malware.

Muchos, muchos de verdad, muchos agradecimientos a los mantenedores de Microsoft Visual C++ Redistributable Version, Syncplay, mpv, yt-dlp y ffmepg por seguir con estos proyectos realmente extraordinarios. Pueden apoyar los proyectos ya sea mejorándolos o de forma monetaria. Links en los respectivos repositorios.

Este proyecto es sin ánimos de lucro.
