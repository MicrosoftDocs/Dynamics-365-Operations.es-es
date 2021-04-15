---
title: Programar capacidad de la carga de trabajo
description: Este tema explica cómo configurar y programar la capacidad de carga de trabajo para los trabajadores de un almacén o para un almacén completo.
author: MarkusFogelberg
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WMSWorkloadCapacity
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e2458009dabd71e6c8423e8e607a0cedb4765b88
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817350"
---
# <a name="schedule-workload-capacity"></a>Programar capacidad de la carga de trabajo

[!include[banner](../includes/banner.md)]

Puede programar la capacidad de la carga de trabajo para almacenes y también proyectar las cargas de trabajo actuales y futuras para los trabajadores de los almacenes individuales. Puede proyectar la carga de trabajo para el almacén completo o bien, proyectar la carga de trabajo de forma independiente para las cargas de trabajo entrantes y salientes.

Para proyectar la salida de la carga de trabajo para los almacenes seleccionados, los datos de la programación maestra deben estar disponibles para esos almacenes. Para obtener más información, consulte [Visión general de planes maestros](../master-planning/master-plans.md).

## <a name="schedule-and-view-workloads-for-a-warehouse"></a>Programar y ver cargas de trabajo para un almacén

Para programar la capacidad de la carga de trabajo para un almacén, crea una configuración de carga de trabajo para uno o varios almacenes y, a continuación, asocia la configuración de la carga de trabajo con un plan maestro. En la configuración de la capacidad de la carga de trabajo, puede definir límites para el peso o el volumen de las transacciones entrantes y salientes. También puede crear más de una configuración para cada almacén y, a continuación, asociar la configuración a planes maestros individuales. Por ejemplo, puede usar este enfoque para adaptarse a los cambios estacionales en los recursos.

Si los trabajadores de un almacén trabajan con transacciones para las cargas de trabajo entrantes y salientes, puede configurar la configuración de la capacidad del almacén para proyectar la carga de trabajo en una vista combinada.

Para programar y ver cargas de trabajo para los almacenes, debe completar las tareas siguientes:

1. Cree una configuración de la capacidad de la carga de trabajo y defina límites de la capacidad de la carga de trabajo para uno o varios almacenes.
2. Asociar la configuración de la capacidad de la carga de trabajo con un plan maestro para crear las proyecciones de la carga de trabajo y especificar cuánto tiempo se aplicarán las proyecciones.

### <a name="create-a-workload-capacity-setup-for-a-warehouse"></a>Crear una configuración de la capacidad de la carga de trabajo para un almacén

1. Seleccione **Gestión del inventario** \> **Configuración** \> **Supervisión de almacén** \> **Capacidad de la carga de trabajo**.
2. En el Panel de acciones, haga clic en **Nuevo** para crear una configuración de capacidad de carga de trabajo.
3. En la ficha **Almacenes**, seleccione **Nuevo** y, a continuación, introduzca valores en la línea para asociar un almacén con la configuración de capacidad de la carga de trabajo.
4. Active la casilla de verificación **Carga de trabajo combinada de entrada y salida** si el informe **Capacidad de carga de trabajo** muestra la carga de trabajo total de las transacciones entrantes y salientes en una vista.
5. En la ficha desplegable **Tipos de transacciones**, seleccione los tipos de transacción entrantes y salientes a los que se aplicarán los límites de la carga de trabajo.

    > [!NOTE]
    > Debe seleccionar al menos un tipo de transacción para la carga de trabajo entrante y la carga de trabajo saliente.

#### <a name="define-limits-for-volume-or-weight"></a>Definir límites de volumen o peso

Puede configurar límites para volumen o peso según la limitación que sea relevante para los recursos de almacén. Los límites que se especifican se incluyen en la proyección de la capacidad de la carga de trabajo que puede ver en el informe **Capacidad de carga de trabajo**.

En la información de proyecto sobre volumen y peso para artículos, se deben especificar para todos los productos el tipo estándar de volumen de un artículo de inventario y el peso de un artículo de inventario. Los campos que son obligatorios están disponibles en los siguientes grupos de campos en la ficha desplegable **Administrar inventario** de la página **Detalles de producto emitido** :

- Tratamiento
- Dimensiones físicas
- Medidas de peso

Si esta información no se especifica correctamente, recibirá un mensaje al generar el informe **Capacidad de carga de trabajo**. En el informe, puede explorar en profundidad para identificar la información que falta y que es necesaria para proyectar la carga de trabajo futura.

### <a name="associate-a-workload-capacity-setup-with-a-master-plan"></a>Asociar una configuración de capacidad de la carga de trabajo con un plan maestro

1. Seleccione **Gestión del inventario** \> **Periódico** \> **Programar carga de trabajo**.
2. En el campo **Plan maestro**, seleccione el plan maestro que usarlo para las proyecciones de la carga de trabajo.
3. En el campo **Número de días**, especifique el número de días que cubre la proyección de la carga de trabajo.
4. En el campo **Carga de trabajo**, seleccione la configuración de la carga de trabajo para asociarla al plan maestro.

### <a name="view-workload-capacity"></a>Ver capacidad de la carga de trabajo

1. Seleccione **Gestión del inventario** \> **Consultas e informes** \> **Informes de inventario físico** \> **Capacidad de carga de trabajo**.
2. En el campo **Número de columnas**, especifique el número de columnas que desea mostrar en el informe.
3. En el campo **Tipo de pedido**, seleccione **Planificado y confirmado**, **Planificado** o **Confirmado** , para indicar el tipo de pedidos que desea proyectar en el informe.
4. En el campo **Tipo de carga**, seleccione un tipo de carga para especificar si la capacidad de la carga de trabajo se debe proyectarse para volumen o para peso.
5. En el campo **Capacidad de carga de trabajo**, seleccione una configuración para la capacidad de carga de trabajo.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]