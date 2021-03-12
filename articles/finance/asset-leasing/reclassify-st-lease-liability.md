---
title: Reclasificar la parte a corto plazo de un pasivo por arrendamiento
description: Este tema explica cómo crear un movimiento de diario mensual para reclasificar una parte del pasivo por arrendamiento como a corto plazo.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 08ca824bb4c4a02a80f2187fb5f8fe4e8b7327c9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992923"
---
# <a name="reclassify-the-short-term-portion-of-lease-liability"></a><span data-ttu-id="9c002-103">Reclasificar la parte a corto plazo de un pasivo por arrendamiento</span><span class="sxs-lookup"><span data-stu-id="9c002-103">Reclassify the short-term portion of lease liability</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c002-104">Este tema explica cómo crear un movimiento de diario mensual para reclasificar una parte del pasivo por arrendamiento como a corto plazo.</span><span class="sxs-lookup"><span data-stu-id="9c002-104">This topic explains how to create a monthly journal entry to reclassify a portion of the lease liability as short-term.</span></span> <span data-ttu-id="9c002-105">Cuando la programación que se selecciona en el proceso por lotes es **Reclasificación del pasivo por arrendamiento a corto plazo**, se crea un movimiento de diario.</span><span class="sxs-lookup"><span data-stu-id="9c002-105">When the schedule that is selected in the batch process is **Short-term lease liability reclass**, a journal entry is created.</span></span> <span data-ttu-id="9c002-106">Esta entrada se utiliza para contabilizar la parte actual del pasivo por arrendamiento el último día del mes.</span><span class="sxs-lookup"><span data-stu-id="9c002-106">This entry is used to post the current portion of the lease liability on the last day of the month.</span></span> <span data-ttu-id="9c002-107">Al mismo tiempo, se registra una entrada de reversión a partir del primer día del mes siguiente.</span><span class="sxs-lookup"><span data-stu-id="9c002-107">At the same time, a reversal entry is posted as of the first day of the next month.</span></span>

<span data-ttu-id="9c002-108">La parte a corto plazo del pasivo por arrendamiento se muestra en el programa de amortización de pasivos.</span><span class="sxs-lookup"><span data-stu-id="9c002-108">The short-term portion of the lease liability is shown on the liability amortization schedule.</span></span> <span data-ttu-id="9c002-109">Cuando se registra el movimiento del diario, la columna **Diario de reclasificación de pasivos creado** está disponible y el id. de diario también se completa en la programación.</span><span class="sxs-lookup"><span data-stu-id="9c002-109">When the journal entry is posted, the **Liability reclass journal created** column becomes available, and the journal ID is also filled in on the schedule.</span></span>

<span data-ttu-id="9c002-110">Para crear y contabilizar el movimiento de diario de reclasificación de pasivos a corto plazo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9c002-110">To create and post the short-term liability reclassification journal entry, follow these steps.</span></span>

1. <span data-ttu-id="9c002-111">Vaya a **Arrendamiento de activos \> Periódico \> Creación de diario de lotes**.</span><span class="sxs-lookup"><span data-stu-id="9c002-111">Go to **Asset leasing \> Periodic \> Batch journal creation**.</span></span>
2. <span data-ttu-id="9c002-112">En el cuadro de diálogo **Creación de diario de lotes**, en el campo **Seleccionar programación**, seleccione **Reclasificación del pasivo por arrendamiento a corto plazo**.</span><span class="sxs-lookup"><span data-stu-id="9c002-112">In the **Batch journal creation** dialog box, in the **Select schedule** field, select **Short-term lease liability reclass**.</span></span>
3. <span data-ttu-id="9c002-113">En el campo **Grupo de arrendamientos**, seleccione un grupo de arrendamientos.</span><span class="sxs-lookup"><span data-stu-id="9c002-113">In the **Lease group** field, select a lease group.</span></span> <span data-ttu-id="9c002-114">Alternativamente, en el campo **Id. del libro**, seleccione el id. del libro.</span><span class="sxs-lookup"><span data-stu-id="9c002-114">Alternatively, in the **Book ID** field, select the book ID.</span></span>
4. <span data-ttu-id="9c002-115">Active el parámetro **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="9c002-115">Turn on the **Post** parameter.</span></span> <span data-ttu-id="9c002-116">Alternativamente, si la entrada debe crearse pero no publicarse, deje este parámetro desactivado.</span><span class="sxs-lookup"><span data-stu-id="9c002-116">Alternatively, if the entry should be created but not posted, leave this parameter turned off.</span></span>
5. <span data-ttu-id="9c002-117">Active el parámetro **Vista previa antes de registrar** para ver la entrada antes de que se registre.</span><span class="sxs-lookup"><span data-stu-id="9c002-117">Turn on the **Preview before posting** parameter to view the entry before it's posted.</span></span>
6. <span data-ttu-id="9c002-118">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9c002-118">Select **OK**.</span></span>
