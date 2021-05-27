---
title: Calcular las facturas de TDS utilizando el formulario de pedido de compra y el formulario de pedido de ventas
description: Este tema enumera los pasos para calcular los impuestos deducidos en el origen (TDS) en varios tipos de facturas.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: e7925206f3c060c6332de9d4972c8a7fb0066be2
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023558"
---
# <a name="calculate-tds-invoices-using-purchase-order-form-and-sales-order-form"></a><span data-ttu-id="51500-103">Calcular las facturas de TDS utilizando el formulario de pedido de compra y el formulario de pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="51500-103">Calculate TDS invoices using purchase order form and sales order form</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="51500-104">Este tema enumera los pasos para calcular el impuesto deducido en el origen (TDS) en varios tipos de facturas utilizando las páginas de **Pedido de compra**, **Diario de compra**, **Pedido marco** y **Pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="51500-104">This topic lists the steps for calculating Tax Deducted at Source (TDS) on various types of invoices using the **Purchase order**, **Purchase journal**, **Blanket order**, and **Sales order** pages.</span></span>

1. <span data-ttu-id="51500-105">Cree un pedido de compra, un diario de compra, un pedido marco de compra o un pedido de ventas utilizando la página que aparece.</span><span class="sxs-lookup"><span data-stu-id="51500-105">Create a purchase order, purchase journal, purchase blanket order, or a sales order using the page listed.</span></span> <span data-ttu-id="51500-106">Especifique los detalles necesarios.</span><span class="sxs-lookup"><span data-stu-id="51500-106">Enter the required details.</span></span>

2. <span data-ttu-id="51500-107">Seleccione la pestaña **Configuración** para ver la naturaleza del evaluado del proveedor o cliente.</span><span class="sxs-lookup"><span data-stu-id="51500-107">Select the **Setup** tab to view the nature of the assessee of the vendor or customer.</span></span> <span data-ttu-id="51500-108">Esta información se enumera en el campo **Naturaleza del evaluado**, en el el grupo de campo **Grupo de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="51500-108">This information is listed in the **Nature of assessee** field, under the **Withholding tax group** field group.</span></span>

3. <span data-ttu-id="51500-109">En el campo **Grupo TDS**, consulte o modifique el grupo TDS predeterminado definido para el proveedor o cliente.</span><span class="sxs-lookup"><span data-stu-id="51500-109">In the **TDS group** field, view or modify the default TDS group defined for the vendor or customer.</span></span>

   > [!NOTE]
   > <span data-ttu-id="51500-110">El campo **Grupo TCS** no está disponible cuando selecciona un grupo TDS en el campo **Grupo TDS**.</span><span class="sxs-lookup"><span data-stu-id="51500-110">The **TCS group** field isn't available when you select a TDS group in the **TDS group** field.</span></span> <span data-ttu-id="51500-111">TDS se calcula solo si se ha seleccionado la casilla **Calcular retención de impuestos** para el proveedor o cliente en las páginas **Todos los proveedores** o **Todos los clientes**.</span><span class="sxs-lookup"><span data-stu-id="51500-111">TDS is calculated only if the **Calculate withholding tax** check box is selected for the vendor or customer on the **All vendors** or **All customers** page.</span></span>  

4. <span data-ttu-id="51500-112">Cree líneas de artículos en la pestaña **Líneas** e introduzca los detalles requeridos.</span><span class="sxs-lookup"><span data-stu-id="51500-112">Create item lines on the **Lines** tab and enter the required details.</span></span>

5. <span data-ttu-id="51500-113">Seleccione la pestaña **Configuración** (nivel de línea) para ver o cambiar el grupo TDS definido en el nivel de encabezado.</span><span class="sxs-lookup"><span data-stu-id="51500-113">Select the **Setup** tab (line-level) to view or change the TDS group defined at the header-level.</span></span> <span data-ttu-id="51500-114">El grupo TDS se muestra en el campo **Grupo TDS**, que está en el grupo de campo **Grupo de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="51500-114">The TDS group is displayed in the **TDS group** field, which is under the **Withholding tax group** field group.</span></span>

6. <span data-ttu-id="51500-115">Seleccione la pestaña **Información de impuestos** y seleccione direcciones alternativas que estén configuradas para el nombre de la empresa que se muestra en este campo.</span><span class="sxs-lookup"><span data-stu-id="51500-115">Select the **Tax information** tab and select alternate addresses that are set up for the company name that's displayed in this field.</span></span> <span data-ttu-id="51500-116">El nombre de la empresa se muestra en el campo **Nombre**, que está en el grupo de campo **Información de la empresa**.</span><span class="sxs-lookup"><span data-stu-id="51500-116">The company name is displayed in the **Name** field, which is under the **Company information** field group.</span></span> 

   <span data-ttu-id="51500-117">El TAN del nombre de la empresa seleccionada se muestra en el campo **Número de cuenta de impuestos** (**TAN**), en el grupo de campo **Retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="51500-117">The TAN of the selected company name is displayed in the **Tax Account Number** (**TAN**) field, under the **Withholding tax** field group.</span></span> 

7. <span data-ttu-id="51500-118">Seleccione **Retención de impuestos** para abrir la página **Transacciones de retención temporal de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="51500-118">Select **Withholding tax** to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="51500-119">Consulte los siguientes campos en el panel superior de la página **Transacciones de retención temporal de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="51500-119">View the following fields on the upper pane of the **Temporary withholding tax transactions** page.</span></span>

   - <span data-ttu-id="51500-120">**Retención** **de** **importe** **total** **de impuestos**: el total de TDS calculado para la transacción para el grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="51500-120">**Withholding** **tax** **amount** **in** **total** - The total TDS calculated for the transaction for the TDS group.</span></span>

   - <span data-ttu-id="51500-121">**Valor**: el porcentaje total utilizado para calcular TDS para la transacción.</span><span class="sxs-lookup"><span data-stu-id="51500-121">**Value** - The total percentage used to calculate TDS for the transaction.</span></span> <span data-ttu-id="51500-122">El porcentaje total se basa en la fórmula que se define para los códigos de impuestos TDS adjuntos al grupo TDS.</span><span class="sxs-lookup"><span data-stu-id="51500-122">The total percentage is based on the formula that is defined for TDS tax codes attached to the TDS group.</span></span>

   - <span data-ttu-id="51500-123">**Importe total de la retención de impuestos ajustada**: el importe total de TDS ajustado para todos los códigos de impuestos en el grupo TDS.</span><span class="sxs-lookup"><span data-stu-id="51500-123">**Adjusted withholding tax amount in total** - The total adjusted TDS amount for all tax codes in the TDS group.</span></span>

   - <span data-ttu-id="51500-124">**TDS**: si se selecciona, se adjunta un grupo de TDS a la transacción.</span><span class="sxs-lookup"><span data-stu-id="51500-124">**TDS** - If selected, a TDS group is attached to the transaction.</span></span>

<span data-ttu-id="51500-125">Los campos en las pestañas **Información general**, **General** y **Ajuste** en la página **Transacciones de retención temporal de impuestos** muestra la cantidad de TDS calculada y los detalles de la cantidad de TDS ajustada para cada código de impuestos de TDS adjunto al grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="51500-125">The fields on the **Overview**, **General**, and **Adjustment** tabs on the **Temporary withholding tax transactions** page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>

8. <span data-ttu-id="51500-126">Seleccione **Umbral** para abrir la página **Umbral**.</span><span class="sxs-lookup"><span data-stu-id="51500-126">Select **Threshold** to open the **Threshold** page.</span></span> <span data-ttu-id="51500-127">Consulte el límite de umbral definido para el componente de impuestos de TDS adjunto a un código de impuestos de TDS específico en esta página.</span><span class="sxs-lookup"><span data-stu-id="51500-127">View the threshold limit defined for the TDS tax component attached to a specific TDS tax code on this page.</span></span>

9. <span data-ttu-id="51500-128">Seleccione **Diseñador de fórmulas** para abrir la página **Diseñador de fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="51500-128">Select **Formula designer** to open the **Formula designer** page.</span></span> <span data-ttu-id="51500-129">Consulte la fórmula definida para un código de impuestos TDS específico en esta página.</span><span class="sxs-lookup"><span data-stu-id="51500-129">View the formula that is defined for a specific TDS tax code on this page.</span></span> 

10. <span data-ttu-id="51500-130">Registre la factura.</span><span class="sxs-lookup"><span data-stu-id="51500-130">Post the invoice.</span></span> <span data-ttu-id="51500-131">La cantidad de TDS calculada en las facturas de compra se registra en la cuenta de proveedores y la cantidad de TDS calculada en las facturas de venta se contabiliza en la cuenta de clientes que se define para cada código de impuestos de TDS en el grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="51500-131">The TDS amount calculated on purchase invoices is posted to the payable account and the TDS amount calculated on sales invoices is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="51500-132">Las cuentas de proveedores o de clientes para los códigos de impuestos TDS se definen en la página **Códigos de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="51500-132">The payable accounts or receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>

11. <span data-ttu-id="51500-133">Seleccione el botón **Consulta** y el botón **> Factura > Retención de impuestos registrados** para abrir la página **Transacciones de retención de impuestos**.</span><span class="sxs-lookup"><span data-stu-id="51500-133">Select **Inquiry** button **> Invoice > Posted withholding tax** button to open the **Withholding tax transactions** page.</span></span> <span data-ttu-id="51500-134">Puede ver el porcentaje total utilizado para calcular TDS para la transacción en el campo **Valor**.</span><span class="sxs-lookup"><span data-stu-id="51500-134">You can view the total percentage used to calculate TDS for the transaction in the **Value** field.</span></span>

<span data-ttu-id="51500-135">Los campos en las pestañas **Descripción general**, **General** e **Importe** en la página **Transacciones de retención de impuestos** muestran la información de TDS calculada para la transacción.</span><span class="sxs-lookup"><span data-stu-id="51500-135">The fields on the **Overview**, **General**, and **Amount** tabs on the **Withholding tax transactions** page display the information of TDS calculated for the transaction.</span></span> <span data-ttu-id="51500-136">Consulte la información de cálculo de TDS para cada código de impuestos de TDS adjunto al grupo de TDS.</span><span class="sxs-lookup"><span data-stu-id="51500-136">View the TDS calculation information for each TDS tax code attached to the TDS group.</span></span>
