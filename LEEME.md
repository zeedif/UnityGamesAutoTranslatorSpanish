# Traducción al Español para Hollowbody

Sigue los pasos a continuación para instalar la traducción usando BepInEx y el plugin AutoTranslator.

## Requisitos Previos

### Instalación del gestor de mods BepInEx

1. Dirígete a la página de [BepInEx/releases](https://github.com/BepInEx/BepInEx/releases) para descargar la última versión del gestor de mods. Se recomienda la **versión 5.4.23.3**, que es la que se usó para esta traducción.

2. Descarga el archivo zip adecuado para tu sistema operativo:
   - **BepInEx_win_x64_{version}.zip** para sistemas operativos Windows de 64 bits (el más común).
   - **BepInEx_win_x86_{version}.zip** para sistemas operativos Windows de 32 bits.

   > **Nota:** Para verificar si tu sistema operativo es de 32 o 64 bits, sigue estos pasos:
   > - Abre el menú de **Inicio**.
   > - Escribe "Acerca de tu PC" y selecciónalo.
   > - En la sección **Especificaciones del dispositivo** podrás ver si tu sistema es de 32 o 64 bits en **Tipo de sistema**.

3. Extrae el contenido del archivo .zip descargado en el directorio raíz del juego. La ruta predeterminada para Steam es:
`C:\Program Files (x86)\Steam\steamapps\common\Hollowbody`
Para encontrar esta carpeta:
   - Abre Steam y busca el juego **Hollowbody**.
   - Haz clic derecho sobre el juego, selecciona **Administrar** y luego **Ver archivos locales**.
   - Extrae el contenido del archivo **.zip** en esta carpeta.
   ![](../Shared/hollowbody-1.gif)

4. Ejecuta el juego una vez. BepInEx creará nuevas carpetas en el directorio del juego, incluyendo una carpeta llamada `BepInEx` que contendrá las subcarpetas `config` y `plugins`.

### Instalación del plugin XUnity.AutoTranslator

1. Dirígete a la página de [AutoTranslator/releases](https://github.com/bbepis/XUnity.AutoTranslator/releases) para descargar la última versión del plugin. Se recomienda la **versión 5.4.5**, que es la que se usó para esta traducción.

2. Descarga el archivo que corresponda a tu instalación:
   - **XUnity.AutoTranslator-BepInEx-{version}.zip** para juegos basados en Mono o .NET como *Hollowbody*.
   - *(No uses la versión XUnity.AutoTranslator-BepInEx-**IL2CPP**-{version}.zip, ya que el juego no usa esa tecnología. Los juegos IL2CPP suelen tener un archivo llamado GameAssembly.dll en su carpeta de datos, lo cual no es el caso aquí).*

3. Extrae el contenido del archivo descargado en el mismo directorio raíz del juego, donde previamente instalaste BepInEx.
   - Abre Steam, busca **Hollowbody**.
   - Haz clic derecho sobre el juego, selecciona **Administrar** y luego **Ver archivos locales**.
   - Extrae el contenido del archivo **.zip** en esa carpeta.

   > La estructura de archivos debe quedar de la siguiente manera:
   > ```
   > {DirectorioDelJuego}/BepInEx/core/XUnity.Common.dll
   > {DirectorioDelJuego}/BepInEx/plugins/XUnity.ResourceRedirector/XUnity.ResourceRedirector.dll
   > {DirectorioDelJuego}/BepInEx/plugins/XUnity.ResourceRedirector/XUnity.ResourceRedirector.BepInEx.dll
   > {DirectorioDelJuego}/BepInEx/plugins/XUnity.AutoTranslator/XUnity.AutoTranslator.Plugin.Core.dll
   > ...
   > ```
   ![](../Shared/hollowbody-2.gif)

4. Ejecuta el juego nuevamente. Esto generará el archivo de configuración del plugin en `BepInEx/config/AutoTranslatorConfig.ini`.

## Instalación de la traducción

### Método rápido

1. Descarga el archivo ZIP de la traducción desde la [página de releases](https://github.com/zeedif/UnityGamesAutoTranslatorSpanish/releases) del proyecto.
2. Extrae el contenido del archivo `.zip` directamente en el directorio raíz de tu juego.
3. Si se te solicita, elige la opción para **combinar las carpetas y sobrescribir** cualquier archivo existente.
4. ¡Listo! La traducción debería estar funcionando automáticamente.

### Método personalizado

Si prefieres un mayor control sobre la traducción, puedes modificar manualmente el archivo `AutoTranslatorConfig.ini`:

1. Localiza y abre el archivo `BepInEx/config/AutoTranslatorConfig.ini` en el directorio del juego.

2. Modifica las siguientes líneas para desactivar la traducción automática y configurar el idioma de la traducción al español:

   Antes:
   ```ini
   Endpoint=GoogleTranslateV2

   [General]
   Language=en
   FromLanguage=ja
   ```

   - Endpoint: Deja esta línea en blanco para desactivar la traducción automática de nuevos textos.
   - Language: Configura el idioma de salida como español (`es`).
   - FromLanguage: Permite que el plugin detecte automáticamente (`auto`) el idioma original.

   Después:
   ```ini
   Endpoint=

   [General]
   Language=es
   FromLanguage=auto
   ```

3. Descarga el ZIP de la traducción, y copia únicamente la carpeta `es` que se encuentra dentro de `BepInEx/Translation` a la carpeta `BepInEx/Translation` de tu juego.

4. ¡Listo! La traducción debería estar funcionando automáticamente.

### Consideraciones adicionales
- **Personaliza la traducción:** Si deseas habilitar la traducción automática para textos no traducidos, investiga las opciones disponibles en la documentación del plugin. Si notas que ciertas partes del juego no se traducen correctamente, puedes editar manualmente los archivos de traducción generados en la carpeta `BepInEx/Translation`. 

- **Colabora con la traducción:** Puedes reportar errores encontrados en la traducción (crear un Issue) o sugerir cambios en la traducción y añadir líneas encontradas sin traducir (crear una Pull Request) en el repositorio del proyecto.