---
title: El usuario puede acceder a Human Resources pero no a Onboard o Attract
description: Este tema explica cómo resolver el problema en el que un usuario puede tener acceso a Microsoft Dynamics 365 Talent - Human Resources, pero no puede tener acceso a Attract ni Onboard.
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
ms.openlocfilehash: 6c384d9a7100982eabd201d910e1bea14355dc1f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462454"
---
# <a name="user-can-access-human-resources-but-not-onboard-or-attract"></a><span data-ttu-id="42347-103">El usuario puede acceder a Human Resources pero no a Onboard o Attract</span><span class="sxs-lookup"><span data-stu-id="42347-103">User can access Human Resources but not Onboard or Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="42347-104">**Detalles del entorno**</span><span class="sxs-lookup"><span data-stu-id="42347-104">**Environment details**</span></span>

- <span data-ttu-id="42347-105">La implementación de Microsoft Dynamics Lifecycle Services (LCS) la realizó el usuario A.</span><span class="sxs-lookup"><span data-stu-id="42347-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="42347-106">El usuario A agregó a B como usuario a Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="42347-106">User A added user B as a user to Microsoft Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="42347-107">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="42347-107">**Issue**</span></span>

<span data-ttu-id="42347-108">El usuario B puede tener acceso a Human Resources, pero no puede tener acceso a la aplicación Talent: Attract o la aplicación Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="42347-108">User B can access Human Resources, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="42347-109">Cuando el usuario intenta ir a **Aplicaciones de experiencia**, se le lleva en su lugar a un entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="42347-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="42347-110">**Solución**</span><span class="sxs-lookup"><span data-stu-id="42347-110">**Solution**</span></span>

<span data-ttu-id="42347-111">El usuario B de tener asignados derechos de ver el entorno de Microsoft Power Apps que el usuario A creó durante el proceso de abastecimiento.</span><span class="sxs-lookup"><span data-stu-id="42347-111">User B must be assigned the rights to view the Microsoft Power Apps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="42347-112">Para obtener más información, consulte “Conceder acceso al entorno” en [Aprovisionar Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="42347-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="42347-113">**Solución a largo plazo**</span><span class="sxs-lookup"><span data-stu-id="42347-113">**Long-term solution**</span></span>

<span data-ttu-id="42347-114">Microsoft está considerando asignar automáticamente los derechos adecuados a Onboard y Attract cuando se agrega un usuario a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="42347-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Human Resources.</span></span>
