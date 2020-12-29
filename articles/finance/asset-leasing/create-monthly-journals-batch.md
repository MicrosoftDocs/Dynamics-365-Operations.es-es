---
title: Crear movimientos de diario mensuales en lote
description: Este tema explica cómo crear asientos de diario en un lote para ayudar a aumentar la eficiencia cuando se registran los gastos de arrendamiento mensuales.
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
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a2293f6bd3ce66832996652c3bfca0fc4bc73782
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "4447802"
---
# <a name="create-monthly-journal-entries-in-a-batch"></a><span data-ttu-id="959d3-103">Crear movimientos de diario mensuales en lote</span><span class="sxs-lookup"><span data-stu-id="959d3-103">Create monthly journal entries in a batch</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="959d3-104">Este tema explica cómo crear asientos de diario en un lote para ayudar a aumentar la eficiencia cuando se registran los gastos de arrendamiento mensuales.</span><span class="sxs-lookup"><span data-stu-id="959d3-104">This topic explains how to create journal entries in a batch to help increase efficiency when monthly lease expenses are recorded.</span></span> <span data-ttu-id="959d3-105">El procesamiento por lotes se puede utilizar para crear asientos de diario a partir de múltiples programaciones.</span><span class="sxs-lookup"><span data-stu-id="959d3-105">Batch processing can be used to create journal entries from multiple schedules.</span></span> <span data-ttu-id="959d3-106">Estos asientos de diario pueden incluir pagos de arrendamientos, amortización de pasivos, amortización de activos por derecho de uso (ROU) y gastos a cargo del arrendatario en un arrendamiento de capital.</span><span class="sxs-lookup"><span data-stu-id="959d3-106">These journal entries can include lease payments, liability amortization, right-of-use (ROU) asset amortization, and executory cost expenses.</span></span> <span data-ttu-id="959d3-107">También puede utilizar el procesamiento por lotes para realizar el reconocimiento inicial de varios arrendamientos al mismo tiempo o para crear ajustes de transición para varios arrendamientos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="959d3-107">You can also use batch processing to do the initial recognition of multiple leases at the same time, or to create transition adjustments for multiple leases at the same time.</span></span>

<span data-ttu-id="959d3-108">Para configurar un trabajo por lotes o procesar facturas de pago, depreciación o intereses para varios arrendamientos, vaya a **Arrendamiento de activos \> Periódico \> Creación de diario por lotes**.</span><span class="sxs-lookup"><span data-stu-id="959d3-108">To set up a batch job, or to process payment invoices, depreciation, or interest for multiple leases, go to **Asset leasing \> Periodic \> Batch journal creation**.</span></span> <span data-ttu-id="959d3-109">En el cuadro de diálogo que aparece, puede seleccionar la programación desde la que se deben crear las entradas del diario.</span><span class="sxs-lookup"><span data-stu-id="959d3-109">In the dialog box that appears, you can select the schedule that the journal entries should be created from.</span></span> <span data-ttu-id="959d3-110">También puede especificar si el proceso por lotes debe ejecutarse para entidades, grupos de arrendamiento o libros de arrendamiento específicos.</span><span class="sxs-lookup"><span data-stu-id="959d3-110">You can also specify whether the batch process should be run for specific entities, lease groups, or lease books.</span></span>

> [!NOTE]
> <span data-ttu-id="959d3-111">Las transacciones posteriores, como los programas de amortización de pasivos, los pagos, la depreciación y los gastos, se contabilizarán solo después de que se registre el reconocimiento inicial de los arrendamientos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="959d3-111">Subsequent transactions, such as liability amortization schedules, payments, depreciation, and expenses, will be posted only after the initial recognition for corresponding leases is posted.</span></span>
>
> <span data-ttu-id="959d3-112">Se crean las entradas del diario, pero no se contabilizarán hasta que seleccione el comando **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="959d3-112">The journal entries are created, but they won't be posted until you select the **Run** command.</span></span>
