---
title: Registro de ventas y pagos en línea
description: Este procedimiento le guía por la configuración y ejecución de un trabajo por lotes periódico para crear pedidos de ventas y pagos para transacciones de la tienda en línea.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13839bbe6ca03f3cfc7036fce87477bf7d5af2a7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "353503"
---
# <a name="posting-of-online-sales-and-payments"></a><span data-ttu-id="01748-103">Registro de ventas y pagos en línea</span><span class="sxs-lookup"><span data-stu-id="01748-103">Posting of online sales and payments</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="01748-104">Este procedimiento le guía por la configuración y ejecución de un trabajo por lotes periódico para crear pedidos de ventas y pagos para transacciones de la tienda en línea.</span><span class="sxs-lookup"><span data-stu-id="01748-104">This procedure walks through configuring and running a recurrent batch job to create sales orders and payments for online store transactions.</span></span> <span data-ttu-id="01748-105">Este procedimiento usa la empresa USRT en los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="01748-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="01748-106">Vaya a Todos los espacios de trabajo > Operaciones financieras de tienda.</span><span class="sxs-lookup"><span data-stu-id="01748-106">Go to All workspaces > Retail store financials.</span></span>
2. <span data-ttu-id="01748-107">Haga clic en Sincronizar pedidos.</span><span class="sxs-lookup"><span data-stu-id="01748-107">Click Synchronize orders.</span></span>
3. <span data-ttu-id="01748-108">En el campo Jerarquía organizativa, seleccione "Tiendas por región".</span><span class="sxs-lookup"><span data-stu-id="01748-108">In the Organization hierarchy field, select 'Retail Stores by Region'.</span></span>
    * <span data-ttu-id="01748-109">Seleccione una tienda en línea concreta o un nodo si desea crear el trabajo por lotes para un grupo de tiendas.</span><span class="sxs-lookup"><span data-stu-id="01748-109">Select either a specific online store, or select a node if you want to create the batch job for a group of stores.</span></span>  
    * <span data-ttu-id="01748-110">Haga clic en la flecha para agregar su selección.</span><span class="sxs-lookup"><span data-stu-id="01748-110">Click the arrow to add your selection.</span></span>  
4. <span data-ttu-id="01748-111">Haga clic en la ficha Ejecutar en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="01748-111">Click the Run in the background tab.</span></span>
5. <span data-ttu-id="01748-112">Active o desactive la casilla Procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="01748-112">Check or uncheck the Batch processing checkbox.</span></span>
6. <span data-ttu-id="01748-113">Haga clic en Periodicidad.</span><span class="sxs-lookup"><span data-stu-id="01748-113">Click Recurrence.</span></span>
7. <span data-ttu-id="01748-114">Seleccione la opción No hay fecha final.</span><span class="sxs-lookup"><span data-stu-id="01748-114">Select the No end date option.</span></span>
8. <span data-ttu-id="01748-115">En el campo Recuento, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="01748-115">In the Count field, enter a number.</span></span>
9. <span data-ttu-id="01748-116">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="01748-116">Click OK.</span></span>
10. <span data-ttu-id="01748-117">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="01748-117">Click OK.</span></span>

