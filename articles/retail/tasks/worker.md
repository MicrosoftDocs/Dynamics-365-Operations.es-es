---
title: Configurar un trabajador
description: Este procedimiento demuestra cómo configurar a un trabajador comercial como representante de ventas, que sea apto comisión en ventas en PDV.
author: jblucher
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, HcmWorker
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 797640b487884fc487582addea274007e4ba7a7d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563629"
---
# <a name="configure-a-worker"></a><span data-ttu-id="e975a-103">Configurar un trabajador</span><span class="sxs-lookup"><span data-stu-id="e975a-103">Configure a worker</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="e975a-104">Este procedimiento demuestra cómo configurar a un trabajador comercial como representante de ventas, que sea apto comisión en ventas en PDV.</span><span class="sxs-lookup"><span data-stu-id="e975a-104">This procedure demonstrates how to configure a retail worker as a sales representative who is eligible for commission on sales in POS.</span></span> <span data-ttu-id="e975a-105">Este procedimiento usa la empresa de datos de demostración USRT.</span><span class="sxs-lookup"><span data-stu-id="e975a-105">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-commission-sales-group-for-the-worker"></a><span data-ttu-id="e975a-106">Crear un grupo de comisión de ventas para el trabajador</span><span class="sxs-lookup"><span data-stu-id="e975a-106">Create a commission sales group for the worker</span></span>
1. <span data-ttu-id="e975a-107">Vaya a Ventas y marketing > Comisiones > Grupos de ventas.</span><span class="sxs-lookup"><span data-stu-id="e975a-107">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="e975a-108">Se puede asignar trabajadores a uno o más grupos de ventas.</span><span class="sxs-lookup"><span data-stu-id="e975a-108">Workers can be assigned to one or more sales groups.</span></span> <span data-ttu-id="e975a-109">En PDV, puede elegir cualquier grupo de ventas que contenga trabajadores de la libreta de direcciones de la tienda.</span><span class="sxs-lookup"><span data-stu-id="e975a-109">In POS, you can choose any sales group that contains workers from the store's address book.</span></span>  
2. <span data-ttu-id="e975a-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="e975a-110">Click New.</span></span>
3. <span data-ttu-id="e975a-111">En el campo Grupo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e975a-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="e975a-112">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e975a-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="e975a-113">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e975a-113">Click Save.</span></span>
6. <span data-ttu-id="e975a-114">En el panel de acciones, haga clic en General.</span><span class="sxs-lookup"><span data-stu-id="e975a-114">On the Action Pane, click General.</span></span>
7. <span data-ttu-id="e975a-115">Haga clic en representante de Ventas.</span><span class="sxs-lookup"><span data-stu-id="e975a-115">Click Sales rep.</span></span>
    * <span data-ttu-id="e975a-116">Un grupo de ventas puede contener más de un trabajador.</span><span class="sxs-lookup"><span data-stu-id="e975a-116">A sales group can contain more than one worker.</span></span> <span data-ttu-id="e975a-117">Las comisiones pueden dividirse entre los trabajadores en función de cómo defina la proporción de la comisión.</span><span class="sxs-lookup"><span data-stu-id="e975a-117">Commissions can be split between workers based on how you define the commission share.</span></span>  
8. <span data-ttu-id="e975a-118">En el campo Nombre, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="e975a-118">In the Name field, enter or select a value.</span></span>
9. <span data-ttu-id="e975a-119">En el campo proporción de la Comisión, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="e975a-119">In the Commission share field, enter a number.</span></span>
10. <span data-ttu-id="e975a-120">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e975a-120">Click Save.</span></span>
11. <span data-ttu-id="e975a-121">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e975a-121">Close the page.</span></span>
12. <span data-ttu-id="e975a-122">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e975a-122">Close the page.</span></span>

## <a name="assign-the-workers-default-sales-group"></a><span data-ttu-id="e975a-123">Asignar el grupo de ventas predeterminado de trabajadores</span><span class="sxs-lookup"><span data-stu-id="e975a-123">Assign the workers default sales group</span></span>
1. <span data-ttu-id="e975a-124">Vaya a Venta minorista y comercio > Empleados > Trabajadores.</span><span class="sxs-lookup"><span data-stu-id="e975a-124">Go to Retail and commerce > Employees > Workers.</span></span>
2. <span data-ttu-id="e975a-125">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e975a-125">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="e975a-126">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e975a-126">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="e975a-127">Haga clic en la pestaña Comercial.</span><span class="sxs-lookup"><span data-stu-id="e975a-127">Click the Retail tab.</span></span>
    * <span data-ttu-id="e975a-128">Un trabajador puede asignarse a un grupo de ventas predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e975a-128">A worker can be assigned to a default sales group.</span></span> <span data-ttu-id="e975a-129">El grupo de ventas predeterminado se añadirá automáticamente a las líneas de ventas en PDV, si la opción está habilitada en el perfil de funcionalidad para la tienda.</span><span class="sxs-lookup"><span data-stu-id="e975a-129">The default sales group will be automatically added to sales lines in POS if the option is enabled in the functionality profile for the store.</span></span>  
5. <span data-ttu-id="e975a-130">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="e975a-130">Click Edit.</span></span>
6. <span data-ttu-id="e975a-131">En el campo Grupo predeterminado, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="e975a-131">In the Default group field, enter or select a value.</span></span>
7. <span data-ttu-id="e975a-132">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e975a-132">Click Save.</span></span>

