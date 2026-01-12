# Windows 11 Lite: Edición Optimizada y Desatendida (22H2) 🚀

Este repositorio contiene la documentación y el proceso detallado de la creación de una imagen personalizada de **Windows 11 (Versión 22H2)**. El objetivo principal es ofrecer un sistema operativo funcional en equipos con recursos limitados (CPU y RAM) y una instalación totalmente automatizada.

## 🎯 Objetivos de la Práctica

* **Optimización Extrema:** Reducir el consumo de recursos para máquinas de gama baja.
* **Instalación Desatendida:** Configuración "Zero-Touch" que permite pasar desde el arranque hasta el escritorio de Windows sin intervención del usuario.
* **Compatibilidad:** Bypass de requisitos oficiales de Windows 11 (TPM 2.0 y Secure Boot).
* **Actualizaciones:** Base 22H2 preparada para soportar actualizaciones hasta la 25H2.

---

## 🛠 Herramientas y Herencia
* **Software:** [NTLite](https://www.ntlite.com/)
* **Imagen Base:** Windows 11 22H2 ISO Oficial.
* **Metodología:** Basado en técnicas de eliminación selectiva de componentes para "Debloating" profundo.

---

## ⚙️ Proceso de Modificación (Paso a Paso)

### 1. Eliminación de Componentes
Se realizó una limpieza profunda para liberar espacio en disco y memoria RAM:
* **Apps:** Eliminación del Cliente de Microsoft, Lector PDF, Windows Push-to-install, Xbox y servicios relacionados.
* **Localización:** Se eliminaron todos los idiomas excepto **Español** (Argentina/España) y el pseudo-local de prueba.
* **Multimedia:** Eliminación del Narrador y componentes multimedia redundantes.
* **Seguridad:** Reducción del Centro de Seguridad (manteniendo lo esencial para la estabilidad).

### 2. Configuración y Características
Se desactivaron funciones pesadas que consumen ciclos de CPU en segundo plano:
* **Desactivados:** Windows Search, Work Folders Client e Imprimir en PDF de Microsoft.
* **Energía:** Eliminación de los menús de **Hibernación** y **Suspensión** para reducir el tamaño del archivo de sistema y optimizar el apagado.

### 3. Personalización de la Interfaz (UI)
* **Efectos visuales:** Desactivación de animaciones para una respuesta instantánea.
* **Barra de tareas:** Limpieza de iconos de Chat (Teams), Widgets y Centro de Notificaciones.
* **Escritorio:** Eliminación de iconos predeterminados (Papelera, Mi Equipo, Panel de Control) y fijación de aplicaciones de la tienda.
* **Estética:** Aplicación de **Tema Oscuro** por defecto y personalización de la paleta de colores azul.

### 4. Privacidad y Sistema
* **Telemetría:** Desactivación total de Cortana y del envío de informes de diagnóstico a Microsoft.
* **Instalación Automática:** Bloqueo de la instalación automática de aplicaciones patrocinadas (bloatware).
* **Bypass de Hardware:** Desactivación del requisito de **TPM** para permitir la instalación en cualquier procesador.
* **Optimización de Disco:** Desactivación de **SysMain** (Optimizado para SSD) y BitLocker.

---

## 🤖 Configuración Desatendida (Zero-Touch)

Para lograr que el sistema llegue al escritorio sin clics del usuario, se configuró el apartado **Desatendido** en NTLite con los siguientes parámetros:

| Sección | Configuración |
| :--- | :--- |
| **Idioma Local** | Español (Argentina) |
| **Idioma Interfaz** | Español (España) |
| **EULA** | Omitir página de licencia automáticamente |
| **Privacidad** | Omitir todas las páginas de configuración de privacidad (OOBE) |
| **Cuenta de Usuario** | Creación automática de cuenta local con privilegios de Administrador |
| **Telemetría** | Configurada como "Falso" (Desactivada) |

---

## 🚀 Resultado Final
El resultado es una imagen ISO altamente eficiente que:
1.  Arranca en equipos antiguos sin errores de compatibilidad.
2.  No solicita ninguna configuración durante la instalación.
3.  Inicia directamente en el escritorio con un consumo de RAM significativamente inferior a la versión comercial.

---

## ⚠️ Notas
> Una vez creada e instalada la imagen, los componentes eliminados **no pueden volver a agregarse**. Esta distribución está pensada para entornos de máximo rendimiento y minimalismo.
