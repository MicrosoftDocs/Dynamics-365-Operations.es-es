---
title: No se puede crear un entorno en el centro de administración de Power Apps
description: Este artículo explica qué hacer si el administrador no puede crear un entorno en el centro de administración Microsoft Power Apps.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 73c8910900ba6486a8e60a547b07ea0c82a6cb10
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053356"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a>No se puede crear un entorno en el centro de administración de Power Apps

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Emisión**

- La administración de inquilinos/entorno no puede crear un entorno en el centro de gestión de Microsoft Power Apps.
- El usuario no tiene una licencia que le dé derecho a crear entornos.

**Solución**

Asegúrese de que el administrador de inquilinos haya asignado una licencia P2 de Power Apps válida para el usuario que crea el entorno. Los planes de servicio de Microsoft Dynamics siguientes proporcionan permisos para crear entornos:

| Referencia de almacén (SKU) global del producto       | Plan de servicio de Power Apps P2  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | Power Apps para Dynamics 365 |
| Microsoft Dynamics 365 Plan Enterprise Edition | Power Apps para Dynamics 365 |

Tenga en cuenta que diversas SKU de Microsoft Office también proporcionan el derecho, junto con SKU de Power Apps Plan 2 independientes. El aspecto importante es que una de estas SKU debe estar presente.

1. Ir a [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Siga las instrucciones en [Aprovisionar Recursos humanos](/dynamics365/unified-operations/talent/provisioning-talent) para crear los entornos.


[!INCLUDE[footer-include](../includes/footer-banner.md)]