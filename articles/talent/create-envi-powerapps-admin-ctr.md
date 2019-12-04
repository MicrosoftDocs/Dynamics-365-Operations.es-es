---
title: No se puede crear un entorno en el centro de administración de Power Apps
description: Este tema explica qué hacer si la gestión no puede crear un entorno en el centro de gestión de Microsoft Power Apps.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 5923c59ab5dde13fed0483972e76634031404fd8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773228"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a>No se puede crear un entorno en el centro de administración de Power Apps

[!include [banner](includes/banner.md)]

**Emisión**

- La administración de inquilinos/entorno no puede crear un entorno en el centro de gestión de Microsoft Power Apps.
- Una licencia que da a los usuarios el derecho de realizar el paso de creación del entorno no se ha asignado directamente al usuario que está realizando ese paso.

**Solución**

Asegúrese de que la gestión de arrendatarios haya asignado una licencia válida de Power Apps P2 directamente al usuario que llevará a cabo el paso de la creación del entorno. Aquí hay los planes de servicio de Microsoft Dynamics que proporcionan ese derecho.

| Referencia de almacén (SKU) global del producto       | Plan de servicio de Power Apps P2  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | Power Apps para Dynamics 365 |
| Microsoft Dynamics 365 Plan Enterprise Edition | Power Apps para Dynamics 365 |

Tenga en cuenta que diversas SKU de Microsoft Office también proporcionan el derecho, junto con SKU de Power Apps Plan 2 independientes. El aspecto importante es que una de estas SKU debe estar presente.

1. Ir a [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Cree los entornos siguiendo las instrucciones indicadas en [Aprovisionar Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).
