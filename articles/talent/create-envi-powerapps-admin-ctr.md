---
title: "No se puede crear un entorno en el centro de gestión de PowerApps"
description: "Este tema explica qué hacer si la gestión no puede crear un entorno en el centro de gestión de Microsoft PowerApps."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 6f9b7ceef6895b295e6ae5a50d8ac7970497efe5
ms.contentlocale: es-es
ms.lasthandoff: 12/04/2018

---

# <a name="cant-create-an-environment-in-the-powerapps-admin-center"></a>No se puede crear un entorno en el centro de gestión de PowerApps

[!include [banner](includes/banner.md)]

**Emisión**

- La administración de inquilinos/entorno no puede crear un entorno en el centro de gestión de Microsoft PowerApps.
- Una licencia que da a los usuarios el derecho de realizar el paso de creación del entorno no se ha asignado directamente al usuario que está realizando ese paso.

**Solución**

Asegúrese de que la gestión de arrendatarios haya asignado una licencia válida de PowerApps P2 directamente al usuario que llevará a cabo el paso de la creación del entorno. Aquí hay los planes de servicio de Microsoft Dynamics que proporcionan ese derecho.

| Referencia de almacén (SKU) global del producto       | Plan de servicio de PowerApps P2  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | PowerApps for Dynamics 365 |
| Microsoft Dynamics 365 Plan Enterprise Edition | PowerApps for Dynamics 365 |

Tenga en cuenta que diversas SKU de Microsoft Office también proporcionan el derecho, junto con SKU de PowerApps Plan 2 independientes. El aspecto importante es que una de estas SKU debe estar presente.

1. Ir a [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Cree los entornos siguiendo las instrucciones indicadas en [Aprovisionar Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).

