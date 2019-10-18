---
title: El usuario puede acceder a Core HR pero no a Onboard y Attract
description: Este tema explica cómo resolver el problema en el que un usuario puede tener acceso a Microsoft Dynamics 365 Talent - Core HR, pero no puede tener acceso a Attract ni Onboard.
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
ms.openlocfilehash: 80b1f8aeabfd033f393463f4be5a61447377f2d9
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "2009315"
---
# <a name="user-can-access-core-hr-but-not-onboard-or-attract"></a><span data-ttu-id="26259-103">El usuario puede acceder a Core HR pero no a Onboard y Attract</span><span class="sxs-lookup"><span data-stu-id="26259-103">User can access Core HR but not Onboard or Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="26259-104">**Detalles del entorno**</span><span class="sxs-lookup"><span data-stu-id="26259-104">**Environment details**</span></span>

- <span data-ttu-id="26259-105">La implementación de Microsoft Dynamics Lifecycle Services (LCS) la realizó el usuario A.</span><span class="sxs-lookup"><span data-stu-id="26259-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="26259-106">El usuario A agregó a B como usuario a Microsoft Dynamics 365 Talent: Core HR.</span><span class="sxs-lookup"><span data-stu-id="26259-106">User A added user B as a user to Microsoft Dynamics 365 Talent: Core HR.</span></span>

<span data-ttu-id="26259-107">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="26259-107">**Issue**</span></span>

<span data-ttu-id="26259-108">El usuario B puede tener acceso a Core HR, pero no puede tener acceso a la aplicación Talent: Attract o la aplicación Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="26259-108">User B can access Core HR, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="26259-109">Cuando el usuario intenta ir a **Aplicaciones de experiencia**, se le lleva en su lugar a un entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="26259-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="26259-110">**Solución**</span><span class="sxs-lookup"><span data-stu-id="26259-110">**Solution**</span></span>

<span data-ttu-id="26259-111">El usuario B de tener asignados derechos de ver el entorno de Microsoft PowerApps que el usuario A creó durante el proceso de abastecimiento.</span><span class="sxs-lookup"><span data-stu-id="26259-111">User B must be assigned the rights to view the Microsoft PowerApps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="26259-112">Para obtener más información, consulte “Conceder acceso al entorno” en [Aprovisionar Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="26259-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="26259-113">**Solución a largo plazo**</span><span class="sxs-lookup"><span data-stu-id="26259-113">**Long-term solution**</span></span>

<span data-ttu-id="26259-114">Microsoft está considerando asignar automáticamente los derechos adecuados a Onboard y Attract cuando se agrega un usuario a Core HR.</span><span class="sxs-lookup"><span data-stu-id="26259-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Core HR.</span></span>
