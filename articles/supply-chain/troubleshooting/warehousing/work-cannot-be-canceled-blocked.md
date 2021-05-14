---
title: El trabajo no se puede cancelar porque está bloqueado
description: El trabajo no se puede cancelar porque está bloqueado
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a7ab4c7263947767164702fb7dd6da7573175253
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924288"
---
# <a name="work-cant-be-canceled-because-its-blocked"></a><span data-ttu-id="a58f6-103">El trabajo no se puede cancelar porque está bloqueado</span><span class="sxs-lookup"><span data-stu-id="a58f6-103">Work can't be canceled because it's blocked</span></span>

<span data-ttu-id="a58f6-104">Código de error: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage</span><span class="sxs-lookup"><span data-stu-id="a58f6-104">Error code: WHSCancellationOfWorkBlockedByExecutingWave_ErrorMessage</span></span>

## <a name="symptoms"></a><span data-ttu-id="a58f6-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="a58f6-105">Symptoms</span></span>

<span data-ttu-id="a58f6-106">El sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="a58f6-106">The system shows the following error message:</span></span>

> <span data-ttu-id="a58f6-107">El trabajo %1 no se puede cancelar porque está bloqueado por el tipo de motivo %2.</span><span class="sxs-lookup"><span data-stu-id="a58f6-107">Work %1 cannot be cancelled because it is blocked by reason type %2.</span></span> <span data-ttu-id="a58f6-108">El trabajo debe desbloquearse para poderlo cancelar.</span><span class="sxs-lookup"><span data-stu-id="a58f6-108">The work must be unblocked before it can be cancelled.</span></span>

## <a name="cause"></a><span data-ttu-id="a58f6-109">Causa</span><span class="sxs-lookup"><span data-stu-id="a58f6-109">Cause</span></span>

<span data-ttu-id="a58f6-110">El trabajo está bloqueado y no se puede cancelar.</span><span class="sxs-lookup"><span data-stu-id="a58f6-110">The work is blocked and can't be canceled.</span></span>

<span data-ttu-id="a58f6-111">En la página **Trabajo**, en la pestaña **General**, la opción **Bloqueado** está configurada en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="a58f6-111">On the **Work** page, on the **General** tab, the **Blocked** option is set to *Yes*.</span></span> <span data-ttu-id="a58f6-112">Esta configuración indica que el trabajo está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="a58f6-112">This setting indicates that the work is blocked.</span></span> <span data-ttu-id="a58f6-113">La pestaña **Motivos de bloqueo** muestra por qué se bloqueó el trabajo.</span><span class="sxs-lookup"><span data-stu-id="a58f6-113">The **Blocking reasons** tab shows why the work was blocked.</span></span>

## <a name="resolution"></a><span data-ttu-id="a58f6-114">Resolución</span><span class="sxs-lookup"><span data-stu-id="a58f6-114">Resolution</span></span>

<span data-ttu-id="a58f6-115">Para desbloquear el trabajo, seleccione la pestaña **Motivos de bloqueo**, y luego siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a58f6-115">To unblock the work, select the **Blocking reasons** tab, and then follow one of these steps:</span></span>

- <span data-ttu-id="a58f6-116">Si el campo **Motivo de bloqueo del trabajo** está configurado en *Razón indefinida*: en el panel de acciones, en la pestaña **Trabajo**, en el grupo **Trabajo**, seleccione **Desbloquear trabajo**.</span><span class="sxs-lookup"><span data-stu-id="a58f6-116">If the **Work blocking reason** field is set to *Undefined reason*: On the Action Pane, on the **Work** tab, in the **Work** group, select **Unblock work**.</span></span>
- <span data-ttu-id="a58f6-117">Si el campo **Motivo de bloqueo del trabajo** está establecido en *Procesamiento de lanzamiento*: en el panel de acciones, en la pestaña **Información relacionada**, en el grupo **Información relacionada**, seleccione **Lanzamiento**.</span><span class="sxs-lookup"><span data-stu-id="a58f6-117">If the **Work blocking reason** field is set to *Processing wave*: On the Action Pane, on the **Related information** tab, in the **Related information** group, select **Wave**.</span></span> <span data-ttu-id="a58f6-118">Luego, en la página **Lanzamientos**, en el panel de acciones, en la pestaña **Lanzamiento**, en el grupo **Lanzamiento**, seleccione **Limpiar datos de lanzamiento**.</span><span class="sxs-lookup"><span data-stu-id="a58f6-118">Then, on the **Waves** page, on the Action Pane, on the **Wave** tab, in the **Wave** group, select **Cleanup wave data**.</span></span>

## <a name="workaround"></a><span data-ttu-id="a58f6-119">Solución alternativa</span><span class="sxs-lookup"><span data-stu-id="a58f6-119">Workaround</span></span>

<span data-ttu-id="a58f6-120">Si los pasos anteriores no solucionaron el problema, puede cancelar el trabajo siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a58f6-120">If the previous steps didn't fix the issue, you can cancel the work by following these steps.</span></span>

1. <span data-ttu-id="a58f6-121">Vaya a **Gestion de almacenes \> Tareas periódicas \> Limpiar \> Cancelar trabajo**.</span><span class="sxs-lookup"><span data-stu-id="a58f6-121">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="a58f6-122">En el campo **Id. de trabajo**, especifique el id. del trabajo que desea cancelar, y que actualmente tiene un valor de **Estado del trabajo** de *Abierto*, *En curso*, *Cancelado*, *Combinado* o *Cerrado*.</span><span class="sxs-lookup"><span data-stu-id="a58f6-122">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="a58f6-123">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a58f6-123">Select **OK**.</span></span>
1. <span data-ttu-id="a58f6-124">Seleccione **Sí** para confirmar que desea cancelar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="a58f6-124">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="a58f6-125">Para obtener más información, consulte [Cancelar trabajo de almacén para control de excepciones](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="a58f6-125">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
