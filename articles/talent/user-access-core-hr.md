---
title: El usuario puede tener acceso a Core HR pero no a la aplicación Onboard ni Attract.
description: Este tema explica cómo resolver el problema en el que un usuario puede tener acceso a Microsoft Dynamics 365 for Talent Core HR, pero no puede tener acceso a la aplicación Attract ni Onboard.
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
ms.openlocfilehash: ece6a81c54ef1421284fc79ab82ed3e31a972255
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519040"
---
# <a name="user-can-access-core-hr-but-not-the-onboard-or-attract-app"></a><span data-ttu-id="76f92-103">El usuario puede acceder a Core HR pero no a las aplicaciones Onboard y Attract</span><span class="sxs-lookup"><span data-stu-id="76f92-103">User can access Core HR but not the Onboard or Attract app</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="76f92-104">**Detalles del entorno**</span><span class="sxs-lookup"><span data-stu-id="76f92-104">**Environment details**</span></span>

- <span data-ttu-id="76f92-105">La implementación de Microsoft Dynamics Lifecycle Services (LCS) la realizó el usuario A.</span><span class="sxs-lookup"><span data-stu-id="76f92-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="76f92-106">El usuario A agregó a B como usuario a Microsoft Dynamics 365 for Talent Core HR.</span><span class="sxs-lookup"><span data-stu-id="76f92-106">User A added user B as a user to Microsoft Dynamics 365 for Talent Core HR.</span></span>

<span data-ttu-id="76f92-107">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="76f92-107">**Issue**</span></span>

<span data-ttu-id="76f92-108">El usuario B puede tener acceso a Core HR, pero no puede tener acceso a la aplicación Talent: Attract o la aplicación Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="76f92-108">User B can access Core HR, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="76f92-109">Cuando el usuario intenta ir a **Aplicaciones de experiencia**, se le lleva en su lugar a un entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="76f92-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="76f92-110">**Solución**</span><span class="sxs-lookup"><span data-stu-id="76f92-110">**Solution**</span></span>

<span data-ttu-id="76f92-111">El usuario B de tener asignados derechos de ver el entorno de Microsoft PowerApps que el usuario A creó durante el proceso de abastecimiento.</span><span class="sxs-lookup"><span data-stu-id="76f92-111">User B must be assigned the rights to view the Microsoft PowerApps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="76f92-112">Para obtener más información, consulte “Conceder acceso al entorno” en [Aprovisionar Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="76f92-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="76f92-113">**Solución a largo plazo**</span><span class="sxs-lookup"><span data-stu-id="76f92-113">**Long-term solution**</span></span>

<span data-ttu-id="76f92-114">Microsoft está considerando asignar automáticamente los derechos adecuados a Onboard y Attract cuando se agrega un usuario a Core HR.</span><span class="sxs-lookup"><span data-stu-id="76f92-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Core HR.</span></span>
