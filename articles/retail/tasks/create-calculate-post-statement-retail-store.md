---
title: Crear, calcular y registrar un extracto para una tienda
description: Este procedimiento le guía por los pasos manuales para crear, calcular y registrar un extracto para un almacén.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9ea30e7e008bfcce77a7ee2f4d7d01a6cf1ababc
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548333"
---
# <a name="create-calculate-and-post-a-statement-for-a-retail-store"></a><span data-ttu-id="f042c-103">Crear, calcular y registrar un extracto para una tienda</span><span class="sxs-lookup"><span data-stu-id="f042c-103">Create, calculate, and post a statement for a retail store</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="f042c-104">Este procedimiento le guía por los pasos manuales para crear, calcular y registrar un extracto para un almacén.</span><span class="sxs-lookup"><span data-stu-id="f042c-104">This procedure walks through the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="f042c-105">También hay trabajos por lotes que se pueden configurar para las mismas tareas.</span><span class="sxs-lookup"><span data-stu-id="f042c-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="f042c-106">Los pasos para configurar y ejecutar los trabajos por lotes se pueden encontrar en otros temas.</span><span class="sxs-lookup"><span data-stu-id="f042c-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="f042c-107">Para completar este procedimiento, debe tener transacciones que se completaron en PDV y después se incluyeron en Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="f042c-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics AX.</span></span> <span data-ttu-id="f042c-108">Este registro usa la empresa USRT en los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="f042c-108">This recording uses the USRT company in demo data.</span></span> <span data-ttu-id="f042c-109">Este procedimiento puede referirse a Microsoft Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="f042c-109">This procedure may refer to Microsoft Dynamics AX.</span></span> <span data-ttu-id="f042c-110">Tenga en cuenta que Dynamics AX ahora se denomina Microsoft Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="f042c-110">Please note that Dynamics AX is now called Microsoft Dynamics 365 for Operations.</span></span>

1. <span data-ttu-id="f042c-111">Vaya a Todos los espacios de trabajo > ..</span><span class="sxs-lookup"><span data-stu-id="f042c-111">Go to All workspaces > ..</span></span> <span data-ttu-id="f042c-112">> Operaciones financieras de tienda.</span><span class="sxs-lookup"><span data-stu-id="f042c-112">> Retail store financials.</span></span>
2. <span data-ttu-id="f042c-113">Haga clic en Nuevo extracto.</span><span class="sxs-lookup"><span data-stu-id="f042c-113">Click New statement.</span></span>
3. <span data-ttu-id="f042c-114">En el campo Número de tienda, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f042c-114">In the Store number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="f042c-115">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f042c-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="f042c-116">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f042c-116">Click OK.</span></span>
    * <span data-ttu-id="f042c-117">El grupo Configuración tiene la configuración que controla qué transacciones se incluyen en el extracto y cómo se agrupan en las líneas de extracto.</span><span class="sxs-lookup"><span data-stu-id="f042c-117">The Setup group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="f042c-118">Puede abrir el grupo de configuración y cambiar estos ajustes, o puede usar los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="f042c-118">You can open the Setup group and change these settings, or you can use the defaults.</span></span>  
    * <span data-ttu-id="f042c-119">El campo Método de extracto define cómo se agruparán las líneas de extracto.</span><span class="sxs-lookup"><span data-stu-id="f042c-119">The Statement method field defines how the statement lines will be grouped.</span></span>  
    * <span data-ttu-id="f042c-120">Seleccione un miembro del personal o un registro si desea calcular un extracto solo para el registro o el miembros del personal específico.</span><span class="sxs-lookup"><span data-stu-id="f042c-120">Select a staff member or a register if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="f042c-121">En el campo Método de cierre, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="f042c-121">In the Closing method field, select an option.</span></span>
7. <span data-ttu-id="f042c-122">Haga clic en Calcular extracto.</span><span class="sxs-lookup"><span data-stu-id="f042c-122">Click Calculate statement.</span></span>
8. <span data-ttu-id="f042c-123">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="f042c-123">Click Yes.</span></span>
    * <span data-ttu-id="f042c-124">Tras calcular el extracto, debe haber líneas creadas con importes totales para cada método de pago y el método de extracto que se usó.</span><span class="sxs-lookup"><span data-stu-id="f042c-124">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    * <span data-ttu-id="f042c-125">Especifique un importe contado en cada línea si se necesita especificar o actualizar.</span><span class="sxs-lookup"><span data-stu-id="f042c-125">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="f042c-126">El campo contado se rellena con importes de las declaraciones por forma de pago realizadas en PDV.</span><span class="sxs-lookup"><span data-stu-id="f042c-126">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="f042c-127">Haga clic en Registrar extracto.</span><span class="sxs-lookup"><span data-stu-id="f042c-127">Click Post statement.</span></span>
10. <span data-ttu-id="f042c-128">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="f042c-128">Click Close.</span></span>
11. <span data-ttu-id="f042c-129">Vaya a Venta minorista y comercio > Canales > Operaciones financieras de tienda.</span><span class="sxs-lookup"><span data-stu-id="f042c-129">Go to Retail and commerce > Channels > Retail store financials.</span></span>
12. <span data-ttu-id="f042c-130">Haga clic en la ficha Extractos registrados.</span><span class="sxs-lookup"><span data-stu-id="f042c-130">Click the Posted statements tab.</span></span>

