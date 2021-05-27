---
title: Configurar un cuotas de pago para pagos de la autoridad de TDS
description: Este tema explica cómo configurar las cuotas de pago que se cobran por los pagos de la autoridad con impuestos deducidos en el origen (TDS).
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
ms.openlocfilehash: b52331bb1c7a1bc2c764008112f3df9cc0385995
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023583"
---
# <a name="set-up-payment-fees-for-tds-authority-payments"></a><span data-ttu-id="3253f-103">Configurar un cuotas de pago para pagos de la autoridad de TDS</span><span class="sxs-lookup"><span data-stu-id="3253f-103">Set up payment fees for TDS authority payments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3253f-104">Este tema explica cómo configurar las cuotas de pago que se cobran por los pagos de la autoridad con impuestos deducidos en el origen (TDS).</span><span class="sxs-lookup"><span data-stu-id="3253f-104">This topic explains how to set up payment fees that are charged for Tax Deducted at Source (TDS) authority payments.</span></span>

1. <span data-ttu-id="3253f-105">Vaya a **Proveedores \> Configuración de pagos \> Cuota de pago**.</span><span class="sxs-lookup"><span data-stu-id="3253f-105">Go to **Accounts payable \> Payment setup \> Payment fee**.</span></span>

    <span data-ttu-id="3253f-106">[![Página de cuota de pago](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)</span><span class="sxs-lookup"><span data-stu-id="3253f-106">[![Payment fee page](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)</span></span>

2. <span data-ttu-id="3253f-107">Seleccione **Nuevo** para crear una cuota de pago y especificar los detalles necesarios.</span><span class="sxs-lookup"><span data-stu-id="3253f-107">Select **New** to create a payment fee, and enter the required details.</span></span>
3. <span data-ttu-id="3253f-108">En el campo **Tipo de cuota**, seleccione el tipo de cuota de pago:</span><span class="sxs-lookup"><span data-stu-id="3253f-108">In the **Fee type** field, select the type of payment fee:</span></span>

    - <span data-ttu-id="3253f-109">**None**</span><span class="sxs-lookup"><span data-stu-id="3253f-109">**None**</span></span>
    - <span data-ttu-id="3253f-110">**Interés**: se cobran intereses sobre los pagos atrasados que se realizan al proveedor de la autoridad de TDS.</span><span class="sxs-lookup"><span data-stu-id="3253f-110">**Interest** – Interest is charged on late payments that are made to the TDS authority vendor.</span></span>
    - <span data-ttu-id="3253f-111">**Otros**: se cobran otros cargos sobre los pagos atrasados que se realizan al proveedor de la autoridad de TDS.</span><span class="sxs-lookup"><span data-stu-id="3253f-111">**Others** – Other charges are charged on late payments that are made to the TDS authority vendor.</span></span>

    <span data-ttu-id="3253f-112">Si selecciona **Interés** u **Otros**, el campo **Cargo** se establece automáticamente en **Contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="3253f-112">If you select **Interest** or **Others**, the **Charge** field is automatically set to **Ledger**.</span></span>

4. <span data-ttu-id="3253f-113">Si ha seleccionado **Interés** u **Otros** en el campo **Tipo de campo**, en el campo **Cuenta principal**, seleccione la cuenta contable en la que se registrarán los intereses u otros cargos.</span><span class="sxs-lookup"><span data-stu-id="3253f-113">If you selected **Interest** or **Others** in the **Field type** field, in the **Main account** field, select the ledger account to post the interest or other charges to.</span></span>
5. <span data-ttu-id="3253f-114">Especifique los otros detalles.</span><span class="sxs-lookup"><span data-stu-id="3253f-114">Enter the other required details.</span></span>
6. <span data-ttu-id="3253f-115">En el panel de acciones, seleccione **Configuración de cuota de pago** para abrir la página **Configuración de cuota de pago**, donde puede configurar cuotas de pago para varias combinaciones de bancos, métodos de pago, especificaciones de pago, divisas e intervalos de fechas.</span><span class="sxs-lookup"><span data-stu-id="3253f-115">On the Action Pane, select **Payment fee setup** to open the **Payment fee setup** page, where you can set up payment fees for various combinations of banks, methods of payment, payment specifications, currencies, and date intervals.</span></span>

    <span data-ttu-id="3253f-116">[![Página de configuración de cuota de pago](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)</span><span class="sxs-lookup"><span data-stu-id="3253f-116">[![Payment fee setup page](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)</span></span>

7. <span data-ttu-id="3253f-117">En la pestaña **Información general**, en el campo **Agrupaciones**, especifique para qué bancos está configurando la cuota de pago:</span><span class="sxs-lookup"><span data-stu-id="3253f-117">On the **Overview** tab, in the **Groupings** field, specify which banks you're setting up the payment fee for:</span></span>

    - <span data-ttu-id="3253f-118">**Tabla**: la tarifa es válida para una cuenta bancaria específica.</span><span class="sxs-lookup"><span data-stu-id="3253f-118">**Table** – The fee is valid for a specific bank account.</span></span>
    - <span data-ttu-id="3253f-119">**Grupo**: la tarifa es válida para un grupo bancario específico.</span><span class="sxs-lookup"><span data-stu-id="3253f-119">**Group** – The fee is valid for a specific bank group.</span></span>
    - <span data-ttu-id="3253f-120">**Todos**: la cuota es válida para todas las cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="3253f-120">**All** – The fee is valid for all the bank accounts.</span></span>

8. <span data-ttu-id="3253f-121">Si ha seleccionado **Tabla** o **Grupo** en el campo **Agrupaciones**, en el campo **Relación del banco**, seleccione la cuenta bancaria o el grupo bancario específicos para los que está configurando la cuota de pago.</span><span class="sxs-lookup"><span data-stu-id="3253f-121">If you selected **Table** or **Group** in the **Groupings** field, in the **Bank relation** field, select the specific bank account or bank group that you're setting up the payment fee for.</span></span>
9. <span data-ttu-id="3253f-122">En el campo **Método de pago**, seleccione el método de pago que se usará para el pago de las cuotas.</span><span class="sxs-lookup"><span data-stu-id="3253f-122">In the **Method of payment** field, select the method of payment for the payment of fees.</span></span>
10. <span data-ttu-id="3253f-123">En el campo **Especificación del pago**, seleccione o introduzca el código de especificación de pago que se generó en la página **Especificación de pago**.</span><span class="sxs-lookup"><span data-stu-id="3253f-123">In the **Payment specification** field, select or enter the payment specification code that was generated on the **Payment specification** page.</span></span>
    - <span data-ttu-id="3253f-124">Especificación del pago se utiliza con formas de pago de transferencia electrónica de fondos.</span><span class="sxs-lookup"><span data-stu-id="3253f-124">The Payment specification is used with electronic fund transfer methods of payment.</span></span>
12. <span data-ttu-id="3253f-125">En el campo **Divisa de pago**, seleccione la divisa que activa la cuota.</span><span class="sxs-lookup"><span data-stu-id="3253f-125">In the **Payment currency** field, select the currency that activates the fee.</span></span> <span data-ttu-id="3253f-126">Solo las transacciones que usan la divisa seleccionada pueden activar la cuota.</span><span class="sxs-lookup"><span data-stu-id="3253f-126">Only transactions that use the selected currency can activate the fee.</span></span> <span data-ttu-id="3253f-127">Si deja este campo en blanco, todas las divisas activan la cuota.</span><span class="sxs-lookup"><span data-stu-id="3253f-127">If you leave this field blank, all currencies activate the fee.</span></span>
13. <span data-ttu-id="3253f-128">En el campo **Porcentaje/Importe**, seleccione el método de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3253f-128">In the **Percentage/Amount** field, select the calculation method.</span></span> <span data-ttu-id="3253f-129">Las opciones son **Importe**, **Porcentaje** e **Intervalo**.</span><span class="sxs-lookup"><span data-stu-id="3253f-129">The options are **Amount**, **Percent**, and **Interval**.</span></span>
14. <span data-ttu-id="3253f-130">En el campo **Importe de la cuota**, especifique el importe de la cuota como un porcentaje del pago o el importe de un pago.</span><span class="sxs-lookup"><span data-stu-id="3253f-130">In the **Fee amount** field, specify the fee amount as either a percentage of the payment or the amount for one payment.</span></span>
15. <span data-ttu-id="3253f-131">En el campo **Divisa de cuota**, seleccione el código de divisa para la cuota.</span><span class="sxs-lookup"><span data-stu-id="3253f-131">In the **Fee currency** field, specify the currency code for the fee.</span></span>
16. <span data-ttu-id="3253f-132">Seleccione la pestaña **General** para ver o modificar los detalles de la cuenta bancaria seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3253f-132">Select the **General** tab to view or modify the details for the selected bank account.</span></span>

    <span data-ttu-id="3253f-133">[![Pestaña General](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)</span><span class="sxs-lookup"><span data-stu-id="3253f-133">[![General tab](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)</span></span>

16. <span data-ttu-id="3253f-134">En el campo **Mínimo**, introduzca el importe mínimo de transacción que activa la cuota.</span><span class="sxs-lookup"><span data-stu-id="3253f-134">In the **Minimum** field, enter the minimum transaction amount that activates the fee.</span></span>
17. <span data-ttu-id="3253f-135">En el campo **Máximo**, introduzca el importe máximo de transacción que activa la cuota.</span><span class="sxs-lookup"><span data-stu-id="3253f-135">In the **Maximum** field, enter the maximum transaction amount that activates the fee.</span></span>
18. <span data-ttu-id="3253f-136">En los campos **Fecha inicial** y **Fecha final**, defina un rango de fechas para calcular las cuotas.</span><span class="sxs-lookup"><span data-stu-id="3253f-136">In the **From date** and **To date** fields, define a date range for calculating fees.</span></span>
19. <span data-ttu-id="3253f-137">En el campo **Cuota mínima**, especifique el importe de la cuota como un porcentaje del pago o el importe de un pago.</span><span class="sxs-lookup"><span data-stu-id="3253f-137">In the **Minimum fee** field, specify the amount of the fee as either a percentage of the payment or the amount for one payment.</span></span>
20. <span data-ttu-id="3253f-138">En el campo **Grupo de impuestos**, seleccione el grupo de impuestos que se utilizará para calcular el impuesto para el importe de la cuota.</span><span class="sxs-lookup"><span data-stu-id="3253f-138">In the **Sales tax group** field, select the sales tax group to use to calculate the sales tax for the fee amount.</span></span>
21. <span data-ttu-id="3253f-139">En el campo **Grupo de impuestos de artículos**, seleccione el grupo de impuestos de artíuclos que se utilizará para calcular el impuesto de artículos para el importe de la cuota.</span><span class="sxs-lookup"><span data-stu-id="3253f-139">In the **Item sales tax group** field, select the item sales tax group to use to calculate the item sales tax for the fee amount.</span></span>
22. <span data-ttu-id="3253f-140">Seleccione la pestaña **Intervalo**.</span><span class="sxs-lookup"><span data-stu-id="3253f-140">Select the **Interval** tab.</span></span> 

    <span data-ttu-id="3253f-141">[![Pestaña de intervalo](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)</span><span class="sxs-lookup"><span data-stu-id="3253f-141">[![Interval tab](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)</span></span>

23. <span data-ttu-id="3253f-142">En el campo **Días**, especifique el número de días entre la fecha de registro (fecha de descuento) del pago y la fecha de vencimiento del pagaré.</span><span class="sxs-lookup"><span data-stu-id="3253f-142">In the **Days** field, enter the number of days between the posting date (discounting date) of the payment and the due date of the promissory note.</span></span>
24. <span data-ttu-id="3253f-143">En el campo **Porcentaje/Importe**, seleccione si la especificación es un porcentaje o una cantidad fija.</span><span class="sxs-lookup"><span data-stu-id="3253f-143">In the **Percentage/Amount** field, select whether the specification is a percentage or a set amount.</span></span>
25. <span data-ttu-id="3253f-144">En el campo **Importe de la cuota**, introduzca el importe de la cuota como un porcentaje del pago o el importe de un pago.</span><span class="sxs-lookup"><span data-stu-id="3253f-144">In the **Fee amount** field, enter the amount of the fee as either a percentage of the payment or the amount for one payment.</span></span>
26. <span data-ttu-id="3253f-145">Cierre la página **Configuración de cuota de pago**.</span><span class="sxs-lookup"><span data-stu-id="3253f-145">Close the **Payment fee setup** page.</span></span>
27. <span data-ttu-id="3253f-146">Cierre la página **Cuota de pago**.</span><span class="sxs-lookup"><span data-stu-id="3253f-146">Close the **Payment fee** page.</span></span>
