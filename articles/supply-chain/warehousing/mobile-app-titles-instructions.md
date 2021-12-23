---
title: Personalizar los títulos y las instrucciones de los pasos para la aplicación móvil Warehouse Management
description: Este tema describe cómo crear y mostrar instrucciones personalizadas para cada paso de cada flujo de tareas que configure para la aplicación móvil Warehouse Management.
author: Mirzaab
ms.date: 08/11/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-11
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: ffd433427b2c5011740a7ee54c93713689945df3
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2021
ms.locfileid: "7902256"
---
# <a name="customize-step-titles-and-instructions-for-the-warehouse-management-mobile-app"></a>Personalizar los títulos y las instrucciones de los pasos para la aplicación móvil Warehouse Management

> [!IMPORTANT]
> Las características que se describen en este tema se aplican solo a la nueva aplicación móvil Warehouse Management. No afectan a la antigua aplicación de almacén, que ahora está obsoleta.

Este tema describe cómo crear y mostrar instrucciones personalizadas para cada paso de cada flujo de tareas que configure para la aplicación móvil Warehouse Management. Cuando los trabajadores del almacén reciben instrucciones bien escritas, pueden comenzar a utilizar nuevos flujos inmediatamente sin necesidad de formación previa. Esta función proporciona las siguientes ventajas:

- **Aumente la velocidad de los trabajadores permitiéndoles seguir instrucciones sencillas para cada paso de la tarea.** Cada paso de un flujo proporciona instrucciones que permiten a los trabajadores de primera línea comprender la tarea.
- **Proporcione instrucciones que coincidan con sus propios procesos.** Escriba sus propias instrucciones para que coincidan con sus procesos comerciales y de almacén. Por ejemplo, puede hacer que la terminología se ajuste a su espacio físico y abreviaturas locales.

## <a name="turn-on-the-warehouse-app-step-instructions-feature"></a>Activar la función Instrucciones de los pasos de la aplicación de almacén

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de la función:** *Instrucciones de los pasos de la aplicación de almacén*

## <a name="step-titles-and-step-instructions-in-the-app"></a>Títulos e instrucciones de pasos en la aplicación

Cada paso de un flujo de tareas en la aplicación móvil Warehouse Management se identifica mediante un Id. de paso. Además, cada paso tiene un título, un icono y una instrucción. (Para obtener más información, consulte [Asignar iconos y títulos de pasos la aplicación móvil Warehouse Management](step-icons-titles.md).)

### <a name="step-titles"></a>Títulos de pasos

Un *título del paso* es una breve descripción de lo que debe hacer un trabajador durante un paso. Aparece como texto grande en la parte superior de la pantalla, como se muestra en la siguiente ilustración.

![Ejemplo de un título de paso en la aplicación móvil Warehouse Management](media/wma-step-title.png "Ejemplo de un título de paso en la aplicación móvil Warehouse Management")

> [!TIP]
> Debido al gran tamaño del texto, debe intentar que los títulos de los pasos sean lo más cortos posible. De lo contrario, el texto podría cortarse. Sin embargo, para títulos largos, los trabajadores pueden mantener pulsado el título para abrir un cuadro de diálogo que muestra el texto completo.

### <a name="step-instructions"></a>Instrucciones detalladas

Una *instrucción paso a paso* es una descripción más larga que proporciona más información sobre lo que debe hacer un trabajador durante un paso. Aparece en un cuadro de diálogo emergente, como se muestra en la siguiente ilustración.

![Ejemplo de una instrucción de paso en la aplicación móvil Warehouse Management](media/wma-step-instructions.png "Ejemplo de una instrucción de paso en la aplicación móvil Warehouse Management")

La instrucción de paso se muestra automáticamente cuando se abre un paso. Los trabajadores pueden descartarla tocando en cualquier lugar fuera del cuadro de diálogo emergente. Además, el cuadro de diálogo incluye la casilla **No volver a mostrar** que los trabajadores pueden seleccionar para evitar que la instrucción aparezca la próxima vez que realicen la misma tarea.

## <a name="load-the-default-setup"></a>Cargar la configuración predeterminada

Cuando activa por primera vez la función *Instrucciones de los pasos de la aplicación de almacén*, su sistema no contendrá títulos o instrucciones de pasos personalizables. Por lo tanto, lo primero que debe hacer es cargar la configuración predeterminada. La configuración predeterminada proporciona textos para todos los Id. de pasos disponibles en todos los idiomas admitidos. Para cargar la configuración predeterminada, siga estos pasos.

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \>Pasos del dispositivo móvil**.
1. En el panel de acciones, seleccione **Crear configuración predeterminada**. La página se completa con los pasos estándar.

## <a name="customize-step-titles-and-instructions"></a>Personalizar los títulos y las instrucciones de los pasos

Para personalizar el título o las instrucciones de un paso en varios idiomas, siga estos pasos.

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \>Pasos del dispositivo móvil**.

    La página **Pasos del dispositivo móvil** enumera todos los pasos que están disponibles para su sistema. Cada Id. de paso se puede compartir entre cualquier número de elementos del menú del dispositivo móvil. Si se comparte un Id. de paso entre varios elementos del menú, se muestra el mismo título e instrucción para todos esos elementos del menú. Sin embargo, puede crear invalidaciones para personalizar el título y las instrucciones para elementos de menú específicos. (Para obtener más información, consulte la sección siguiente).

    La cuadrícula incluye las siguientes columnas:

    - **Nombre del elemento del menú** – Las filas en las que esta columna está en blanco utilizan el título e instrucciones de paso predeterminados que se aplican a todos los elementos del menú del dispositivo móvil para los que no se define ninguna invalidación. Las filas en las que esta columna se establece con el nombre de un elemento de menú tienen invalidaciones que se aplican solo al elemento de menú especificado.
    - **Id. de paso** – El Id. único del paso.
    - **Título de la entrada** – El título que se muestra cuando la aplicación solicita nueva información. Normalmente, los campos de la página están en blanco (es decir, no tienen valores preestablecidos).
    - **Título para confirmación** – El título que se muestra cuando la aplicación solicita la confirmación de un valor que ya está almacenado en el sistema. Normalmente, los campos de la página tienen valores predeterminados.

1. Busque la combinación de los valores de **Id. de paso** y **Nombre del elemento del menú** que desea editar y seleccione el valor en la columna **Id. de paso**. La página que se abre enumera todas las traducciones disponibles para el título y la instrucción del paso seleccionado.
1. Siga uno de estos pasos para personalizar el texto para cualquier idioma. Ambas opciones le permiten editar textos para idiomas existentes. Sin embargo, solo la primera opción le permite agregar textos para nuevos idiomas, mientras que solo la segunda opción le permite ver y editar textos para todas las invalidaciones existentes específicas del menú del idioma seleccionado.

    - En la barra de herramientas, seleccione **Agregar** para abrir un cuadro de diálogo donde puede agregar o editar textos para cualquier idioma admitido. Establezca el campo **Idioma de referencia** con el idioma para el que desea ver los valores. Los valores se muestran en la columna de la izquierda. Establezca el campo **Idioma de las traducciones** con el idioma que desea agregar o personalizar. En la columna de la derecha, edite los valores de los campos **Título de la entrada**, **Instrucción para la entrada**, **Título para confirmación** y **Instrucción para confirmación** que necesite. A continuación seleccione **Aceptar**.
    - En la cuadrícula, busque y seleccione la fila donde el campo **Idioma** está configurado en el idioma que desea editar. En la barra de herramientas, seleccione **Ver &lt;traducciones&gt; de idioma de este paso** para abrir un cuadro de diálogo donde puede editar textos para todas las invalidaciones disponibles para el idioma seleccionado. El cuadro de diálogo incluye una cuadrícula que tiene filas para ambos textos estándar (donde el campo **Nombre del elemento del menú** está en blanco) y para cada texto de invalidación disponible (donde el campo **Nombre del elemento del menú** se establece en el nombre del elemento de menú al que se aplica la anulación). Edite los valores de los campos **Título de la entrada**, **Instrucción para la entrada**, **Título para confirmación** y **Instrucción para confirmación** que necesite. A continuación seleccione **Aceptar**.

1. Continúe trabajando hasta que haya definido todos los títulos e instrucciones requeridos para cada idioma requerido.

## <a name="add-menu-specific-overrides"></a>Agregar invalidaciones específicas del menú

Como se mencionó en la sección anterior, puede crear cualquier número de invalidaciones específicas del menú para cada Id. de paso. Puede utilizar esta capacidad para editar y cambiar la instrucción para que se adapte mejor a su proceso comercial local para un elemento de menú específico. Por ejemplo, para la selección de ventas, si su empresa suele proporcionar identificaciones de trabajo a los trabajadores en un documento impreso, puede proporcionar una pista de que los trabajadores deben comenzar escaneando una identificación de trabajo.

Cada invalidación se aplica a un elemento de menú de dispositivo móvil específico y puede contener cualquier número de traducciones. Si no existe una invalidación para un elemento de menú, el elemento de menú utiliza los textos estándar. Si no se define una traducción de invalidación para un idioma, se utilizan los textos estándar, incluso para los elementos del menú donde se define una anulación para otros idiomas.

Para crear y configurar una nueva invalidación, siga estos pasos.

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \>Pasos del dispositivo móvil**.
1. En la cuadrícula, busque y seleccione la fila para la que desea crear una invalidación.
1. En el panel de acciones, seleccione **Agregar configuración de paso**.
1. En el cuadro de diálogo desplegable **Agregar configuración de paso**, establezca el campo **Opción del menú** con el nombre del elemento de menú del dispositivo móvil al que se aplica su invalidación. A continuación seleccione **Aceptar**.
1. La página que aparece muestra todos los textos que están disponibles para la nueva invalidación. Inicialmente, solo se crea un idioma. Todos los demás idiomas seguirán usando los textos estándar a menos que agregue esos idiomas aquí. Edite los textos y agregue nuevos idiomas según lo requiera, como se describe en la sección anterior.
