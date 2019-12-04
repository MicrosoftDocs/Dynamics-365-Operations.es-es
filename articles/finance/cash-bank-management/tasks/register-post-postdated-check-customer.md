---
title: Registrar un cheque con pago diferido para un cliente
description: Puede registrar detalles de un cheque con fecha futura recibido de un cliente.
author: kweekley
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f27675a2aa2160619bf78eea33bba2ce0b7bd81
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188105"
---
# <a name="register-and-post-a-postdated-check-for-a-customer"></a><span data-ttu-id="7ad62-103">Registrar un cheque con pago diferido para un cliente</span><span class="sxs-lookup"><span data-stu-id="7ad62-103">Register and post a postdated check for a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7ad62-104">Puede registrar detalles de un cheque con fecha futura recibido de un cliente.</span><span class="sxs-lookup"><span data-stu-id="7ad62-104">You can register details of a postdated check received from a customer.</span></span> <span data-ttu-id="7ad62-105">También puede registrar los cheques con fecha futura y generar transacciones financieras.</span><span class="sxs-lookup"><span data-stu-id="7ad62-105">You can also post the postdated check and generate financial transactions.</span></span>   <span data-ttu-id="7ad62-106">Realice las tareas siguientes antes de registrar un cheque con fecha futura de un cliente:   • Configure cheques con fecha futura en la página Gestión de efectivo y bancos • Configure una forma de pago para los cheques con fecha futura   El rol para este procedimiento es Tesorero.</span><span class="sxs-lookup"><span data-stu-id="7ad62-106">Complete the following tasks before you register and post a postdated check received from a customer:   • Set up postdated check in the Cash and bank management page • Set up a method of payment for postdated checks   The role for this procedure is Treasurer.</span></span> <span data-ttu-id="7ad62-107">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="7ad62-107">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="7ad62-108">Vaya a Clientes > Pagos > Diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="7ad62-108">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="7ad62-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="7ad62-109">Click New.</span></span>
3. <span data-ttu-id="7ad62-110">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7ad62-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="7ad62-111">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="7ad62-111">Click Lines.</span></span>
5. <span data-ttu-id="7ad62-112">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7ad62-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="7ad62-113">En el campo Cuenta, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="7ad62-113">In the Account field, specify the desired values.</span></span>
7. <span data-ttu-id="7ad62-114">En el campo Crédito, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="7ad62-114">In the Credit field, enter a number.</span></span>
    * <span data-ttu-id="7ad62-115">Introduzca el importe especificado en el cheque con fecha futura.</span><span class="sxs-lookup"><span data-stu-id="7ad62-115">Enter the amount specified in the postdated check.</span></span>  
8. <span data-ttu-id="7ad62-116">Haga clic en la ficha Pago.</span><span class="sxs-lookup"><span data-stu-id="7ad62-116">Click the Payment tab.</span></span>
9. <span data-ttu-id="7ad62-117">En el campo Forma de pago, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7ad62-117">In the Method of payment field, type a value.</span></span>
    * <span data-ttu-id="7ad62-118">Seleccione la forma de pago del cheque con fecha futura.</span><span class="sxs-lookup"><span data-stu-id="7ad62-118">Select the method of payment for the postdated check.</span></span>  
10. <span data-ttu-id="7ad62-119">Haga clic en la ficha Cheques con fecha futura.</span><span class="sxs-lookup"><span data-stu-id="7ad62-119">Click the Postdated checks tab.</span></span>
11. <span data-ttu-id="7ad62-120">Especifique una fecha en el campo Fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="7ad62-120">In the Maturity date field, enter a date.</span></span>
    * <span data-ttu-id="7ad62-121">Indique la fecha en que vence el pago del cheque con fecha futura.</span><span class="sxs-lookup"><span data-stu-id="7ad62-121">Enter the date when the postdated check is due for payment.</span></span>  
12. <span data-ttu-id="7ad62-122">En el campo Sucursal bancaria emisora, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7ad62-122">In the Issuing bank branch field, type a value.</span></span>
    * <span data-ttu-id="7ad62-123">Especifique los detalles del banco del cheque con fecha futura.</span><span class="sxs-lookup"><span data-stu-id="7ad62-123">Enter the bank details of the postdated check.</span></span>  
13. <span data-ttu-id="7ad62-124">En el campo Número de cheque, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7ad62-124">In the check number field, type a value.</span></span>
14. <span data-ttu-id="7ad62-125">En el campo Nombre del banco emisor, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7ad62-125">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="7ad62-126">Especifique los detalles del banco del cheque con fecha futura.</span><span class="sxs-lookup"><span data-stu-id="7ad62-126">Enter the bank details of the postdated check.</span></span>  
15. <span data-ttu-id="7ad62-127">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="7ad62-127">Click Post.</span></span>
16. <span data-ttu-id="7ad62-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7ad62-128">Close the page.</span></span>
