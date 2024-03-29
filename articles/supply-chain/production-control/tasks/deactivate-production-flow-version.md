---
title: Desactivar una versión de flujo de producción
description: Cuando ya no se necesita una versión del flujo de producción activa, se puede desactivar.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1691dc644e2e191a9e74980784d6dcf741dcd598
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576769"
---
# <a name="deactivate-a-production-flow-version"></a>Desactivar una versión de flujo de producción

[!include [banner](../../includes/banner.md)]

Cuando ya no se necesita una versión del flujo de producción activa, se puede desactivar. Debe usar esta opción únicamente si todas las reglas kanban y las actividades han terminado y no están activadas de nuevo. Tenga en cuenta que la fecha de caducidad de todas las reglas kanban relacionadas con esta versión del flujo de producción se actualizarán con la fecha y hora actuales. 

Para modificar una versión de flujo de producción activa, considere configurar una fecha de vencimiento para la versión activa y cree una nueva versión. Esto le permitirá continuar con sus operaciones de producción mientras prepara la nueva versión y las reglas kanban relacionadas. 

Para que una versión del flujo de producción activa expire, deberá establecer una fecha de vencimiento. En ese sentido, la desactivación es más bien una excepción que una regla. 

Para este procedimiento necesita un flujo de producción con una versión que se pueda desactivar. No intente esto en un entorno de producción salvo que totalmente convencido de que la versión que está completamente obsoleta.


## <a name="deactivate-a-production-flow-version"></a>Desactivar una versión de flujo de producción
1. Vaya a Control de producción > Configuración > Flujo de producción lean > Flujos de producción.
2. En la lista, busque y seleccione el registro deseado.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. En la lista, busque y seleccione el registro deseado.
5. Haga clic en Desactivar.
    * No continúe si no está convencido de que esta versión del flujo de producción está obsoleta. Haciendo clic en Acepar expirarán todas las reglas kanban activas y se pondrá fin de forma inmediata a todas las actividades de producción y de reabastecimiento de esta versión del flujo de producción.  
6. Haga clic en Aceptar



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]