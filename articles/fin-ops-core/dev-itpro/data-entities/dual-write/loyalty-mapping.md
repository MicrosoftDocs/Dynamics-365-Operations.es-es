---
title: Tarjetas de fidelización de clientes y puntos de recompensa
description: Este tema describe la integración de datos sobre tarjetas de fidelización de clientes y puntos de recompensa entre aplicaciones en escritura dual.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: d2c3845c1a7371d9e992495246e8dd0eb8631020
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747996"
---
# <a name="customer-loyalty-cards-and-reward-points"></a>Tarjetas de fidelización de clientes y puntos de recompensa

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Las empresas clasifican a los clientes y brindan servicios sofisticados, basados en los patrones de compras y gastos de los clientes. Por ejemplo, Dynamics 365 Commerce, tiene la infraestructura y las funciones para facilitar y gestionar tarjetas de fidelización de clientes, puntos de recompensa, precios basados en lealtad y experiencias de compra basadas en recompensas. Cuando los datos sobre tarjetas de fidelización de clientes y puntos de recompensa en Commerce se sincronizan con Dataverse, las aplicaciones Customer Engagement pueden usar esos datos. Por ejemplo, los usuarios de Dynamics 365 Customer Service pueden usar los datos para proporcionar los mismos servicios sofisticados a través del servicio de asistencia.

## <a name="templates"></a>Plantillas

| Aplicaciones de Finance and Operations | Aplicaciones basadas en modelos en Dynamics 365 | Descripción |
|-----------------------------|-----------------------------------|-------------|
| Tarjeta de fidelización                | msdyn\_loyaltycards               | Esta plantilla sincroniza información sobre las tarjetas de fidelización del cliente. |
| Puntos de recompensa de fidelización       | msdyn\_loyaltyrewardpoints        | Esta plantilla sincroniza información sobre los puntos de recompensa del cliente. |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]