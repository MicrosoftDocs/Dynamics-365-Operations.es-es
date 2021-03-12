---
title: Configurar descripciones predeterminadas para registro automático
description: En este tema se explica cómo configurar el texto predeterminado que se usa para describir los asientos contables que se registran automáticamente en la contabilidad general. Puede configurar el texto de la descripción predeterminada mediante el texto de forma libre o seleccionando variables fijas.
author: aprilolson
manager: AnnBe
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 222564
ms.assetid: ''
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d1b73b104ed8a8a015cb97dcf3055a648cfb083d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994749"
---
# <a name="set-up-default-descriptions-for-automatic-posting"></a><span data-ttu-id="98ee7-104">Configurar descripciones predeterminadas para registro automático</span><span class="sxs-lookup"><span data-stu-id="98ee7-104">Set up default descriptions for automatic posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="98ee7-105">En este tema se explica cómo configurar el texto predeterminado que se usa para describir los asientos contables que se registran automáticamente en la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="98ee7-105">This topic explains how to set up default text that is used to describe accounting entries that are posted automatically to the general ledger.</span></span> <span data-ttu-id="98ee7-106">Puede configurar el texto de la descripción predeterminada mediante el texto de forma libre o seleccionando variables fijas.</span><span class="sxs-lookup"><span data-stu-id="98ee7-106">You can set up default description text by using free-form text or by selecting fixed variables.</span></span>

> [!NOTE]
> <span data-ttu-id="98ee7-107">Para algunos tipos de transacciones de algunos países o regiones, también puede incluir texto de los campos de la base de datos de Microsoft Dynamics AX relacionados con dichos tipos de transacción.</span><span class="sxs-lookup"><span data-stu-id="98ee7-107">For some transaction types in some countries or regions, you can also include text from fields in the Microsoft Dynamics AX database that are related to those transaction types.</span></span> <span data-ttu-id="98ee7-108">Para obtener una lista de los tipos de transacciones, y los países y regiones, consulte la sección [Opcional: agregar otro texto a las descripciones predeterminadas](#optional-add-other-text-to-default-descriptions) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="98ee7-108">For a list of the transaction types, and the countries and regions, see the [Optional: Add other text to default descriptions](#optional-add-other-text-to-default-descriptions) section later in this topic.</span></span>

## <a name="set-up-default-descriptions"></a><span data-ttu-id="98ee7-109">Configurar descripciones predeterminadas</span><span class="sxs-lookup"><span data-stu-id="98ee7-109">Set up default descriptions</span></span>

1. <span data-ttu-id="98ee7-110">Vaya a **Administración de la organización** \> **Configurar** \> **Descripciones predeterminadas**.</span><span class="sxs-lookup"><span data-stu-id="98ee7-110">Go to **Organization administration** \> **Setup** \> **Default descriptions**.</span></span>
2. <span data-ttu-id="98ee7-111">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="98ee7-111">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="98ee7-112">En el campo **Descripción**, seleccione el tipo de transacción para el que desea crear una descripción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="98ee7-112">In the **Description** field, select the type of transaction to create a default description for.</span></span>
4. <span data-ttu-id="98ee7-113">En el campo **Idioma**, seleccione el idioma al que se aplica la descripción.</span><span class="sxs-lookup"><span data-stu-id="98ee7-113">In the **Language** field, select the language that the description applies to.</span></span>
5. <span data-ttu-id="98ee7-114">En el campo **Texto**, escriba la descripción predeterminada.</span><span class="sxs-lookup"><span data-stu-id="98ee7-114">In the **Text** field, enter the default description.</span></span> <span data-ttu-id="98ee7-115">Puede escribir texto en el campo o puede usar una o más de las siguientes variables de texto sin formato:</span><span class="sxs-lookup"><span data-stu-id="98ee7-115">You can type text in the field, or you can use one or more of the following free-text variables:</span></span>

    - <span data-ttu-id="98ee7-116">**%1**: agregar la fecha de la transacción.</span><span class="sxs-lookup"><span data-stu-id="98ee7-116">**%1** – Add the transaction date.</span></span>
    - <span data-ttu-id="98ee7-117">**%2**: agregar un identificador que corresponde con el tipo de documento que se está registrando en la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="98ee7-117">**%2** – Add an identifier that corresponds to the document type that is being posted to the general ledger.</span></span> <span data-ttu-id="98ee7-118">Por ejemplo, para los tipos de transacción que están relacionadas con las facturas, la variable **%2** agrega el número de factura.</span><span class="sxs-lookup"><span data-stu-id="98ee7-118">For example, for transaction types that are related to invoices, the **%2** variable adds the invoice number.</span></span>
    - <span data-ttu-id="98ee7-119">**%3**: agregar un identificador relacionado con el tipo de documento que se está registrando en la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="98ee7-119">**%3** – Add an identifier that is related to the document type that is being posted to the general ledger.</span></span> <span data-ttu-id="98ee7-120">Por ejemplo, para los tipos de transacción relacionados con las facturas, la variable **%3** agrega el número de cuenta del cliente.</span><span class="sxs-lookup"><span data-stu-id="98ee7-120">For example, for transaction types that are related to invoices, the **%3** variable adds the customer account number.</span></span>

## <a name="optional-add-other-text-to-default-descriptions"></a><span data-ttu-id="98ee7-121">Opcional: agregar otro texto a las descripciones predeterminadas</span><span class="sxs-lookup"><span data-stu-id="98ee7-121">Optional: Add other text to default descriptions</span></span>

<span data-ttu-id="98ee7-122">Para algunos tipos de transacciones de algunos países o regiones, las descripciones predeterminadas pueden incluir texto proveniente de campos de datos relacionados con dichos tipos de transacción.</span><span class="sxs-lookup"><span data-stu-id="98ee7-122">For some transaction types in some countries or regions, default descriptions can include text that comes from fields in your data that are related to those transaction types.</span></span> <span data-ttu-id="98ee7-123">En las listas siguientes se muestran tipos de transacción y los países o regiones para los que está disponible esta opción.</span><span class="sxs-lookup"><span data-stu-id="98ee7-123">The following lists show the transaction types, and the countries and regions, that this option is available for.</span></span>

<span data-ttu-id="98ee7-124">**Tipos de transacciones**</span><span class="sxs-lookup"><span data-stu-id="98ee7-124">**Transaction types**</span></span>

<span data-ttu-id="98ee7-125">Puede agregar otro texto a las descripciones predeterminadas para los tipos de transacción relacionados con los tipos de documentos siguientes:</span><span class="sxs-lookup"><span data-stu-id="98ee7-125">You can add other text to default descriptions for transaction types that are related to the following document types:</span></span>

- <span data-ttu-id="98ee7-126">Facturas del cliente</span><span class="sxs-lookup"><span data-stu-id="98ee7-126">Customer invoices</span></span>
- <span data-ttu-id="98ee7-127">Notas de abono de cliente</span><span class="sxs-lookup"><span data-stu-id="98ee7-127">Customer credit notes</span></span>
- <span data-ttu-id="98ee7-128">Pagos en efectivo de cliente</span><span class="sxs-lookup"><span data-stu-id="98ee7-128">Customer cash payments</span></span>
- <span data-ttu-id="98ee7-129">Pagos de proveedores</span><span class="sxs-lookup"><span data-stu-id="98ee7-129">Vendor payments</span></span>
- <span data-ttu-id="98ee7-130">Pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="98ee7-130">Sales orders</span></span>
- <span data-ttu-id="98ee7-131">Pedidos de compra</span><span class="sxs-lookup"><span data-stu-id="98ee7-131">Purchase orders</span></span>
- <span data-ttu-id="98ee7-132">Diarios de inventario</span><span class="sxs-lookup"><span data-stu-id="98ee7-132">Inventory journals</span></span>
- <span data-ttu-id="98ee7-133">Planificación maestra (MRP)</span><span class="sxs-lookup"><span data-stu-id="98ee7-133">Master planning (MRP)</span></span>
- <span data-ttu-id="98ee7-134">Activos fijos</span><span class="sxs-lookup"><span data-stu-id="98ee7-134">Fixed assets</span></span>

<span data-ttu-id="98ee7-135">**Países y regiones**</span><span class="sxs-lookup"><span data-stu-id="98ee7-135">**Countries and regions**</span></span>

<span data-ttu-id="98ee7-136">Esta opción está disponible para los siguientes países y regiones:</span><span class="sxs-lookup"><span data-stu-id="98ee7-136">This option is available for the following countries and regions:</span></span>

- <span data-ttu-id="98ee7-137">Brasil</span><span class="sxs-lookup"><span data-stu-id="98ee7-137">Brazil</span></span>
- <span data-ttu-id="98ee7-138">China</span><span class="sxs-lookup"><span data-stu-id="98ee7-138">China</span></span>
- <span data-ttu-id="98ee7-139">República Checa</span><span class="sxs-lookup"><span data-stu-id="98ee7-139">Czech Republic</span></span>
- <span data-ttu-id="98ee7-140">Europa del Este</span><span class="sxs-lookup"><span data-stu-id="98ee7-140">Eastern Europe</span></span>
- <span data-ttu-id="98ee7-141">Hungría</span><span class="sxs-lookup"><span data-stu-id="98ee7-141">Hungary</span></span>
- <span data-ttu-id="98ee7-142">India</span><span class="sxs-lookup"><span data-stu-id="98ee7-142">India</span></span>
- <span data-ttu-id="98ee7-143">Japón</span><span class="sxs-lookup"><span data-stu-id="98ee7-143">Japan</span></span>
- <span data-ttu-id="98ee7-144">Lituania</span><span class="sxs-lookup"><span data-stu-id="98ee7-144">Lithuania</span></span>
- <span data-ttu-id="98ee7-145">Letonia</span><span class="sxs-lookup"><span data-stu-id="98ee7-145">Latvia</span></span>
- <span data-ttu-id="98ee7-146">Polonia</span><span class="sxs-lookup"><span data-stu-id="98ee7-146">Poland</span></span>
- <span data-ttu-id="98ee7-147">Rusia</span><span class="sxs-lookup"><span data-stu-id="98ee7-147">Russia</span></span>

### <a name="add-text-to-default-descriptions"></a><span data-ttu-id="98ee7-148">Agregar otro texto a las descripciones predeterminadas</span><span class="sxs-lookup"><span data-stu-id="98ee7-148">Add text to default descriptions</span></span>

<span data-ttu-id="98ee7-149">Tras completar los pasos de la sección [Configurar descripciones predeterminadas](#set-up-default-descriptions) anterior de este tema, siga estos pasos para agregar otro texto a las descripciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="98ee7-149">After you complete the steps in the [Set up default descriptions](#set-up-default-descriptions) section earlier in this topic, follow these steps to add other text to the default descriptions.</span></span>

1. <span data-ttu-id="98ee7-150">En la ficha desplegable **Parámetros**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="98ee7-150">On the **Parameters** FastTab, select **Add**.</span></span>
2. <span data-ttu-id="98ee7-151">En el campo **Tabla de referencia**, seleccione la tabla de base de datos desde la que desea agregar datos de parámetros a la descripción.</span><span class="sxs-lookup"><span data-stu-id="98ee7-151">In the **Reference table** field, select the database table from which to add parameter data to the description.</span></span>
3. <span data-ttu-id="98ee7-152">En el campo **Campo de referencia**, seleccione el campo desde el que desea agregar datos de parámetros a la descripción.</span><span class="sxs-lookup"><span data-stu-id="98ee7-152">In the **Reference field** field, select the field from which to add parameter data to the description.</span></span>
4. <span data-ttu-id="98ee7-153">Repita los pasos del 1 al 3 para agregar más parámetros.</span><span class="sxs-lookup"><span data-stu-id="98ee7-153">Repeat steps 1 through 3 to add more parameters.</span></span>
