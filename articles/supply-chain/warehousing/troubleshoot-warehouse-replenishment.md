---
title: Solucionar problemas de reabastecimiento de almacenes
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con reabastecimiento de almacenes en Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 7748a18d2b6f612b3ac9ac1a75efb6ae5f13859a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993905"
---
# <a name="troubleshoot-warehouse-replenishment"></a><span data-ttu-id="88baf-103">Solucionar problemas de reabastecimiento de almacenes</span><span class="sxs-lookup"><span data-stu-id="88baf-103">Troubleshoot warehouse replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="88baf-104">Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con reabastecimiento de almacenes en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="88baf-104">This topic describes how to fix common issues that you might encounter while you work with warehouse replenishment in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-work-1-cannot-be-unblocked-because-it-has-unfinished-replenishment-work"></a><span data-ttu-id="88baf-105">Recibo el siguiente mensaje de error: "El Id. de trabajo %1 no se puede desbloquear porque tiene un trabajo de reabastecimiento sin terminar".</span><span class="sxs-lookup"><span data-stu-id="88baf-105">I receive the following error message: "Work %1 cannot be unblocked because it has unfinished replenishment work."</span></span>

### <a name="issue-description"></a><span data-ttu-id="88baf-106">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="88baf-106">Issue description</span></span>

<span data-ttu-id="88baf-107">El trabajo de picking está bloqueado debido al trabajo de reabastecimiento dependiente.</span><span class="sxs-lookup"><span data-stu-id="88baf-107">Picking work is blocked because of dependent replenishment work.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="88baf-108">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="88baf-108">Issue resolution</span></span>

<span data-ttu-id="88baf-109">Cuando utiliza el reabastecimiento de demanda de oleada, si una ubicación de picking debe reabastecerse para satisfacer la demanda de la orden de origen, el sistema crea tanto el trabajo de reabastecimiento como el trabajo de picking.</span><span class="sxs-lookup"><span data-stu-id="88baf-109">When you use wave demand replenishment, if a picking location must be replenished to fulfill the source order demand, the system creates both the replenishment work and the picking work.</span></span> <span data-ttu-id="88baf-110">Sin embargo, bloquea el trabajo de picking hasta que se completa el trabajo de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="88baf-110">However, it blocks the picking work until the replenishment work is completed.</span></span> <span data-ttu-id="88baf-111">Este comportamiento es intencional, porque la ubicación de recolección no tendrá suficiente inventario a menos que se complete el trabajo de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="88baf-111">This behavior is intentional, because the picking location won't have enough inventory unless the replenishment work is completed.</span></span> <span data-ttu-id="88baf-112">Complete el trabajo de reabastecimiento y luego procese el trabajo de selección.</span><span class="sxs-lookup"><span data-stu-id="88baf-112">Complete the replenishment work, and then process the picking work.</span></span>
