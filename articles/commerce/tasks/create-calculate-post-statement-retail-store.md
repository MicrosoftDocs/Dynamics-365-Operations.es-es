---
title: Crear, calcular y registrar extractos para una tienda
description: En este tema se describen los pasos manuales para crear, calcular y registrar un extracto para un almacén.
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
ms.openlocfilehash: 3b26ea5c816339eef88bfdd9ac59701dcaa31fe4
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3023938"
---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a><span data-ttu-id="5ccc6-103">Crear, calcular y registrar extractos para una tienda</span><span class="sxs-lookup"><span data-stu-id="5ccc6-103">Create, calculate, and post statements for a retail store</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="5ccc6-104">En este tema se describen los pasos manuales para crear, calcular y registrar un extracto para un almacén.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-104">This topic describes the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="5ccc6-105">También hay trabajos por lotes que se pueden configurar para las mismas tareas.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="5ccc6-106">Los pasos para configurar y ejecutar los trabajos por lotes se pueden encontrar en otros temas.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="5ccc6-107">Para completar este procedimiento, debe tener transacciones que se completaron en PDV y después se incluyeron en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics 365 Commerce.</span></span> <span data-ttu-id="5ccc6-108">Este registro usa la empresa USRT en los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-108">This recording uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="5ccc6-109">Seleccione **Operaciones financieras de tienda** en la página principal.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-109">Select **Store financials** from the home page.</span></span>
2. <span data-ttu-id="5ccc6-110">Seleccione **Nuevo extracto**.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-110">Select **New statement**.</span></span>
3. <span data-ttu-id="5ccc6-111">En el campo **Número de tienda**, seleccione una opción en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-111">In the **Store number** field, select a option from the drop-down.</span></span>
4. <span data-ttu-id="5ccc6-112">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-112">Select **OK**.</span></span>
5. <span data-ttu-id="5ccc6-113">El grupo **Configuración** contiene la configuración que controla qué transacciones se incluyen en el extracto y cómo se agrupan en las líneas de extracto.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-113">The **Setup** group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="5ccc6-114">Puede abrir el grupo **Configuración** y cambiar estos ajustes, o puede usar los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-114">You can open the **Setup** group and change these settings, or you can use the defaults.</span></span>  
    - <span data-ttu-id="5ccc6-115">El campo **Método de extracto** define cómo se agruparán las líneas de extracto.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-115">The **Statement method** field defines how the statement lines will be grouped.</span></span>  
    - <span data-ttu-id="5ccc6-116">Seleccione un miembro del personal o un registro en el campo **Personal/registro** si desea calcular un extracto solo para el registro o el miembro del personal concretos.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-116">Select a staff member or a register in the **staff/register** field if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="5ccc6-117">En el campo **Método de cierre**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-117">In the **Closing method** field, select an option.</span></span>
7. <span data-ttu-id="5ccc6-118">Seleccione **Calcular extracto** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-118">Select **Calculate statement** from the Action Pane.</span></span>
8. <span data-ttu-id="5ccc6-119">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-119">Select **Yes**.</span></span>
    - <span data-ttu-id="5ccc6-120">Tras calcular el extracto, debe haber líneas creadas con importes totales para cada método de pago y el método de extracto que se usó.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-120">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    - <span data-ttu-id="5ccc6-121">Especifique un importe contado en cada línea si se necesita especificar o actualizar.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-121">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="5ccc6-122">El campo contado se rellena con importes de las declaraciones por forma de pago realizadas en PDV.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-122">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="5ccc6-123">Seleccione **Registrar extracto** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-123">Select **Post statement** from the Action Pane.</span></span>
10. <span data-ttu-id="5ccc6-124">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-124">Select **Close**.</span></span>
11. <span data-ttu-id="5ccc6-125">Cierre el panel.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-125">Close the pane.</span></span>
12. <span data-ttu-id="5ccc6-126">En la página principal, seleccione **Operaciones financieras de tienda**.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-126">At the home page, select **Store financials**.</span></span>
13. <span data-ttu-id="5ccc6-127">Seleccione la pestaña **Extractos registrados**.</span><span class="sxs-lookup"><span data-stu-id="5ccc6-127">Select the **Posted statements** tab.</span></span>

