---
title: Novedades o cambios en la aplicación móvil Warehouse Management
description: Este tema enumera las funciones nuevas y modificadas para cada versión publicada de la aplicación móvil Warehouse Management para Microsoft Dynamics 365 Supply Chain Management.
author: MarkusFogelberg
ms.date: 09/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: ac3ea6a088b2086054eb692cd0688b269dafca51
ms.sourcegitcommit: e7eeca05d738e9e46d6185d1ba349836ebafc1a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2021
ms.locfileid: "7485631"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a>Novedades o cambios en la aplicación móvil Warehouse Management

[!include [banner](../includes/banner.md)]

Este tema enumera las nuevas funciones, las revisiones, las mejoras y los problemas conocidos para cada versión publicada de la aplicación móvil Warehouse Management para Microsoft Dynamics 365 Supply Chain Management.

## <a name="version-20100"></a>Versión 2.0.10.0

Esta versión introduce las características nuevas, correcciones y mejoras siguientes:

- Animación agregada al deslizar por listas y páginas.
- El texto ahora se ajusta correctamente en la página de error de conexión.
- Los cuadros combinados sin valores predeterminados ahora se muestran correctamente.
- La información en el área del subtítulo ahora se muestra solo en la página de detalles completos.
- Los campos de entrada vacíos ya no se muestran en la tarjeta de detalles.
- Los valores de confirmación ya no están duplicados en la tarjeta de detalles.
- Se han solucionado varios problemas que provocaban que el sistema dejara de responder.

## <a name="version-2090"></a>Versión 2.0.9.0

Esta versión soluciona un problema en el que la aplicación podía dejar de responder si los usuarios subían una página desde la parte superior de una lista.

## <a name="version-2080"></a>Versión 2.0.8.0

Esta versión introduce las características nuevas, correcciones y mejoras siguientes:

- Soporte agregado para la [función de instrucciones de paso](mobile-app-titles-instructions.md) que se introdujo en Supply Chain Management versión 10.0.21.
- Se agregó una animación de sugerencias para mostrar a los usuarios que pueden cerrar superposiciones deslizando hacia abajo.
- Se agregó soporte para teclas de función en listas de acciones y menús. Los usuarios pueden mantener pulsada cualquier tecla de función durante tres segundos para obtener una lista de los comandos disponibles.
- Se solucionó un problema que causaba que se mostrara el siguiente mensaje de error en algunos dispositivos: "No se puede encontrar una vista adecuada para el tamaño especificado".
- Se solucionó un problema por el cual el modo de pantalla completa no siempre funcionaba cuando se usaba el teclado en pantalla.
- Se solucionó un problema por el cual el deslizamiento de página no funcionaba en dispositivos Windows.
- Se han solucionado varios problemas que provocaban que el sistema dejara de responder.

## <a name="version-2070"></a>Versión 2.0.7.0

### <a name="new-features-fixes-and-improvements-in-version-2070"></a>Nuevas funciones, correcciones y mejoras en la versión 2.0.7.0

- Se agregó una sección a la página **Acerca de** que verifica la última versión publicada de la aplicación.
- Se facilitó el desplazamiento y el deslizamiento entre páginas.
- Se modificó el icono del botón ascendente/descendente en la lista de trabajo.
- Se redujeron los márgenes de la tarjeta **Detalles** para permitir que quepa más información.
- Se aplicaron varias mejoras de rendimiento para reducir el problema de que la aplicación se ralentizara con el tiempo.
- Si hay más controles de los que caben en la pantalla, lo que genera una paginación, el control giratorio ya no se desplaza de la misma forma que la página.
- Se da prioridad a mostrar el último valor escaneado sobre mostrar el título de la tarea, por lo que si se superponen, el título de la tarea se truncará.
- Se han solucionado varios problemas que provocaban que el sistema dejara de responder.
- El texto en varios lugares ya no se corta en algunos idiomas.
- La aplicación ahora se ejecuta en modo de pantalla completa de forma predeterminada.
- Se solucionó un problema que ocasionalmente causaba que los escaneos se ignoraran en la página principal con ciertos dispositivos.

### <a name="known-issues-in-version-2070"></a>Problemas conocidos en la versión 2.0.7.0

- En algunos dispositivos, recibirá el siguiente mensaje de error cuando inicie la aplicación o comience una tarea: "No se puede encontrar una vista adecuada para el tamaño especificado". Si ve este mensaje de error en cualquiera de sus dispositivos, debe degradar la aplicación móvil Warehouse Management a la versión 2.0.6.0 en ese dispositivo y esperar para actualizar hasta que se publique la próxima versión de la aplicación.

## <a name="version-2060"></a>Versión 2.0.6.0

### <a name="new-features-fixes-and-improvements-in-version-2060"></a>Nuevas funciones, correcciones y mejoras en la versión 2.0.6.0

Esta versión introduce las características nuevas, correcciones y mejoras siguientes:

- El modo de demostración ahora muestra todas las etiquetas en el idioma del dispositivo.
- Es menos probable que reciba el siguiente mensaje de error: "No se puede encontrar una vista adecuada para el tamaño especificado".
- Se ha aumentado la altura mínima para las tarjetas de trabajo (para los casos en los que se configuran tres o menos campos para aparecer en la lista de trabajo).
- Se han mejorado los márgenes (se desvanecen) en la parte inferior de las tarjetas de detalles.
- Los símbolos no válidos en los archivos XML que se intercambian con el servidor ahora se manejan correctamente. (Por ejemplo, los caracteres no imprimibles ahora se manejan con elegancia y ya no hacen que la aplicación deje de responder).
- Los errores HTTP (como el "error 503") cuando se envía una solicitud del servidor ahora se manejan correctamente.
- Mientras se muestra un error, la lista de opciones ya no se muestra automáticamente para los controles del cuadro combinado.
- La aplicación ya no deja de responder debido a la orientación de la pantalla que se selecciona en la configuración del usuario.
- Las imágenes de productos ahora se muestran en entornos de autoservicio. (Este cambio se aplica solo a las versiones de baja resolución. El servicio de administración de archivos no admite imágenes de tamaño completo en entornos de autoservicio).
- Se solucionó un problema que involucraba selecciones cortas de cantidad cero.
- La aplicación ya no deja de responder cuando una tarjeta de detalles muestra varios campos idénticos.

### <a name="known-issues-in-version-2060"></a>Problemas conocidos en la versión 2.0.6.0

Existen los siguientes problemas conocidos en esta versión:

- La aplicación (especialmente la lista de trabajo) se vuelve más lenta con el tiempo.
- **Versión de Windows:** cuando se utiliza una pistola USB para escanear en Windows, los resultados inconsistentes hacen que los símbolos escaneados se confundan.

## <a name="version-2050"></a>Versión 2.0.5.0

Esta versión introduce las características nuevas, correcciones y mejoras siguientes:

- El secreto del cliente ya no está oculto en la configuración de la conexión.
- Ahora puede mantener presionado cualquier texto para verlo por completo.
- Se ha mejorado el mensaje de error cuando faltan los permisos de almacenamiento.
- Se han agregado nuevas secuencias de control para algunos flujos.
- El botón enviar ya no está disponible incorrectamente debido al tamaño de la ventana.
- Los controles deslizantes ahora pueden continuar en pantallas más pequeñas cuando se utilizan botones de mayor tamaño.
- La superposición de cuatro botones ya no se corta.
- El teclado ahora admite el botón Eliminar.
- Se solucionó un problema de brillo que podría ocurrir cuando se presiona el teclado.
- Se han solucionado varios problemas con los datos de demostración.
- Se solucionó un problema que afectaba a los campos numéricos en la página de detalles.
- El teclado de la pantalla ya no desaparece ocasionalmente en algunos dispositivos.
- Se han corregido varios errores de la interfaz de usuario (UI), como errores que afectaban el color de fondo y la posición.
- Se ha mejorado la interfaz de usuario en ruso.
- Se han solucionado varios problemas que provocaban que el sistema dejara de responder.
- Se solucionó un problema relacionado con la reapertura de la calculadora.
- **Versión Android:** Un problema que causó que Android 4.4 dejara de responder al inicio se ha corregido.
- **Versión Android:** La escala mínima se ha reducido al 50 por ciento.

## <a name="version-2040"></a>Versión 2.0.4.0

La versión 2.0.4.0 fue la primera versión disponible en general de la aplicación móvil Warehouse Management.

### <a name="new-features-fixes-and-improvements-in-version-2040"></a>Nuevas funciones, correcciones y mejoras en la versión 2.0.4.0

Esta versión presenta las siguientes funciones nuevas, correcciones y mejoras que no estaban disponibles en la versión preliminar:

- Si una tarjeta de detalles incluye dos etiquetas que tienen datos idénticos, una de las etiquetas está oculta.
- Los caracteres especiales ahora se muestran de forma predeterminada y la opción para ocultarlos se ha eliminado de la configuración del usuario.
- Los botones de envío deshabilitados ahora se muestran como no disponibles en la vista compacta sostenida por el brazo.
- Un cambio en la lógica de secuenciación de los controles garantiza un escalado más fluido entre los dispositivos. Por lo tanto, hay menos necesidad de ajustar la escala de fuentes o botones.
- El tema de color predeterminado se ha cambiado a *Oscuro*.
- El icono que falta para el botón de envío deshabilitado se ha agregado en la vista de cinta.
- Las excepciones de tiempo de espera ahora lo llevan a la página de conexión en lugar de mostrar un error en línea.
- Si no hay ninguna acción de envío disponible (como **OK**, **Sí**, **Aceptar**, **Hecho** o **Terminado**), el botón de enviar se desactivará.
- Se ha mejorado la estabilidad de la aplicación.
- Hay una solución para la vulnerabilidad de seguridad [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701).
- **Versión de Windows:** se ha solucionado un problema en Windows, donde los menús no respondían después de cambiar el tamaño de la ventana.

### <a name="known-issue-in-version-2040"></a>Problema conocido en la versión 2.0.4.0

Existe el siguiente problema conocido en esta versión:

- Esta versión tiene un problema con los dispositivos que usan Android 4.4. Es posible que experimente problemas al usar la aplicación en esta versión de Android.
