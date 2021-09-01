---
title: Los administradores del sistema no pueden compensar las retenciones de pedidos porque no están autorizados
description: Los administradores del sistema no pueden compensar las retenciones de pedidos porque no están autorizados.
author: SmithaNataraj
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 0d0fbcc111d77ae1a362984033216f5973e2bc74f2ee95947b662ef60a13d83e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750915"
---
# <a name="system-administrators-cant-clear-order-holds-because-they-arent-authorized"></a>Los administradores del sistema no pueden compensar las retenciones de pedidos porque no están autorizados

Número de KB: 4614642

## <a name="symptoms"></a>Síntomas

Los administradores del sistema no pueden compensar las retenciones de pedidos de ventas a menos que tengan el rol específico que se les asigna en el código de retención de pedidos.

## <a name="resolution"></a>Resolución

El acceso a algunas operaciones, como la compensación de pedidos de ventas retenidos, se controla mediante la configuración de una política comercial. Por lo general, los administradores del sistema no pueden realizar operaciones de este tipo. 

Con mayor frecuencia, el acceso para realizar una tarea específica se rige por políticas comerciales y solo las personas específicas de una organización están autorizadas para realizar esa tarea. Los ejemplos incluyen aprobaciones que son el resultado de aprobaciones de flujo de trabajo y tareas específicas que son el resultado de una configuración de flujo de trabajo.

Aunque ningún flujo de trabajo está asociado con las retenciones de pedidos, el principio es similar. Un rol relevante designa al grupo específico de personas en una organización que tienen derecho a compensar retenciones de pedidos. Este derecho no debe otorgarse necesariamente a todos los administradores, porque ese enfoque infringe la política comercial definida.
