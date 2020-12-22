---
title: Crear un libro de trabajo de Excel para editar transacciones minoristas
description: En este tema se describe cómo crear un libro de Excel para poder editar transacciones minoristas en Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: b2b6e98db54e7747912aad26f4b8ae24b9ad5a6d
ms.sourcegitcommit: ce51ff2b6099c75dceb99de6dea9d53baf99772d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2020
ms.locfileid: "4459913"
---
# <a name="create-an-excel-workbook-to-edit-retail-transactions"></a><span data-ttu-id="1d127-103">Crear un libro de trabajo de Excel para editar transacciones minoristas</span><span class="sxs-lookup"><span data-stu-id="1d127-103">Create an Excel workbook to edit retail transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1d127-104">En este tema se describe cómo crear un libro de Excel para poder editar transacciones minoristas en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1d127-104">This topic describes how to create an Excel workbook so that you can edit retail transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="1d127-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="1d127-105">Overview</span></span>

<span data-ttu-id="1d127-106">Existe una plantilla de Excel predefinida a la que los clientes pueden obtener acceso desde diferentes partes del sistema y utilizar para editar y auditar transacciones minoristas.</span><span class="sxs-lookup"><span data-stu-id="1d127-106">There is a predefined Excel template that customers can access from different parts of the system and use to edit and audit retail transactions.</span></span> <span data-ttu-id="1d127-107">Sin embargo, los clientes también pueden crear un libro de Excel personalizado para este propósito.</span><span class="sxs-lookup"><span data-stu-id="1d127-107">However, customers can also create a custom Excel workbook for this purpose.</span></span>

## <a name="create-and-configure-an-excel-workbook"></a><span data-ttu-id="1d127-108">Crear y configurar un libro de Excel</span><span class="sxs-lookup"><span data-stu-id="1d127-108">Create and configure an Excel workbook</span></span>

<span data-ttu-id="1d127-109">Para crear y configurar un libro de Excel para que pueda editar transacciones minoristas, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1d127-109">To create and configure an Excel workbook so that you can edit retail transactions, follow these steps.</span></span>

1. <span data-ttu-id="1d127-110">Abra Excel y cree un libro en blanco.</span><span class="sxs-lookup"><span data-stu-id="1d127-110">Open Excel, and create a blank workbook.</span></span>
1. <span data-ttu-id="1d127-111">En la pestaña **Insertar**, seleccione **Mis complementos**.</span><span class="sxs-lookup"><span data-stu-id="1d127-111">On the **Insert** tab, select **My add-ins**.</span></span>
1. <span data-ttu-id="1d127-112">En el panel derecho, seleccione el vínculo **Agregar información del servidor**.</span><span class="sxs-lookup"><span data-stu-id="1d127-112">In the right pane, select the **Add server information** link.</span></span>
1. <span data-ttu-id="1d127-113">Escriba la dirección URL del servidor y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1d127-113">Enter the server URL, and then select **OK**.</span></span>
1. <span data-ttu-id="1d127-114">Si recibe un mensaje de error "No se encontraron registros de applet", siga estos pasos para resolver el problema:</span><span class="sxs-lookup"><span data-stu-id="1d127-114">If you receive a "No applet registrations found" error message, follow these steps to resolve the issue:</span></span>

    1. <span data-ttu-id="1d127-115">En Commerce, vaya a **Administración del sistema \> Configuración \> Parámetros de aplicación de Office**.</span><span class="sxs-lookup"><span data-stu-id="1d127-115">In Commerce, go to **System administration \> Setup \> Office app parameters**.</span></span>
    1. <span data-ttu-id="1d127-116">En la ficha desplegable **Parámetros de aplicación**, seleccione **Inicializar parámetros de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="1d127-116">On the **App parameters** FastTab, select **Initialize app parameters**.</span></span>
    1. <span data-ttu-id="1d127-117">En el cuadro de mensaje de confirmación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1d127-117">In the confirmation message box, select **OK**.</span></span>
    1. <span data-ttu-id="1d127-118">En la ficha desplegable **Applets registrados**, seleccione **Inicializar registro de applet**.</span><span class="sxs-lookup"><span data-stu-id="1d127-118">On the **Registered applets** FastTab, select **Initialize applet registration**.</span></span>
    1. <span data-ttu-id="1d127-119">Repita los tres pasos anteriores según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="1d127-119">Repeat the previous three steps as required.</span></span>

1. <span data-ttu-id="1d127-120">Seleccione **Diseño** y, a continuación, **Agregar tabla**.</span><span class="sxs-lookup"><span data-stu-id="1d127-120">Select **Design**, and then select **Add table**.</span></span>
1. <span data-ttu-id="1d127-121">En función de los datos que deben modificarse, seleccione las entidades que se deben agregar al libro de Excel para su edición.</span><span class="sxs-lookup"><span data-stu-id="1d127-121">Based on the data that has to be modified, select the entities that must be added to the Excel workbook for editing.</span></span> <span data-ttu-id="1d127-122">Utilice la siguiente tabla como referencia.</span><span class="sxs-lookup"><span data-stu-id="1d127-122">Use the following table as a reference.</span></span>

    | <span data-ttu-id="1d127-123">Tipo de transacción</span><span class="sxs-lookup"><span data-stu-id="1d127-123">Transaction type</span></span> | <span data-ttu-id="1d127-124">Entidades de datos que se usarán</span><span class="sxs-lookup"><span data-stu-id="1d127-124">Data entities to use</span></span> |
    |------------------|----------------------|
    | <span data-ttu-id="1d127-125">Transacciones de pago al contado sin entrega a domicilio, Pedidos en línea, Pedidos de clientes asincrónicos, Ofertas de clientes asincrónicas</span><span class="sxs-lookup"><span data-stu-id="1d127-125">Cash and carry transactions, Online orders, Async customer orders, Async customer quotes</span></span> | <span data-ttu-id="1d127-126">Transacción (auditable), Transacción de ventas (auditable), Transacciones de pago (auditables), Transacciones de impuestos (auditables), Transacciones de descuento (auditables), Transacciones de cargos (auditables)</span><span class="sxs-lookup"><span data-stu-id="1d127-126">Transaction (auditable), Sales transaction (auditable), Payment transactions (auditable), Tax transactions (auditable), Discount transactions (auditable), Charge transactions (auditable)</span></span> |
    | <span data-ttu-id="1d127-127">Ingreso bancario</span><span class="sxs-lookup"><span data-stu-id="1d127-127">Bank drop</span></span> | <span data-ttu-id="1d127-128">Transacción (auditable), Transacciones de forma de pago bancarias (auditables)</span><span class="sxs-lookup"><span data-stu-id="1d127-128">Transaction (auditable), Banked tender transactions (auditable)</span></span> |
    | <span data-ttu-id="1d127-129">Ingreso en caja fuerte</span><span class="sxs-lookup"><span data-stu-id="1d127-129">Safe drop</span></span> | <span data-ttu-id="1d127-130">Transacción (auditable), Transacciones de forma de pago en caja fuerte (auditables)</span><span class="sxs-lookup"><span data-stu-id="1d127-130">Transaction (auditable), Safe tender transactions (auditable)</span></span> |
    | <span data-ttu-id="1d127-131">Declaración por forma de pago</span><span class="sxs-lookup"><span data-stu-id="1d127-131">Tender declaration</span></span> | <span data-ttu-id="1d127-132">Transacción (auditable), Transacciones de declaración por forma de pago (auditables)</span><span class="sxs-lookup"><span data-stu-id="1d127-132">Transaction (auditable), Tender declaration transactions (auditable)</span></span> |
    | <span data-ttu-id="1d127-133">Ingresos, gastos</span><span class="sxs-lookup"><span data-stu-id="1d127-133">Income, Expense</span></span> | <span data-ttu-id="1d127-134">Transacción (auditable), Transacciones de ingresos/gastos (auditables), Transacciones de pago (auditables)</span><span class="sxs-lookup"><span data-stu-id="1d127-134">Transaction (auditable), Income/Expense transactions (auditable), Payment transactions (auditable)</span></span> |
    | <span data-ttu-id="1d127-135">Declarar importe inicial, Supresión de forma de pago, Entrada flotante, Cambio de la forma de pago, Pago de factura, Depósito del cliente</span><span class="sxs-lookup"><span data-stu-id="1d127-135">Declare starting amount, Tender removal, Float entry, Change tender, Invoice payment, Customer deposit</span></span> | <span data-ttu-id="1d127-136">Transacción (auditable), Transacciones de pago (auditables)</span><span class="sxs-lookup"><span data-stu-id="1d127-136">Transaction (auditable), Payment transactions (auditable)</span></span> |

    > [!NOTE]
    > <span data-ttu-id="1d127-137">Es importante que agregue solo una entidad de datos a cada libro de Excel.</span><span class="sxs-lookup"><span data-stu-id="1d127-137">It's important that you add only one data entity to each Excel workbook.</span></span> <span data-ttu-id="1d127-138">Además, todos los campos que están marcados con un símbolo de llave deben agregarse al libro correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1d127-138">Additionally, all fields that are marked by a key symbol must be added to the relevant workbook.</span></span>

1. <span data-ttu-id="1d127-139">Una vez configurado el libro, aplique los filtros necesarios.</span><span class="sxs-lookup"><span data-stu-id="1d127-139">After the workbook is configured, apply the required filters.</span></span> <span data-ttu-id="1d127-140">Asegúrese de aplicar los mismos filtros a todas las hojas de cálculo del archivo.</span><span class="sxs-lookup"><span data-stu-id="1d127-140">Be sure to apply the same filters to all the worksheets in the file.</span></span> <span data-ttu-id="1d127-141">Evite cargar grandes cantidades de datos en el archivo de Excel.</span><span class="sxs-lookup"><span data-stu-id="1d127-141">Avoid loading very large amounts of data into the Excel file.</span></span> <span data-ttu-id="1d127-142">De lo contrario, el rendimiento podría verse afectado y Excel y su sistema podrían ralentizarse.</span><span class="sxs-lookup"><span data-stu-id="1d127-142">Otherwise, performance might be affected, and Excel and your system might slow down.</span></span> <span data-ttu-id="1d127-143">Recomendamos que use siempre "Empresa" y "Número de extracto" o "Número de transacción" como filtros para su archivo.</span><span class="sxs-lookup"><span data-stu-id="1d127-143">We recommend that you always use "Company" and either "Statement Number" or "Transaction Number" as filters for your file.</span></span>
1. <span data-ttu-id="1d127-144">Una vez configurados los filtros, seleccione **Actualizar** para cargar los datos.</span><span class="sxs-lookup"><span data-stu-id="1d127-144">After the filters are configured, select **Refresh** to load the data.</span></span>
1. <span data-ttu-id="1d127-145">Edite los datos necesarios y luego publíquelos.</span><span class="sxs-lookup"><span data-stu-id="1d127-145">Edit the required data, and then publish it.</span></span> <span data-ttu-id="1d127-146">Si el botón **Publicar** no está disponible, algunos campos clave probablemente no se agregaron al libro de Excel.</span><span class="sxs-lookup"><span data-stu-id="1d127-146">If the **Publish** button is unavailable, some key fields probably weren't added to the Excel workbook.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1d127-147">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1d127-147">Additional resources</span></span>

[<span data-ttu-id="1d127-148">Editar y auditar transacciones de gestión de efectivo y pago al contado sin entrega a domicilio</span><span class="sxs-lookup"><span data-stu-id="1d127-148">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="1d127-149">Editar y auditar transacciones de pedidos de cliente asincrónicas y pedidos en línea</span><span class="sxs-lookup"><span data-stu-id="1d127-149">Edit and audit online order and asynchronous customer order transactions</span></span>](edit-order-trans.md)

[<span data-ttu-id="1d127-150">Editar dimensiones financieras para transacciones minoristas</span><span class="sxs-lookup"><span data-stu-id="1d127-150">Edit financial dimensions for retail transactions</span></span>](edit-financial-dim.md)

[<span data-ttu-id="1d127-151">Agregar campos a un libro de trabajo de Excel para editar transacciones minoristas</span><span class="sxs-lookup"><span data-stu-id="1d127-151">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)
