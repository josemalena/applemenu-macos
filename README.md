# Applets macOS Style para Cinnamon

Este repositorio incluye dos applets para Cinnamon:

- `applemenu@macos`: menú estilo Apple con accesos a sistema, cierre de sesión, reinicio, apagado y ventana de `Force Quit`.
- `appmenu@macos`: muestra el nombre de la aplicación activa y ofrece opciones como `Quit` y `About`.

## Compatibilidad

- `applemenu@macos`: Cinnamon `6.0`, `6.2`, `6.4`, `6.6`
- `appmenu@macos`: Cinnamon `5.8`, `6.0`, `6.2`, `6.4`, `6.6`

## Dependencias

Antes de instalarlos, asegúrate de tener:

- `python3`
- `python3-gi`
- `wmctrl`
- Cinnamon funcionando sobre Linux Mint o una instalación compatible

En Debian, Ubuntu o Linux Mint normalmente basta con:

```bash
sudo apt install python3 python3-gi wmctrl
```

## Instalación

1. Crea la carpeta de applets locales si no existe:

```bash
mkdir -p ~/.local/share/cinnamon/applets
```

2. Copia las carpetas de los applets a la ruta de Cinnamon:

```bash
cp -r applemenu@macos ~/.local/share/cinnamon/applets/
cp -r appmenu@macos ~/.local/share/cinnamon/applets/
```

3. Reinicia Cinnamon.

En X11 puedes usar:

```bash
cinnamon --replace &
```

Si prefieres, también puedes cerrar sesión y volver a entrar.

## Activación

1. Abre `Configuración del sistema`.
2. Entra en `Applets`.
3. Busca:
   - `Apple Menu`
   - `Application Menu (macOS-style)`
4. Añádelos al panel.
5. Reordénalos según el diseño que quieras.

## Configuración

### `applemenu@macos`

Permite definir:

- `icon-path`: ruta a un icono SVG o PNG para el botón del menú

### `appmenu@macos`

Permite definir:

- `fallback-label`: texto mostrado cuando no hay una ventana activa
- `label-padding-left`: espacio izquierdo del texto en píxeles

## Notas

- `applemenu@macos` ejecuta un script Python (`applemenu.py`) para mostrar los diálogos de apagado, reinicio, cierre de sesión y `Force Quit`.
- La función `Force Quit` depende de `wmctrl` y está pensada para sesiones X11.
- Algunas acciones como `About This Computer` y `App Store...` usan herramientas comunes de Linux Mint como `mintreport` y `mintinstall`. Si no existen en tu sistema, esas opciones no funcionarán.
