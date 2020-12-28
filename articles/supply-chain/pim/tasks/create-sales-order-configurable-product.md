---
title: Crear un pedido de ventas para un producto configurable
description: Este procedimiento muestra cómo se debe aplicar una plantilla de configuración a un producto en un pedido de ventas.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 988d87757019d20dcaf675af925166ed376685f5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436845"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a><span data-ttu-id="1dc9f-103">Crear un pedido de ventas para un producto configurable</span><span class="sxs-lookup"><span data-stu-id="1dc9f-103">Create a sales order for a configurable product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1dc9f-104">Este procedimiento muestra cómo se debe aplicar una plantilla de configuración a un producto en un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-104">This procedure shows how to apply a configuration template to a product on a sales order.</span></span> <span data-ttu-id="1dc9f-105">Este ejemplo usa el modelo de altavoz D0006 en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-105">This example uses the D0006 speaker model in the USMF demo data company.</span></span> <span data-ttu-id="1dc9f-106">Normalmente, un procesador del pedido de ventas utiliza este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-106">Typically, a sales order processor uses this procedure.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="1dc9f-107">Crear un pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="1dc9f-107">Create a sales order</span></span>
1. <span data-ttu-id="1dc9f-108">Haga clic en Consulta y procesamiento de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-108">Click Sales order processing and inquiry.</span></span>
2. <span data-ttu-id="1dc9f-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-109">Click New.</span></span>
3. <span data-ttu-id="1dc9f-110">Haga clic en Pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-110">Click Sales order.</span></span>
4. <span data-ttu-id="1dc9f-111">En el campo Cuenta de cliente, seleccione US-001.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-111">In the Customer account field, select US-001.</span></span> 
5. <span data-ttu-id="1dc9f-112">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="1dc9f-112">Click OK.</span></span>
6. <span data-ttu-id="1dc9f-113">En el campo Código de artículo, seleccione D0006.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-113">In the Item number field, select D0006.</span></span>
    * <span data-ttu-id="1dc9f-114">Para esta tarea, debe seleccionar un producto configurable.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-114">For this task, you must select a configurable product.</span></span>  
7. <span data-ttu-id="1dc9f-115">Haga clic en Producto y suministro.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-115">Click Product and supply.</span></span>
8. <span data-ttu-id="1dc9f-116">Haga clic en Configurar la línea.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-116">Click Configure line.</span></span>
    * <span data-ttu-id="1dc9f-117">Tenga en cuenta que el precio ha cambiado, en función de la configuración seleccionada, y que ahora el campo Incluir cable se ha establecido como Verdadero.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-117">Note that the price has changed, based on the configuration that was selected, and that the Include cable field is now set to True.</span></span>  
    * <span data-ttu-id="1dc9f-118">Anote el precio predeterminado y la configuración que se selecciona para el cable.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-118">Note the default price and the settings that are selected for the cable.</span></span>  
9. <span data-ttu-id="1dc9f-119">Haga clic en Cargar plantilla.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-119">Click Load template.</span></span>
    * <span data-ttu-id="1dc9f-120">Este ejemplo muestra cómo puede aplicar una plantilla para seleccionar una configuración predefinida.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-120">This example shows how you can apply a template to select a predefined configuration.</span></span> <span data-ttu-id="1dc9f-121">Si utiliza este procedimiento como una guía de la tarea y desea ver los otros valores de atributo que están disponibles, debe hacer clic en el botón Desbloquear.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-121">If you're using this procedure as a task guide and want to see the other attribute values that are available, you must click the Unlock button.</span></span>  
10. <span data-ttu-id="1dc9f-122">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="1dc9f-122">Click OK.</span></span>
11. <span data-ttu-id="1dc9f-123">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="1dc9f-123">Click OK.</span></span>
12. <span data-ttu-id="1dc9f-124">Expanda la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-124">Expand the Line details section.</span></span>
13. <span data-ttu-id="1dc9f-125">Haga clic en la ficha Producto.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-125">Click the Product tab.</span></span>
    * <span data-ttu-id="1dc9f-126">La configuración del artículo se enumera ahora bajo las dimensiones del producto.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-126">The configuration of the item is now listed under the product dimensions.</span></span>  
14. <span data-ttu-id="1dc9f-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1dc9f-127">Close the page.</span></span>

## <a name="select-the-product-configuration"></a><span data-ttu-id="1dc9f-128">Seleccione la configuración del producto</span><span class="sxs-lookup"><span data-stu-id="1dc9f-128">Select the product configuration</span></span>

