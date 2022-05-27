---
title: Novedades o cambios en la aplicación móvil Warehouse Management
description: Este tema enumera las funciones nuevas y modificadas para cada versión publicada de la aplicación móvil Warehouse Management para Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 04/25/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-06-07
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: c79b18d24c8b9cb90a570496882fdfe91dc6ba51
ms.sourcegitcommit: a4dc7d170f1504631127c3e92af0c6b03468d375
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/02/2022
ms.locfileid: "8661836"
---
# <a name="whats-new-or-changed-in-the-warehouse-management-mobile-app"></a>Novedades o cambios en la aplicación móvil Warehouse Management

[!include [banner](../includes/banner.md)]

Este tema enumera las nuevas funciones, las revisiones, las mejoras y los problemas conocidos para cada versión publicada de la aplicación móvil Warehouse Management para Microsoft Dynamics 365 Supply Chain Management.

## <a name="version-20220"></a>Versión 2.0.22.0

Esta versión introduce las características nuevas, correcciones y mejoras siguientes:

- Se corrigieron varios problemas de bloqueo.
- Se solucionó un problema por el cual algunos caracteres no se reconocían al escanear o escribir en la página predeterminada.
- Se solucionó un problema por el que presionar la tecla retroceso en la página predeterminada se eliminaban dos caracteres a la vez.
- Se solucionó un problema por el cual el campo **Ordenar por** en la lista **Lista de trabajo** mostraba un valor incorrecto que no correspondería con el orden de clasificación real de las tarjetas.
- Se solucionó un problema por el que se mostraba un diseño incorrecto después de cambiar el tamaño de la ventana de la aplicación mientras se ejecutaba en Microsoft Windows.
- Se solucionó un problema por el que desplazarse en una lista emergente podía hacer que algunos elementos de la lista permanecieran ocultos o se distorsionaran.
- Se rediseñó la página de inicio de sesión para permitir que muestre los campos de nombre de usuario y contraseña en la misma página cuando se ejecuta en pantallas más grandes.
- Se mejoró la forma en que los controles reaccionan al toque rápido.
- Se agregó una vista de registro de errores en la aplicación.
- Se agregaron varias mejoras de accesibilidad (narración mejorada, se corrigieron marcadores de posición austentes en Android, se habilitó entrada de teclado para controles deslizantes y más).

## <a name="version-20200"></a>Versión 2.0.20.0

Esta versión introduce las características nuevas, correcciones y mejoras siguientes:

- Se corrigieron varios problemas de bloqueo.
- Se solucionó un problema por el cual se mostraban valores incorrectos en las tarjetas de la página **Lista de trabajo**.
- Mejoró la experiencia de desplazamiento y se eliminó la inestabilidad del desplazamiento en las páginas **Lista de trabajo** y **Consulta de artículo** en Android.
- Se agregó un botón de salida a la página de inicio de sesión, que cierra la aplicación.

## <a name="version-20190"></a>Versión 2.0.19.0

Esta versión introduce las características nuevas, correcciones y mejoras siguientes:

- Se mejoró el flujo de consulta de datos genéricos.
- Se mejoró el problema de vibración en las páginas **Lista de trabajo** y **Consulta de artículo**.
- Reducción del consumo de batería.
- Se eliminó el límite en la cantidad de campos para tarjetas de trabajo.
- Se ajustó la altura de las tarjetas de trabajo para que todas tengan el mismo tamaño, independientemente del número de campos en cada una.
- Se solucionó un problema por el cual los caracteres de espacio en los códigos de barras se recortaban.
- Se agregó la configuración **Estilo de botón**, que le permite cambiar entre la vista deslizante y la vista de botones en todos los tipos de dispositivos.
- Se han solucionado varios problemas que podían provocar que la aplicación dejase de funcionar.
- Establecer foco automáticamente en el primer cuadro de texto en páginas personalizadas.
- Mejoras de accesibilidad relacionadas con la luminosidad, el contraste, la narración y los textos de marcador de posición que faltan.

## <a name="version-20170"></a>Versión 2.0.17.0

Esta versión introduce las características nuevas, correcciones y mejoras siguientes:

- Se solucionó un problema por el cual los códigos de barras se escaneaban incorrectamente.
- Se solucionó el problema de escaneo GS1 para el escáner de la cámara.
- Se solucionó el problema de escaneo GS1 para el escáner de código de barras en los dispositivos Zebra.
- Se mejoró el flujo de consulta de desvíos, por lo que seleccionar una tarjeta en un desvío ahora vuelve al flujo principal.
- Se agregó soporte para un flujo de consulta de datos genéricos.
- Se agregó un mensaje para informar a los usuarios sobre los cambios en el estado de conectividad de la red.
- Permisos de almacenamiento alineados con la política de privacidad de almacenamiento en Android 10.
- Para los flujos que lo necesitan, el indicador de cantidad ahora incluye una posición que permite a los usuarios enviar un valor numérico vacío.
- Se corrigieron problemas con la orientación del número giratorio.
- Se solucionó un problema por el cual la rueda giratoria de cantidad saltaba al valor incorrecto.
- Se solucionó un problema por el cual la entrada a la página principal se perdía cuando se completaba desde la página de detalles.
- Se solucionó un problema por el cual el texto del marcador de posición se trataría como el valor seleccionado inicialmente en las listas de selección.
- El botón "Enviar" en los pasos de confirmación ahora se habilita automáticamente si hay valores preseleccionados.
- Se corrigió la tarjeta de detalles para mostrar tantas líneas como sea posible para los campos de texto que tienen varias líneas.
- Se corrigió la altura de los botones "Enviar" y "Más acciones", por lo que ahora ocupan menos espacio en la pantalla.
- Se agregaron títulos de lista de selección faltantes.
- Se solucionó un problema por el cual el botón Atrás no funcionaba.
- Se agregaron varias correcciones y mejoras de navegación del teclado, incluso en las siguientes páginas:
  - Inicio de sesión de usuario
  - Seleccionar conexión
  - Editar conexión
- Se corrigió el desplazamiento al usar la navegación del teclado.
- Accesibilidad mejorada, incluidas las siguientes mejoras:
  - Visibilidad y contraste de colores fijos.
  - Se evitó la pérdida del enfoque del teclado cuando se cierran las páginas emergentes.
  - Se agregaron mensajes de error a la narración.
  - Aumentó el tamaño de los valores de marcador de posición en el banner de paso.
- Se corrigió el ejemplo de la página heredada personalizada en modo de demostración.

## <a name="version-20150"></a>Versión 2.0.15.0

Esta versión introduce las características nuevas, correcciones y mejoras siguientes:

- Rendimiento mejorado al solucionar un problema de fuga de memoria.
- Se solucionó un problema por el cual algunos valores de campo no se actualizaban correctamente cuando se seleccionaban en la página de detalles.

## <a name="version-20140"></a>Versión 2.0.14.0

Esta versión introduce las características nuevas, correcciones y mejoras siguientes:

- Se solucionó un problema que deshabilitaba el botón Enviar predeterminado.

## <a name="version-20130"></a>Versión 2.0.13.0

Esta versión introduce las características nuevas, correcciones y mejoras siguientes:

- Desplazamiento mejorado entre páginas con animación más suave.
- Se corrigieron las respuestas poco intuitivas a los movimientos de deslizamiento y las congelaciones ocasionales de la pantalla.
- Combinaciones mejoradas de color de fondo y texto en modo oscuro para una mejor legibilidad.
- Se solucionó un problema por el cual parte del texto podía volverse muy pequeño al cambiar el tamaño de la ventana de la aplicación.
- Se solucionó un problema que podía hacer que la aplicación fallara a veces al escanear códigos de barras.
- Se agregó la posibilidad de reemplazar un control deslizante con un botón.
- Se solucionó un problema que podía hacer que la aplicación mostrara el mensaje de error "AADSTS7000215: se proporcionó un secreto de cliente no válido".
- Se corrigió la animación de sugerencias que mostraba cómo cerrar una página con un gesto de deslizar hacia abajo.
- Se agregó la posibilidad de cerrar una página con un gesto de deslizar hacia abajo.
- Se solucionó un problema por el cual los títulos de la lista desplegable no se mostraban en la página **Configuración de usuario**.
- Se solucionó un problema de localización por el que la aplicación no reconocía una coma (,) como separador decimal.
- Accesibilidad mejorada.
- Se corrigió la navegación en la página **Nueva conexión** para proporcionar una mejor accesibilidad.
- Se solucionó un problema por el cual el teclado virtual (en pantalla) no aparecía al seleccionar un campo de entrada.
- Se solucionó un problema que podía bloquear la aplicación si los usuarios cambiaban rápidamente el tamaño de su ventana.
- Se solucionó un problema por el cual una pulsación rápida de teclas a veces se interpretaba como una pulsación prolongada.
- Se solucionó un problema por el cual el diseño de la aplicación podía corromperse debido a las personalizaciones de campo realizadas en Supply Chain Management.
- Se solucionó un problema por el cual las ubicaciones de los elementos no se mostraban correctamente.
- Se solucionó un problema relacionado con la selección corta para el flujo de trabajo de la variante del producto.
- Se eliminó la validación innecesaria de campos que contienen valores predeterminados preestablecidos.
- Rendimiento mejorado.
- Se agregó una nueva configuración que permite a los usuarios elegir cómo se filtran y ordenan los campos en la página de la tarjeta.

## <a name="version-20110"></a>Versión 2.0.11.0

Esta versión introduce las características nuevas, correcciones y mejoras siguientes:

- Soporte agregado para campos promocionados.
- Se agregó soporte para la navegación del teclado por hardware.
- Accesibilidad mejorada.
- Tarjetas de detalles mejoradas.
- Desvíos mejorados para pasos de elementos de menú.
- Mejoras menores en la interfaz de usuario.
- Se solucionó un problema que podía hacer que la aplicación fallara al escanear códigos de barras.
- Se han solucionado varios problemas que podían provocar que el sistema dejara de responder.

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
