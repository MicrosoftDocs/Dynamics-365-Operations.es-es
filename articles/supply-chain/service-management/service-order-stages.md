---
title: Etapas de pedido de servicio
description: Al definir etapas para un pedido de servicio y asignarlas a los trabajadores, puede controlar el flujo de un pedido de servicio a través de las tareas que diferentes personas realizan en la organización de servicio.
author: sorenva
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAStageTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3e748afbd159d7a8fca1372676872cc02dd7ea57
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671741"
---
# <a name="service-order-stages"></a>Etapas de pedido de servicio   

[!include [banner](../includes/banner.md)]


Puede establecer etapas en un pedido de servicio para definir las tareas que se deben completar, el orden en el que se completarán y los trabajadores responsables de completarlas. Al definir etapas para un pedido de servicio y asignarlas a los trabajadores, puede controlar el flujo de un pedido de servicio a través de las tareas que diferentes personas realizan en la organización de servicio. La secuencia de etapas debe incluir una etapa inicial.

También puede definir las acciones que están permitidas en cada etapa. Por ejemplo, si desactiva la casilla de verificación **Registrar** en todas las etapas, excepto la última, evita el registro de pedidos de servicio antes de que estos se hayan procesado en toda la secuencia de etapas.

## <a name="branching-in-service-order-stages"></a>Ramificación de las etapas de pedido de servicio

Cuando configure una etapa de servicio, puede crear varias opciones, o ramas, para seleccionar para la siguiente etapa de servicio. Todas las ramas que cree estarán disponibles para seleccionarlas cuando la etapa inicial se complete. Por ejemplo, configure **Planificación** como etapa inicial. Cree dos etapas denominadas **En proceso** y **Cancelar**, y seleccione **Planificación** como etapa principal para ellas. Asigne la etapa **Planificación** al pedido de ventas. Cuando la etapa de planificación para el pedido de ventas se complete, podrá seleccionar la etapa **En proceso** si el pedido de ventas está listo para trabajar en él, o puede seleccionar la etapa **Cancelar** si el pedido de ventas se ha cancelado.

## <a name="see-also"></a>Consulte también

[Configurar las etapas de pedido de servicio](set-up-service-order-stages.md)

[Cambiar la etapa del pedido de servicio](change-service-order-stage.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]