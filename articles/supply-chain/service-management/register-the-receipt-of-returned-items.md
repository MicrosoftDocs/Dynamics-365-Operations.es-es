---
title: Registro de la recepción de artículos devueltos
description: Puede registrar la recepción de artículos devueltos mediante el formulario Visión general de llegadas o el formulario Registro.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverview, InventTransRegister
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42ca1d4d2d9b45d79cf479833f83e498e3b73540
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436596"
---
# <a name="register-the-receipt-of-returned-items"></a><span data-ttu-id="389c3-103">Registro de la recepción de artículos devueltos</span><span class="sxs-lookup"><span data-stu-id="389c3-103">Register the receipt of returned items</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="389c3-104">Hay dos métodos para registrar la recepción de artículos devueltos.</span><span class="sxs-lookup"><span data-stu-id="389c3-104">There are two methods for registering the receipt of returned items.</span></span> <span data-ttu-id="389c3-105">El primer método es el proceso de recepción en un almacén que usa el formulario **Visión general de llegadas**.</span><span class="sxs-lookup"><span data-stu-id="389c3-105">The first method is a warehouse receiving process that uses the **Arrival overview** form.</span></span> <span data-ttu-id="389c3-106">El segundo usa el formulario **Registro**.</span><span class="sxs-lookup"><span data-stu-id="389c3-106">The second uses the **Registration** form.</span></span>

## <a name="register-the-receipt-of-returned-items-in-the-arrival-overview-form"></a><span data-ttu-id="389c3-107">Registre el recibo de artículos devueltos en el formulario Visión general de llegadas</span><span class="sxs-lookup"><span data-stu-id="389c3-107">Register the receipt of returned items in the Arrival overview form</span></span>

<span data-ttu-id="389c3-108">Puede utilizar el formulario **Visión general de llegadas** para identificar un envío de devolución por su número de autorización de devolución de materiales (RMA).</span><span class="sxs-lookup"><span data-stu-id="389c3-108">You can use the **Arrival overview** form to identify a return shipment by its Return Material Authorization (RMA) number.</span></span> <span data-ttu-id="389c3-109">Si está definido un nombre de diario en la ficha **Configuración** y existen líneas de diario que se correspondan con las líneas seleccionadas en el formulario **Visión general de llegadas**, se creará automáticamente un nuevo encabezado de diario al hacer clic en **Iniciar llegada**.</span><span class="sxs-lookup"><span data-stu-id="389c3-109">If a journal name is defined on the **Setup** tab, and journal lines that correspond to the lines selected on the **Arrival overview** form exist, a new journal header is created when you click **Start arrival**.</span></span>

1.  <span data-ttu-id="389c3-110">Haga clic en **Gestión del inventario** \> **Periódico** \> **Visión general de llegadas**.</span><span class="sxs-lookup"><span data-stu-id="389c3-110">Click **Inventory management** \> **Periodic** \> **Arrival overview**.</span></span>

2.  <span data-ttu-id="389c3-111">En el campo **Configurar nombre**, seleccione **Pedido de devolución** y, a continuación haga clic en **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="389c3-111">In the **Setup name** field, select **Return order**, and then click **Update**.</span></span>
    

    > [!TIP]
    > <P><span data-ttu-id="389c3-112">Puede utilizar los campos <STRONG>Intervalo</STRONG> para filtrar los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="389c3-112">You can use the <STRONG>Range</STRONG> fields to narrow the search results.</span></span> <span data-ttu-id="389c3-113">Puede escribir o seleccionar el número de RMA en el campo <STRONG>Número RMA</STRONG> para obtener un resultado exacto.</span><span class="sxs-lookup"><span data-stu-id="389c3-113">You can type or select the RMA number in the <STRONG>RMA number</STRONG> field for an exact result.</span></span> <span data-ttu-id="389c3-114">Para definir y guardar un conjunto de filtros que restrinjan las entradas que se muestran, haga clic en la ficha <STRONG>Configuración</STRONG>. Los filtros disponibles incluyen tipos, almacenes y muelles.</span><span class="sxs-lookup"><span data-stu-id="389c3-114">To define and save a set of filters that will restrict which incoming arrivals are displayed, click the <STRONG>Setup</STRONG> tab. The available filters include types, warehouses, and docks.</span></span></P>

    

    > [!WARNING]
    > <P><span data-ttu-id="389c3-115">Los pedidos de devolución no se pueden mezclar con otros tipos de llegada en el formulario <STRONG>Visión general de llegadas</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="389c3-115">Return orders cannot be mixed with other arrival types in the <STRONG>Arrival overview</STRONG> form.</span></span> <span data-ttu-id="389c3-116">Por lo tanto, la referencia siempre será pedido de ventas, pero no se especificará ningún Id. de pedido de ventas en el encabezado del diario.</span><span class="sxs-lookup"><span data-stu-id="389c3-116">Therefore, the reference will always be sales order, but no sales order ID will be specified on the journal header.</span></span></P>



3.  <span data-ttu-id="389c3-117">En la cuadrícula **Recibos**, localice la línea que corresponda al artículo que se está devolviendo y active la casilla de la columna **Seleccionar para llegada**.</span><span class="sxs-lookup"><span data-stu-id="389c3-117">In the **Receipts** grid, locate the line that matches the item being returned, and then select the check box in the **Select for arrival** column.</span></span>

4.  <span data-ttu-id="389c3-118">Si desea excluir determinadas líneas de la recepción de devolución, como artículos del pedido original que no se incluyeron en el envío de devolución, desactive las casillas **Seleccionar para llegada** asociadas en la tabla **Líneas** de la parte inferior del formulario.</span><span class="sxs-lookup"><span data-stu-id="389c3-118">To exclude certain lines from the return receipt, such as items from the original order that were not included in the return shipment, clear the associated **Select for arrival** check boxes in the **Lines** table in the lower part of the form.</span></span>

5.  <span data-ttu-id="389c3-119">Haga clic en el botón **Iniciar llegada** para crear un diario de recepción.</span><span class="sxs-lookup"><span data-stu-id="389c3-119">Click the **Start arrival** button to create an arrival journal.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="389c3-120">Puede seleccionar varios pedidos de devolución e incluirlos a todos en un único proceso de llegada.</span><span class="sxs-lookup"><span data-stu-id="389c3-120">You can select multiple return orders and include them all in a single arrival process.</span></span> <span data-ttu-id="389c3-121">Cada línea del pedido de devolución se copiará en la línea correspondiente del diario de recepción de artículos.</span><span class="sxs-lookup"><span data-stu-id="389c3-121">Each return order line will be copied into a corresponding item arrival journal line.</span></span></P>

    

    > [!NOTE]
    > <P><span data-ttu-id="389c3-122">También puede crear manualmente un diario de recepción mediante el formulario <STRONG>Recepción de artículos</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="389c3-122">You can also manually create an arrival journal by using the <STRONG>Item arrival</STRONG> form.</span></span> 



6.  <span data-ttu-id="389c3-123">Haga clic en **Gestión del inventario** \> **Diarios** \> **Recepción de artículos** \> **Recepción de artículos**.</span><span class="sxs-lookup"><span data-stu-id="389c3-123">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Item arrival**.</span></span>

7.  <span data-ttu-id="389c3-124">Seleccione el diario de recepción que acaba de crear y, a continuación, haga clic en **Líneas** para abrir el formulario **Líneas de diario, ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="389c3-124">Select the arrival journal that you just created and then click **Lines** to open the **Journal lines, locations** form.</span></span>

8.  <span data-ttu-id="389c3-125">En la ficha **General**, ajuste el número en el campo **Cantidad**, si fuera necesario, y asígnele un código de disposición en el campo **Código de disposición**.</span><span class="sxs-lookup"><span data-stu-id="389c3-125">On the **General** tab, adjust the number in the **Quantity** field, if it is required, and then assign a disposition code in the **Disposition code** field.</span></span>
    
    <span data-ttu-id="389c3-126">Como alternativa, puede marcar la casilla **Gestión de cuarentena** para someter los artículos devueltos a un proceso de inspección dentro de un pedido de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="389c3-126">Alternatively, you can select the **Quarantine management** check box to have the returned items sent through an inspection process in the context of a quarantine order.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="389c3-127">Si envía los artículos devueltos a la cuarentena, no puede especificar un código de disposición.</span><span class="sxs-lookup"><span data-stu-id="389c3-127">If you send the returned items through quarantine, you cannot specify a disposition code.</span></span></P>



9.  <span data-ttu-id="389c3-128">Haga clic en el botón **Validar**.</span><span class="sxs-lookup"><span data-stu-id="389c3-128">Click the **Validate** button.</span></span>

10. <span data-ttu-id="389c3-129">Si no hay errores en el proceso de validación, haga clic en **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="389c3-129">If there are no errors in the validation process, click **Post**.</span></span>

## <a name="register-the-receipt-of-returned-items-in-the-registration-form"></a><span data-ttu-id="389c3-130">Registre el recibo de artículos devueltos en el formulario de Registro</span><span class="sxs-lookup"><span data-stu-id="389c3-130">Register the receipt of returned items in the Registration form</span></span>

<span data-ttu-id="389c3-131">En vez de utilizar el formulario **Visión general de llegadas**, puede utilizar el formulario **Registro** para registrar la recepción de artículos devueltos.</span><span class="sxs-lookup"><span data-stu-id="389c3-131">As an alternative to using the **Arrival overview** form, you can use the **Registration** form to register the arrival of returned items.</span></span>

1.  <span data-ttu-id="389c3-132">Haga clic en **Ventas y marketing** \> **Común** \> **Pedidos de devolución** \> **Todos los pedidos de devolución**.</span><span class="sxs-lookup"><span data-stu-id="389c3-132">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span> <span data-ttu-id="389c3-133">Cree un nuevo pedido de devolución o abra el pedido de devolución de la lista.</span><span class="sxs-lookup"><span data-stu-id="389c3-133">Create a new return order or open the return order from the list.</span></span> <span data-ttu-id="389c3-134">En la ficha desplegable **Líneas**, seleccione la línea de pedido de devolución.</span><span class="sxs-lookup"><span data-stu-id="389c3-134">On the **Lines** FastTab, select the return order line.</span></span> <span data-ttu-id="389c3-135">Haga clic en **Actualizar línea** y luego en **Registro**.</span><span class="sxs-lookup"><span data-stu-id="389c3-135">Click **Update line**, and then click **Registration**.</span></span>

2.  <span data-ttu-id="389c3-136">Asigne un código de disposición en el campo **Código de disposición** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="389c3-136">Assign a disposition code in the **Disposition code** field, and then click **OK**.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="389c3-137">No se podrá enviar el artículo para inspección como pedido de cuarentena mediante el formulario <STRONG>Registro</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="389c3-137">It is not possible to send the item for inspection as a quarantine order using the <STRONG>Registration</STRONG> form.</span></span></P>



3.  <span data-ttu-id="389c3-138">En la cuadrícula **Transacciones**, seleccione la transacción que vaya a registrar.</span><span class="sxs-lookup"><span data-stu-id="389c3-138">In the **Transactions** grid, select the transaction to be registered.</span></span>

4.  <span data-ttu-id="389c3-139">En la cuadrícula **Registrar ahora** , haga click en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="389c3-139">In the **Register now** grid, click **Add**.</span></span> <span data-ttu-id="389c3-140">Repita los dos pasos anteriores hasta que todos los artículos devueltos aparezcan en la cuadrícula **Registrar ahora**.</span><span class="sxs-lookup"><span data-stu-id="389c3-140">Repeat the previous two steps until all of the returned items appear in the **Register now** grid.</span></span>

5.  <span data-ttu-id="389c3-141">Haga clic en **Registrar todo**.</span><span class="sxs-lookup"><span data-stu-id="389c3-141">Click **Post all**.</span></span>

## <a name="see-also"></a><span data-ttu-id="389c3-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="389c3-142">See also</span></span>

<span data-ttu-id="389c3-143">[Visión general de llegadas (formulario)](https://technet.microsoft.com/library/hh227654\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="389c3-143">[Arrival overview (form)](https://technet.microsoft.com/library/hh227654\(v=ax.60\))</span></span>

  


