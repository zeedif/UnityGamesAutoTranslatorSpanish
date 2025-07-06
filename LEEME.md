Sigue los pasos a continuación para instalar la traducción usando MelonLoader y el plugin AutoTranslator.

## Requisitos Previos

### Instalación del gestor MelonLoader

1. Dirígete a la página de [MelonLoader/releases](https://github.com/LavaGang/MelonLoader/releases) para descargar la última versión del gestor de mods MelonLoader.

2. Descarga el archivo `MelonLoader.Installer.exe` o el archivo zip adecuado para tu sistema operativo:
   - **MelonLoader.x64.zip** para sistemas operativos de 64 bits.
   - **MelonLoader.x86.zip** para sistemas operativos de 32 bits.

   > **Nota:** Para verificar si tu sistema operativo es de 32 o 64 bits, sigue estos pasos:
   > - Abre el menú de **Inicio**.
   > - Escribe "Acerca de tu PC" y selecciónalo.
   > - En la sección **Especificaciones del dispositivo** podrás ver si tu sistema es de 32 o 64 bits en **Tipo de sistema**.

3. Extrae el contenido del archivo .zip descargado en el directorio raíz del juego. La ruta predeterminada para Steam es:
`C:\Program Files (x86)\Steam\steamapps\common\Muse Dash`
Para encontrar esta carpeta:
   - Abre Steam y busca el juego **Muse Dash**.
   - Haz clic derecho sobre el juego, selecciona **Administrar** y luego **Ver archivos locales**.
   - Extrae el contenido del archivo **.zip** en esta carpeta.

4. Ejecuta el juego una vez para que MelonLoader cree las carpetas `Mods` y `UserData` en el directorio del juego.

### Instalación del plugin XUnity.AutoTranslator

1. Dirígete la página de [AutoTranslator/releases](https://github.com/bbepis/XUnity.AutoTranslator/releases) para descargar la última versión del plugin AutoTranslator.

2. Descarga el archivo que corresponda a tu instalación:
   - **XUnity.AutoTranslator-MelonMod-{version}.zip** para juegos basados en Mono o .NET.
   - **XUnity.AutoTranslator-MelonMod-IL2CPP-{version}.zip** para juegos basados en IL2CPP.

3. Extrae el contenido del archivo descargado en el mismo directorio raíz del juego, donde previamente instalaste MelonLoader.
   - Abre Steam, busca **Muse Dash**.
   - Haz clic derecho sobre el juego, selecciona **Administrar** y luego **Ver archivos locales**.
   - Extrae el contenido del archivo **.zip** en esa carpeta.

   > La estructura de archivos debe quedar de la siguiente manera:
   > ```
   > {DirectorioDelJuego}/Mods/XUnity.AutoTranslator.Plugin.MelonMod.dll
   > ...
   > ```

4. Ejecuta el juego nuevamente. Esto generará el archivo de configuración del plugin en `AutoTranslator/Config.ini`.

## Instalación de la traducción

### Método rápido

1. Copia el contenido completo de este directorio (donde se encuentra este archivo **README.md**) al directorio raíz de tu juego.
2. Si se te solicita, sobrescribe cualquier archivo existente.
3. ¡Listo! La traducción debería estar funcionando automáticamente

### Método personalizado

Si prefieres un mayor control sobre la traducción, puedes modificar manualmente el archivo `Config.ini`:

1. Localiza y abre el archivo `AutoTranslator/Config.ini` en el directorio del juego.

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

3. Copia únicamente la carpeta `AutoTranslator/Translation` en la carpeta `{DirectorioDelJuego}/AutoTranslator` y sobreescribe los archivos.

4. ¡Listo! La traducción debería estar funcionando automáticamente.

### Consideraciones adicionales
- **Personaliza la traducción:** Si deseas habilitar la traducción automática, investiga las opciones disponibles en la documentación del plugin. Esto permitirá que el plugin traduzca automáticamente textos que no estén incluidos en la traducción actual (por ejemplo, los añadidos en actualizaciones recientes). Si notas que ciertas partes del juego no se traducen correctamente, puedes editar manualmente los archivos de traducción generados en la carpeta `Autotranslator/Translation`. 

- **Colabora con la traducción:** Puedes reportar errores encontrados en la traducción (crear un Issue) o sugerir cambios en la traducción y añadir líneas encontradas sin traducir (crear una Pull Request) en el repositorio del proyecto.