---
title: Contratos de servicio
description: El acuerdo de servicio le permite definir los recursos utilizados en una visita de servicio típica y cómo se facturan dichos servicios al cliente.
author: ShylaThompson
manager: AnnBe
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c6425dcf1c89f625d997be0dd4a52aaecb6e6d65
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568290"
---
# <a name="service-agreements"></a>Contratos de servicio

[!include [banner](../includes/banner.md)]

El acuerdo de servicio le permite definir los recursos utilizados en una visita de servicio típica y cómo se facturan dichos servicios al cliente.

Todos los acuerdos de servicio están vinculados a proyectos mediante los cuales se registran y facturan las transacciones. No obstante, puede facturar las transacciones de pedido de servicio directamente a través del proyecto sin conectarse primero al pedido de servicio de un acuerdo de servicio. Esto podría resultar útil si el pedido de servicio es una visita única y la necesidad de procesar las transacciones del servicio rápidamente es más importante que la necesidad de mantener información detallada del acuerdo de servicio sobre un cliente durante un período de tiempo.

## <a name="service-agreement"></a>Acuerdo de servicio

En cada acuerdo de servicio, debe especificar un proyecto, un id. de acuerdo de servicio y un grupo de acuerdos de servicio. El grupo de acuerdos de servicio se puede utilizar para ordenar y organizar contratos de servicio.

Una cabecera de acuerdo de servicio contiene los parámetros que se aplicarán a todas las líneas del acuerdo vinculadas:

-  Si se ha suspendido el acuerdo de servicio. Si se ha suspendido el acuerdo de servicio, no se pueden generar pedidos de servicio a partir del acuerdo de servicio.
-  La duración del acuerdo de servicio.
-  Cómo se combinarán las líneas del pedido de servicio en los pedidos de servicio.
-  Si el acuerdo de servicio es una plantilla.

En la cabecera del acuerdo de servicio, también configurar todos los objetos de servicio y las tareas de servicio que se pueden utilizar con el acuerdo de servicio especificando las tareas o los objetos de servicio específicos que deben estar vinculados a las distintas líneas del acuerdo.

También puede copiar líneas del acuerdo de servicio o líneas de la plantilla de servicio en el acuerdo de servicio actual desde la cabecera del acuerdo de servicio.

Se pueden suspender acuerdos de servicio y detener líneas de acuerdos de servicio individuales.

Si selecciona la casilla **Suspendido** en un contrato de servicio, no podrá:

-    Crear automáticamente o manualmente pedidos de servicio para el acuerdo de servicio.

Si selecciona la casilla **Detenido** en una línea de contrato de servicio, no podrá:

-    Crear automáticamente o manualmente pedidos de servicio para la línea de acuerdo de servicio.
-    Copiar la línea de acuerdo de servicio en otro acuerdo de servicio o pedido de servicio.


> [!NOTE]
> Si se suspende un acuerdo de servicio, se detendrán todas las líneas asociadas a dicho acuerdo independientemente de su estado individual.

## <a name="service-agreement-lines"></a>Líneas del acuerdo de servicio

Las líneas del acuerdo de servicio describen detalladamente el contenido del trabajo de servicio propuesto. Estas líneas contienen los siguientes parámetros:

-  El tipo de transacción y la descripción del tipo de transacción.
-  El empleado que realiza el trabajo de servicio.
-  Los objetos del acuerdo de servicio en los que debe llevarse a cabo el servicio.
-  La frecuencia con la que se realiza el trabajo y se registran transacciones de artículos, gastos y cuotas asociadas.
-  La ventana de horas en la que pueden agruparse las líneas del pedido de servicio en un pedido de servicio.
-  Las tareas de servicio utilizadas para agrupar conjuntos de líneas del acuerdo en tareas de trabajo y para describir al técnico de servicio y a los clientes qué tarea de servicio debe proporcionarse.
-  Si se ha detenido una línea. Si se ha detenido una línea, no se pueden crear pedidos de servicio para dicha línea individual.
-  La configuración del proyecto, como la categoría y la propiedad de líneas.

## <a name="related-topics"></a>Temas relacionados

[Crear acuerdos de servicios](create-service-agreements.md)
