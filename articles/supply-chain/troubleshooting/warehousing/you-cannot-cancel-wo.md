---
title: No puede cancelar el trabajo de un usuario
description: No puede cancelar el trabajo de un usuario
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
ms.openlocfilehash: e5f6912cfb1d5be8e46b7989856af99f8a611c11
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924410"
---
# <a name="you-cant-cancel-work-that-is-on-a-user"></a><span data-ttu-id="1a985-103">No puede cancelar el trabajo de un usuario</span><span class="sxs-lookup"><span data-stu-id="1a985-103">You can't cancel work that is on a user</span></span>

<span data-ttu-id="1a985-104">Código de error: WAX708</span><span class="sxs-lookup"><span data-stu-id="1a985-104">Error code: WAX708</span></span>

## <a name="symptoms"></a><span data-ttu-id="1a985-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="1a985-105">Symptoms</span></span>

<span data-ttu-id="1a985-106">El sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="1a985-106">The system shows the following error message:</span></span>

> <span data-ttu-id="1a985-107">No se puede cancelar el trabajo asignado a un usuario.</span><span class="sxs-lookup"><span data-stu-id="1a985-107">You cannot cancel work that is on a user.</span></span>

## <a name="cause"></a><span data-ttu-id="1a985-108">Causa</span><span class="sxs-lookup"><span data-stu-id="1a985-108">Cause</span></span>

<span data-ttu-id="1a985-109">El trabajo está bloqueado por un usuario y no se puede cancelar.</span><span class="sxs-lookup"><span data-stu-id="1a985-109">The work is locked by a user and can't be canceled.</span></span> <span data-ttu-id="1a985-110">Para confirmar esto, abra el id. de trabajo y luego abra la pestaña **General**. Si el trabajo está bloqueado, el campo **Situación laboral** se establecerá en *En curso*, y el campo **Bloqueado por** se establecerá en un id. de usuario.</span><span class="sxs-lookup"><span data-stu-id="1a985-110">To confirm this, open the work ID and then open the **General** tab. If the work is locked, the **Work status** field will be set to *In progress*, and the **Locked by** field will be set to a user ID.</span></span>

## <a name="resolution"></a><span data-ttu-id="1a985-111">Resolución</span><span class="sxs-lookup"><span data-stu-id="1a985-111">Resolution</span></span>

<span data-ttu-id="1a985-112">Para cancelar el trabajo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1a985-112">To cancel the work, follow these steps.</span></span>

1. <span data-ttu-id="1a985-113">Vaya a **Gestion de almacenes \> Tareas periódicas \> Limpiar \> Cancelar trabajo**.</span><span class="sxs-lookup"><span data-stu-id="1a985-113">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="1a985-114">En el campo **Id. de trabajo**, especifique el id. del trabajo que desea cancelar.</span><span class="sxs-lookup"><span data-stu-id="1a985-114">In the **Work ID** field, specify the ID of the work that you want to cancel.</span></span>
1. <span data-ttu-id="1a985-115">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1a985-115">Select **OK**.</span></span>
1. <span data-ttu-id="1a985-116">Seleccione **Sí** para confirmar que desea cancelar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="1a985-116">Select **Yes** to confirm that you want to cancel the work.</span></span>

<span data-ttu-id="1a985-117">Para obtener más información, consulte [Cancelar trabajo de almacén para control de excepciones](../../warehousing/cancel-warehouse-work.md).</span><span class="sxs-lookup"><span data-stu-id="1a985-117">For more information, see [Cancel warehouse work for exception handling](../../warehousing/cancel-warehouse-work.md).</span></span>
