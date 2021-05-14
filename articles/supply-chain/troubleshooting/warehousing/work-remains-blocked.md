---
title: El trabajo permanece bloqueado
description: El trabajo permanece bloqueado
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTableListPage_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f85364d1ecfadc36b26c3395ab4402d3cb3b1603
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924139"
---
# <a name="work-remains-blocked"></a><span data-ttu-id="445dc-103">El trabajo permanece bloqueado</span><span class="sxs-lookup"><span data-stu-id="445dc-103">Work remains blocked</span></span>

<span data-ttu-id="445dc-104">Código de error: WHSWorkBlockingExecutingWaveReason_ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="445dc-104">Error code: WHSWorkBlockingExecutingWaveReason_ErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="445dc-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="445dc-105">Symptoms</span></span>

<span data-ttu-id="445dc-106">El sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="445dc-106">The system shows the following error message:</span></span>

> <span data-ttu-id="445dc-107">El trabajo %1 permanece bloqueado porque el lanzamiento relacionado %2 tiene el estado %3.</span><span class="sxs-lookup"><span data-stu-id="445dc-107">Work %1 remains blocked because the related wave %2 has status %3.</span></span>

## <a name="cause"></a><span data-ttu-id="445dc-108">Causa</span><span class="sxs-lookup"><span data-stu-id="445dc-108">Cause</span></span>

<span data-ttu-id="445dc-109">El trabajo se está procesando actualmente en un lanzamiento y no puede desbloquearse, como lo indica una de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="445dc-109">The work is currently being processed on a wave and can't be unblocked, as indicated by one of the following conditions:</span></span>

- <span data-ttu-id="445dc-110">En la pestaña **Motivos de bloqueo** el campo **Motivo de bloqueo del trabajo** para una o más líneas está establecido en *Lanzamiento de procesamiento*.</span><span class="sxs-lookup"><span data-stu-id="445dc-110">On the **Blocking reasons** tab, the **Work blocking reason** field for one or more lines is set to *Processing wave*.</span></span>
- <span data-ttu-id="445dc-111">Cuando selecciona **Lanzamiento** en el grupo **Información relacionada** de la pestaña **Información relacionada** del panel de acciones, el campo **Estado de lanzamiento** se establece en *Procesamiento*.</span><span class="sxs-lookup"><span data-stu-id="445dc-111">When you select **Wave** in the **Related information** group on the **Related information** tab of the Action Pane, the **Wave status** field is set to *Processing*.</span></span>

## <a name="resolution"></a><span data-ttu-id="445dc-112">Resolución</span><span class="sxs-lookup"><span data-stu-id="445dc-112">Resolution</span></span>

<span data-ttu-id="445dc-113">En el panel de acciones, en la ficha **Información relacionada** del grupo **Información relacionada**, seleccione **Lanzamiento**.</span><span class="sxs-lookup"><span data-stu-id="445dc-113">On the Action Pane, on the **Related information** tab, in the **Related information** group, select **Wave**.</span></span> <span data-ttu-id="445dc-114">Luego, en la página **Lanzamientos**, en el panel de acciones, en la pestaña **Lanzamiento**, en el grupo **Lanzamiento**, seleccione **Limpiar datos de lanzamiento**.</span><span class="sxs-lookup"><span data-stu-id="445dc-114">Then, on the **Waves** page, on the Action Pane, on the **Wave** tab, in the **Wave** group, select **Cleanup wave data**.</span></span>

## <a name="workaround"></a><span data-ttu-id="445dc-115">Solución alternativa</span><span class="sxs-lookup"><span data-stu-id="445dc-115">Workaround</span></span>

<span data-ttu-id="445dc-116">Si los pasos anteriores no solucionaron el problema, puede cancelar el trabajo siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="445dc-116">If the previous steps didn't fix the issue, you can cancel the work by following these steps.</span></span>

1. <span data-ttu-id="445dc-117">Vaya a **Gestion de almacenes \> Tareas periódicas \> Limpiar \> Cancelar trabajo**.</span><span class="sxs-lookup"><span data-stu-id="445dc-117">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="445dc-118">En el campo **Id. de trabajo**, especifique el id. del trabajo que desea cancelar, y que actualmente tiene un valor de **Estado del trabajo** de *Abierto*, *En curso*, *Cancelado*, *Combinado* o *Cerrado*.</span><span class="sxs-lookup"><span data-stu-id="445dc-118">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="445dc-119">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="445dc-119">Select **OK**.</span></span>
1. <span data-ttu-id="445dc-120">Seleccione **Sí** para confirmar que desea cancelar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="445dc-120">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="445dc-121">Para obtener más información, consulte [Cancelar trabajo de almacén para control de excepciones](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="445dc-121">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
