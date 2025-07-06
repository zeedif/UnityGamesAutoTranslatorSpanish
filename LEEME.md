Sigue los pasos a continuación para instalar la traducción usando BepInEx y el plugin AutoTranslator.

## Requisitos Previos

### Instalación del gestor BepInEx

1. Dirígete la página de [BepInEx/releases](https://github.com/BepInEx/BepInEx/releases) para descargar la última versión del gestor de mods y plugins BepInEx.

2. Descarga el archivo adecuado para tu sistema operativo:
   - **BepInEx_win_x64_{version}.zip** para sistemas operativos de 64 bits.
   - **BepInEx_win_x86_{version}.zip** para sistemas operativos de 32 bits.

    > **Nota:** Para verificar si tu sistema operativo es de 32 o 64 bits, sigue estos pasos:
    > - Abre el menú de **Inicio**.
    > - Escribe "Acerca de tu PC" y selecciónalo.
    > - En la sección **Especificaciones del dispositivo** podrás ver si tu sistema es de 32 o 64 bits en **Tipo de sistema**.

3. Extrae el contenido del archivo descargado en el directorio raíz del juego. La ruta predeterminada para Steam es:
`C:\Program Files (x86)\Steam\steamapps\common\Spooky's Jump Scare Mansion HD Renovation`
Para encontrar esta carpeta:
   - Abre Steam y busca el juego **Spooky's Jump Scare Mansion HD Renovation**.
   - Haz clic derecho sobre el juego, selecciona **Administrar** y luego **Ver archivos locales**.
   - Extrae el contenido del archivo **.zip** en esta carpeta.

5. Ejecuta el juego por primera vez para generar los archivos de configuración en la carpeta `BepInEx/config`.

### Instalación del plugin XUnity.AutoTranslator

1. Dirígete la página de [AutoTranslator/releases](https://github.com/bbepis/XUnity.AutoTranslator/releases) para descargar la última versión del plugin AutoTranslator.

2. Descarga el archivo que corresponda a tu instalación:
   - **XUnity.AutoTranslator-BepInEx-{version}.zip** para juegos basados en Mono o .NET.
   - **XUnity.AutoTranslator-BepInEx-IL2CPP-{version}.zip** para juegos basados en IL2CPP.

3. Extrae el contenido del archivo descargado en el mismo directorio raíz del juego, donde previamente instalaste BepInEx.
   - Abre Steam, busca **Spooky's Jump Scare Mansion HD Renovation**.
   - Haz clic derecho sobre el juego, selecciona **Administrar** y luego **Ver archivos locales**.
   - Extrae el contenido del archivo **.zip** en esa carpeta.

    > La estructura de archivos debe quedar de la siguiente manera:
    > ```
    > {DirectorioDelJuego}/BepInEx/core/XUnity.Common.dll
    > {DirectorioDelJuego}/BepInEx/plugins/XUnity.ResourceRedirector/XUnity.ResourceRedirector.dll
    > {DirectorioDelJuego}/BepInEx/plugins/XUnity.AutoTranslator/XUnity.AutoTranslator.Plugin.Core.dll
    > {DirectorioDelJuego}/BepInEx/plugins/XUnity.AutoTranslator/XUnity.AutoTranslator.Plugin.BepInEx.dll
    > {DirectorioDelJuego}/BepInEx/plugins/XUnity.AutoTranslator/Translators/{Traductor}.dll
    > ...
    > ```

4. Ejecuta el juego nuevamente. Esto generará el archivo de configuración del plugin en `BepInEx/config/AutoTranslatorConfig.ini`.

## Instalación de la traducción

### Método rápido

1. Copia el contenido completo de este directorio (donde se encuentra este archivo **README.md**) al directorio raíz de tu juego.
2. Si se te solicita, sobrescribe cualquier archivo existente.
3. ¡Listo! La traducción debería estar funcionando automáticamente.

### Método personalizado

Si prefieres un mayor control sobre la traducción, puedes modificar manualmente el archivo `AutoTranslatorConfig.ini`:

1. Localiza y abre el archivo BepInEx/config/config.ini en el directorio del juego.

2. Modifica las siguientes líneas para desactivar la traducción automática y configurar el idioma de la traducción al español:

   Antes:
   ```ini
   Endpoint=GoogleTranslateV2

   [General]
   Language=en
   FromLanguage=ja
   ```

   - Endpoint: Deja esta línea en blanco para desactivar la traducción automática.
   - Language: Configura el idioma de salida como español (`es`).
   - FromLanguage: Permite que el plugin detecte automáticamente (`auto`) el idioma original.

   Después:
   ```ini
   Endpoint=

   [General]
   Language=es
   FromLanguage=auto
   ```

3. Copia únicamente la carpeta `BepInEx/Translation` en la carpeta `{DirectorioDelJuego}/BepInEx` y sobreescribe los archivos.

4. ¡Listo! La traducción debería estar funcionando automáticamente.

### Consideraciones adicionales
- **Personaliza la traducción:** Si deseas habilitar la traducción automática, investiga las opciones disponibles en la documentación del plugin. Esto permitirá que el plugin traduzca automáticamente textos que no estén incluidos en la traducción actual (por ejemplo, los añadidos en actualizaciones recientes). Si notas que ciertas partes del juego no se traducen correctamente, puedes editar manualmente los archivos de traducción generados en la carpeta `BepInEx/Translation`. 

- **Colabora con la traducción:** Puedes reportar errores encontrados en la traducción (crear un Issue) o sugerir cambios en la traducción y añadir líneas encontradas sin traducir (crear una Pull Request) en el repositorio del proyecto.