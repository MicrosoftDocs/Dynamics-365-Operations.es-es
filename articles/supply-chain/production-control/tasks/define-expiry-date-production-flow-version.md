---
title: Definir una fecha de vencimiento para una versión del flujo de producción
description: Para finalizar la validez y el procesamiento de una versión de flujo de producción en una fecha concreta, o planificar la sustitución de una versión activa por una versión nueva, necesita establecer una fecha de vencimiento en la versión.
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
ms.openlocfilehash: 9f6ee9177664767c31eaa3e9b65d7559a1a9662f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574434"
---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a>Definir una fecha de vencimiento para una versión del flujo de producción

[!include [banner](../../includes/banner.md)]

Para finalizar la validez y el procesamiento de una versión de flujo de producción en una fecha concreta, o planificar la sustitución de una versión activa por una versión nueva, necesita establecer una fecha de vencimiento en la versión. No es necesario desactivar la versión.


## <a name="set-an-expiration-date-to-end-a-production-flow-version"></a>Establecer una fecha de vencimiento para finalizar una versión del flujo de producción
1. Vaya a Control de producción > Configuración > Flujo de producción lean > Flujos de producción.
2. En la lista, busque y seleccione el registro deseado.
    * Seleccione cualquier flujo de producción que tenga una versión ya definida.  
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. Haga clic en Editar.
5. En la lista, marque la fila seleccionada.
6. En el campo Fecha de vencimiento, especifique una fecha y una hora.
    * Para la fecha de vencimiento, no se iniciará ni se activará una nueva versión. Tampoco no será posible crear o iniciar trabajos para este flujo de producción. Podrá completar los trabajos después de la fecha de vencimiento.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]