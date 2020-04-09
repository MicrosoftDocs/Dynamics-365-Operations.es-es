---
title: Depositar pagos de cliente
description: Pagos de cliente en depósito.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1d903f557fbaeb720dd4a34dc1c772be0dcb56eb
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140199"
---
# <a name="deposit-customer-payments"></a><span data-ttu-id="726c3-103">Depositar pagos de cliente</span><span class="sxs-lookup"><span data-stu-id="726c3-103">Deposit customer payments</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="726c3-104">Pagos de cliente en depósito.</span><span class="sxs-lookup"><span data-stu-id="726c3-104">Deposit customer payments.</span></span> <span data-ttu-id="726c3-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="726c3-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="726c3-106">Vaya a **Panel de exploración > Módulos > Clientes > Pagos > Diario de pagos**.</span><span class="sxs-lookup"><span data-stu-id="726c3-106">Go to **Navigation pane > Modules > Accounts receivable > Payments > Payment journal**.</span></span>
2. <span data-ttu-id="726c3-107">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="726c3-107">Select **New**.</span></span>
3. <span data-ttu-id="726c3-108">En el campo **Nombre**, seleccione **CustPay** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="726c3-108">In the **Name** field, select **CustPay** in the drop-down menu.</span></span>
4. <span data-ttu-id="726c3-109">Seleccionar **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="726c3-109">Select **Lines**.</span></span>
5. <span data-ttu-id="726c3-110">En el campo **Cuenta**, seleccione el cliente para el que esté registrando el pago.</span><span class="sxs-lookup"><span data-stu-id="726c3-110">In the **Account** field, select the customer for whom you are recording the payment.</span></span>
6. <span data-ttu-id="726c3-111">En el campo **Crédito**, especifique el importe del pago.</span><span class="sxs-lookup"><span data-stu-id="726c3-111">In the **Credit** field, enter the amount of the payment.</span></span> <span data-ttu-id="726c3-112">Puede elegir dejar el importe en blanco y hacer que el sistema lo calcule seleccionando las facturas pagadas.</span><span class="sxs-lookup"><span data-stu-id="726c3-112">You can choose to leave the amount blank, and have the system calculate it by selecting the invoices which were paid.</span></span>  
7. <span data-ttu-id="726c3-113">En el campo **Referencia del pago**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="726c3-113">In the **Payment reference** field, type a value.</span></span> <span data-ttu-id="726c3-114">La referencia de pago podría ser el número de cheque para el pago que se está introduciendo.</span><span class="sxs-lookup"><span data-stu-id="726c3-114">The payment reference could be the check number for the payment you are entering.</span></span> <span data-ttu-id="726c3-115">La referencia de pago es obligatoria para incluir el pago en un resguardo de depósito.</span><span class="sxs-lookup"><span data-stu-id="726c3-115">The payment reference is required in order to include the payment on a deposit slip.</span></span>  
8. <span data-ttu-id="726c3-116">Marque el cuadro Utilizar un resguardo del depósito.</span><span class="sxs-lookup"><span data-stu-id="726c3-116">Mark the box Use a deposit slip.</span></span> <span data-ttu-id="726c3-117">Si el pago debe incluirse en el depósito, cambie este ajuste a Sí.</span><span class="sxs-lookup"><span data-stu-id="726c3-117">If the payment should be included in the deposit, change this setting to Yes.</span></span>  
9. <span data-ttu-id="726c3-118">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="726c3-118">Select **New**.</span></span>
10. <span data-ttu-id="726c3-119">En el campo **Cuenta**, seleccione el cliente para el siguiente pago.</span><span class="sxs-lookup"><span data-stu-id="726c3-119">In the **Account** field, select the customer for the next payment.</span></span>
11. <span data-ttu-id="726c3-120">En el campo **Crédito**, especifique el importe del pago.</span><span class="sxs-lookup"><span data-stu-id="726c3-120">In the **Credit** field, enter the payment amount.</span></span>
12. <span data-ttu-id="726c3-121">En el campo **Referencia del pago**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="726c3-121">In the **Payment reference** field, type a value.</span></span>
13. <span data-ttu-id="726c3-122">Marque el cuadro **Utilizar un resguardo del depósito**.</span><span class="sxs-lookup"><span data-stu-id="726c3-122">Mark the box **Use a deposit slip**.</span></span>
14. <span data-ttu-id="726c3-123">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="726c3-123">Select **Post**.</span></span> <span data-ttu-id="726c3-124">Los pagos deben registrarse para poder generar el resguardo de depósito.</span><span class="sxs-lookup"><span data-stu-id="726c3-124">Payments must be posted before the deposit slip can be generated.</span></span> <span data-ttu-id="726c3-125">Esto es así para garantizar que los pagos no cambian después de generarse el resguardo de depósito.</span><span class="sxs-lookup"><span data-stu-id="726c3-125">This is to ensure that the payments don't change after the deposit slip is generated.</span></span>  
15. <span data-ttu-id="726c3-126">Seleccione **Funciones**.</span><span class="sxs-lookup"><span data-stu-id="726c3-126">Select **Functions**.</span></span>
16. <span data-ttu-id="726c3-127">Seleccione **Resguardo de depósito**.</span><span class="sxs-lookup"><span data-stu-id="726c3-127">Select **Deposit slip**.</span></span>
17. <span data-ttu-id="726c3-128">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="726c3-128">Select **OK**.</span></span> <span data-ttu-id="726c3-129">La primera página que se usa para crear el resguardo de depósito.</span><span class="sxs-lookup"><span data-stu-id="726c3-129">The first page is used to create the deposit slip.</span></span>  
18. <span data-ttu-id="726c3-130">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="726c3-130">Select **OK**.</span></span> <span data-ttu-id="726c3-131">El segundo paso es imprimir el resguardo de depósito, si bien este paso no es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="726c3-131">The second step is to print the deposit slip, but this step is not required.</span></span>  

