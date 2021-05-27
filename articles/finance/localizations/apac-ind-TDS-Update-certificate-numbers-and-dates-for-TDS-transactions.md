---
title: Actualizar números y fechas de certificados para transacciones de TDS
description: Este tema explica cómo actualizar los certificados recuperables para registrar los números y las fechas de los certificados que se registraron para cuentas de proveedor, cliente y contables con impuestos deducidos en el origen (TDS).
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
ms.openlocfilehash: 248de8e12703a84482b67d0899857a6efb33531c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023564"
---
# <a name="update-certificate-numbers-and-dates-for-tds-transactions"></a><span data-ttu-id="de249-103">Actualizar números y fechas de certificados para transacciones de TDS</span><span class="sxs-lookup"><span data-stu-id="de249-103">Update certificate numbers and dates for TDS transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="de249-104">Este tema explica cómo actualizar los certificados recuperables para registrar los números y las fechas de los certificados que se registraron para cuentas de proveedor, cliente y contables con impuestos deducidos en el origen (TDS).</span><span class="sxs-lookup"><span data-stu-id="de249-104">This topic explains how to update the recoverable certificate numbers and dates that were recorded for vendor, customer, and ledger accounts for Tax Deducted at Source (TDS).</span></span> <span data-ttu-id="de249-105">Puede ver los certificados para transacciones de TDS en la página **Certificados recuperables**.</span><span class="sxs-lookup"><span data-stu-id="de249-105">You can view the certificates for TDS transactions on the **Recoverable certificates** page.</span></span> <span data-ttu-id="de249-106">Puede actualizar los certificados utilizando el la página **Actualizar certificados**.</span><span class="sxs-lookup"><span data-stu-id="de249-106">You can update the certificates by using the **Update Certificates** page.</span></span>

<span data-ttu-id="de249-107">Siga estos pasos para actualizar los números y fechas de certificados para transacciones de TDS.</span><span class="sxs-lookup"><span data-stu-id="de249-107">Follow these steps to update certificate numbers and dates for TDS transactions.</span></span>

1. <span data-ttu-id="de249-108">Vaya a **Impuesto \> Declaraciones \> Retención de impuestos \> Actualizar certificado**.</span><span class="sxs-lookup"><span data-stu-id="de249-108">Go to **Tax \> Declarations \> Withholding tax \> Update certificate**.</span></span>

    <span data-ttu-id="de249-109">[![Página Actualizar certificado](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)</span><span class="sxs-lookup"><span data-stu-id="de249-109">[![Update certificate page](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)</span></span>

2. <span data-ttu-id="de249-110">En la página **Actualizar certificado**, en la sección **Seleccionar**, en el campo **Tipo de impuesto**, seleccione **TDS**.</span><span class="sxs-lookup"><span data-stu-id="de249-110">On the **Update certificate** page, in the **Select** section, in the **Tax type** field, select **TDS**.</span></span>
3. <span data-ttu-id="de249-111">En el campo **Número de certificado**, seleccione el número de certificado de TDS del cliente o del proveedor.</span><span class="sxs-lookup"><span data-stu-id="de249-111">In the **Certificate number** field, select the customer's or vendor's TDS certificate number.</span></span>

    > [!NOTE]
    > <span data-ttu-id="de249-112">El campo **Número de certificado** enumera solo los números de certificado de TDS para los que se ha marcado la casilla **Cerrado** en la página **Certificados recuperables**.</span><span class="sxs-lookup"><span data-stu-id="de249-112">The **Certificate number** field lists only TDS certificate numbers that the **Closed** check box is cleared for on the **Recoverable certificates** page.</span></span>

    <span data-ttu-id="de249-113">El campo **Fecha del certificado** muestra la fecha del certificado.</span><span class="sxs-lookup"><span data-stu-id="de249-113">The **Certificate date** field shows the certificate date.</span></span> <span data-ttu-id="de249-114">El campo **Tipo de cuenta** muestra el tipo de cuenta para la que se recibe el número de certificado de TDS y el campo **Nombre** muestra el nombre de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="de249-114">The **Account type** field shows the type of account that the TDS certificate number is received for, and the **Name** field shows the name of the account.</span></span>

5. <span data-ttu-id="de249-115">En los campos **Fecha inicial** y **Fecha final**, seleccione las fechas iniciales y finales del período para mostrar las transacciones de TDS.</span><span class="sxs-lookup"><span data-stu-id="de249-115">In the **From date** and **To date** fields, select the start and end dates of the period to show the TDS transactions for.</span></span>
6. <span data-ttu-id="de249-116">Seleccione **Mostrar datos** para ver las transacciones de TDS que se registraron durante el período seleccionado.</span><span class="sxs-lookup"><span data-stu-id="de249-116">Select **Show data** to view the TDS transactions that were posted during the selected period.</span></span>

    <span data-ttu-id="de249-117">En la pestaña **Información general**, la cuadrícula en el panel superior muestra la siguiente información sobre cada transacción de TDS que se publicó para el proveedor o cliente durante el período seleccionado:</span><span class="sxs-lookup"><span data-stu-id="de249-117">On the **Overview** tab, the grid in the upper pane shows the following information about each TDS transaction that was posted for the vendor or customer during the selected period:</span></span>

    - <span data-ttu-id="de249-118">**Asiento**: el número de asiento de la transacción de TDS.</span><span class="sxs-lookup"><span data-stu-id="de249-118">**Voucher** – The voucher number of the TDS transaction.</span></span>
    - <span data-ttu-id="de249-119">**Fecha**: la fecha de la transacción de TDS.</span><span class="sxs-lookup"><span data-stu-id="de249-119">**Date** – The date of the TDS transaction.</span></span>
    - <span data-ttu-id="de249-120">**Importe**: el importe de la factura sobre el que se calcularón los TDS.</span><span class="sxs-lookup"><span data-stu-id="de249-120">**Amount** – The invoice amount that the TDS was calculated on.</span></span>
    - <span data-ttu-id="de249-121">**Importe del impuesto**: el importe del impuesto TDS que se calculó para la transacción.</span><span class="sxs-lookup"><span data-stu-id="de249-121">**Tax amount** – The TDS tax amount that was calculated for the transaction.</span></span>

7. <span data-ttu-id="de249-122">Para mover transacciones de TDS específicas de la cuadrícula superior a la cuadrícula inferior, seleccione las transacciones y luego seleccione **Incluir**.</span><span class="sxs-lookup"><span data-stu-id="de249-122">To move specific TDS transactions from the upper grid to the lower grid, select the transactions, and then select **Include**.</span></span> <span data-ttu-id="de249-123">Alternativamente, seleccione **Incluir todo** para mover todas las transacciones de TDS de la cuadrícula superior a la cuadrícula inferior.</span><span class="sxs-lookup"><span data-stu-id="de249-123">Alternatively, select **Include all** to move all TDS transactions from the upper grid to the lower grid.</span></span>

    <span data-ttu-id="de249-124">Para mover transacciones de TDS específicas o todas las transacciones de TDS de la cuadrícula inferior a la cuadrícula superior, use el botón **Excluir** o **Excluir todo**.</span><span class="sxs-lookup"><span data-stu-id="de249-124">To move specific TDS transactions or all TDS transactions from the lower grid to the upper grid, use the **Exclude** or **Exclude all** button.</span></span>

8. <span data-ttu-id="de249-125">Seleccione **Actualizar** para actualizar los campos **Número de certificado** y la **Fecha del certificado** para transacciones de TDS en la cuadrícula inferior.</span><span class="sxs-lookup"><span data-stu-id="de249-125">Select **Update** to update the **Certificate number** and **Certificate date** fields for TDS transactions in the lower grid.</span></span>
10. <span data-ttu-id="de249-126">Vaya a **Impuesto \> Impuestos indirectos \> Retención de impuestos \> Certificado recuperable** y seleccione **Consulta** para ver las líneas de transacciones actualizadas que tienen los nuevos números de certificado en la página **Transacciones de certificados**.</span><span class="sxs-lookup"><span data-stu-id="de249-126">Go to **Tax \> Indirect taxes \> Withholding tax \> Recoverable certificate**, and select **Inquiry** to view the updated transaction lines that have the new certificate numbers on the **Certificate transactions** page.</span></span>

    <span data-ttu-id="de249-127">[![Página Transacciones de certificados](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)</span><span class="sxs-lookup"><span data-stu-id="de249-127">[![Certificate transactions page](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)</span></span>
