---
title: Notificar como terminado desde el dispositivo de tarjetas de trabajo
description: Este tema describe cómo configurar el sistema para que los usuarios de un dispositivo de tarjeta de trabajo puedan informar productos terminados de una orden de producción al inventario.
author: johanhoffmann
manager: tfehr
ms.date: 05/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: f5d34893ddc8adc3785ec50dbd72438cf8f68c5d
ms.sourcegitcommit: 52ba8d3e6af72df5dab6c04b9684a61454d353ad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "3403271"
---
# <a name="report-as-finished-from-the-job-card-device"></a>Notificar como terminado desde el dispositivo de tarjetas de trabajo

[!include [banner](../includes/banner.md)]

Los trabajadores usan la página **Informar de progreso** en el dispositivo de tarjeta de trabajo para informar de cantidades que se han completado para un trabajo de producción.

## <a name="control-whether-quantities-that-are-reported-as-finished-are-added-to-inventory"></a>Controle si las cantidades que se informan como terminadas se agregan al inventario

Para controlar si las cantidades que se informan como terminadas en la última operación se deben agregar al inventario y cómo hacerlo, siga estos pasos.

1. Vaya a **Control de producTO \> Configuración \> Ejecución de fabricación \> Valores predeterminados de pedido de producción**.
1. En la pestaña **Informar como terminado**, configure el campo **Actualizar informe terminado en línea** en uno de los siguientes valores:

    - **No**: no se agregará ninguna cantidad al inventario cuando se notifiquen cantidades en la última operación. El estado de la orden de producción nunca cambiará.
    - **Estado + Cantidad**: el estado de la orden de producción cambiará a *Informado como terminado*, y la cantidad se informará como terminada al inventario.
    - **Cantidad**: la cantidad se informará como terminada al inventario, pero el estado de la orden de producción nunca cambiará.
    - **Estado**: Solo cambiará el estado de la orden de producción. No se agregará ninguna cantidad al inventario cuando se notifiquen cantidades en la última operación.

> [!NOTE]
> Las cantidades no se siguen en el inventario si las operaciones de las que se informa como terminadas no están definidas como última operación. Sin embargo, esas cantidades se pueden usar para ver el progreso. También se pueden incluir en reglas que controlan si los trabajadores pueden comenzar la siguiente operación antes de alcanzar un umbral definido de cantidades informadas en la operación anterior. Puede definir estas reglas en la pestaña **Validación de cantidad** de la página **Valores predeterminados de orden de producción**.

Para obtener más información sobre cómo trabajar con la página **Valores predeterminados de orden de producción**, consulte [Parámetros de producción en la ejecución de fabricación](production-parameters-manufacturing-execution.md).

## <a name="report-batch-controlled-items-as-finished"></a>Informar de los artículos controlados por lotes como terminados

El dispositivo de tarjeta de trabajo admite tres escenarios para informar sobre artículos por lotes. Estos escenarios se aplican tanto a los artículos que están habilitados para procesos de almacén avanzados como a los artículos que no están habilitados para procesos de almacén avanzados.

- **Números de lote asignados manualmente:** los trabajadores introducen un número de lote personalizado. Este número de lote puede provenir de una fuente externa que el sistema no conoce.
- **Números de lote predefinidos:** los trabajadores seleccionan un número de lote en una lista de números de lote que el sistema genera automáticamente antes de que la orden de producción se envíe al dispositivo de la tarjeta de trabajo.
- **Números de lote fijos:** los trabajadores no introducen ni seleccionan un número de lote. En cambio, el sistema asigna automáticamente un número de lote a la orden de producción antes de su lanzamiento.

Para habilitar cada escenario, siga estos pasos.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Seleccione el producto a configurar.
1. En la ficha desplegable **Administrar inventario**, en el campo **Grupo de número de lote**, seleccione el grupo de números de seguimiento configurado para soportar el escenario.

> [!NOTE]
> De manera predeterminada, si no se asigna un grupo de números de lote a un producto controlado por lotes, el dispositivo de la tarjeta de trabajo posibilita una entrada manual para el número de lote durante el informe como terminado.

Las siguientes subsecciones describen cómo configurar grupos de números de seguimiento para admitir cada uno de los tres escenarios para informar sobre artículos por lotes.

### <a name="enable-batch-number-reporting-on-the-job-card-device"></a>Habilitar el informe del número de lote en el dispositivo de la tarjeta de trabajo

Para permitir que sus dispositivos de tarjeta de trabajo acepten un número de lote durante el informe como terminado, debe usar [gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para activar las siguientes características (en este orden):

1. Mejora de la experiencia del usuario para el cuadro de diálogo de progreso del informe en el dispositivo de tarjeta de trabajo.
1. Habilite esta opción para especificar números de lote y serie mientras se notifica como terminado desde el dispositivo de tarjeta de trabajo (Vista previa)

### <a name="set-up-a-tracking-number-group-that-lets-workers-manually-assign-a-batch-number"></a>Configure un grupo de números de seguimiento que permita a los trabajadores asignar manualmente un número de lote

Para permitir números de lote asignados manualmente, siga estos pasos para establecer un número de grupo de seguimiento.

1. Vaya a **Gestión de inventario \> Configurar \> Dimensiones \> Seguimiento de grupos de números**.
1. Cree o seleccione el grupo de números de seguimiento para configurar.
1. En la ficha desplegable **General**, configure la opción **Manual** en **Sí**.

    ![Página de grupos de números de seguimiento](media/tracking-number-group-manual.png "Página de grupos de números de seguimiento")

1. Establezca otros valores según lo requiera y luego seleccione este grupo de números de seguimiento como el grupo de números de lote para los productos lanzados para los que desea usar este escenario.

Cuando usa este escenario, el campo **Número de lote** que la página **Informar progreso** del dispositivo de la tarjeta de trabajo proporciona un cuadro de texto donde los trabajadores pueden introducir cualquier valor.

![Página de informes de progreso con un campo para números de lote manuales](media/job-card-device-batch-manual.png "Página de informes de progreso con un campo para números de lote manuales")

### <a name="set-up-a-tracking-number-group-that-provides-a-list-of-predefined-batch-numbers"></a>Configurar un grupo de números de seguimiento que proporcione una lista de números de lote predefinidos

Para proporcionar una lista de números de lote predefinidos, siga estos pasos para establecer un número de grupo de seguimiento.

1. Vaya a **Gestión de inventario \> Configurar > Dimensiones \> Seguimiento de grupos de números**.
1. Cree o seleccione el grupo de números de seguimiento para configurar.
1. En la ficha desplegable **General**, configure la opción **Solo para transacciones de inventario** en **Sí**.
1. Utilice el campo **Por cantidad** para dividir los números de lote por cantidad, según el valor que introduzca. Por ejemplo, tiene una orden de producción para diez piezas, y el campo **Por cantidad** se establece en *2*. En este caso, se asignarán cinco números de lote a la orden de producción cuando se cree.

    ![Página de grupos de números de seguimiento](media/tracking-number-group-predefined.png "Página de grupos de números de seguimiento")

1. Establezca otros valores según lo requiera y luego seleccione este grupo de números de seguimiento como el grupo de números de lote para los productos lanzados para los que desea usar este escenario.

Cuando usa este escenario, el campo **Número de lote** que proporciona la página **Informar de progreso** del dispositivo de la tarjeta de trabajo es una lista desplegable donde los trabajadores deben introducir un valor predefinido.

![Página de informes de progreso con una lista de números de lote predefinidos](media/job-card-device-batch-predefined.png "Página de informes de progreso con una lista de números de lote predefinidos")

### <a name="set-up-a-tracking-number-group-that-automatically-assigns-batch-numbers"></a>Configurar un grupo de números de seguimiento que asigne automáticamente números de lote

Si los números de lote deben asignarse automáticamente, sin la intervención del trabajador, siga estos pasos para configurar un grupo de números de seguimiento.

1. Vaya a **Gestión de inventario \> Configurar \> Dimensiones \> Seguimiento de grupos de números**.
1. Cree o seleccione el grupo de números de seguimiento para configurar.
1. En la ficha desplegable **General**, configure la opción **Solo para transacciones de inventario** en **No**.
1. Establezca la opción **Manual** en **No**.

    ![Página de grupos de números de seguimiento](media/tracking-number-group-fixed.png "Página de grupos de números de seguimiento")

1. Establezca otros valores según lo requiera y luego seleccione este grupo de números de seguimiento como el grupo de números de lote para los productos lanzados para los que desea usar este escenario.

Cuando usa este escenario, el campo **Número de lote** que proporciona la página **Informar progreso** del dispositivo de la tarjeta de trabajo muestra un valor, pero los trabajadoresno pueden editarlo.

![Página de informes de progreso con un número de lote fijo](media/job-card-device-batch-fixed.png "Página de informes de progreso con un número de lote fijo")

## <a name="report-as-finished-to-a-license-plate"></a>Notificar como terminado a una matrícula

Los procesos avanzados de almacén pueden usar la dimensión de la placa de matrícula para seguir el inventario en ubicaciones de almacén que se han configurado para este propósito. En este caso, se requiere el número de placa cuando un trabajador informa que las cantidades están terminadas.

### <a name="enable-license-plate-reporting-and-label-printing"></a>Habilitar informe de matrícula e impresión de etiquetas

Para usar las características que se describen en esta sección, debe usar [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para activar las siguientes características (en este orden):

1. Matrícula de entidad de almacén para notificaciones agregada al dispositivo de tarjetas de trabajo
1. Habilitar la generación automática de matrícula de entidad de almacén al informar como terminado en el dispositivo de tarjetas de trabajo
1. Imprimir etiqueta desde dispositivo de tarjeta de trabajo

### <a name="set-up-reporting-as-finished-to-a-license-plate"></a>Configurar infromes de terminado para una matrícula

Para controlar si los trabajadores deben reutilizar una matrícula existente o generar una nueva matrícula cuando informan de cantidades como terminadas, siga estos pasos.

1. Vaya a **Control de producción \> Configuración \> Ejecución de fabricación \> Configurar tarjeta de trabajo para dispositivos**.
2. Para cada dispositivo, establezca las siguientes opciones:

    - **Generar matrícula**: establezca esta opción en **Sí** para generar una nueva matrícula para cada informe de terminado. Establézcalo en **No** si se debe usar una matrícula existente para cada informe de terminado.
    - **Etiqueta de impresión**: establezca esta opción en **Sí** si el trabajador debe imprimir una etiqueta de matrícula para cada informe de terminado. Establézcalo en **No** si no se requiere etiqueta. 

![Configurar tarjeta de trabajo para página de dispositivos](media/config-job-card-raf.png "Configurar tarjeta de trabajo para página de dispositivos")

> [!NOTE]
> Para configurar la etiqueta, vaya a **Gestión de almacenes \> Configurar \> Ruta de documentos \> Ruta de documentos**. Para más información, consulte [Habilitar la impresión de etiquetas de matrículas](../warehousing/tasks/license-plate-label-printing.md).
