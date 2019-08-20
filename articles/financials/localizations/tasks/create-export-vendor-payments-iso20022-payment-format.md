---
title: Creación y exportación de pagos de proveedor mediante el formato de pago de ISO20022
description: Este procedimiento muestra cómo crear líneas de pago en el diario de pago de proveedor y generar un archivo de pago de proveedor utilizando el ejemplo ISO2022 Transferencia de crédito.
author: mrolecki
manager: AnnBe
ms.date: 01/17/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b70ad94014587ba8e55735192dbe0ab2e4adf4ee
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2019
ms.locfileid: "1849000"
---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a><span data-ttu-id="ca6ae-103">Creación y exportación de pagos de proveedor mediante el formato de pago de ISO20022</span><span class="sxs-lookup"><span data-stu-id="ca6ae-103">Create and export vendor payments using ISO20022 payment format</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ca6ae-104">Este tema muestra cómo crear líneas de pago en el diario de pago de proveedor y generar un archivo de pago de proveedor utilizando el ejemplo ISO2022 Transferencia de crédito.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-104">This topic explains how to create payment lines in the vendor payment journal and generate a vendor payment file using ISO2022 Credit transfer example.</span></span>

<span data-ttu-id="ca6ae-105">Este es el quinto procedimiento, de cinco, que muestra el proceso de pago del proveedor mediante las configuraciones de informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-105">This is the fifth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="ca6ae-106">Use los datos de demostración de DEMF para completar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-106">Use the DEMF demo data to complete this example.</span></span>

## <a name="example"></a><span data-ttu-id="ca6ae-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca6ae-107">Example</span></span>

1.  <span data-ttu-id="ca6ae-108">Vaya a **Proveedores > Pagos > Diario de pagos**.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-108">Go to **Accounts payable > Payments > Payment journal**.</span></span>
2.  <span data-ttu-id="ca6ae-109">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-109">Click **New**.</span></span>
3.  <span data-ttu-id="ca6ae-110">En el campo **Nombre**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-110">In the **Name** field, enter or select a value.</span></span>
4.  <span data-ttu-id="ca6ae-111">Haga clic en **Líneas > Propuesta de pago > Crear propuesta de pago**.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-111">Click **Lines > Payment proposal > Create payment proposal**.</span></span>
5.  <span data-ttu-id="ca6ae-112">Expanda la sección **Registros que incluir**.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-112">Expand the **Records to include** section.</span></span>
6.  <span data-ttu-id="ca6ae-113">Haga clic en **Filtro.**</span><span class="sxs-lookup"><span data-stu-id="ca6ae-113">Click **Filter**.</span></span>
7.  <span data-ttu-id="ca6ae-114">En la lista, seleccione la fila para la **tabla Proveedores** y el **campo Cuenta de proveedor**.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-114">In the list, select the row for **Vendors table** and **Vendor account field**.</span></span>
8.  <span data-ttu-id="ca6ae-115">En el campo **Criterios**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-115">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="ca6ae-116">Puede aplicar cualquier criterio para seleccionar transacciones de proveedor para pagar, por ejemplo, use DE-001 como cuenta de proveedor.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-116">You can apply any criteria for selecting vendor transactions to pay, for this example, use DE-001 as a vendor account.</span></span>
12. <span data-ttu-id="ca6ae-117">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-117">Click **OK**.</span></span>
13. <span data-ttu-id="ca6ae-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-118">Click **OK**.</span></span>
14. <span data-ttu-id="ca6ae-119">Haga clic en **Crear pagos**.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-119">Click **Create payments**.</span></span>
15. <span data-ttu-id="ca6ae-120">Generación de un archivo de pago ISO20022.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-120">Generate an ISO20022 payment file.</span></span>
    1.  <span data-ttu-id="ca6ae-121">Haga clic en **Generar pagos**.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-121">Click **Generate payments**.</span></span>
    2.  <span data-ttu-id="ca6ae-122">En el campo **Método de pago**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-122">In the **Method of payment** field, enter or select a value.</span></span>
    3.  <span data-ttu-id="ca6ae-123">En el campo **Nombre de archivo**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-123">In the **File name** field, type a value.</span></span> <span data-ttu-id="ca6ae-124">Para este ejemplo, debido al pago de euros, el archivo generado cumplirá con la SEPA.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-124">For this example, because of the EUR payment, the generated file will be SEPA compliant.</span></span> <span data-ttu-id="ca6ae-125">La transferencia de crédito ISO20022 así como los formatos de pago de otro proveedor también se pueden utilizar para generar pagos en otras divisas.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-125">ISO20022 credit transfer as well as other vendor payment formats can also be used for generating payments in other currencies.</span></span>
    4.  <span data-ttu-id="ca6ae-126">En el campo **Cuenta bancaria**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ca6ae-126">In the **Bank account** field, enter or select a value.</span></span>

