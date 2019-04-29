---
title: Novedades y cambios en Dynamics 365 for Talent Core HR (1 de octubre de 2018)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 92f06d29dfa8110106a2a0e71434b2c0c75110b5
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2019
ms.locfileid: "859284"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-8-2018"></a><span data-ttu-id="2b20f-103">Novedades y cambios en Dynamics 365 for Talent Core HR (8 de octubre de 2018)</span><span class="sxs-lookup"><span data-stu-id="2b20f-103">What's new or changed in Dynamics 365 for Talent Core HR (October 8, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2b20f-104">**Compilación 8.1.1050.0**</span><span class="sxs-lookup"><span data-stu-id="2b20f-104">**Build 8.1.1050.0**</span></span>

<span data-ttu-id="2b20f-105">Este tema describe las características que son nuevas o que se han cambiado en Core HR.</span><span class="sxs-lookup"><span data-stu-id="2b20f-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="allow-other-dates-to-be-used-on-leave-tier-basis-leave-management"></a><span data-ttu-id="2b20f-106">Permitir que otras fechas se utilicen en la base de nivel de la licencia (Administración de la licencia)</span><span class="sxs-lookup"><span data-stu-id="2b20f-106">Allow other dates to be used on leave tier basis (Leave Management)</span></span>

<span data-ttu-id="2b20f-107">Al conceder una licencia a los empleados, la función del nivel de baja determina cuánto tiempo de licencia acumula el empleado.</span><span class="sxs-lookup"><span data-stu-id="2b20f-107">When awarding leave to employees, the award tier basis determines how much time off an employee accrues.</span></span> <span data-ttu-id="2b20f-108">Actualmente, estos niveles se basan en la fecha inicial del empleado y la fecha de antigüedad.</span><span class="sxs-lookup"><span data-stu-id="2b20f-108">Currently, these tiers are based on employee start date and seniority date.</span></span> <span data-ttu-id="2b20f-109">En algunos casos, las organizaciones necesitan que estos niveles se basen en otras fechas, como la fecha del aniversario o la fecha original de contratación.</span><span class="sxs-lookup"><span data-stu-id="2b20f-109">In some scenarios, organizations need these tiers to be based on other dates, like anniversary date or original hire date.</span></span> <span data-ttu-id="2b20f-110">Estas fechas ya se utilizan en el plan de la licencia para determinar cuándo se producen acumulaciones, se ha agregado la capacidad para que se usen estas mismas fechas si un empleado está inscrito en un plan para determinar el importe de acumulación.</span><span class="sxs-lookup"><span data-stu-id="2b20f-110">These dates are already used on the leave plan to determine when accruals happen, the ability for these same dates to be used when an employee is enrolled in a plan have been added to determine the accrual amount.</span></span> 

## <a name="other-changes"></a><span data-ttu-id="2b20f-111">Otros cambios</span><span class="sxs-lookup"><span data-stu-id="2b20f-111">Other changes</span></span>
<span data-ttu-id="2b20f-112">Se han incluido diversas correcciones en esta versión.</span><span class="sxs-lookup"><span data-stu-id="2b20f-112">Miscellanous fixes have been included in this release.</span></span>

## <a name="known-issue"></a><span data-ttu-id="2b20f-113">Problema conocido</span><span class="sxs-lookup"><span data-stu-id="2b20f-113">Known issue</span></span>

<span data-ttu-id="2b20f-114">**Problema:** Al agregar nuevos archivos adjuntos a un trabajador, los botones **Nuevo** y **Editar** se atenúan. **Solución alternativa:** Antes de abrir la página de los datos adjuntos, asegúrese de que los cuadros informativos de la página **Trabajador** estén cerrados.</span><span class="sxs-lookup"><span data-stu-id="2b20f-114">**Issue:** When adding a new attachment to a worker, the **New** and **Edit** buttons are grayed out. **Workaround:** Before opening the attachment page, make sure that the FactBoxes on the **Worker** page are closed.</span></span> <span data-ttu-id="2b20f-115">Si se cierran los cuadros informativos cuando la página **Trabajador** se carga, los botones de datos adjuntos se habilitan.</span><span class="sxs-lookup"><span data-stu-id="2b20f-115">If the FactBoxes are closed when the **Worker** page is loaded, the attachments buttons will be enabled.</span></span> <span data-ttu-id="2b20f-116">(Este problema se corregirá en la siguiente actualización de la plataforma).</span><span class="sxs-lookup"><span data-stu-id="2b20f-116">(This issue will be fixed in the next platform update.)</span></span>
