---
title: Creación de órdenes de trabajo
description: En este tema se explica cómo crear órdenes de trabajo en Administración de activos.
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
ms.openlocfilehash: b23ed3251b2f6cf4f34b423ce2f85301d6ab31a1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875877"
---
# <a name="creating-work-orders"></a>Creación de órdenes de trabajo


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Cuando haya programado trabajos de mantenimiento preventivo, el paso siguiente es crear las órdenes de trabajo para los trabajos. Esta tarea se lleva a cabo en uno de los programas de mantenimiento. Los trabajos programados en un programa de mantenimiento pueden tener distintos tipos de referencia:

| Tipo de referencia | Descripción                    |
|-----------------------|------------------------------------------------------------------------------------------------------------|
| Planes de mantenimiento     | Trabajos de mantenimiento preventivo basados en los tipos de planes de mantenimiento "Hora" o "Contador".                       |
| Rondas de mantenimiento    | Trabajos de mantenimiento preventivo que contienen varios activos que requieren un tipo de mantenimiento similar.           |
| Solicitud de mantenimiento   | Pedido creado manualmente para el mantenimiento o la reparación de un activo, que se puede convertir en una orden de trabajo. |


1. Haga clic en **Administración de activos** > **Común** > **Toda la programación de mantenimiento** o **Líneas de programa de mantenimiento abiertas** o **Conjuntos abiertos de la programación de mantenimiento**.

2. Seleccione los trabajos de mantenimiento programados para los que desea crear una orden de trabajo y para hacer clic en **Orden de trabajo**. El número total de horas previstas para las líneas seleccionadas se muestra en el campo **Horas de previsión de mantenimiento**.

3. En la sección **Parámetros**, seleccione cuántas órdenes de trabajo se deben crear. Puede crear una orden de trabajo por línea de programa de mantenimiento o varias órdenes de trabajo función de las selecciones realizadas en la sección **Una orden de trabajo por**.

4. Seleccione un **Tipo de orden de trabajo** que se usará en todas las órdenes de trabajo que cree.

5. Haga clic en **Aceptar**. Se crearán una o más órdenes de trabajo.

![Figura 1](media/18-preventive-maintenance.png)

