# RetroBatch

Beta

## Características

- **Lanzamiento de juegos retro**: Inicia tus juegos favoritos de forma rápida y sencilla.
- **Configuración simplificada**: Personaliza opciones de emulación a través de archivos de configuración en Batch.
- **Soporte para múltiples emuladores**: Configura y utiliza diferentes núcleos de RetroArch.

## Requisitos

- Windows OS
- RetroArch instalado
- Conocimientos básicos de uso de la línea de comandos

## Instalación

1. Descarga RetroArch desde [su página oficial](https://www.retroarch.com/).
2. Clona este repositorio o descarga el ZIP y extrae los archivos en una carpeta de tu elección.
3. Asegúrate de que la ruta a RetroArch esté correctamente configurada en el script `launch.bat`.

## Uso

1. Abre el archivo `launch.bat`.
2. Selecciona el núcleo de emulación y el juego que deseas iniciar.
3. Sigue las instrucciones en pantalla para disfrutar de tu juego retro.

### Ejemplo de uso

```batch
@echo off
echo Selecciona el núcleo de emulacion:
echo 1. NES
echo 2. SNES
echo 3. Mega Drive
set /p core="Selecciona una opción (1-3): "

if %core%==1 (
    set core_path="C:\path\to\retroarch.exe -L cores/nestopia_libretro.dll"
) else if %core%==2 (
    set core_path="C:\path\to\retroarch.exe -L cores/snes9x_libretro.dll"
) else if %core%==3 (
    set core_path="C:\path\to\retroarch.exe -L cores/segaboot_libretro.dll"
) else (
    echo Opción no válida.
    exit /b
)

set /p game_path="Ingresa la ruta del juego: "
%core_path% "%game_path%"
