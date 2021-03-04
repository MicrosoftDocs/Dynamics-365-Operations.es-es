---
title: Tiempo de inactividad para órdenes de trabajo
description: Este tema describe cómo crear registros de tiempo de inactividad por mantenimiento en el activo seleccionado en una orden de trabajo.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 263a044a0a378e95ea271ac1c6f468f9e3287f26
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436672"
---
# <a name="maintenance-downtime-for-work-orders"></a>Tiempo de inactividad para órdenes de trabajo

[!include [banner](../../includes/banner.md)]


Puede crear registros de tiempo de inactividad por mantenimiento en el activo seleccionado en una orden de trabajo. Esta capacidad resulta útil si desea registrar el tiempo de inactividad por mantenimiento en una o más máquinas en el área de producción. En primer lugar, cree los códigos de motivo del tiempo de inactividad por mantenimiento que desee usar, por ejemplo, **Desglose** y **Parada planificada**. Este paso se hace en la página **Códigos de motivo del tiempo de inactividad por mantenimiento**. A continuación, puede crear registros de tiempo de inactividad por mantenimiento en la página **Tiempo de inactividad por mantenimiento** y agregar códigos de motivo de inactividad por mantenimiento relevantes.

## <a name="create-maintenance-downtime-reason-codes"></a>Crear códigos de motivo del tiempo de inactividad por mantenimiento

1. Seleccione **Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Códigos de motivo del tiempo de inactividad por mantenimiento**.

2. Seleccione **Nuevo**.

3. En el campo **Código de motivo del tiempo de inactividad por mantenimiento**, especifique un identificador para el código de motivo del tiempo de inactividad mantenimiento.

4. Escriba un nombre en el campo **Nombre**.

5. Seleccione la casilla de verificación **Inclusión de KPI** si el código de motivo se debe incluir en los cálculos de los indicadores clave de rendimiento (KPI) para el activo. Normalmente, las detenciones de producción planificadas no deben incluirse en los cálculos de KPI ya que no afectan al rendimiento previsto.

6. Seleccione **Guardar**.

La ilustración siguiente muestra un ejemplo de página de **Códigos de motivo de inactividad por mantenimiento**.

![Figura 1](media/15-work-orders.png)

 Cuando haya creado los códigos de motivo del tiempo de inactividad por mantenimiento que desea usar, puede crear registros de tiempo de inactividad por mantenimiento para órdenes de trabajo y activos.


## <a name="create-maintenance-downtime-registrations"></a>Crear registros del tiempo de inactividad por mantenimiento

1. Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. Seleccione la orden de trabajo y, a continuación, en la pestaña **Orden de trabajo**, en el grupo **Activo**, seleccione **Tiempo de inactividad por mantenimiento**.

3. Seleccione **Nuevo**.

4. Defina la fecha y el intervalo de tiempo del registro de tiempo de inactividad por mantenimiento en los campos **Desde** y **Hasta**.

>[!NOTE]
>Al salir del campo **Hasta**, la duración en horas se inserta automáticamente en el campo **Duración**.

5. Seleccione un código de motivo en el campo **Código de motivo del tiempo de inactividad por mantenimiento**.

6. Repita los pasos del 3 al 5 para agregar registros.

7. Seleccione **Guardar**.

En la ilustración siguiente se muestra un ejemplo de lista de registro de tiempo de inactividad por mantenimiento.

![Figura 2](media/16-work-orders.png)

El calendario usado para calcular un registro de tiempo de inactividad por mantenimiento depende de la selección en la configuración de activos y parámetros. Si se selecciona un recurso en un activo en el campo **Recurso** de la ficha desplegable **Activo fijo** de la página **Todos los activos** , se utiliza la configuración del calendario para el grupo de recursos asociado, como se muestra en la ilustración siguiente.

![Figura 3](media/17-work-orders.png)

Si no se selecciona ningún recurso en el activo, se utiliza el calendario estándar seleccionado en la página **Parámetros de administración de activos**, como se muestra en la siguiente figura.

![Figura 4](media/18-work-orders.png)

Haga clic en **Administración de activos de la empresa** > **Consultas** > **Tiempo de inactividad por mantenimiento** para obtener una visión general de todos los registros de tiempo de inactividad por mantenimiento.

>[!NOTE]
>Todos los calendarios utilizados en el módulo **Administración de activos** se configuran en **Administración de la organización** > **Configuración** > **Calendarios** > **Calendarios**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]