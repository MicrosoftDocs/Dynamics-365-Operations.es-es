--- 
title: Procesamiento de devoluciones para pago
description: "Este procedimiento muestra cómo convertir en notas de abono devoluciones de cliente aprobadas y procesadas."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 791ec304b9ea7c49fbea506d73c4daffd4478739
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="process-rebates-for-payment"></a><span data-ttu-id="27060-103">Procesamiento de devoluciones para pago</span><span class="sxs-lookup"><span data-stu-id="27060-103">Process rebates for payment</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="27060-104">Este procedimiento muestra cómo convertir en notas de abono devoluciones de cliente aprobadas y procesadas.</span><span class="sxs-lookup"><span data-stu-id="27060-104">This procedure demonstrates how to convert approved and processed customer rebates to credit notes.</span></span> <span data-ttu-id="27060-105">Puede ejecutar este procedimiento en la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="27060-105">You can use this guide in the USMF demo company.</span></span> <span data-ttu-id="27060-106">La condición previa para este procedimiento es tener una o más reclamaciones de devolución con estado Marcar.</span><span class="sxs-lookup"><span data-stu-id="27060-106">The precondition for this guide is to have one or more rebate claims which have a status of Mark.</span></span> <span data-ttu-id="27060-107">Si está usando USMF, debe ejecutar el procedimiento "Generación y procesamiento de devoluciones de cliente" antes de comenzar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="27060-107">If you’re using USMF you should run the "Generate and process customer rebates" guide before you start this guide.</span></span>


## <a name="convert-rebate-claims-to-credit-note"></a><span data-ttu-id="27060-108">Conversión de reclamaciones de devolución en notas de abono</span><span class="sxs-lookup"><span data-stu-id="27060-108">Convert rebate claims to credit note</span></span>
1. <span data-ttu-id="27060-109">Vaya a Todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="27060-109">Go to All customers.</span></span>
2. <span data-ttu-id="27060-110">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="27060-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="27060-111">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="27060-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="27060-112">En el panel de acciones, haga clic en Cobrar.</span><span class="sxs-lookup"><span data-stu-id="27060-112">On the Action Pane, click Collect.</span></span>
5. <span data-ttu-id="27060-113">Haga clic en Liquidar transacciones.</span><span class="sxs-lookup"><span data-stu-id="27060-113">Click Settle transactions.</span></span>
6. <span data-ttu-id="27060-114">Haga clic en Funciones.</span><span class="sxs-lookup"><span data-stu-id="27060-114">Click Functions.</span></span>
7. <span data-ttu-id="27060-115">Haga clic en Programa de devoluciones.</span><span class="sxs-lookup"><span data-stu-id="27060-115">Click Rebate program.</span></span>
    * <span data-ttu-id="27060-116">La página Devolución muestra las reclamaciones de devolución que ha procesado en el área de trabajo de devoluciones de cliente y que se encuentran en estado Marcar.</span><span class="sxs-lookup"><span data-stu-id="27060-116">The Rebate page lists the rebate claims that you have processed in the customer rebate workbench and that are in status Mark.</span></span>    
8. <span data-ttu-id="27060-117">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="27060-117">Click Edit.</span></span>
    * <span data-ttu-id="27060-118">Defina las marcas de verificación del campo Marcar para las reclamaciones que desee incluir en nota de abono.</span><span class="sxs-lookup"><span data-stu-id="27060-118">Set checkmarks in the Mark field for the claims that you want to include into credit note.</span></span>   
9. <span data-ttu-id="27060-119">Haga clic en Funciones.</span><span class="sxs-lookup"><span data-stu-id="27060-119">Click Functions.</span></span>
10. <span data-ttu-id="27060-120">Haga clic en Crear nota de abono.</span><span class="sxs-lookup"><span data-stu-id="27060-120">Click Create credit note.</span></span>
    * <span data-ttu-id="27060-121">Aparece un mensaje para informarle de que se ha registrado un diario (este es el diario de consumo de clientes, como se haya especificado en la página de parámetros de clientes).</span><span class="sxs-lookup"><span data-stu-id="27060-121">A message appears to inform you that a journal has been posted (This is the Accounts receivable consumption journal, as specified in the Accounts receivable parameters page).</span></span> <span data-ttu-id="27060-122">Esto hace que el importe real de pasivos (crédito) se desplace al saldo del cliente.</span><span class="sxs-lookup"><span data-stu-id="27060-122">This causes the real liability (credit) amount to be moved to the customer balance.</span></span> <span data-ttu-id="27060-123">Esto significa que se ha abonado la cuenta del cliente, y que se ha adeudado la cuenta de acumulación de devoluciones.</span><span class="sxs-lookup"><span data-stu-id="27060-123">This means that the customer’s account has been credited, and the Rebate accrual account has been debited.</span></span>  
11. <span data-ttu-id="27060-124">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="27060-124">Close the page.</span></span>
12. <span data-ttu-id="27060-125">Haga clic en Cancelar.</span><span class="sxs-lookup"><span data-stu-id="27060-125">Click Cancel.</span></span>
    * <span data-ttu-id="27060-126">Esto actualiza la página para que pueda ver las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="27060-126">This refreshes the page so that you can see the updates.</span></span>  
13. <span data-ttu-id="27060-127">En el panel de acciones, haga clic en Cobrar.</span><span class="sxs-lookup"><span data-stu-id="27060-127">On the Action Pane, click Collect.</span></span>
14. <span data-ttu-id="27060-128">Haga clic en Liquidar transacciones.</span><span class="sxs-lookup"><span data-stu-id="27060-128">Click Settle transactions.</span></span>
    * <span data-ttu-id="27060-129">Observe cómo se ha agregado al saldo del cliente una transacción por un importe negativo, el cual representa el importe de devolución total, sin referencia de factura.</span><span class="sxs-lookup"><span data-stu-id="27060-129">Note that a transaction for negative amount, representing the total rebate amount, without invoice reference has been added to the customer balance.</span></span>   
15. <span data-ttu-id="27060-130">Haga clic en Cancelar.</span><span class="sxs-lookup"><span data-stu-id="27060-130">Click Cancel.</span></span>


