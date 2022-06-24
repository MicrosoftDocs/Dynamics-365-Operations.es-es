---
title: Solucionar problemas relacionados con el conocimiento de soluciones
description: Este artículo proporciona información de solución de problemas que puede ayudarlo a solucionar problemas relacionados con el conocimiento de la solución.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c280eef995664c640e382817dda9d6e1cde154c6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871506"
---
# <a name="troubleshoot-issues-related-to-solution-awareness"></a>Solucionar problemas relacionados con el conocimiento de soluciones

[!include [banner](../../includes/banner.md)]





Este artículo proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de finanzas y operaciones y Dataverse. Especificamente proporciona información que puede ayudarlo a solucionar problemas relacionados con el conocimiento de la solución.

> [!IMPORTANT]
> Algunos de los problemas que aborda este artículo pueden requerir la característica de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos. La sección para cada problema explica si se requiere una función o credenciales específicas.

## <a name="error-on-the-dual-write-page"></a>Error en la página de doble escritura

En la página **Doble escritura**, puede recibir un mensaje de error similar al siguiente ejemplo:

*La entidad con un nombre 'msdyn\_dualwriteentitymap' con namemapping =' Logical 'no se encontró en MetadataCache.*

Para solucionar el problema, asegúrese de que la solución de núcleo de doble escritura esté instalada en Dataverse. La solución central de doble escritura es un requisito previo para el conocimiento de la solución.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]