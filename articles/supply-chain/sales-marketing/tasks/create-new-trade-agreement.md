---
title: Crear un nuevo acuerdo comercial
description: Este procedimiento muestra cómo crear un acuerdo comercial por el que se registra un nuevo precio de venta acordado con un cliente específico.
author: omulvad
manager: tfehr
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1642da7b06363d1f704e51276b5cb36823707231
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383439"
---
# <a name="create-a-new-trade-agreement"></a><span data-ttu-id="5382e-103">Crear un nuevo acuerdo comercial</span><span class="sxs-lookup"><span data-stu-id="5382e-103">Create a new trade agreement</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5382e-104">Este procedimiento muestra cómo crear un acuerdo comercial por el que se registra un nuevo precio de venta acordado con un cliente específico.</span><span class="sxs-lookup"><span data-stu-id="5382e-104">This procedure shows you how to create a trade agreement where you register a new product sales price that you've agreed with a specific customer.</span></span> <span data-ttu-id="5382e-105">Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="5382e-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="5382e-106">Si utiliza sus propios datos, antes de comenzar este procedimiento deberá asegurarse de que exista un nombre de diario de acuerdo comercial en el que la relación predeterminada esté establecida en "Precio (ventas)".</span><span class="sxs-lookup"><span data-stu-id="5382e-106">If you're using your own data, before you start this guide you need to make sure that a Trade agreement journal name exists where the Default relation is set to "Price (sales)".</span></span>


## <a name="create-and-post-a-new-trade-agreement-journal"></a><span data-ttu-id="5382e-107">Creación y registro de un diario de acuerdos comerciales nuevos</span><span class="sxs-lookup"><span data-stu-id="5382e-107">Create and post a new trade agreement journal</span></span>
1. <span data-ttu-id="5382e-108">Vaya a **Panel de navegación > Módulos > Ventas y marketing > Precios y descuentos > Diarios de acuerdos comerciales**.</span><span class="sxs-lookup"><span data-stu-id="5382e-108">Go to **Navigation pane > Modules > Sales and marketing > Prices and discounts > Trade agreement journals**.</span></span>
2. <span data-ttu-id="5382e-109">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5382e-109">Click **New**.</span></span>
3. <span data-ttu-id="5382e-110">En el campo **Nombre**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5382e-110">In the **Name** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="5382e-111">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="5382e-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="5382e-112">En **Panel Acciones**, haga clic en **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="5382e-112">On **Action Pane**, click **Lines**.</span></span>
6. <span data-ttu-id="5382e-113">En el campo **Código de cuenta**, seleccione 'Tabla'.</span><span class="sxs-lookup"><span data-stu-id="5382e-113">In the **Account code** field, select 'Table'.</span></span>
    
    <span data-ttu-id="5382e-114">En este ejemplo, va a actualizar el precio para un cliente específico, por lo que tiene que elegir Tabla.</span><span class="sxs-lookup"><span data-stu-id="5382e-114">In this example, you're updating the price for a specific customer, which means you need to choose Table.</span></span> <span data-ttu-id="5382e-115">Si fuera a actualizar el precio de lista del producto, seleccionaría 'Todo', de modo que el nuevo precio fuera válido para todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="5382e-115">If you were updating the product's list price, you would select 'All', so that the new price is valid for all customers.</span></span> <span data-ttu-id="5382e-116">Si fuera a diferenciar precios entre distintos segmentos de cliente, seleccionaría Grupo.</span><span class="sxs-lookup"><span data-stu-id="5382e-116">If you were differentiating prices among different customer segments, then you would select Group.</span></span> <span data-ttu-id="5382e-117">Para seleccionar Grupo debe haber configurado grupos de precios de cliente.</span><span class="sxs-lookup"><span data-stu-id="5382e-117">To select Group, you must have set up Customer price groups.</span></span>  

7. <span data-ttu-id="5382e-118">En el campo **Selección de cuentas**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5382e-118">In the **Account selection** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="5382e-119">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="5382e-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="5382e-120">En el campo **Código de artículo**, seleccione 'Tabla'.</span><span class="sxs-lookup"><span data-stu-id="5382e-120">In the **Item code** field, select 'Table'.</span></span>
    
    <span data-ttu-id="5382e-121">Al introducir un acuerdo comercial del tipo 'Precio (ventas)', solo se debe seleccionar Tabla en el campo **Código de artículo**.</span><span class="sxs-lookup"><span data-stu-id="5382e-121">When you are entering a trade agreement of type 'Price (sales)', you must only select 'Table' in the **Item code** field.</span></span> <span data-ttu-id="5382e-122">Esto es así porque un precio es un valor absoluto, y no puede ser el mismo para todos los productos o un grupo de productos.</span><span class="sxs-lookup"><span data-stu-id="5382e-122">This is because a price is an absolute value and cannot be same for all products or a group of products.</span></span>
    
10. <span data-ttu-id="5382e-123">En el campo **Relación de artículos**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5382e-123">In the **Item relation** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="5382e-124">En la lista, seleccione el producto que desee incluir en el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="5382e-124">In the list, select the product you want to include in the agreement.</span></span> <span data-ttu-id="5382e-125">Anote el producto que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5382e-125">Make a note of which product you've selected.</span></span>  
12. <span data-ttu-id="5382e-126">Especifique una cantidad mínima en el campo **Desde**.</span><span class="sxs-lookup"><span data-stu-id="5382e-126">In the **From** field, enter a minimum quantity.</span></span>
    - <span data-ttu-id="5382e-127">Si el cliente tiene que pedir una cantidad mínima para poder optar al nuevo precio, deberá especificar la cantidad aquí.</span><span class="sxs-lookup"><span data-stu-id="5382e-127">If the customer has to order a minimum quantity before they can qualify for the new price, then you need to specify that quantity here.</span></span>  
    - <span data-ttu-id="5382e-128">Especifique un valor en el campo **Hasta** para especificar la cantidad máxima por encima de la cual no será válido el precio del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="5382e-128">Enter a value in the **To** field to specify the maximum quantity above which the agreement's price will not be valid.</span></span> <span data-ttu-id="5382e-129">Si ofrece precios y descuentos según distintas cantidades por niveles, especifique cada segmento de cantidad como par de cantidades mínima y máxima en los campos **Desde** y **Hasta**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5382e-129">If you offer prices and discounts based on multiple quantity breaks, then specify each quantity bracket as a pair of minimum and maximum quantity in the **From** and **To** fields respectively.</span></span>
13. <span data-ttu-id="5382e-130">En el **campo Importe en divisa**, escriba un precio.</span><span class="sxs-lookup"><span data-stu-id="5382e-130">In the **Amount in currency field**, enter a price.</span></span>
14. <span data-ttu-id="5382e-131">En la sección **Detalles**, en el campo **Fecha inicial**, especifique una fecha desde la cual será válido este acuerdo.</span><span class="sxs-lookup"><span data-stu-id="5382e-131">Under the **Details** section, in the **From date** field, enter a date from which this agreement will be valid.</span></span>
15. <span data-ttu-id="5382e-132">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5382e-132">Click **Save**.</span></span>
16. <span data-ttu-id="5382e-133">Hacer clic en **Validar**.</span><span class="sxs-lookup"><span data-stu-id="5382e-133">Click **Validate**.</span></span>
17. <span data-ttu-id="5382e-134">Haga clic en **Validar las líneas seleccionadas**.</span><span class="sxs-lookup"><span data-stu-id="5382e-134">Click **Validate selected lines**.</span></span>
18. <span data-ttu-id="5382e-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5382e-135">Click **OK**.</span></span>
19. <span data-ttu-id="5382e-136">Haga clic en **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="5382e-136">Click **Post**.</span></span>
20. <span data-ttu-id="5382e-137">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5382e-137">Click **OK**.</span></span>

## <a name="view-trade-agreements-for-a-product"></a><span data-ttu-id="5382e-138">Visualización de acuerdos comerciales para un producto</span><span class="sxs-lookup"><span data-stu-id="5382e-138">View trade agreements for a product</span></span>
1. <span data-ttu-id="5382e-139">Vaya a **Panel de navegación > Módulos > Gestión de información de productos > Productos > Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="5382e-139">Go to **Navigation pane > Modules > Product information management > Products > Released products**.</span></span>
2. <span data-ttu-id="5382e-140">En la lista, busque y seleccione el producto cuyo precio acaba de actualizar.</span><span class="sxs-lookup"><span data-stu-id="5382e-140">In the list, find and select the product whose price you have just updated.</span></span>
3. <span data-ttu-id="5382e-141">En **Panel de acciones**, haga clic en **Vender**.</span><span class="sxs-lookup"><span data-stu-id="5382e-141">On the **Action Pane**, click **Sell**.</span></span>
4. <span data-ttu-id="5382e-142">Haga clic en **Ver acuerdos comerciales**</span><span class="sxs-lookup"><span data-stu-id="5382e-142">Click **View trade agreements**.</span></span>
    
    <span data-ttu-id="5382e-143">Revise los detalles del acuerdo comercial de precios que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="5382e-143">Review the details of the price trade agreement you have just created.</span></span>    

5. <span data-ttu-id="5382e-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5382e-144">Close the page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5382e-145">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5382e-145">Additional resources</span></span>
### <a name="community-blogs"></a><span data-ttu-id="5382e-146">Blogs de la comunidad</span><span class="sxs-lookup"><span data-stu-id="5382e-146">Community blogs</span></span>
- [<span data-ttu-id="5382e-147">Precios de ventas en Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="5382e-147">Sales prices in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/11/14/sales-prices-in-dynamics-365-for-finance-and-operations/#sales_price_in_trade_agreements)
