---
title: Procesamiento de devoluciones para pago
description: Este procedimiento muestra cómo convertir en notas de abono devoluciones de cliente aprobadas y procesadas.
author: omulvad
manager: tfehr
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 981068d26d232b10efd8d7288daaf7358aee3728
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3980703"
---
# <a name="process-rebates-for-payment"></a><span data-ttu-id="c7143-103">Procesamiento de devoluciones para pago</span><span class="sxs-lookup"><span data-stu-id="c7143-103">Process rebates for payment</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c7143-104">Este procedimiento muestra cómo convertir en notas de abono devoluciones de cliente aprobadas y procesadas.</span><span class="sxs-lookup"><span data-stu-id="c7143-104">This procedure demonstrates how to convert approved and processed customer rebates to credit notes.</span></span> <span data-ttu-id="c7143-105">Puede ejecutar este procedimiento en la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="c7143-105">You can use this guide in the USMF demo company.</span></span> <span data-ttu-id="c7143-106">La condición previa para este procedimiento es tener una o más reclamaciones de devolución con estado Marcar.</span><span class="sxs-lookup"><span data-stu-id="c7143-106">The precondition for this guide is to have one or more rebate claims which have a status of Mark.</span></span> <span data-ttu-id="c7143-107">Si está usando USMF, debe ejecutar el procedimiento "Generación y procesamiento de devoluciones de cliente" antes de comenzar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c7143-107">If you're using USMF you should run the "Generate and process customer rebates" guide before you start this guide.</span></span>


## <a name="convert-rebate-claims-to-credit-note"></a><span data-ttu-id="c7143-108">Conversión de reclamaciones de devolución en notas de abono</span><span class="sxs-lookup"><span data-stu-id="c7143-108">Convert rebate claims to credit note</span></span>
1. <span data-ttu-id="c7143-109">Vaya a Todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="c7143-109">Go to All customers.</span></span>
2. <span data-ttu-id="c7143-110">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="c7143-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c7143-111">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c7143-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c7143-112">En el panel de acciones, haga clic en Cobrar.</span><span class="sxs-lookup"><span data-stu-id="c7143-112">On the Action Pane, click Collect.</span></span>
5. <span data-ttu-id="c7143-113">Haga clic en Liquidar transacciones.</span><span class="sxs-lookup"><span data-stu-id="c7143-113">Click Settle transactions.</span></span>
6. <span data-ttu-id="c7143-114">Haga clic en Funciones.</span><span class="sxs-lookup"><span data-stu-id="c7143-114">Click Functions.</span></span>
7. <span data-ttu-id="c7143-115">Haga clic en Programa de devoluciones.</span><span class="sxs-lookup"><span data-stu-id="c7143-115">Click Rebate program.</span></span>
    * <span data-ttu-id="c7143-116">La página Devolución muestra las reclamaciones de devolución que ha procesado en el área de trabajo de devoluciones de cliente y que se encuentran en estado Marcar.</span><span class="sxs-lookup"><span data-stu-id="c7143-116">The Rebate page lists the rebate claims that you have processed in the customer rebate workbench and that are in status Mark.</span></span>    
8. <span data-ttu-id="c7143-117">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="c7143-117">Click Edit.</span></span>
    * <span data-ttu-id="c7143-118">Defina las marcas de verificación del campo Marcar para las reclamaciones que desee incluir en nota de abono.</span><span class="sxs-lookup"><span data-stu-id="c7143-118">Set checkmarks in the Mark field for the claims that you want to include into credit note.</span></span>   
9. <span data-ttu-id="c7143-119">Haga clic en Funciones.</span><span class="sxs-lookup"><span data-stu-id="c7143-119">Click Functions.</span></span>
10. <span data-ttu-id="c7143-120">Haga clic en Crear nota de abono.</span><span class="sxs-lookup"><span data-stu-id="c7143-120">Click Create credit note.</span></span>
    * <span data-ttu-id="c7143-121">Aparece un mensaje para informarle de que se ha registrado un diario (este es el diario de consumo de clientes, como se haya especificado en la página de parámetros de clientes).</span><span class="sxs-lookup"><span data-stu-id="c7143-121">A message appears to inform you that a journal has been posted (This is the Accounts receivable consumption journal, as specified in the Accounts receivable parameters page).</span></span> <span data-ttu-id="c7143-122">Esto hace que el importe real de pasivos (crédito) se desplace al saldo del cliente.</span><span class="sxs-lookup"><span data-stu-id="c7143-122">This causes the real liability (credit) amount to be moved to the customer balance.</span></span> <span data-ttu-id="c7143-123">Esto significa que se ha abonado la cuenta del cliente, y que se ha adeudado la cuenta de acumulación de devoluciones.</span><span class="sxs-lookup"><span data-stu-id="c7143-123">This means that the customer's account has been credited, and the Rebate accrual account has been debited.</span></span>  
11. <span data-ttu-id="c7143-124">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c7143-124">Close the page.</span></span>
12. <span data-ttu-id="c7143-125">Haga clic en Cancelar.</span><span class="sxs-lookup"><span data-stu-id="c7143-125">Click Cancel.</span></span>
    * <span data-ttu-id="c7143-126">Esto actualiza la página para que pueda ver las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="c7143-126">This refreshes the page so that you can see the updates.</span></span>  
13. <span data-ttu-id="c7143-127">En el panel de acciones, haga clic en Cobrar.</span><span class="sxs-lookup"><span data-stu-id="c7143-127">On the Action Pane, click Collect.</span></span>
14. <span data-ttu-id="c7143-128">Haga clic en Liquidar transacciones.</span><span class="sxs-lookup"><span data-stu-id="c7143-128">Click Settle transactions.</span></span>
    * <span data-ttu-id="c7143-129">Observe cómo se ha agregado al saldo del cliente una transacción por un importe negativo, el cual representa el importe de devolución total, sin referencia de factura.</span><span class="sxs-lookup"><span data-stu-id="c7143-129">Note that a transaction for negative amount, representing the total rebate amount, without invoice reference has been added to the customer balance.</span></span>   
15. <span data-ttu-id="c7143-130">Haga clic en Cancelar.</span><span class="sxs-lookup"><span data-stu-id="c7143-130">Click Cancel.</span></span>

