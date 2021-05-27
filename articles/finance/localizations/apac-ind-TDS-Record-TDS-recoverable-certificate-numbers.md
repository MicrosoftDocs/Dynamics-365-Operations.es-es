---
title: Registrar los números de los certificados recuperables de TDS
description: Este tema explica cómo usar la página de certificados recuperables para registrar los números de certificado y las fechas de los certificados con impuestos deducidos en el origen (TDS) que se reciben para un proveedor, cliente o contabilidad general específicos.
author: kailiang
mms.date: 02/12/2021
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
ms.openlocfilehash: b501c331cccc6d030f36d0a13ba0a6a13c08c733
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023554"
---
# <a name="record-tds-recoverable-certificate-numbers"></a><span data-ttu-id="3c2d1-103">Registrar los números de los certificados recuperables de TDS</span><span class="sxs-lookup"><span data-stu-id="3c2d1-103">Record TDS recoverable certificate numbers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3c2d1-104">Este tema explica cómo usar la página de **Certificados recuperables** para registrar los números de certificado y las fechas de los certificados con impuestos deducidos en el origen (TDS) que se reciben para un proveedor, cliente o contabilidad general específicos.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-104">This topic explains how to use the **Recoverable certificates** page to record the certificate numbers and dates for Tax Deducted at Source (TDS) certificates that are received for a specific vendor, customer, or ledger.</span></span> <span data-ttu-id="3c2d1-105">Para actualizar los números de certificado de TDS y las fechas que se registran para las transacciones de TDS en esta página, utilice la página **Actualizar certificado** (**Contabilidad general \> Periódica \> Retención de impuestos \> Actualizar certificado**).</span><span class="sxs-lookup"><span data-stu-id="3c2d1-105">To update the TDS certificate numbers and dates that are recorded for TDS transactions on this page, use the **Update certificate** page (**General ledger \> Periodic \> Withholding tax \> Update certificate**).</span></span> <span data-ttu-id="3c2d1-106">Una vez que hayan terminado de actualizar los números de certificado TDS, ciérrelos.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-106">After you've finished updating TDS certificate numbers, close them.</span></span>

<span data-ttu-id="3c2d1-107">Siga estos pasos para registrar los números y fechas del certificado TDS.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-107">Follow these steps to record the TDS certificate numbers and dates.</span></span>

1. <span data-ttu-id="3c2d1-108">Vaya a **Impuestos \> Impuesto indirecto \> Retención de impuestos \> Certificados recuperables**.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-108">Go to **Tax \> Indirect tax \> Withholding tax \> Recoverable certificates**.</span></span>

    <span data-ttu-id="3c2d1-109">[![Página de certificados recuperables](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png)</span><span class="sxs-lookup"><span data-stu-id="3c2d1-109">[![Recoverable certificates page](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png)</span></span> 

2. <span data-ttu-id="3c2d1-110">En la página **Certificados recuperables**, en el campo **Tipo de impuesto**, seleccione **TDS**.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-110">On the **Recoverable certificates** page, in the **Tax type** field, select **TDS**.</span></span>
3. <span data-ttu-id="3c2d1-111">Seleccione **Nuevo** para crear un registro.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-111">Select **New** to create a record.</span></span>
4. <span data-ttu-id="3c2d1-112">En el campo **Número de certificado**, introduzca el número del certificado de TDS.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-112">In the **Certificate number** field, enter the TDS certificate number.</span></span>
5. <span data-ttu-id="3c2d1-113">En el campo **Tipo de cuenta**, seleccione el tipo de cuenta para la que se recibe el certificado de TDS: **Proveedor**, **Cliente** o **Contabilidad general**.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-113">In the **Account type** field, select the type of account that the TDS certificate is received for: **Vendor**, **Customer**, or **Ledger**.</span></span>
6. <span data-ttu-id="3c2d1-114">En el campo **Cuenta**, seleccione el número de cuenta de proveedor, cliente o contabilidad general, según el tipo de cuenta que haya seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-114">In the **Account** field, select the vendor, customer, or ledger account number, depending on the account type that you selected.</span></span> <span data-ttu-id="3c2d1-115">El campo **Nombre** muestra el nombre del proveedor, cliente o cuenta contable.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-115">The **Name** field shows the name of the vendor, customer, or ledger account.</span></span>
7. <span data-ttu-id="3c2d1-116">En el campo **Importe del certificado**, introduzca el importe del certificado de TDS.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-116">In the **Certificate amount** field, enter the amount of the TDS certificate.</span></span>
8. <span data-ttu-id="3c2d1-117">En el campo **Fecha**, introduzca la fecha certificada del número del certificado.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-117">In the **Date** field, enter the certificate date for the certificate number.</span></span>
9. <span data-ttu-id="3c2d1-118">Seleccione **Consultas** para abrir la página **Transacciones de certificados**, donde puede ver las transacciones de TDS para las que se actualizan el número y la fecha del certificado de TDS.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-118">Select **Inquiries** to open the **Certificate transactions** page, where you can view the TDS transactions that the TDS certificate number and date are updated for.</span></span> <span data-ttu-id="3c2d1-119">Esta información se puede actualizar en la página **Actualizar certificado** (**Impuesto \> Declaraciones \> Retención de impuestos \> Actualizar certificado**).</span><span class="sxs-lookup"><span data-stu-id="3c2d1-119">This information can be updated on the **Update certificate** page (**Tax \> Declarations \> Withholding tax \> Update certificate**).</span></span>

    <span data-ttu-id="3c2d1-120">La página **Actualizar certificado** muestra la siguiente información para cada transacción de TDS:</span><span class="sxs-lookup"><span data-stu-id="3c2d1-120">The **Update certificate** page shows the following information for each TDS transaction:</span></span>

    - <span data-ttu-id="3c2d1-121">**Fecha**: la fecha de registro de la transacción de TDS.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-121">**Date** – The posting date of the TDS transaction.</span></span>
    - <span data-ttu-id="3c2d1-122">**Asiento**: el número de asiento de la transacción de TDS.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-122">**Voucher** – The voucher number of the TDS transaction.</span></span>
    - <span data-ttu-id="3c2d1-123">**Origen**: el módulo en el que se creó la transacción de TDS.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-123">**Source** – The module that the TDS transaction was created in.</span></span>
    - <span data-ttu-id="3c2d1-124">**Cuenta**: el número de cuenta de proveedor, cliente o cuenta contable para el que se creó la transacción de TDS.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-124">**Account** – The vendor, customer, or ledger account number that the TDS transaction was created for.</span></span>
    - <span data-ttu-id="3c2d1-125">**Nombre**: el número de cuenta de proveedor, cliente o cuenta contable para el que se creó la transacción de TDS.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-125">**Name** – The name of the vendor, customer, or ledger account that the TDS transaction was created for.</span></span>
    - <span data-ttu-id="3c2d1-126">**Importe**: el importe de la factura sobre el que se calcularón los TDS.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-126">**Amount** – The invoice amount that the TDS was calculated on.</span></span>
    - <span data-ttu-id="3c2d1-127">**Importe del impuesto**: el importe del impuesto TDS que se calculó para la transacción.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-127">**Tax amount** – The TDS tax amount that was calculated for the transaction.</span></span>
    - <span data-ttu-id="3c2d1-128">**Fecha del certificado**: la fecha del certificado de TDS que se actualizó para la transacción de TDS.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-128">**Certificate date** – The TDS certificate date that was updated for the TDS transaction.</span></span>
    - <span data-ttu-id="3c2d1-129">**Número del certificado**: el número del certificado de TDS que se actualizó para la transacción de TDS.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-129">**Certificate number** – TDS certificate number that was updated for the TDS transaction.</span></span>

10. <span data-ttu-id="3c2d1-130">En la página **Certificados recuperables**, seleccione la casilla **Cerrado** para cerrar el número de certificado de TDS después de que haya terminado de actualizarlo para transacciones de TDS en la página **Actualizar certificado**.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-130">On the **Recoverable certificates** page, select the **Closed** check box to close the TDS certificate number after you've finished updating it for TDS transactions on the **Update certificate** page.</span></span>

    <span data-ttu-id="3c2d1-131">Para seleccionar la casilla **Cerrado** para todos los registros de la página, seleccione **Marcar todo**.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-131">To select the **Closed** check box for all records on the page, select **Mark all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3c2d1-132">Los números de certificado de TDS con la casilla **Cerrado** seleccionada no están disponibles en la página **Actualizar certificado**.</span><span class="sxs-lookup"><span data-stu-id="3c2d1-132">TDS certificate numbers that the **Closed** check box is selected for aren't available on the **Update certificate** page.</span></span>
