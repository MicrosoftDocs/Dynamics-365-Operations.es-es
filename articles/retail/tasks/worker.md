--- 
title: Configurar trabajadores comerciales
description: "Este procedimiento demuestra cómo configurar a un trabajador comercial como representante de ventas, que sea apto comisión en ventas en PDV."
author: jblucher
manager: AnnBe
ms.date: 02/22/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: f583c421c2f6dfd019d9586cb7d14f3298127d94
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---
# <a name="configure-retail-workers"></a><span data-ttu-id="9dbba-103">Configurar trabajadores comerciales</span><span class="sxs-lookup"><span data-stu-id="9dbba-103">Configure retail workers</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="9dbba-104">Este procedimiento demuestra cómo configurar a un trabajador comercial como representante de ventas, que sea apto comisión en ventas en PDV.</span><span class="sxs-lookup"><span data-stu-id="9dbba-104">This procedure demonstrates how to configure a retail worker as a sales representative who is eligible for commission on sales in POS.</span></span> <span data-ttu-id="9dbba-105">Este procedimiento usa la empresa de datos de demostración USRT.</span><span class="sxs-lookup"><span data-stu-id="9dbba-105">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-commission-sales-group-for-the-worker"></a><span data-ttu-id="9dbba-106">Crear un grupo de comisión de ventas para el trabajador</span><span class="sxs-lookup"><span data-stu-id="9dbba-106">Create a commission sales group for the worker</span></span>
1. <span data-ttu-id="9dbba-107">Vaya a Ventas y marketing > Comisiones > Grupos de ventas.</span><span class="sxs-lookup"><span data-stu-id="9dbba-107">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="9dbba-108">Se puede asignar trabajadores a uno o más grupos de ventas.</span><span class="sxs-lookup"><span data-stu-id="9dbba-108">Workers can be assigned to one or more sales groups.</span></span> <span data-ttu-id="9dbba-109">En PDV, puede elegir cualquier grupo de ventas que contenga trabajadores de la libreta de direcciones de la tienda.</span><span class="sxs-lookup"><span data-stu-id="9dbba-109">In POS, you can choose any sales group that contains workers from the store's address book.</span></span>  
2. <span data-ttu-id="9dbba-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="9dbba-110">Click New.</span></span>
3. <span data-ttu-id="9dbba-111">En el campo Grupo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9dbba-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="9dbba-112">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9dbba-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="9dbba-113">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9dbba-113">Click Save.</span></span>
6. <span data-ttu-id="9dbba-114">En el panel de acciones, haga clic en General.</span><span class="sxs-lookup"><span data-stu-id="9dbba-114">On the Action Pane, click General.</span></span>
7. <span data-ttu-id="9dbba-115">Haga clic en representante de Ventas.</span><span class="sxs-lookup"><span data-stu-id="9dbba-115">Click Sales rep.</span></span>
    * <span data-ttu-id="9dbba-116">Un grupo de ventas puede contener más de un trabajador.</span><span class="sxs-lookup"><span data-stu-id="9dbba-116">A sales group can contain more than one worker.</span></span> <span data-ttu-id="9dbba-117">Las comisiones pueden dividirse entre los trabajadores en función de cómo defina la proporción de la comisión.</span><span class="sxs-lookup"><span data-stu-id="9dbba-117">Commissions can be split between workers based on how you define the commission share.</span></span>  
8. <span data-ttu-id="9dbba-118">En el campo Nombre, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="9dbba-118">In the Name field, enter or select a value.</span></span>
9. <span data-ttu-id="9dbba-119">En el campo proporción de la Comisión, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="9dbba-119">In the Commission share field, enter a number.</span></span>
10. <span data-ttu-id="9dbba-120">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9dbba-120">Click Save.</span></span>
11. <span data-ttu-id="9dbba-121">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9dbba-121">Close the page.</span></span>
12. <span data-ttu-id="9dbba-122">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9dbba-122">Close the page.</span></span>

## <a name="assign-the-workers-default-sales-group"></a><span data-ttu-id="9dbba-123">Asignar el grupo de ventas predeterminado de trabajadores</span><span class="sxs-lookup"><span data-stu-id="9dbba-123">Assign the workers default sales group</span></span>
1. <span data-ttu-id="9dbba-124">Vaya a Venta minorista y comercio > Empleados > Trabajadores.</span><span class="sxs-lookup"><span data-stu-id="9dbba-124">Go to Retail and commerce > Employees > Workers.</span></span>
2. <span data-ttu-id="9dbba-125">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="9dbba-125">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="9dbba-126">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9dbba-126">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="9dbba-127">Haga clic en la pestaña Comercial.</span><span class="sxs-lookup"><span data-stu-id="9dbba-127">Click the Retail tab.</span></span>
    * <span data-ttu-id="9dbba-128">Un trabajador puede asignarse a un grupo de ventas predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9dbba-128">A worker can be assigned to a default sales group.</span></span> <span data-ttu-id="9dbba-129">El grupo de ventas predeterminado se añadirá automáticamente a las líneas de ventas en PDV, si la opción está habilitada en el perfil de funcionalidad para la tienda.</span><span class="sxs-lookup"><span data-stu-id="9dbba-129">The default sales group will be automatically added to sales lines in POS if the option is enabled in the functionality profile for the store.</span></span>  
5. <span data-ttu-id="9dbba-130">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="9dbba-130">Click Edit.</span></span>
6. <span data-ttu-id="9dbba-131">En el campo Grupo predeterminado, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="9dbba-131">In the Default group field, enter or select a value.</span></span>
7. <span data-ttu-id="9dbba-132">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="9dbba-132">Click Save.</span></span>


