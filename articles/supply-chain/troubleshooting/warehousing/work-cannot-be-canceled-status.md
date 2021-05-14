---
title: El trabajo no se puede cancelar debido a su estado
description: El trabajo no se puede cancelar debido a su estado
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
ms.openlocfilehash: 60b4da44ca5e6790302e0797640317cef8493db7
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924264"
---
# <a name="work-cant-be-canceled-because-of-its-status"></a><span data-ttu-id="15a25-103">El trabajo no se puede cancelar debido a su estado</span><span class="sxs-lookup"><span data-stu-id="15a25-103">Work can't be canceled because of its status</span></span>

<span data-ttu-id="15a25-104">Código de error: WAX2190</span><span class="sxs-lookup"><span data-stu-id="15a25-104">Error code: WAX2190</span></span>

## <a name="symptoms"></a><span data-ttu-id="15a25-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="15a25-105">Symptoms</span></span>

<span data-ttu-id="15a25-106">El sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="15a25-106">The system shows the following error message:</span></span>

> <span data-ttu-id="15a25-107">No se puede cancelar el trabajo %1 porque su estado es %2.</span><span class="sxs-lookup"><span data-stu-id="15a25-107">You cannot cancel work %1 because it has a status of %2.</span></span>

## <a name="cause"></a><span data-ttu-id="15a25-108">Causa</span><span class="sxs-lookup"><span data-stu-id="15a25-108">Cause</span></span>

<span data-ttu-id="15a25-109">El trabajo no se puede cancelar en su estado actual.</span><span class="sxs-lookup"><span data-stu-id="15a25-109">The work can't be canceled in its current state.</span></span>

<span data-ttu-id="15a25-110">El encabezado del trabajo o las líneas del trabajo no tienen el valor de **Estado del trabajo** esperado.</span><span class="sxs-lookup"><span data-stu-id="15a25-110">The work header or work lines don't have the expected **Work status** value.</span></span> <span data-ttu-id="15a25-111">El campo **Estado del trabajo** del encabezado del trabajo no está configurado como *Abierto* ni como *En curso*.</span><span class="sxs-lookup"><span data-stu-id="15a25-111">The **Work status** field on the work header isn't set to *Open* or *In progress*.</span></span>

## <a name="resolution"></a><span data-ttu-id="15a25-112">Resolución</span><span class="sxs-lookup"><span data-stu-id="15a25-112">Resolution</span></span>

<span data-ttu-id="15a25-113">Para cancelar el trabajo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="15a25-113">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="15a25-114">Vaya a **Gestion de almacenes \> Tareas periódicas \> Limpiar \> Cancelar trabajo**.</span><span class="sxs-lookup"><span data-stu-id="15a25-114">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="15a25-115">En el campo **Id. de trabajo**, especifique el id. del trabajo que desea cancelar.</span><span class="sxs-lookup"><span data-stu-id="15a25-115">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="15a25-116">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="15a25-116">Select **OK**.</span></span>
1. <span data-ttu-id="15a25-117">Seleccione **Sí** para confirmar que desea cancelar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="15a25-117">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="15a25-118">Para obtener más información, consulte [Cancelar trabajo de almacén para control de excepciones](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="15a25-118">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
