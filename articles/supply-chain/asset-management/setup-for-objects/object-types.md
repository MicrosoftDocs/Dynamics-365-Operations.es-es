---
title: Tipos de activos
description: En este tema se explica cómo crear tipos de activos en Administración de activos. También describe los elementos relacionados con los tipos de activos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectJobType, EntAssetObjectType, EntAssetObjectTypeDefaultSparePart, EntAssetObjectTypeDefaultSparePartApprove, EntAssetObjectTypeDefaultCreateCombinations, EntAssetObjectTypeDefault, EntAssetObjectTypeDefaultCopy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5a5db915c94cf9a454dc39e9174b3282a3f6bb75
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436760"
---
# <a name="asset-types"></a>Tipos de activos

[!include [banner](../../includes/banner.md)]



Este tema explica cómo crear tipos de activos. También describe los elementos relacionados con los tipos de activos. Los tipos de activos se usan como categorías generales para los activos. Algunos ejemplos son máquinas CNC, equipo de medición y motores de camión. Los tipos de activo se usan para gestionar los tipos de trabajo de mantenimiento (tareas de mantenimiento), los estados de ciclo de vida de activo, los contadores, los atributos de activo, las plantillas de evaluación de condición y los modelos de activo que se pueden seleccionar para un activo. Al crear un activo, debe especificar el tipo.

Para cada tipo de activo, se pueden crear variaciones de la configuración del tipo de activo. Por ejemplo, si tiene un tipo de activo **Camiones**, puede crear variaciones de ese tipo de activo para los distintos fabricantes del activo y modelos del activo. A cada configuración de tipo de activo se le pueden agregar las piezas de repuesto y los planes de mantenimiento necesarios.

Primero, se deben configurar los tipos de activo requeridos. A continuación, crea los modelos de activos que deben estar relacionados con los tipos de activos. Finalmente, en la página **Valores predeterminados de tipos de activo**, crea todas las variaciones de tipos de activos necesarias para su equipo.

## <a name="create-an-asset-type"></a>Crear un tipo de activo

1. Seleccione **Administración de activos** > **Configuración** > **Tipos de activos** > **Tipos de activos**.
2. Seleccione **Nuevo** para crear un tipo de activo.
3. En el campo **Tipo de activo**, introduzca un id. de tipo de activo.
4. Escriba un nombre en el campo **Nombre**.
5. En el campo **Modelo de ciclo de vida de activo**, seleccione un modelo de ciclo de vida de activo. Para obtener más información sobre los estados de ciclo de vida de activo y los modelos de ciclo de vida de activo, consulte [Estados de ciclo de vida de activo](object-stages.md).
6. Establezca la opción **Total** en **Sí** si se calculan los valores de KPI resumidos para los activos con este tipo de activo.
7. Seleccione **Guardar**.
8. En la ficha desplegable **Tipos de trabajos de mantenimiento**, seleccione los tipos de trabajo de mantenimiento que deben relacionarse con el tipo de activo.

    - Para seleccionar un tipo de trabajo de mantenimiento, selecciónelo en el campo **Tipos de trabajo de mantenimiento restantes** y seleccione el botón de flecha derecha ![botón de flecha derecha](media/29-setup-for-objects.png) para moverlo a la sección **Tipos de trabajo de mantenimiento seleccionados**.
    - Para seleccionar todos los tipos de trabajo de mantenimiento disponibles, seleccione el botón de ![flecha todo hacia delante](media/30-setup-for-objects.png). Todos los tipos de trabajo de mantenimiento se transfieren del campo **Tipos de trabajo de mantenimiento restantes** al campo **Tipos de trabajo de mantenimiento seleccionados**.
    - Para cancelar la selección de un tipo de trabajo de mantenimiento, selecciónelo en el campo **Tipos de trabajo de mantenimiento seleccionados** y seleccione el botón de flecha izquierda ![botón de flecha izquierda](media/31-setup-for-objects.png) para moverlo al campo **Tipos de trabajo de mantenimiento restantes**.

9. También puede seleccionar los contadores que deben estar relacionados con el tipo de activo. En la ficha desplegable **Contadores**, realice las selecciones necesarias mediante los métodos que se describen para los tipos de trabajo de mantenimiento en el paso 8. Para obtener más información sobre la configuración de los contadores, consulte [Contadores](counters.md).
10. También puede seleccionar los tipos de atributo que deben estar relacionados con el tipo de activo. En la ficha desplegable **Evaluaciones de condición**, realice las selecciones necesarias mediante los métodos que se describen para los tipos de trabajo de mantenimiento en el paso 8. A continuación, cree la secuencia preferida de tipos de atributo, seleccione un tipo de atributo en el campo **Tipos de atributo seleccionados** y use los botones de flecha arriba y abajo para moverlo. La secuencia de tipos de atributo se mostrará en los activos que usen este tipo de activo. Para obtener más información sobre los atributos de activo, consulte [Tipos de atributo de mantenimiento](../setup-for-functional-locations/specification-types.md).

    > [!NOTE]
    > Al agregar nuevos tipos de atributo en el FastTab **Tipos de atributo**, los activos existentes se actualizan automáticamente con esa información.

11. También puede seleccionar las plantillas de evaluación de condición que deben estar relacionadas con el tipo de activo. En la ficha desplegable **Evaluaciones de condición**, realice las selecciones necesarias mediante los métodos que se describen para los tipos de trabajo de mantenimiento en el paso 8. Para obtener más información acerca de las plantillas y los registros de evaluación de condición, consulte [Evaluación de condición](../setup-for-objects/condition-assessment.md).
12. El FastTab **Modelo de activo** muestra a todas las combinaciones de fabricantes y modelos de activos configuradas en el tipo de activo seleccionado. Para ver las combinaciones divididas por fabricante, seleccione **Modelo de activo** para abrir la página **Modelo de activo**.

    En la página **Modelo de activo**, puede agregar relaciones de modelo de activo y tipo de activo. Además, en la página **Tipos de activo**, puede agregar relaciones de modelo de activo y fabricante de activo directamente a un tipo de activo. Finalmente, en la página **Modelo de activo** (**Administración de activos** \> **Configuración** \> **Activos** \> **Modelo de activo**), puede crear nuevas relaciones entre tipo de activo, modelo de activo y fabricante de activo. Por lo tanto, hay tres maneras de configurar y editar las relaciones entre fabricante de activo, modelo de activo y tipo de activo. Todas las combinaciones disponibles se muestran desde perspectivas diferentes y puede seleccionar el punto de entrada preferido al trabajar con la configuración.

> [!NOTE]
> - Si selecciona contadores en un tipo de activo, las selecciones se actualizan automáticamente en la página **Contadores** (**Administración de activos** > **Configuración** > **Activos** > **Tipos de activos** > **Contadores**).
> - Los campos de la sección **Detalles** en la ficha desplegable **General** muestran el número de tipos de trabajo de mantenimiento, contadores, atributos, etc., configurados en el tipo de activo seleccionado.

Normalmente, las órdenes de trabajo que se crean manualmente se relacionan con el mantenimiento correctivo, mientras que las órdenes de trabajo que se crean automáticamente están relacionadas con el mantenimiento preventivo. Al crear manualmente órdenes de trabajo, solo pueden usarse los tipos de trabajo de mantenimiento que se seleccionan en la ficha desplegable **Tipos de trabajo de mantenimiento** de la página **Tipos del activo**. Sin embargo, las órdenes de trabajo creadas automáticamente pueden utilizar todos los tipos de trabajo de mantenimiento creados en la página **Tipos de trabajo de mantenimiento** (**Administración de activos** \> **Configuración** \> **Trabajos** \> **Tipos de trabajo de mantenimiento**).

## <a name="create-asset-type-setup-lines"></a>Crear líneas de configuración de tipo de activo

1. Seleccione **Administración de activos** \> **Configuración** \> **Activos** \> **Tipos de activos** \> **Configuración de tipo de activo**. Como alternativa, seleccione **Administración de activos** \> **Configuración** \> **Activos** \> **Tipos de activo** \> **Tipos del activo**, seleccione un tipo de activo y, a continuación seleccione **Configuración de tipo de activo**.
2. La primera vez que se utiliza la página **Configuración de tipo de activo**, puede encontrar útil el botón **Crear combinaciones**. Puede usar este botón para crear rápidamente todas las combinaciones de un modelo de activo en un tipo de activo. Seleccione **Crear combinaciones**, seleccione el tipo de activo para el que desea crear las combinaciones y, a continuación, seleccione **Aceptar**.

    > [!NOTE]
    > Si no va a usar todas las combinaciones de configuraciones de tipos de activo que se han creado automáticamente, puede eliminar una configuración seleccionándola y seleccionando después **Eliminar**.

3. Seleccione **Nuevo** para crear manualmente una configuración de tipo de activo.
4. En función de lo específica que deba ser la configuración del tipo de activo, realice selecciones en **Tipo de activo**, **Fabricante** y **Modelo**.
5. Si hay un contrato de garantía relacionado con el tipo de activo, selecciónelo en **Garantía del proveedor** y **Garantía del cliente**. 
6. En el FastTab **Recambios**, seleccione **Agregar** para agregar repuestos a la configuración del tipo de activo seleccionada.
7. Para aprobar un recambio, seleccione la línea de la pieza de repuesto y, a continuación seleccione **Aprobar**. Puede seleccionar varias líneas para su aprobación.
8. Para ver si un recambio se usa en otro lugar en Administración de activos (por ejemplo, en relación con activos y órdenes de trabajo), seleccione la línea de la pieza de repuesto y, a continuación, seleccione **Artículo donde utilizado** para abrir la página **Artículo donde utilizado**. Para ver todos piezas de repuesto activas de la lista, seleccione la casilla de verificación **Activas**. Para ver únicamente las piezas de repuesto aprobadas, seleccione la casilla de verificación **Aprobadas**.
9. En el FastTab **Planes de mantenimiento**, seleccione **Agregar** para agregar planes de mantenimiento a la configuración del tipo de activo seleccionada.
10. Para copiar una configuración de tipo de activo en otra configuración, puede usar la función Copiar. Seleccione la configuración de tipo de activo en la que desea copiar una configuración, seleccione **Copiar configuración** y seleccione el tipo de activo del que desea copiar la configuración. Los valores de las distintas opciones determinan cuánta información se incluye. Cuando haya terminado, seleccione **Aceptar** para copiar la configuración.

> [!NOTE]
> Si tiene muchas líneas de piezas de repuesto y muchas líneas de planes de mantenimiento que piensa a reutilizar, la función de copia le permite copiar de forma rápida y sencilla los datos de configuración de varias combinaciones de configuraciones de tipos de activo.

## <a name="spare-parts-on-the-asset-type-setup"></a>Recambios en la configuración de tipo de activo

Como se describe en “Crear líneas de configuración de tipo de activo”, las piezas de repuesto se configuran en los modelos de activo en la página **Configuración de tipo de activo**. Por lo tanto, cuando abre la página **Configuración de tipo de activo**, solo ve las piezas de repuesto relacionadas con la combinación seleccionada de tipo de activo, fabricante de activo y modelo de activo. Para ver una lista de todos los registros de piezas de repuesto, abra la página **Recambios** (**Administración de activos** \> **Consultas** \> **Recambios**).

En la página **Recambios**, también puede crear nuevas piezas de repuesto para combinaciones existentes de tipo de activo, fabricante de activo y modelo de activo. Puede decidir si prefiere crear registros de piezas de repuesto en la página **Configuración de tipo de activo** o la página **Recambios**. La página **Configuración de tipo de activo** proporciona una visión general de los datos de la combinación seleccionada de tipo de activo, fabricante de activo y modelo de activo, mientras que la página **Recambios** proporciona una visión general completa de todas las líneas de configuración del tipo de activo. Si la página **Recambios** contiene muchos registros, la página **Configuración de tipo de activo** puede darle una mejor visión general.

Para ver si el recambio de la línea seleccionada se usa en otro lugar en Administración de activos (por ejemplo, en relación con activos y órdenes de trabajo), seleccione **Artículo donde utilizado** para abrir la página **Artículo donde utilizado**. 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]