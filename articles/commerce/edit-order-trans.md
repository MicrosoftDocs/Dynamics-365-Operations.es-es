---
title: Editar y auditar transacciones de pedidos de cliente asincrónicas y pedidos en línea
description: En este tema se describe cómo editar y auditar transacciones de pedidos de cliente asincrónicas y pedidos en línea en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: b9f2db25c8897662baa177752d0c5fc4ac6178a4
ms.sourcegitcommit: ce51ff2b6099c75dceb99de6dea9d53baf99772d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2020
ms.locfileid: "4459911"
---
# <a name="edit-and-audit-online-order-and-asynchronous-customer-order-transactions"></a><span data-ttu-id="a14e9-103">Editar y auditar transacciones de pedidos de cliente asincrónicas y pedidos en línea</span><span class="sxs-lookup"><span data-stu-id="a14e9-103">Edit and audit online order and asynchronous customer order transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a14e9-104">En este tema se describe cómo editar y auditar transacciones de pedidos de cliente asincrónicas y pedidos en línea en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a14e9-104">This topic describes how to edit and audit online order and asynchronous customer order transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a14e9-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="a14e9-105">Overview</span></span>

<span data-ttu-id="a14e9-106">Entre las versiones 10.0.5 y 10.0.6 de Commerce, se agregó soporte para editar transacciones de pago al contado sin entrega a domicilio (como ventas y devoluciones) y transacciones de gestión del efectivo (como entrada flotante y suspensión de forma de pago).</span><span class="sxs-lookup"><span data-stu-id="a14e9-106">Between Commerce versions 10.0.5 and 10.0.6, support was added for editing cash and carry transactions (such as sales and returns) and cash management transactions (such as float entry and tender removal).</span></span> <span data-ttu-id="a14e9-107">En la versión 10.0.7 de Commerce, se agregó soporte para editar transacciones de pedidos en línea y transacciones de pedidos de clientes asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="a14e9-107">In Commerce version 10.0.7, support was added for editing online order transactions and asynchronous customer order transactions.</span></span>

## <a name="edit-and-audit-order-transactions"></a><span data-ttu-id="a14e9-108">Editar y auditar transacciones de pedidos</span><span class="sxs-lookup"><span data-stu-id="a14e9-108">Edit and audit order transactions</span></span>

<span data-ttu-id="a14e9-109">Para editar y auditar transacciones de pedidos en la sede central de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a14e9-109">To edit and audit order transactions in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="a14e9-110">Instale el [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).</span><span class="sxs-lookup"><span data-stu-id="a14e9-110">Install the [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).</span></span>
1. <span data-ttu-id="a14e9-111">En la página **Parámetros comerciales**, en la pestaña **Pedidos de cliente**, en la ficha desplegable **Pedido**, especifique un código de retención para **Código de retención para errores de sincronización de pedidos**.</span><span class="sxs-lookup"><span data-stu-id="a14e9-111">On the **Retail parameters** page, on the **Customer orders** tab, on the **Order** FastTab, specify a hold code for **Hold code for order synchronization errors**.</span></span>
1. <span data-ttu-id="a14e9-112">Abra el espacio de trabajo **Operaciones financieras de tienda**.</span><span class="sxs-lookup"><span data-stu-id="a14e9-112">Open the **Store financials** workspace.</span></span> <span data-ttu-id="a14e9-113">Las ventanas **Errores de sincronización de pedidos en línea** y **Errores de sincronización de pedidos de cliente** ofrecen una vista prefiltrada de la página de transacciones minoristas.</span><span class="sxs-lookup"><span data-stu-id="a14e9-113">The **Online order synchronization errors** and **Customer order synchronization errors** tiles provide a prefiltered view of the retail transaction page.</span></span> <span data-ttu-id="a14e9-114">Cada una muestra los registros de transacciones con error en la sincronización para el tipo de pedido correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a14e9-114">Each shows the transaction records that have failed synchronization for the corresponding order type.</span></span>
1. <span data-ttu-id="a14e9-115">Abra las páginas **Errores de sincronización de pedidos en línea** o **Errores de sincronización de pedidos de cliente**.</span><span class="sxs-lookup"><span data-stu-id="a14e9-115">Open either the **Online order synchronization errors** page or the **Customer order synchronization errors** page.</span></span> <span data-ttu-id="a14e9-116">Seleccione un registro para ver los detalles del error de sincronización.</span><span class="sxs-lookup"><span data-stu-id="a14e9-116">Select a record to view the synchronization error details.</span></span> <span data-ttu-id="a14e9-117">La ficha desplegable **Estado de sincronización** ofrece los siguientes detalles de error:</span><span class="sxs-lookup"><span data-stu-id="a14e9-117">The **Synchronization status** FastTab provides the following error details:</span></span>

    - <span data-ttu-id="a14e9-118">Estado del pedido pendiente</span><span class="sxs-lookup"><span data-stu-id="a14e9-118">Pending order status</span></span>
    - <span data-ttu-id="a14e9-119">Detalles de errores del pedido</span><span class="sxs-lookup"><span data-stu-id="a14e9-119">Order error details</span></span>
    - <span data-ttu-id="a14e9-120">Fecha y hora de modificación</span><span class="sxs-lookup"><span data-stu-id="a14e9-120">Modified date and time</span></span>
    - <span data-ttu-id="a14e9-121">Número de reintentos</span><span class="sxs-lookup"><span data-stu-id="a14e9-121">Retry count</span></span>

1. <span data-ttu-id="a14e9-122">Si los detalles del error indican que el registro debe corregirse, seleccione **Complemento de Office** y luego elija **Editar transacción seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="a14e9-122">If the error details indicate that the record must be fixed, select **Office Add in**, and then select **Edit selected transaction**.</span></span> <span data-ttu-id="a14e9-123">Se abre un archivo de Excel que muestra los detalles de la transacción seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a14e9-123">An Excel file that shows the details of the selected transaction is opened.</span></span>

    - <span data-ttu-id="a14e9-124">Si la transacción que se está editando es una transacción de pedido en línea, el archivo de Excel contiene las siguientes hojas de cálculo:</span><span class="sxs-lookup"><span data-stu-id="a14e9-124">If the transaction that is being edited is an online order transaction, the Excel file contains the following worksheets:</span></span>

        - <span data-ttu-id="a14e9-125">**Transacción**: esta hoja de cálculo tiene los detalles de encabezado para la transacción.</span><span class="sxs-lookup"><span data-stu-id="a14e9-125">**Transaction** – This worksheet has the header details for the transaction.</span></span>
        - <span data-ttu-id="a14e9-126">**Transacción de venta**: esta hoja de cálculo tiene los detalles de línea para la transacción.</span><span class="sxs-lookup"><span data-stu-id="a14e9-126">**Sales transaction** – This worksheet has the line details for the transaction.</span></span>
        - <span data-ttu-id="a14e9-127">**Transacciones de pago**: esta hoja de cálculo tiene los detalles de las líneas de pago para la transacción.</span><span class="sxs-lookup"><span data-stu-id="a14e9-127">**Payment transactions** – This worksheet has the details of the payment lines for the transaction.</span></span>
        - <span data-ttu-id="a14e9-128">**Transacciones de descuento**: esta hoja de cálculo tiene los detalles relacionados con descuentos para la transacción.</span><span class="sxs-lookup"><span data-stu-id="a14e9-128">**Discount transactions** – This worksheet has the discount-related details for the transaction.</span></span>
        - <span data-ttu-id="a14e9-129">**Transacciones de impuestos**: esta hoja de cálculo tiene los detalles relacionados con impuestos para la transacción.</span><span class="sxs-lookup"><span data-stu-id="a14e9-129">**Tax transactions** – This worksheet has the tax-related details for the transaction.</span></span>
        - <span data-ttu-id="a14e9-130">**Transacciones de gastos**: esta hoja de cálculo tiene los detalles relacionados con gastos para la transacción.</span><span class="sxs-lookup"><span data-stu-id="a14e9-130">**Charges transactions** – This worksheet has the charges-related data for the transaction.</span></span>

    - <span data-ttu-id="a14e9-131">Si la transacción que se está editando es una transacción de pedido de cliente asincrónica, el archivo de Excel contiene las siguientes hojas de cálculo:</span><span class="sxs-lookup"><span data-stu-id="a14e9-131">If the transaction that is being edited is an asynchronous customer order transaction, the Excel file contains the following worksheets:</span></span>

        - <span data-ttu-id="a14e9-132">**Líneas**: esta hoja de cálculo tiene los detalles de línea y encabezado para la transacción.</span><span class="sxs-lookup"><span data-stu-id="a14e9-132">**Lines** – This worksheet has the header and line details for the transaction.</span></span>
        - <span data-ttu-id="a14e9-133">**Pagos**: esta hoja de cálculo tiene los detalles de las líneas de pago para la transacción.</span><span class="sxs-lookup"><span data-stu-id="a14e9-133">**Payments** – This worksheet has the details of the payment lines for the transaction.</span></span>
        - <span data-ttu-id="a14e9-134">**Descuentos**: esta hoja de cálculo tiene los detalles relacionados con descuentos para la transacción.</span><span class="sxs-lookup"><span data-stu-id="a14e9-134">**Discounts** – This worksheet has the discount-related details for the transaction.</span></span>
        - <span data-ttu-id="a14e9-135">**Impuestos**: esta hoja de cálculo tiene los detalles relacionados con impuestos para la transacción.</span><span class="sxs-lookup"><span data-stu-id="a14e9-135">**Taxes** – This worksheet has the tax-related details for the transaction.</span></span>
        - <span data-ttu-id="a14e9-136">**Gastos**: esta hoja de cálculo tiene los detalles relacionados con gastos para la transacción.</span><span class="sxs-lookup"><span data-stu-id="a14e9-136">**Charges** – This worksheet has the charges-related data for the transaction.</span></span>

1. <span data-ttu-id="a14e9-137">En el archivo de Excel, en el campo **Estado de pedido pendiente**, introduzca **Edición** y luego publique el cambio.</span><span class="sxs-lookup"><span data-stu-id="a14e9-137">In the Excel file, in the **Pending order status** field, enter **Editing**, and then publish the change.</span></span> <span data-ttu-id="a14e9-138">De esta forma, evita que el trabajo **Sincronizar pedido** que se está ejecutando en el modo por lotes omita este registro durante el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a14e9-138">In this way, you prevent the **Synchronize order** job that is running in batch mode from skipping this record during processing.</span></span>
1. <span data-ttu-id="a14e9-139">En el archivo de Excel, modifique los campos adecuados y, a continuación, cargue los datos de nuevo en la sede central de Commerce usando la funcionalidad de publicación del complemento de Excel de Dynamics.</span><span class="sxs-lookup"><span data-stu-id="a14e9-139">In the Excel file, modify the appropriate fields, and then upload the data back into Commerce headquarters by using the publishing functionality of the Dynamics Excel Add-in.</span></span> <span data-ttu-id="a14e9-140">Una vez se han publicado los datos, los cambios se reflejarán en el sistema.</span><span class="sxs-lookup"><span data-stu-id="a14e9-140">After the data is published, the changes will be reflected in the system.</span></span> <span data-ttu-id="a14e9-141">Durante la publicación, no se realiza ninguna validación para los cambios que hagan los usuarios.</span><span class="sxs-lookup"><span data-stu-id="a14e9-141">During publication, no validation is done for changes that users make.</span></span>
1. <span data-ttu-id="a14e9-142">Para ver una traza de auditoría completa de los cambios, seleccione **Ver traza de auditoría** en el encabezado **Transacción comercial** para los cambios de nivel de encabezado y en la sección y el registro pertinentes de la página de transacción adecuada.</span><span class="sxs-lookup"><span data-stu-id="a14e9-142">You can view a complete audit trail of the changes by selecting **View audit trail** in the **Retail transaction** header for the header-level changes, and in the relevant section and record on the appropriate transaction page.</span></span> <span data-ttu-id="a14e9-143">Por ejemplo, todos los cambios relacionados con las líneas de ventas se mostrarán en la página **Transacciones de ventas**, y todos los cambios relacionados con los pagos se mostrarán en la página **Transacciones de pago**.</span><span class="sxs-lookup"><span data-stu-id="a14e9-143">For example, all changes that are related to sales lines will be shown on the **Sales transactions** page, and all changes that are related to payments will be shown on the **Payment transactions** page.</span></span> <span data-ttu-id="a14e9-144">Se mantienen los siguientes detalles de auditoría para los cambios:</span><span class="sxs-lookup"><span data-stu-id="a14e9-144">The following audit details are maintained for the changes:</span></span>

    - <span data-ttu-id="a14e9-145">Fecha y hora de modificación</span><span class="sxs-lookup"><span data-stu-id="a14e9-145">Modified date and time</span></span>
    - <span data-ttu-id="a14e9-146">Campo</span><span class="sxs-lookup"><span data-stu-id="a14e9-146">Field</span></span>
    - <span data-ttu-id="a14e9-147">Valor anterior</span><span class="sxs-lookup"><span data-stu-id="a14e9-147">Old value</span></span>
    - <span data-ttu-id="a14e9-148">Nuevo valor</span><span class="sxs-lookup"><span data-stu-id="a14e9-148">New value</span></span>
    - <span data-ttu-id="a14e9-149">Modificado por</span><span class="sxs-lookup"><span data-stu-id="a14e9-149">Modified by</span></span>

1. <span data-ttu-id="a14e9-150">Una vez que haya realizado y publicado sus cambios, seleccione **Sincronizar pedido** para iniciar inmediatamente el proceso de sincronización.</span><span class="sxs-lookup"><span data-stu-id="a14e9-150">After you've made and published your changes, select **Synchronize order** to immediately start the synchronization process.</span></span> <span data-ttu-id="a14e9-151">También puede esperar a que el proceso de sincronización que se está ejecutando en el modo por lotes procese la transacción.</span><span class="sxs-lookup"><span data-stu-id="a14e9-151">Alternatively, you can wait for the synchronization process that is running in batch mode to process the transaction.</span></span>

<span data-ttu-id="a14e9-152">De forma predeterminada, una vez que los pedidos se sincronizan correctamente, se ponen en estado de retención, según el código de retención que se define en los parámetros de Commerce.</span><span class="sxs-lookup"><span data-stu-id="a14e9-152">By default, after the orders are successfully synced, they are put in a hold status, based on the hold code that is defined in the Commerce parameters.</span></span> <span data-ttu-id="a14e9-153">La retención en los pedidos debe eliminarse antes de que los pedidos se puedan procesar más para su cumplimiento u otras operaciones.</span><span class="sxs-lookup"><span data-stu-id="a14e9-153">The hold on the orders must be removed before the orders can be processed further for fulfillment or other operations.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a14e9-154">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a14e9-154">Additional resources</span></span>

[<span data-ttu-id="a14e9-155">Editar y auditar transacciones de gestión de efectivo y pago al contado sin entrega a domicilio</span><span class="sxs-lookup"><span data-stu-id="a14e9-155">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="a14e9-156">Editar dimensiones financieras para transacciones minoristas</span><span class="sxs-lookup"><span data-stu-id="a14e9-156">Edit financial dimensions for retail transactions</span></span>](edit-financial-dim.md)

[<span data-ttu-id="a14e9-157">Crear un libro de trabajo de Excel para editar transacciones minoristas</span><span class="sxs-lookup"><span data-stu-id="a14e9-157">Create an Excel workbook to edit retail transactions</span></span>](create-excel-edit.md)

[<span data-ttu-id="a14e9-158">Agregar campos a un libro de trabajo de Excel para editar transacciones minoristas</span><span class="sxs-lookup"><span data-stu-id="a14e9-158">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)
