---
title: La última línea de trabajo cerrada debe ser una colocación
description: La última línea de trabajo cerrada debe ser una colocación
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel, WHSWorkTableListPage_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a5b78154b51252b3ac96ba28c254e823caf87019
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924384"
---
# <a name="the-last-closed-work-line-must-be-a-put"></a><span data-ttu-id="ff228-103">La última línea de trabajo cerrada debe ser una colocación</span><span class="sxs-lookup"><span data-stu-id="ff228-103">The last closed work line must be a put</span></span>

<span data-ttu-id="ff228-104">Código de error: WAX1285</span><span class="sxs-lookup"><span data-stu-id="ff228-104">Error code: WAX1285</span></span>

## <a name="symptoms"></a><span data-ttu-id="ff228-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="ff228-105">Symptoms</span></span>

<span data-ttu-id="ff228-106">El sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="ff228-106">The system shows the following error message:</span></span>

> <span data-ttu-id="ff228-107">La última línea de trabajo cerrada debe ser una colocación.</span><span class="sxs-lookup"><span data-stu-id="ff228-107">The last closed work line must be a put.</span></span>

## <a name="cause"></a><span data-ttu-id="ff228-108">Causa</span><span class="sxs-lookup"><span data-stu-id="ff228-108">Cause</span></span>

<span data-ttu-id="ff228-109">El trabajo no se puede cancelar en su estado actual.</span><span class="sxs-lookup"><span data-stu-id="ff228-109">The work can't be canceled in its current state.</span></span>

<span data-ttu-id="ff228-110">En la última línea de trabajo, el campo **Estado de trabajo** está configurado en *Cerrado*, pero el campo **Tipo de trabajo** no está configurado en *Colocar*.</span><span class="sxs-lookup"><span data-stu-id="ff228-110">On the last work line, the **Work status** field is set to *Closed*, but the **Work type** field isn't set to *Put*.</span></span>

## <a name="resolution"></a><span data-ttu-id="ff228-111">Resolución</span><span class="sxs-lookup"><span data-stu-id="ff228-111">Resolution</span></span>

<span data-ttu-id="ff228-112">Para cancelar el trabajo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ff228-112">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="ff228-113">Vaya a **Gestion de almacenes \> Tareas periódicas \> Limpiar \> Cancelar trabajo**.</span><span class="sxs-lookup"><span data-stu-id="ff228-113">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="ff228-114">En el campo **Id. de trabajo**, especifique el id. del trabajo que desea cancelar.</span><span class="sxs-lookup"><span data-stu-id="ff228-114">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="ff228-115">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff228-115">Select **OK**.</span></span>
1. <span data-ttu-id="ff228-116">Seleccione **Sí** para confirmar que desea cancelar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="ff228-116">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="ff228-117">Para obtener más información, consulte [Cancelar trabajo de almacén para control de excepciones](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="ff228-117">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
