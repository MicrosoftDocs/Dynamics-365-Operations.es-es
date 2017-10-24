---
title: "Cerrar la contabilidad general al final del período"
description: "En este tema se describen las tareas que se completan normalmente al realizar un cierre de período para la contabilidad general."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 16acadf0b814ff5863873280cd8d6e6ddbdcffc8
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="close-the-general-ledger-at-period-end"></a><span data-ttu-id="5b77f-103">Cerrar la contabilidad general al final del período</span><span class="sxs-lookup"><span data-stu-id="5b77f-103">Close the general ledger at period end</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="5b77f-104">En este tema se describen las tareas que se completan normalmente al realizar un cierre de período para la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="5b77f-104">This topic describes the tasks that are typically completed when performing a period closing for General ledger.</span></span> 

<span data-ttu-id="5b77f-105">En Contabilidad general, puede completar los procedimientos de cierre de un período o un año.</span><span class="sxs-lookup"><span data-stu-id="5b77f-105">In General ledger, you can complete closing procedures for a period or a year.</span></span> <span data-ttu-id="5b77f-106">El cierre de procesos prepara al sistema para un período nuevo.</span><span class="sxs-lookup"><span data-stu-id="5b77f-106">Closing processes prepare the system for a new period.</span></span> <span data-ttu-id="5b77f-107">Para preparar el sistema para un año nuevo, debe ejecutar el proceso de cierre de ejercicio.</span><span class="sxs-lookup"><span data-stu-id="5b77f-107">To prepare the system for a new year, you must run the year end close process.</span></span> <span data-ttu-id="5b77f-108">Cada organización tiene diferentes procesos y pasos que realiza para el final de un período.</span><span class="sxs-lookup"><span data-stu-id="5b77f-108">Each organization has different processes and steps that it performs for the end of a period.</span></span> <span data-ttu-id="5b77f-109">A continuación se indican algunos pasos opcionales para finales de períodos:</span><span class="sxs-lookup"><span data-stu-id="5b77f-109">Here are some optional steps for period ends:</span></span>

-   <span data-ttu-id="5b77f-110">Completar todas las tareas para todos los demás módulos, como Clientes, Proveedores e Inventario.</span><span class="sxs-lookup"><span data-stu-id="5b77f-110">Complete all the tasks for all other modules, such as Accounts receivable, Accounts payable, and Inventory.</span></span>
-   <span data-ttu-id="5b77f-111">Comprobar que se registran todos los diarios.</span><span class="sxs-lookup"><span data-stu-id="5b77f-111">Verify that all journals are posted.</span></span>
-   <span data-ttu-id="5b77f-112">Ejecutar la revalorización de divisa extranjera para generar beneficios no realizados o importes de pérdidas.</span><span class="sxs-lookup"><span data-stu-id="5b77f-112">Run foreign currency revaluation to generate any unrealized gain or loss amounts.</span></span>
-   <span data-ttu-id="5b77f-113">Liquidar transacciones para cuenta contable.</span><span class="sxs-lookup"><span data-stu-id="5b77f-113">Settle transactions for each ledger account.</span></span>
-   <span data-ttu-id="5b77f-114">Procesar cualquier asignación obligatoria.</span><span class="sxs-lookup"><span data-stu-id="5b77f-114">Process any required allocations.</span></span>
-   <span data-ttu-id="5b77f-115">Registrar manualmente ajustes de fin de período.</span><span class="sxs-lookup"><span data-stu-id="5b77f-115">Manually post period-end adjustments.</span></span>
-   <span data-ttu-id="5b77f-116">Registrar transacciones en el diario y revisar el informe del **Diario contable**.</span><span class="sxs-lookup"><span data-stu-id="5b77f-116">Journalize transactions, and review the **Ledger journal** report.</span></span>
-   <span data-ttu-id="5b77f-117">Realizar una consolidación mediante una empresa de consolidación o informes financieros.</span><span class="sxs-lookup"><span data-stu-id="5b77f-117">Perform a consolidation by using a consolidation company or Financial reporting.</span></span>
-   <span data-ttu-id="5b77f-118">Generar resultados financieros de final de período con Informes financieros.</span><span class="sxs-lookup"><span data-stu-id="5b77f-118">Generate period-end financial statements by using Financial reporting.</span></span>
-   <span data-ttu-id="5b77f-119">Definir períodos contables en **En espera**, de modo que no se produzca ningún otro registro.</span><span class="sxs-lookup"><span data-stu-id="5b77f-119">Set ledger periods to **On hold**, so that no further posting occurs.</span></span> <span data-ttu-id="5b77f-120">También puede restringir un período a un grupo de usuarios específico mientras se estén produciendo actividades de final de período, para un mayor control.</span><span class="sxs-lookup"><span data-stu-id="5b77f-120">You can also restrict a period to a specific user group while period-end activities are occurring, for better control.</span></span> <span data-ttu-id="5b77f-121">No es buena idea establecer períodos en **Cerrado de forma permanente** porque no se puede volver a abrir un período que se ha cerrado.</span><span class="sxs-lookup"><span data-stu-id="5b77f-121">It's not a good idea to set periods to **Permanently closed**, because you can't reopen a period that has been closed.</span></span>

<span data-ttu-id="5b77f-122">El espacio de trabajo de cierre del período financiero se puede usar para organizar y seguir las tareas necesarias para varios procesos de cierre del ejercicio.</span><span class="sxs-lookup"><span data-stu-id="5b77f-122">The Financial period close workspace can be used to organize and track the tasks required for various period end processes.</span></span> 


<span data-ttu-id="5b77f-123">Para obtener más información, vea los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="5b77f-123">For more information, see the following topics for more information:</span></span>
- [<span data-ttu-id="5b77f-124">Espacio de trabajo de cierre del período financiero</span><span class="sxs-lookup"><span data-stu-id="5b77f-124">Financial period close workspace</span></span>](financial-period-close-workspace.md) 
- [<span data-ttu-id="5b77f-125">Cierre de fin de año</span><span class="sxs-lookup"><span data-stu-id="5b77f-125">Year end close</span></span>](Year-end-close.md)  
- [<span data-ttu-id="5b77f-126">Cierre masivo de período financiero</span><span class="sxs-lookup"><span data-stu-id="5b77f-126">Mass financial period close</span></span>](tasks/mass-financial-period-close.md)





