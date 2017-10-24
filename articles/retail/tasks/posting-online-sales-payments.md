--- 
title: "Registrar ventas y pagos en línea"
description: "Este procedimiento le guía por la configuración y ejecución de un trabajo por lotes periódico para crear pedidos de ventas y pagos para transacciones de la tienda en línea."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e8c3f861a53a3f5c2de29248523ff4efd5e1d072
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="post-online-sales-and-payments"></a><span data-ttu-id="5e2fd-103">Registrar ventas y pagos en línea</span><span class="sxs-lookup"><span data-stu-id="5e2fd-103">Post online sales and payments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="5e2fd-104">Este procedimiento le guía por la configuración y ejecución de un trabajo por lotes periódico para crear pedidos de ventas y pagos para transacciones de la tienda en línea.</span><span class="sxs-lookup"><span data-stu-id="5e2fd-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="5e2fd-105">Este procedimiento usa la empresa USRT en los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="5e2fd-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="5e2fd-106">Vaya a Todos los espacios de trabajo > Operaciones financieras de tienda.</span><span class="sxs-lookup"><span data-stu-id="5e2fd-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="5e2fd-107">Haga clic en Sincronizar pedidos.</span><span class="sxs-lookup"><span data-stu-id="5e2fd-107">Click Synchronize orders.</span></span>
3. <span data-ttu-id="5e2fd-108">En el campo Jerarquía organizativa, seleccione "Tiendas por región".</span><span class="sxs-lookup"><span data-stu-id="5e2fd-108">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="5e2fd-109">Seleccione una tienda en línea concreta o un nodo si desea crear el trabajo por lotes para un grupo de tiendas.</span><span class="sxs-lookup"><span data-stu-id="5e2fd-109">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="5e2fd-110">Haga clic en la flecha para agregar su selección.</span><span class="sxs-lookup"><span data-stu-id="5e2fd-110">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="5e2fd-111">Haga clic en la ficha Ejecutar en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="5e2fd-111">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="5e2fd-112">Active o desactive la casilla Procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="5e2fd-112">Check or uncheck the Batch processing checkbox.</span></span>
6. <span data-ttu-id="5e2fd-113">Haga clic en Periodicidad.</span><span class="sxs-lookup"><span data-stu-id="5e2fd-113">Click Recurrence.</span></span>
7. <span data-ttu-id="5e2fd-114">Seleccione la opción No hay fecha final.</span><span class="sxs-lookup"><span data-stu-id="5e2fd-114">Select the No end date option.</span></span>
8. <span data-ttu-id="5e2fd-115">En el campo Recuento, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="5e2fd-115">In the Count field, enter a number.</span></span>
9. <span data-ttu-id="5e2fd-116">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="5e2fd-116">Click OK.</span></span>
10. <span data-ttu-id="5e2fd-117">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="5e2fd-117">Click OK.</span></span>


