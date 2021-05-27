---
title: Los ajustes de principos de vaciado en líneas L. MAT. no se respetan
description: Los ajustes de principos de vaciado en líneas de lista de materiales (L. MAT.) no se respetan.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchTable,ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 84a84728016119a2a02f59f6903171afbceb48e7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026883"
---
# <a name="flushing-principle-settings-on-bom-lines-arent-respected"></a><span data-ttu-id="25ae5-103">Los ajustes de principos de vaciado en líneas L. MAT. no se respetan</span><span class="sxs-lookup"><span data-stu-id="25ae5-103">Flushing principle settings on BOM lines aren't respected</span></span>

<span data-ttu-id="25ae5-104">Número de KB: 4612725</span><span class="sxs-lookup"><span data-stu-id="25ae5-104">KB number: 4612725</span></span>

## <a name="symptoms"></a><span data-ttu-id="25ae5-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="25ae5-105">Symptoms</span></span>

<span data-ttu-id="25ae5-106">Este problema ocurre cuando el campo **Consumo automático de L. MAT** en la pestaña **Actualización automática** de la página **Parámetros de control de producción** está configurado para *Principio de vaciado*.</span><span class="sxs-lookup"><span data-stu-id="25ae5-106">This issue occurs when the **Automatic BOM consumption** field on the **Automatic update** tab of the **Production control parameters** page is set to *Flushing principle*.</span></span> <span data-ttu-id="25ae5-107">Esta configuración indica que todas las líneas de la lista de materiales (L. MAT.) deben consumirse automáticamente cuando se recibe un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="25ae5-107">This setting indicates that all bill of materials (BOM) lines should automatically be consumed when a purchase order is received.</span></span> <span data-ttu-id="25ae5-108">Si el campo **Principio de vaciado** en las líneas de L. MAT. se establece explícitamente en *Manual*, es de esperar que las líneas de L. MAT. no se consuman automáticamente.</span><span class="sxs-lookup"><span data-stu-id="25ae5-108">If the **Flushing principle** field on BOM lines is explicitly set to *Manual*, you might expect that the BOM lines won't automatically be consumed.</span></span> <span data-ttu-id="25ae5-109">Sin embargo, cuando se produce este problema, las líneas de la L. MAT. donde el campo **Principio de vaciado** está configurado en *Manual* se consumen automáticamente de todos modos.</span><span class="sxs-lookup"><span data-stu-id="25ae5-109">However, when this issue occurs, BOM lines where the **Flushing principle** field is set to *Manual* are automatically consumed anyway.</span></span>

## <a name="resolution"></a><span data-ttu-id="25ae5-110">Resolución</span><span class="sxs-lookup"><span data-stu-id="25ae5-110">Resolution</span></span>

<span data-ttu-id="25ae5-111">Si tiene este problema, es posible que sus parámetros de control de producción estén configurados para invalidad el ajuste de **Principio de vaciado** en las líneas de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="25ae5-111">If you're experiencing this issue, your production control parameters might be set up to override the **Flushing principle** setting on BOM lines.</span></span> <span data-ttu-id="25ae5-112">En la página **Parámetros de control de producción**, en la pestaña **Actualización automática**, compruebe el valor del campo **Consumo automático de L. MAT**.</span><span class="sxs-lookup"><span data-stu-id="25ae5-112">On the **Production control parameters** page, on the **Automatic update** tab, check the value of the **Automatic BOM consumption** field.</span></span> <span data-ttu-id="25ae5-113">Si está configurado para *Siempre*, el sistema ignorará el ajuste de **Principio de vaciado** en todas las líneas de la L. MAT. y siempre vaciará las líneas.</span><span class="sxs-lookup"><span data-stu-id="25ae5-113">If it's set to *Always*, the system will disregard the **Flushing principle** setting on all BOM lines and will always flush the lines.</span></span> <span data-ttu-id="25ae5-114">Para que el sistema respete el ajuste de **Principio de vaciado** en las líneas de la L. MAT., cambie el valor del campo **Consumo automático de L. MAT** a *Principio de vaciado*.</span><span class="sxs-lookup"><span data-stu-id="25ae5-114">To make the system respect the **Flushing principle** setting on BOM lines, change the value of the **Automatic BOM consumption** field to *Flushing principle*.</span></span>
