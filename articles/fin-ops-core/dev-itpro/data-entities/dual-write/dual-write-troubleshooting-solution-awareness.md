---
title: Solucionar problemas relacionados con el conocimiento de la solución
description: Este tema proporciona información de solución de problemas que puede ayudarlo a solucionar problemas relacionados con el conocimiento de la solución.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 013e37269ec3df2bede15b28cffcc175967de9a3
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172630"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>Solucionar problemas relacionados con el conocimiento de la solución

[!include [banner](../../includes/banner.md)]



Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Common Data Service. Especificamente proporciona información que puede ayudarlo a solucionar problemas relacionados con el conocimiento de la solución.

> [!IMPORTANT]
> Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos. La sección para cada problema explica si se requiere una función o credenciales específicas.

## <a name="error-on-the-dual-write-page"></a>Error en la página de doble escritura

En la página **Doble escritura**, puede recibir un mensaje de error similar al siguiente ejemplo:

*La entidad con un nombre 'msdyn\_dualwriteentitymap' con namemapping =' Logical 'no se encontró en MetadataCache.*

Para solucionar el problema, asegúrese de que la solución de núcleo de doble escritura esté instalada en Common Data Service. La solución central de doble escritura es un requisito previo para el conocimiento de la solución.
