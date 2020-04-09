---
title: Definir una fecha de vencimiento para una versión del flujo de producción
description: Para finalizar la validez y el procesamiento de una versión de flujo de producción en una fecha concreta, o planificar la sustitución de una versión activa por una versión nueva, necesita establecer una fecha de vencimiento en la versión.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5d8df396abc3ac4a2c3920e6bf2b21d8a4463df2
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146868"
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

