---
title: Usar datos fiscales de la cuenta de factura
description: Para las entidades jurídicas en España, la funcionalidad Usar datos fiscales de cuenta de factura permite la actualización automática de datos fiscales de los pedidos de ventas, las facturas de texto sin formato y los pedidos de compra, en función de la información de la cuenta de facturación. Este tema proporciona información sobre la funcionalidad Usar datos fiscales de cuenta de factura y explica cómo configurarla.
author: ShylaThompson
manager: AnnBe
ms.date: 10/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, VendParameters
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265224
ms.search.region: Spain
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 805fc2e8fcadc9538e69a0e8d945cae3b52f4b8d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "370474"
---
# <a name="use-fiscal-data-from-the-invoice-account"></a><span data-ttu-id="97fd7-104">Usar datos fiscales de la cuenta de factura</span><span class="sxs-lookup"><span data-stu-id="97fd7-104">Use fiscal data from the invoice account</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="97fd7-105">Para las entidades jurídicas en España, la funcionalidad Usar datos fiscales de cuenta de factura permite la actualización automática de datos fiscales de los pedidos de ventas, las facturas de texto sin formato y los pedidos de compra, en función de la información de la cuenta de facturación.</span><span class="sxs-lookup"><span data-stu-id="97fd7-105">For legal entities in Spain, the Use fiscal data from invoice account functionality enables fiscal data on sales orders, free text invoices, and purchase orders to be updated automatically, based on information from the invoice account.</span></span> <span data-ttu-id="97fd7-106">Este tema proporciona información sobre la funcionalidad Usar datos fiscales de cuenta de factura y explica cómo configurarla.</span><span class="sxs-lookup"><span data-stu-id="97fd7-106">This topic provides information about the Use fiscal data from invoice account functionality and explains how to set it up.</span></span>

<span data-ttu-id="97fd7-107">Para las entidades jurídicas en España, la funcionalidad Usar datos fiscales de cuenta de factura permite la actualización automática de datos fiscales de los pedidos de ventas, las facturas de texto sin formato y los pedidos de compra, en función de la información de la cuenta de facturación.</span><span class="sxs-lookup"><span data-stu-id="97fd7-107">For legal entities in Spain, the Use fiscal data from invoice account functionality enables fiscal data on sales orders, free text invoices, and purchase orders to be updated automatically, based on information from the invoice account.</span></span> <span data-ttu-id="97fd7-108">Los datos fiscales que actualizan incluye el nombre del cliente o proveedor, la dirección y la información fiscal.</span><span class="sxs-lookup"><span data-stu-id="97fd7-108">The fiscal data that is updated includes the customer or vendor name, address, and tax information.</span></span> <span data-ttu-id="97fd7-109">La funcionalidad Usar datos fiscales de cuenta de factura afecta a los siguientes módulos:</span><span class="sxs-lookup"><span data-stu-id="97fd7-109">The Use fiscal data from invoice account functionality affects the following modules:</span></span>

-   <span data-ttu-id="97fd7-110">Proveedores Página de cambio **Cuenta de facturación**</span><span class="sxs-lookup"><span data-stu-id="97fd7-110">Accounts payable **Invoice account** change page</span></span>
-   <span data-ttu-id="97fd7-111">Adquisición y abastecimiento</span><span class="sxs-lookup"><span data-stu-id="97fd7-111">Procurement and sourcing</span></span>
-   <span data-ttu-id="97fd7-112">Clientes</span><span class="sxs-lookup"><span data-stu-id="97fd7-112">Accounts receivable</span></span>
-   <span data-ttu-id="97fd7-113">Ventas y marketing</span><span class="sxs-lookup"><span data-stu-id="97fd7-113">Sales and marketing</span></span>

## <a name="accounts-payable-and-procurement-and-sourcing"></a><span data-ttu-id="97fd7-114">Proveedores y Adquisición y abastecimiento</span><span class="sxs-lookup"><span data-stu-id="97fd7-114">Accounts payable and Procurement and sourcing</span></span>
<span data-ttu-id="97fd7-115">Para gestionar la oportunidad de actualización automática de datos fiscales en cambio de cuenta de facturación del módulo Proveedores, debe configurar un parámetro Usar datos fiscales de cuenta de factura en la ficha Factura de la página **Parámetros de proveedores**.</span><span class="sxs-lookup"><span data-stu-id="97fd7-115">To manage the opportunity of fiscal data automatic update on Invoice account change in the Accounts payable module you need to set up a parameter Use fiscal data from invoice account on Invoice tab of the **Account payable parameters** page.</span></span> <span data-ttu-id="97fd7-116">Las opciones siguientes están disponibles:</span><span class="sxs-lookup"><span data-stu-id="97fd7-116">The following options are available:</span></span>

-   <span data-ttu-id="97fd7-117">**Nunca**: la información se acualiza desde la cuenta del proveedor.</span><span class="sxs-lookup"><span data-stu-id="97fd7-117">**Never** – Information is updated from the vendor account.</span></span>
-   <span data-ttu-id="97fd7-118">**Siempre**: la información se acualiza desde la cuenta de facturación.</span><span class="sxs-lookup"><span data-stu-id="97fd7-118">**Always** – Information is updated from the invoice account.</span></span>
-   <span data-ttu-id="97fd7-119">**Preguntar**: Se le pide al usuario que especifique si la información debe actualizarse desde la cuenta de facturación o la del proveedor.</span><span class="sxs-lookup"><span data-stu-id="97fd7-119">**Ask** – The user is prompted to specify whether information should be updated from the invoice account or the vendor account.</span></span>

<span data-ttu-id="97fd7-120">Cuando se define el parámetro **Usar datos fiscales de cuenta de factura**, pueden actualizarse tres campos de una orden de compra en función del valor del parámetro.</span><span class="sxs-lookup"><span data-stu-id="97fd7-120">When the **Use fiscal data from invoice account** parameter is set, three fields on a purchase order may be updated according the value of the parameter.</span></span> <span data-ttu-id="97fd7-121">Cuando se modifica el campo **Cuenta de facturación**, los campos siguientes se actualizan con la información de la cuenta de facturación:</span><span class="sxs-lookup"><span data-stu-id="97fd7-121">When the **Invoice account** field is changed, the following fields are updated with information from the invoice account:</span></span>

-   <span data-ttu-id="97fd7-122">Nombre</span><span class="sxs-lookup"><span data-stu-id="97fd7-122">Name</span></span>
-   <span data-ttu-id="97fd7-123">Grupo de impuestos sobre las ventas</span><span class="sxs-lookup"><span data-stu-id="97fd7-123">Sales tax group</span></span>
-   <span data-ttu-id="97fd7-124">Exención fiscal</span><span class="sxs-lookup"><span data-stu-id="97fd7-124">Tax exemption</span></span>

## <a name="accounts-receivable-and-sales-and-marketing"></a><span data-ttu-id="97fd7-125">Clientes, ventas y marketing</span><span class="sxs-lookup"><span data-stu-id="97fd7-125">Accounts receivable and Sales and marketing</span></span>
<span data-ttu-id="97fd7-126">Para gestionar la oportunidad de actualización automática de datos fiscales en cambio de **Cuenta de facturación** del módulo **Proveedores**, debe configurar un parámetro "**Usar datos fiscales de cuenta de factura**" en la ficha desplegable **Factura** de la ficha **Actualizaciones** en la página **Parámetros de cliente**.</span><span class="sxs-lookup"><span data-stu-id="97fd7-126">To manage the opportunity of fiscal data automatic update on **Invoice account** change in the **Accounts receivable** module you need to set up a parameter “**Use fiscal data from invoice account**” on the **Invoice** fasttab of the **Updates** tab of the **Account receivable parameters** page.</span></span> <span data-ttu-id="97fd7-127">Las opciones siguientes están disponibles:</span><span class="sxs-lookup"><span data-stu-id="97fd7-127">The following options are available:</span></span>

-   <span data-ttu-id="97fd7-128">**Nunca**: la información se acualiza desde la cuenta del cliente.</span><span class="sxs-lookup"><span data-stu-id="97fd7-128">**Never** – Information is updated from the customer account.</span></span>
-   <span data-ttu-id="97fd7-129">**Siempre**: la información se acualiza desde la cuenta de facturación.</span><span class="sxs-lookup"><span data-stu-id="97fd7-129">**Always** – Information is updated from the invoice account.</span></span>
-   <span data-ttu-id="97fd7-130">**Preguntar**: Se le pide al usuario que especifique si la información debe actualizarse desde la cuenta de facturación o la del cliente.</span><span class="sxs-lookup"><span data-stu-id="97fd7-130">**Ask** – The user is prompted to specify whether information should be updated from the invoice account or the customer account.</span></span>

<span data-ttu-id="97fd7-131">Cuando se establece el parámetro **Usar datos fiscales de cuenta de factura**, es posible actualizar los documentos siguientes desde Clientes:</span><span class="sxs-lookup"><span data-stu-id="97fd7-131">When the **Use fiscal data from invoice account** parameter is set, the following documents from Accounts receivable can be updated:</span></span>

-   <span data-ttu-id="97fd7-132">Pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="97fd7-132">Sales orders</span></span>
-   <span data-ttu-id="97fd7-133">Facturas de servicios</span><span class="sxs-lookup"><span data-stu-id="97fd7-133">Free text invoices</span></span>

<span data-ttu-id="97fd7-134">Cuando se modifica el campo **Cuenta de facturación**, los campos siguientes pueden actualizarse con la información de la cuenta de facturación:</span><span class="sxs-lookup"><span data-stu-id="97fd7-134">When the **Invoice account** field is changed, the following fields can be updated with information from the invoice account:</span></span>

-   <span data-ttu-id="97fd7-135">Nombre</span><span class="sxs-lookup"><span data-stu-id="97fd7-135">Name</span></span>
-   <span data-ttu-id="97fd7-136">Grupo de impuestos sobre las ventas</span><span class="sxs-lookup"><span data-stu-id="97fd7-136">Sales tax group</span></span>
-   <span data-ttu-id="97fd7-137">Exención fiscal</span><span class="sxs-lookup"><span data-stu-id="97fd7-137">Tax exemption</span></span>




