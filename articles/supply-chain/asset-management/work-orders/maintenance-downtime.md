---
title: Tiempo de inactividad por mantenimiento
description: En este tema se describe el tiempo de inactividad por mantenimiento en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cc79dc1b5911679586fa560142ada5add1a881d2
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918253"
---
# <a name="maintenance-downtime"></a>Tiempo de inactividad por mantenimiento


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Puede crear registros de tiempo de inactividad por mantenimiento en el activo seleccionado en una orden de trabajo. Esto resulta útil si desea registrar el tiempo de inactividad por mantenimiento en una o más máquinas en el área de producción. En primer lugar, cree los códigos de motivo del tiempo de inactividad por mantenimiento que desee usar, por ejemplo, desglose y detención planificada. Esto se hace en **Códigos de motivo del tiempo de inactividad por mantenimiento**. A continuación, puede crear registros de tiempo de inactividad por mantenimiento en **Tiempo de inactividad por mantenimiento** y agregar códigos de motivo relevantes.

## <a name="create-maintenance-downtime-reason-codes"></a>Crear códigos de motivo del tiempo de inactividad por mantenimiento

1. Haga clic en **Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Códigos de motivo del tiempo de inactividad por mantenimiento**.

2. Haga clic en **Nuevo**.

3. Inserte un identificador en el campo **Código de motivo del tiempo de inactividad por mantenimiento**.

4. Inserte un nombre para el código de motivo en el campo **Nombre**.

5. Seleccione la casilla **Inclusión de KPI** si el código de motivo debe incluirse en cálculos de KPI activos. Normalmente, las detenciones de producción planificadas no deben incluirse en los cálculos de KPI ya que no afectan al rendimiento previsto.

6. Haga clic en **Guardar**.

![Figura 1](media/15-work-orders.png)


Cuando haya creado los códigos de motivo del tiempo de inactividad por mantenimiento que desea usar, puede crear registros de tiempo de inactividad por mantenimiento para órdenes de trabajo y activos.


## <a name="create-maintenance-downtime-registrations"></a>Crear registros del tiempo de inactividad por mantenimiento

1. Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. Seleccione la orden de trabajo y haga clic en **Tiempo de inactividad por mantenimiento**.

3. Haga clic en **Nuevo**.

4. Inserte el intervalo de fecha y hora para el registro de tiempo de inactividad por mantenimiento en los campos **Desde** y **Hasta**.

5. Al salir del campo **Hasta**, la duración en horas se inserta automáticamente en el campo **Duración**.

6. Seleccione un código de motivo en el campo **Código de motivo del tiempo de inactividad por mantenimiento**.

7. Repita los pasos 3-6 si desea agregar más registros.

8. Haga clic en **Guardar**.


![Figura 2](media/16-work-orders.png)


El calendario usado para calcular un registro de tiempo de inactividad por mantenimiento depende de la selección en la configuración de activos y parámetros. Si se selecciona un recurso en un activo en la ficha desplegable **Todos los activos fijos** > **Activo fijo** > campo **Recurso**, se utiliza la configuración del calendario para el grupo de recursos asociado, como se muestra en la ilustración siguiente.

![Figura 3](media/17-work-orders.png)


Si no se selecciona ningún recurso en el activo, se utiliza el calendario estándar de **Parámetros de administración de activos**, como se muestra en la siguiente figura.

![Figura 4](media/18-work-orders.png)


Haga clic en **Administración de activos de la empresa** > **Consultas** > **Tiempo de inactividad por mantenimiento** para obtener una visión general de todos los registros de tiempo de inactividad por mantenimiento.

>[!NOTE]
>Todos los calendarios utilizados en el módulo **Administración de activos** se configuran en **Administración de la organización** > **Configuración** > **Calendarios** > **Calendarios**.

