# Windows 11 Lite UDIT

Este repositorio documenta la creación de una imagen personalizada de Windows 11 22H2 con instalación desatendida, optimización offline y personalización visual. El objetivo es entregar una ISO reproducible y auditable, preparada para equipos con recursos limitados y una instalación sin interacción.

ISO final (si aplica): https://drive.google.com/drive/folders/1OpO14jZ8rFhT8iPWSzGbO2ycO2h3H4r2?dmr=1&ec=wgc-drive-globalnav-goto

## Objetivos
- Instalar Windows 11 x64 sin interacción hasta el escritorio.
- Crear usuario local automático con autologon.
- Aplicar personalización visual UDIT Amber Retro.
- Instalar aplicaciones esenciales en post-instalación.
- Documentar todo el proceso con herramientas oficiales.

## Herramientas verificadas
Se utilizaron herramientas oficiales y verificadas de Microsoft para mantener compatibilidad y trazabilidad:
- DISM (Deployment Image Servicing and Management)
- PowerShell 5.1
- reg.exe para ajustes de políticas offline
- robocopy para copias consistentes de la ISO
- oscdimg (Windows ADK) para reconstrucción de la ISO

No se usaron herramientas de terceros para la modificación offline.

## Entregables
- README.md con el proceso y estructura del proyecto.
- Presentación: `Sistemas Operativos.pdf`.

## Flujo resumido del proceso
1. Extracción del ISO original a un directorio de trabajo.
2. Montaje de `install.wim` y modificaciones offline con DISM.
3. Eliminación de componentes y ajustes de privacidad.
4. Integración de `AutoUnattend.xml` y estructura `$OEM$`.
5. Scripts de instalación y personalización en `SetupComplete.cmd`.
6. Reconstrucción de la ISO booteable.

## Instalación desatendida
- `AutoUnattend.xml` configura idioma, particionado, OOBE y creación de usuario.
- Usuario automático: `TORETO` (Administrador).
- Contraseña por defecto: `1234`.
- Autologon habilitado para completar la primera sesión.

Se recomienda cambiar la contraseña tras el primer inicio.

## Post-instalación
- `SetupComplete.cmd` ejecuta los scripts de instalación y personalización.
- Logs esperados en `C:\Windows\Logs\Setup`.

## Aplicaciones instaladas
- 7-Zip (instalación silenciosa).
- RetroArch (emulador arcade).
- ROMs legales opcionales (si se incluyen en el build).

No se instala Brave ni se configura como navegador predeterminado.

## Personalización visual
- Wallpapers UDIT Amber con nombres de participantes.
- Tema retro con colores ámbar y ajustes de consola.
- Iconos retro personalizados.

## Estructura OEM
```
ISO_WORK
└─ sources
   └─ $OEM$
      ├─ $1\Installers\...
      └─ $$\Setup\Scripts\SetupComplete.cmd
```

`$1` se copia a `C:\` y `$$` a `C:\Windows` durante la instalación.

## Reconstrucción de la ISO
Ejemplo con Windows ADK:
```
oscdimg.exe -m -o -u2 -udfver102 -bootdata:2#p0,e,b"ISO_WORK\boot\etfsboot.com"#pEF,e,b"ISO_WORK\efi\microsoft\boot\efisys.bin" "ISO_WORK" "Win11_UDIT.iso"
```

## Pruebas recomendadas
- Probar en VM con UEFI antes de usar en hardware real.
- Confirmar autologon de TORETO y aplicación de tema.
- Validar instalación de 7-Zip y RetroArch.
- Revisar logs en `C:\Windows\Logs\Setup`.

## Créditos
Autores: Andrea, Gabriel, Alejandro
