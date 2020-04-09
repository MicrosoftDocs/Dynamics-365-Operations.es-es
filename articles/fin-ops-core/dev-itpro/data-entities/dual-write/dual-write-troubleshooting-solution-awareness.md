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
# <a name="troubleshoot-issues-related-to-solution-awareness"></a><span data-ttu-id="5d9c6-103">Solucionar problemas relacionados con el conocimiento de la solución</span><span class="sxs-lookup"><span data-stu-id="5d9c6-103">Troubleshoot issues related to solution awareness</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="5d9c6-104">Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5d9c6-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="5d9c6-105">Especificamente proporciona información que puede ayudarlo a solucionar problemas relacionados con el conocimiento de la solución.</span><span class="sxs-lookup"><span data-stu-id="5d9c6-105">Specifically, it provides information that can help you fix issues that are related to solution awareness.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d9c6-106">Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="5d9c6-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="5d9c6-107">La sección para cada problema explica si se requiere una función o credenciales específicas.</span><span class="sxs-lookup"><span data-stu-id="5d9c6-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="error-on-the-dual-write-page"></a><span data-ttu-id="5d9c6-108">Error en la página de doble escritura</span><span class="sxs-lookup"><span data-stu-id="5d9c6-108">Error on the Dual-write page</span></span>

<span data-ttu-id="5d9c6-109">En la página **Doble escritura**, puede recibir un mensaje de error similar al siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5d9c6-109">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="5d9c6-110">*La entidad con un nombre 'msdyn\_dualwriteentitymap' con namemapping =' Logical 'no se encontró en MetadataCache.*</span><span class="sxs-lookup"><span data-stu-id="5d9c6-110">*The entity with a name 'msdyn\_dualwriteentitymap' with namemapping='Logical' was not found in the MetadataCache.*</span></span>

<span data-ttu-id="5d9c6-111">Para solucionar el problema, asegúrese de que la solución de núcleo de doble escritura esté instalada en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5d9c6-111">To fix the issue, make sure that the dual-write core solution is installed in Common Data Service.</span></span> <span data-ttu-id="5d9c6-112">La solución central de doble escritura es un requisito previo para el conocimiento de la solución.</span><span class="sxs-lookup"><span data-stu-id="5d9c6-112">The dual-write core solution is a prerequisite for solution awareness.</span></span>
