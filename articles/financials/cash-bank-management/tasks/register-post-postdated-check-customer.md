--- 
title: Registrar un cheque con pago diferido para un cliente
description: Puede registrar detalles de un cheque con fecha futura recibido de un cliente.
author: kweekley
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: d1e3df13c644ffa39621e73d1c907084bbd7ba7c
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="register-and-post-a-postdated-check-for-a-customer"></a><span data-ttu-id="67640-103">Registrar un cheque con pago diferido para un cliente</span><span class="sxs-lookup"><span data-stu-id="67640-103">Register and post a postdated check for a customer</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="67640-104">Puede registrar detalles de un cheque con fecha futura recibido de un cliente.</span><span class="sxs-lookup"><span data-stu-id="67640-104">You can register details of a postdated check received from a customer.</span></span> <span data-ttu-id="67640-105">También puede registrar los cheques con fecha futura y generar transacciones financieras.</span><span class="sxs-lookup"><span data-stu-id="67640-105">You can also post the postdated check and generate financial transactions.</span></span>   <span data-ttu-id="67640-106">Realice las tareas siguientes antes de registrar un cheque con fecha futura de un cliente:   • Configure cheques con fecha futura en la página Gestión de efectivo y bancos • Configure una forma de pago para los cheques con fecha futura   El rol para este procedimiento es Tesorero.</span><span class="sxs-lookup"><span data-stu-id="67640-106">Complete the following tasks before you register and post a postdated check received from a customer:   • Set up postdated check in the Cash and bank management page • Set up a method of payment for postdated checks   The role for this procedure is Treasurer.</span></span> <span data-ttu-id="67640-107">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="67640-107">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="67640-108">Vaya a Clientes > Pagos > Diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="67640-108">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="67640-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="67640-109">Click New.</span></span>
3. <span data-ttu-id="67640-110">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="67640-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="67640-111">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="67640-111">Click Lines.</span></span>
5. <span data-ttu-id="67640-112">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="67640-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="67640-113">En el campo Cuenta, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="67640-113">In the Account field, specify the desired values.</span></span>
7. <span data-ttu-id="67640-114">En el campo Crédito, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="67640-114">In the Credit field, enter a number.</span></span>
    * <span data-ttu-id="67640-115">Introduzca el importe especificado en el cheque con fecha futura.</span><span class="sxs-lookup"><span data-stu-id="67640-115">Enter the amount specified in the postdated check.</span></span>  
8. <span data-ttu-id="67640-116">Haga clic en la ficha Pago.</span><span class="sxs-lookup"><span data-stu-id="67640-116">Click the Payment tab.</span></span>
9. <span data-ttu-id="67640-117">En el campo Forma de pago, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="67640-117">In the Method of payment field, type a value.</span></span>
    * <span data-ttu-id="67640-118">Seleccione la forma de pago del cheque con fecha futura.</span><span class="sxs-lookup"><span data-stu-id="67640-118">Select the method of payment for the postdated check.</span></span>  
10. <span data-ttu-id="67640-119">Haga clic en la ficha Cheques con fecha futura.</span><span class="sxs-lookup"><span data-stu-id="67640-119">Click the Postdated checks tab.</span></span>
11. <span data-ttu-id="67640-120">Especifique una fecha en el campo Fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="67640-120">In the Maturity date field, enter a date.</span></span>
    * <span data-ttu-id="67640-121">Indique la fecha en que vence el pago del cheque con fecha futura.</span><span class="sxs-lookup"><span data-stu-id="67640-121">Enter the date when the postdated check is due for payment.</span></span>  
12. <span data-ttu-id="67640-122">En el campo Sucursal bancaria emisora, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="67640-122">In the Issuing bank branch field, type a value.</span></span>
    * <span data-ttu-id="67640-123">Especifique los detalles del banco del cheque con fecha futura.</span><span class="sxs-lookup"><span data-stu-id="67640-123">Enter the bank details of the postdated check.</span></span>  
13. <span data-ttu-id="67640-124">En el campo Número de cheque, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="67640-124">In the check number field, type a value.</span></span>
14. <span data-ttu-id="67640-125">En el campo Nombre del banco emisor, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="67640-125">In the Issuing bank name field, type a value.</span></span>
    * <span data-ttu-id="67640-126">Especifique los detalles del banco del cheque con fecha futura.</span><span class="sxs-lookup"><span data-stu-id="67640-126">Enter the bank details of the postdated check.</span></span>  
15. <span data-ttu-id="67640-127">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="67640-127">Click Post.</span></span>
16. <span data-ttu-id="67640-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="67640-128">Close the page.</span></span>


