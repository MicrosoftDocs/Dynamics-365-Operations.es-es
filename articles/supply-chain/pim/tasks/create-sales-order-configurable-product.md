---
title: Crear un pedido de ventas para un producto configurable
description: Este procedimiento muestra cómo se debe aplicar una plantilla de configuración a un producto en un pedido de ventas.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8607de5705354aa58c985fb536f3e1d52acd1f37
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921298"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a><span data-ttu-id="1f2f4-103">Crear un pedido de ventas para un producto configurable</span><span class="sxs-lookup"><span data-stu-id="1f2f4-103">Create a sales order for a configurable product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1f2f4-104">Este procedimiento muestra cómo se debe aplicar una plantilla de configuración a un producto en un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-104">This procedure shows how to apply a configuration template to a product on a sales order.</span></span> <span data-ttu-id="1f2f4-105">Este ejemplo usa el modelo de altavoz D0006 en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-105">This example uses the D0006 speaker model in the USMF demo data company.</span></span> <span data-ttu-id="1f2f4-106">Normalmente, un procesador del pedido de ventas utiliza este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-106">Typically, a sales order processor uses this procedure.</span></span>

## <a name="create-a-sales-order"></a><span data-ttu-id="1f2f4-107">Crear un pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="1f2f4-107">Create a sales order</span></span>

1. <span data-ttu-id="1f2f4-108">Vaya a **Ventas y marketing \> Espacios de trabajo \> Procesamiento y consulta de pedidos de venta**.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-108">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="1f2f4-109">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-109">Select **New**.</span></span>
1. <span data-ttu-id="1f2f4-110">Seleccione **Pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-110">Select **Sales order**.</span></span>
1. <span data-ttu-id="1f2f4-111">En el campo **Cuenta de cliente**, seleccione *US-001*.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-111">In the **Customer account** field, select *US-001*.</span></span> 
1. <span data-ttu-id="1f2f4-112">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-112">Select **OK**.</span></span>
1. <span data-ttu-id="1f2f4-113">En el campo **Código de artículo**, seleccione *D0006*.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-113">In the **Item number** field, select *D0006*.</span></span>
    * <span data-ttu-id="1f2f4-114">Para esta tarea, debe seleccionar un producto configurable.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-114">For this task, you must select a configurable product.</span></span>  
1. <span data-ttu-id="1f2f4-115">Seleccione **Producto y suministro**.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-115">Select **Product and supply**.</span></span>
1. <span data-ttu-id="1f2f4-116">Seleccione **Configurar línea**.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-116">Select **Configure line**.</span></span>
    * <span data-ttu-id="1f2f4-117">Tenga en cuenta que el precio ha cambiado, en función de la configuración seleccionada, y que ahora el campo **Incluir cable** se ha establecido como *Verdadero*.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-117">Note that the price has changed, based on the configuration that was selected, and that the **Include cable** field is now set to *True*.</span></span>  
    * <span data-ttu-id="1f2f4-118">Anote el precio predeterminado y la configuración que se selecciona para el cable.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-118">Note the default price and the settings that are selected for the cable.</span></span>  
1. <span data-ttu-id="1f2f4-119">Seleccione **Cargar plantilla**.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-119">Select **Load template**.</span></span>
    * <span data-ttu-id="1f2f4-120">Este ejemplo muestra cómo puede aplicar una plantilla para seleccionar una configuración predefinida.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-120">This example shows how you can apply a template to select a predefined configuration.</span></span> <span data-ttu-id="1f2f4-121">Si utiliza este procedimiento como una guía de la tarea y desea ver los otros valores de atributo que están disponibles, debe seleccionar el botón **Desbloquear**.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-121">If you're using this procedure as a task guide and want to see the other attribute values that are available, you must select the **Unlock** button.</span></span>  
1. <span data-ttu-id="1f2f4-122">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-122">Select **OK**.</span></span>
1. <span data-ttu-id="1f2f4-123">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-123">Select **OK**.</span></span>
1. <span data-ttu-id="1f2f4-124">Expanda la sección **Detalles de línea.**</span><span class="sxs-lookup"><span data-stu-id="1f2f4-124">Expand the **Line details** section.</span></span>
1. <span data-ttu-id="1f2f4-125">Seleccione la pestaña **Producto**.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-125">Select the **Product** tab.</span></span>
    * <span data-ttu-id="1f2f4-126">La configuración del artículo se enumera ahora bajo las dimensiones del producto.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-126">The configuration of the item is now listed under the product dimensions.</span></span>  
1. <span data-ttu-id="1f2f4-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1f2f4-127">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]