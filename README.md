# Windows 11 Lite UDIT

Repositorio con la documentación y los entregables de la distribución Windows 11 Lite UDIT. La imagen es desatendida, optimizada y con tema Amber Retro aplicado automáticamente.

ISO x64 (actualizada): https://drive.google.com/drive/folders/1OpO14jZ8rFhT8iPWSzGbO2ycO2h3H4r2?dmr=1&ec=wgc-drive-globalnav-goto
ISO ARM64 (si aplica): misma carpeta o salida local del build.

## Objetivos
- Instalación sin interacción hasta el escritorio.
- Usuario local automático con autologon.
- Tema Amber Retro (wallpaper, colores, iconos, consola).
- Post-instalación con apps básicas.

## Herramientas verificadas
- DISM
- PowerShell 5.1
- reg.exe
- robocopy
- oscdimg (Windows ADK)

## Entregables
- `README.md`
- `Sistemas Operativos.pdf`

## Estructura OEM
```
ISO_WORK
└─ sources
   └─ $OEM$
      ├─ $1\...
      └─ $$\Setup\Scripts\SetupComplete.cmd
```

## Instalación desatendida
- Usuario: `toreto`
- Contraseña: `1234`
- AutoLogon habilitado

## Post-instalación
- `SetupComplete.cmd` ejecuta scripts de instalación y tema.
- Logs en `C:\Windows\Logs\Setup`.

## Instrucciones x64
1. Montar la ISO x64 en una VM (UEFI).
2. La instalación corre sola hasta el escritorio.
3. Verificar tema Amber y apps instaladas.

## Instrucciones ARM64
1. Montar la ISO ARM64 en Parallels (UEFI).
2. La instalación corre sola hasta el escritorio.
3. Verificar tema Amber y apps instaladas.

## Verificación rápida
- Wallpaper UDIT visible en escritorio.
- Colores ámbar aplicados en ventanas.
- Iconos retro aplicados.
- Usuario `toreto` logueado automáticamente.

## Créditos
Autores: Andrea, Gabriel, Alejandro
