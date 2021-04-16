---
title: Registrar artículos habilitados para almacenamiento avanzado mediante un diario de recepción de artículos
description: Este tema presenta un escenario que muestra cómo registrar artículos mediante el diario de recepción de artículos cuando se usa los procesos avanzados de gestión de almacenes.
author: ShylaThompson
ms.date: 03/24/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c58aa1cec6c0bfe33fa1ef90267dcd8ac1218157
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830843"
---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a><span data-ttu-id="b7821-103">Registrar artículos habilitados para almacenamiento avanzado mediante un diario de recepción de artículos</span><span class="sxs-lookup"><span data-stu-id="b7821-103">Register items for an advanced warehousing enabled item using an item arrival journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b7821-104">Este tema presenta un escenario que muestra cómo registrar artículos mediante el diario de recepción de artículos cuando se usa los procesos avanzados de gestión de almacenes.</span><span class="sxs-lookup"><span data-stu-id="b7821-104">This topic presents a scenario that shows how to register items using the item arrival journal when you are using advanced warehouse management processes.</span></span> <span data-ttu-id="b7821-105">Esto lo realiza normalmente un empleado de recepción.</span><span class="sxs-lookup"><span data-stu-id="b7821-105">This would usually be done by a receiving clerk.</span></span>

## <a name="enable-sample-data"></a><span data-ttu-id="b7821-106">Habilitar datos de muestra</span><span class="sxs-lookup"><span data-stu-id="b7821-106">Enable sample data</span></span>

<span data-ttu-id="b7821-107">Para trabajar en este escenario utilizando los registros de muestra y los valores especificados en este tema, debe utilizar un sistema en el que estén instalados los datos de demostración estándar y debe seleccionar la entidad jurídica *USMF* antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="b7821-107">To work through this scenario using the sample records and values specified in this topic, you must be using a system where the standard demo data is installed, and you must select the *USMF* legal entity before you begin.</span></span>

<span data-ttu-id="b7821-108">En su lugar, puede trabajar en este escenario sustituyendo valores de sus propios datos siempre que tenga los siguientes datos disponibles:</span><span class="sxs-lookup"><span data-stu-id="b7821-108">You can instead work through this scenario by substituting values from your own data provided that you have the following data available:</span></span>

- <span data-ttu-id="b7821-109">Debe tener un pedido de compra confirmada con una línea de pedido de compra abierta.</span><span class="sxs-lookup"><span data-stu-id="b7821-109">You must have a confirmed purchase order with an open purchase order line.</span></span>
- <span data-ttu-id="b7821-110">El artículo de la línea debe mantenerse en existencias.</span><span class="sxs-lookup"><span data-stu-id="b7821-110">The item on the line must be stocked.</span></span> <span data-ttu-id="b7821-111">No debe utilizar variantes de producto y no debe tener dimensiones de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b7821-111">It must not use product variants, and must not have tracking dimensions.</span></span>
- <span data-ttu-id="b7821-112">El artículo debe estar asociado con un grupo de dimensiones de almacenamiento habilitado con proceso de gestión de almacenes.</span><span class="sxs-lookup"><span data-stu-id="b7821-112">The item must be associated with a storage dimension group that has warehouse management process enabled.</span></span>
- <span data-ttu-id="b7821-113">El almacén que se usa debe estar habilitado para los procesos de gestión de almacén y la ubicación que usa para recepción debe controlada por matrículas de entidad de almacén.</span><span class="sxs-lookup"><span data-stu-id="b7821-113">The warehouse that's used must be enabled for warehouse management processes and the location that you use for receiving must be license plate controlled.</span></span>

## <a name="create-an-item-arrival-journal-header-that-uses-warehouse-management"></a><span data-ttu-id="b7821-114">Cree un encabezado de diario de llegada de artículos que utilice la gestión de almacén</span><span class="sxs-lookup"><span data-stu-id="b7821-114">Create an item arrival journal header that uses warehouse management</span></span>

<span data-ttu-id="b7821-115">El siguiente escenario muestra cómo crear un encabezado de diario de llegada de artículos que utiliza la gestión de almacén:</span><span class="sxs-lookup"><span data-stu-id="b7821-115">The following scenario shows how to create an item arrival journal header that uses warehouse management:</span></span>

1. <span data-ttu-id="b7821-116">Asegúrese de que su sistema contenga un pedido de compra confirmada que cumpla con los requisitos descritos en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="b7821-116">Make sure your system contains a confirmed purchase order that fulfils the requirements outlined in the previous section.</span></span> <span data-ttu-id="b7821-117">Este escenario utiliza una orden de compra para la empresa *USMF*, cuenta de proveedor *1001*, almacén *51*, con una línea de pedido para *10 PL* (10 palets) del número de artículo *M9200*.</span><span class="sxs-lookup"><span data-stu-id="b7821-117">This scenario uses a purchase order for company *USMF*, vendor account *1001*, warehouse *51*, with an order line for *10 PL* (10 pallets) of item number *M9200*.</span></span>
1. <span data-ttu-id="b7821-118">Anote el número del pedido de compra que usará.</span><span class="sxs-lookup"><span data-stu-id="b7821-118">Make a note of the purchase order number that you will use.</span></span>
1. <span data-ttu-id="b7821-119">Vaya a **Gestión del inventario \> Movimientos de diario \> Recepción de artículos \> Recepción de artículos**.</span><span class="sxs-lookup"><span data-stu-id="b7821-119">Go to **Inventory management \> Journal entries \> Item arrival \> Item arrival**.</span></span>
1. <span data-ttu-id="b7821-120">En el panel Acciones, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b7821-120">Select **New** on the Action Pane.</span></span>
1. <span data-ttu-id="b7821-121">El cuadro de diálogo **Crear diario de administración de almacén** se abre.</span><span class="sxs-lookup"><span data-stu-id="b7821-121">The **Create warehouse management journal** dialog box opens.</span></span> <span data-ttu-id="b7821-122">Seleccione un nombre de diario en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="b7821-122">Select a journal name in the **Name** field.</span></span>
    - <span data-ttu-id="b7821-123">Si va a utilizar los datos de demostración de la empresa *USMF*, seleccione *WHS*.</span><span class="sxs-lookup"><span data-stu-id="b7821-123">If you are using *USMF* sample data, select *WHS*.</span></span>
    - <span data-ttu-id="b7821-124">Si está utilizando sus propios datos, el diario que elija debe tener **Verificar ubicación de picking** establecido en *No* y **Gestión de cuarentena** establecido en *No*.</span><span class="sxs-lookup"><span data-stu-id="b7821-124">If you're using your own data, the journal you choose must have **Check picking location** set to *No* and **Quarantine management** set to *No*.</span></span>
1. <span data-ttu-id="b7821-125">Establezca **Referencia** a *Pedido de compra*.</span><span class="sxs-lookup"><span data-stu-id="b7821-125">Set **Reference** to *Purchase order*.</span></span>
1. <span data-ttu-id="b7821-126">Establezca **Número de cuenta** en *1001*.</span><span class="sxs-lookup"><span data-stu-id="b7821-126">Set **Account number** to *1001*.</span></span>
1. <span data-ttu-id="b7821-127">Establezca **Número** al número del pedido de compra que identificó para este ejercicio.</span><span class="sxs-lookup"><span data-stu-id="b7821-127">Set **Number** to the number of the purchase order that you identified for this exercise.</span></span>

    <span data-ttu-id="b7821-128">![Diario de recepción de artículos](../media/item-arrival-journal-header.png "Diario de recepción de artículos")</span><span class="sxs-lookup"><span data-stu-id="b7821-128">![Item arrival journal](../media/item-arrival-journal-header.png "Item arrival journal")</span></span>

1. <span data-ttu-id="b7821-129">Seleccione **Aceptar** para crear el encabezado del diario.</span><span class="sxs-lookup"><span data-stu-id="b7821-129">Select the **OK** to create the journal header.</span></span>
1. <span data-ttu-id="b7821-130">En la sección **Líneas de diario**, seleccione **Agregar línea** e introduzca los siguientes datos:</span><span class="sxs-lookup"><span data-stu-id="b7821-130">In the **Journal lines** section, select **Add line** and enter the following data:</span></span>
    - <span data-ttu-id="b7821-131">Establezca **Número de artículo** en *M9200*.</span><span class="sxs-lookup"><span data-stu-id="b7821-131">**Item number** – Set to *M9200*.</span></span> <span data-ttu-id="b7821-132">El **Sitio**, **Almacén**, y **Cantidad** se configurarán en función de los datos de la transacción de inventario para los 10 palés (1000 c / u).</span><span class="sxs-lookup"><span data-stu-id="b7821-132">The **Site**, **Warehouse**, and **Quantity** will get set based on the inventory transaction data for the 10 pallets (1000 ea.).</span></span>
    - <span data-ttu-id="b7821-133">**Ubicación**: establecida en *001*.</span><span class="sxs-lookup"><span data-stu-id="b7821-133">**Location** – Set to  *001*.</span></span> <span data-ttu-id="b7821-134">Esta ubicación específica no rastrea las matrículas.</span><span class="sxs-lookup"><span data-stu-id="b7821-134">This specific location does not track license plates.</span></span>

    <span data-ttu-id="b7821-135">![Línea de diario de recepción de artículos](../media/item-arrival-journal-line.png "Línea de diario de recepción de artículos")</span><span class="sxs-lookup"><span data-stu-id="b7821-135">![Item arrival journal line](../media/item-arrival-journal-line.png "Item arrival journal line")</span></span>

    > [!NOTE]
    > <span data-ttu-id="b7821-136">El campo **Fecha** determina la fecha en la que la cantidad disponible del artículo se registrará en el inventario.</span><span class="sxs-lookup"><span data-stu-id="b7821-136">The **Date** field determines the date on which the on-hand quantity of this item will be registered in the inventory.</span></span>  
    >
    > <span data-ttu-id="b7821-137">El sistema rellenará el **Identificador de lote** si se puede identificar de forma exclusiva con la información proporcionada.</span><span class="sxs-lookup"><span data-stu-id="b7821-137">The **Lot ID** will be populated by the system if it can be uniquely identified from the information provided.</span></span> <span data-ttu-id="b7821-138">De lo contrario, tendrá que introducir esto manualmente.</span><span class="sxs-lookup"><span data-stu-id="b7821-138">Otherwise you will have to enter this manually.</span></span> <span data-ttu-id="b7821-139">Esto es un campo obligatorio, que vincula este registro a una línea de documento de origen específica.</span><span class="sxs-lookup"><span data-stu-id="b7821-139">This is a required field, which links this registration to a specific source document line.</span></span>  

1. <span data-ttu-id="b7821-140">En el panel de acciones, seleccione **Validar**.</span><span class="sxs-lookup"><span data-stu-id="b7821-140">Select **Validate** on the Action Pane.</span></span> <span data-ttu-id="b7821-141">Esto comprueba que el diario está listo para registrarse.</span><span class="sxs-lookup"><span data-stu-id="b7821-141">This checks that the journal is ready to be posted.</span></span> <span data-ttu-id="b7821-142">Si se produce un error en la validación, tendrá que corregir los errores para poder registrar el diario.</span><span class="sxs-lookup"><span data-stu-id="b7821-142">If the validation fails you will need to fix the errors before you can post the journal.</span></span>  
1. <span data-ttu-id="b7821-143">El cuadro de diálogo **Comprobar diario** se abre.</span><span class="sxs-lookup"><span data-stu-id="b7821-143">The **Check journal** dialog box opens.</span></span> <span data-ttu-id="b7821-144">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b7821-144">Select **OK**.</span></span>
1. <span data-ttu-id="b7821-145">Revisar la barra de mensajes.</span><span class="sxs-lookup"><span data-stu-id="b7821-145">Review the message bar.</span></span> <span data-ttu-id="b7821-146">Debe haber un mensaje que indica que se ha completado la operación.</span><span class="sxs-lookup"><span data-stu-id="b7821-146">There should be a message denoting that the operation was completed.</span></span>  
1. <span data-ttu-id="b7821-147">En el panel de acciones, seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="b7821-147">Select **Post** on the Action Pane.</span></span>
1. <span data-ttu-id="b7821-148">El cuadro de diálogo **Registrar diario** se abre.</span><span class="sxs-lookup"><span data-stu-id="b7821-148">The **Post journal** dialog box opens.</span></span> <span data-ttu-id="b7821-149">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b7821-149">Select **OK**.</span></span>
1. <span data-ttu-id="b7821-150">Revisar la barra de mensajes.</span><span class="sxs-lookup"><span data-stu-id="b7821-150">Review the message bar.</span></span> <span data-ttu-id="b7821-151">Debe haber mensajes que indican que se ha completado la operación.</span><span class="sxs-lookup"><span data-stu-id="b7821-151">There should be messages denoting that the operation completed.</span></span>
1. <span data-ttu-id="b7821-152">Seleccione **Funciones > Recibo de producto** en el Panel de acciones para actualizar la línea del pedido de compra y publicar un recibo de producto.</span><span class="sxs-lookup"><span data-stu-id="b7821-152">Select **Functions > Product receipt** on the Action Pane to update the purchase order line and post a product receipt.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
