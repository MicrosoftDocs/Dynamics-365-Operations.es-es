---
title: Actualización automática de los contadores de activos
description: Este tema describe la actualización automática de contadores de activos en la Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 97e6912cd37d6f82d8bf022141f04645a3364ee1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875889"
---
# <a name="automatic-update-of-asset-counters"></a>Actualización automática de los contadores de activos

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

En la sección anterior, se describe el registro manual de los contadores de activos. La configuración de los contadores de activos se describe en [Contadores](../setup-for-objects/counters.md).

Los valores de un contador también se pueden actualizar automáticamente a partir de los registros de producción, en función de las horas de producción o la cantidad de producción. Esto se hace en **Actualizar contadores de activos**. Puede actualizar uno o varios activos insertando un parámetro, **Desde fecha**. Este parámetro especifica la fecha de inicio para los registros de producción (horas o cantidad producida), es decir, la fecha de inicio a partir de la cual deben actualizarse los valores de contador.

Todos los activos que están relacionadas con un recurso *y* tienen contadores de activos, configurados para actualizarse según la cantidad producida o las horas de producción, se incluirán en una actualización automática, y se crearán nuevos valores de contador.

En relación con los contadores basados en la cantidad de producción, la cantidad de artículos y la cantidad de defectos registrados se incluyen en el recuento. Si la unidad utilizada para el registro de cantidad producida es diferente de la unidad utilizada en el contador, la cantidad se convierte para que se corresponda con la unidad del contador.

Como se mencionó anteriormente, los contadores automáticos se pueden actualizar a partir de los registros de producción. Por tanto, el activo para el que desea para actualizar automáticamente los contadores debe estar relacionado con un recurso (máquina). Las descripciones siguientes proporcionan una visión general de la configuración y el procesamiento de órdenes de producción (en el módulo **Control de producción**), que se utiliza como base para la actualización automática de los contadores en un activo del módulo **Administración de activos**.

Cuando se hayan registrado las cantidades o las horas de producción en el recurso, puede actualizar los contadores de activos relacionados.

1. Haga clic en **Administración de activos** > **Periódico** > **Activos** > **Actualizar contadores de activos**.

2. Seleccione la fecha de inicio de la actualización automática en el campo **Desde fecha**.

>[!NOTE]
>La fecha de este campo es la fecha de "trabajo en curso" **Transacciones de ruta** (campo **Control de producción** > **Consultas e informes** > **Producción** > **Transacciones e rutas** > **Fecha física**).

3. Si desea seleccionar los activos específicos, los tipos de activo o los recursos de la actualización automática, haga clic en **Filtro** en la ficha desplegable **Registros que incluir** y haga la selección relevante.

4. Si es necesario, puede configurar la actualización automática como un trabajo por lotes en la ficha desplegable **Ejecutar en segundo plano**.

![Figura 1](media/12-work-orders.png)

5. Haga clic en **Aceptar**. Cuando haya finalizado la actualización del contador, podrá ver los registros del contador relacionados con el activo en **Contadores de activos** (**Administración de activos** > **Común** > **Activos** > **Todos os activos** >seleccionar activo > botón **Contadores**).

En **Totales del contador de activos**, puede obtener una visión general del último registro hecho en todos los tipos de contador en todos los activos. Haga clic en **Administración de activos** > **Consultas** > **Activos** > **Valor agregado de activos**. La vista se muy parecida **Contadores de activos**, pero no puede agregar o editar registros en **Valor agregado de activo**. Es solo para la visión general.

![Figura 2](media/13-work-orders.png)


- Aún es posible crear registros manuales de valor del contador para los tipos de contador que se actualizan. Consulte la sección "Actualización manual de contadores de activos" para obtener más información.
- Puede configurar los contadores relacionados con otro contador, lo que significa que cuando se actualizan un contador, los contadores se actualizan automáticamente al mismo tiempo. Consulte [Contadores](../setup-for-objects/counters.md) en que respecta a la configuración de los contadores relacionados.
