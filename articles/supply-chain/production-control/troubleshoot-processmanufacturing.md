---
title: Solucionar problemas de fabricación en procesos
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con fabricación de procesos.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 71ff5eeb2065a67281393777937d50237ab78d5e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259731"
---
# <a name="troubleshoot-process-manufacturing"></a><span data-ttu-id="d7a69-103">Solucionar problemas de fabricación en procesos</span><span class="sxs-lookup"><span data-stu-id="d7a69-103">Troubleshoot process manufacturing</span></span>

<span data-ttu-id="d7a69-104">Este tema describe cómo solucionar problemas que pueden surgir al trabajar con fabricación de procesos.</span><span class="sxs-lookup"><span data-stu-id="d7a69-104">This topic describes how to fix issues that you might encounter while you work with process manufacturing.</span></span>

## <a name="when-i-use-the-job-card-device-to-report-a-partial-quantity-on-the-last-job-in-a-production-order-all-the-previous-jobs-on-that-order-that-have-a-status-of-in-progress-are-automatically-ended"></a><span data-ttu-id="d7a69-105">Cuando utilizo el dispositivo de tarjeta de trabajo para informar una cantidad parcial en el último trabajo de una orden de producción, todos los trabajos anteriores de ese pedido que tienen el estado En curso se finalizan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d7a69-105">When I use the job card device to report a partial quantity on the last job in a production order, all the previous jobs on that order that have a status of In progress are automatically ended.</span></span>

<span data-ttu-id="d7a69-106">Este comportamiento se debe al diseño.</span><span class="sxs-lookup"><span data-stu-id="d7a69-106">This behavior is by design.</span></span> <span data-ttu-id="d7a69-107">Sobre la página **Valores predeterminados de órdenes de fabricación**, en la pestaña **Informar como terminado**, hay una opción que se llama **Ruta de la marca final**.</span><span class="sxs-lookup"><span data-stu-id="d7a69-107">On the **Production order defaults** page, on the **Report as finished** tab, there is an option that is named **End-mark route**.</span></span> <span data-ttu-id="d7a69-108">Si este tema se establece en *Sí*, se publica un diario de la tarjeta de ruta cuando un trabajador usa el dispositivo de tarjeta de trabajo o el terminal de tarjeta de trabajo para informar la última operación.</span><span class="sxs-lookup"><span data-stu-id="d7a69-108">If this topic is set to *Yes*, a route card journal is posted when a worker uses the job card device or job card terminal to report the last operation.</span></span> <span data-ttu-id="d7a69-109">Este diario marca todas las operaciones como completadas y finaliza todos los trabajos de producción.</span><span class="sxs-lookup"><span data-stu-id="d7a69-109">This journal marks all the operations as completed and ends all the production jobs.</span></span> <span data-ttu-id="d7a69-110">Cuando la opción **Ruta de la marca final** está configurada en *Sí*, el sistema no tiene en cuenta el estado del trabajo que el trabajador seleccionó cuando informó la última operación.</span><span class="sxs-lookup"><span data-stu-id="d7a69-110">When the **End-mark route** option is set to *Yes*, the system doesn't consider the job status that the worker selected when they reported the last operation.</span></span> <span data-ttu-id="d7a69-111">El sistema tampoco considera si el trabajador informa una cantidad total o parcial.</span><span class="sxs-lookup"><span data-stu-id="d7a69-111">The system also doesn't consider whether the worker is reporting a full or partial quantity.</span></span>

## <a name="when-i-attempt-a-stock-closing-i-receive-the-following-warning-message-no-execution-of-backflush-costing-calculation-with-a-date-1-matching-period-end-has-been-registered"></a><span data-ttu-id="d7a69-112">Cuando intento un cierre de existencias, recibo el siguiente mensaje de advertencia: "No se ha ejecutado el cálculo de costos de Backflush con una fecha %1 Se ha registrado el final del período coincidente ".</span><span class="sxs-lookup"><span data-stu-id="d7a69-112">When I attempt a stock closing, I receive the following warning message: "No execution of Backflush costing calculation with a date %1 matching period end has been registered."</span></span>

<span data-ttu-id="d7a69-113">En versiones anteriores a la versión 10.0.13, si no está utilizando el flujo de cálculo de costos de producción ajustada, recibirá el siguiente mensaje de advertencia erróneo durante el cierre del inventario:</span><span class="sxs-lookup"><span data-stu-id="d7a69-113">In releases before release 10.0.13, if you aren't using the lean production costing flow, you receive the following erroneous warning message during inventory closing:</span></span>

> <span data-ttu-id="d7a69-114">Está a punto de ejecutar un cierre de inventario con fecha %1.</span><span class="sxs-lookup"><span data-stu-id="d7a69-114">You are about to execute an Inventory close with a date %1.</span></span> <span data-ttu-id="d7a69-115">No se ha registrado ningún cálculo de contabilización previa de los costes con fecha %1 coincidente con el final del período.</span><span class="sxs-lookup"><span data-stu-id="d7a69-115">No execution of Backflush costing calculation with a date %1 matching period end has been registered.</span></span> <span data-ttu-id="d7a69-116">Recuerde ejecutar un cálculo de contabilización previa de los costes con fecha %1 coincidente con el final del período.</span><span class="sxs-lookup"><span data-stu-id="d7a69-116">Please remember to execute a Backflush costing calculation with a date of %1 matching period end.</span></span> <span data-ttu-id="d7a69-117">La valoración de los inventarios, el costo de los bienes vendidos y las variaciones podrían no ser correctas en el libro mayor auxiliar o en el libro mayor general hasta que se haya ejecutado.</span><span class="sxs-lookup"><span data-stu-id="d7a69-117">The valuation of inventories, cost of goods sold and variances might not be correct in Subledger or General ledger until this has been executed.</span></span>

<span data-ttu-id="d7a69-118">Este problema se ha solucionado en la versión 10.0.13 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="d7a69-118">This issue has been fixed in release 10.0.13 and later.</span></span> <span data-ttu-id="d7a69-119">Para obtener más información, consulte [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).</span><span class="sxs-lookup"><span data-stu-id="d7a69-119">For more information, see [KB 4582468](https://fix.lcs.dynamics.com/Issue/Details?kb=4582468&bugId=468844&dbType=3&qc=fcd64080446a27382cfde3e4c3bdcfb714279185932259cd11ceb0d500617296).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]