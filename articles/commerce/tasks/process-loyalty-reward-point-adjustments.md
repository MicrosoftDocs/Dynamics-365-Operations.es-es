---
title: Procesar ajustes de puntos de recompensa de fidelización
description: Este procedimiento muestra cómo buscar información de la tarjeta de fidelización y ajustar puntos de recompensa de fidelización.
author: scott-tucker
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailLoyaltyCards, RetailLoyaltyCardRewardPointTrans, RetailLoyaltyCardRewardPointAdjustment, RetailAffiliationLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7eae943985cc2bd706c0c3c4ec7b0470e3a54bff
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802632"
---
# <a name="process-loyalty-reward-point-adjustments"></a><span data-ttu-id="7348f-103">Procesar ajustes de puntos de recompensa de fidelización</span><span class="sxs-lookup"><span data-stu-id="7348f-103">Process loyalty reward point adjustments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7348f-104">Este procedimiento muestra cómo buscar información de la tarjeta de fidelización y ajustar puntos de recompensa de fidelización.</span><span class="sxs-lookup"><span data-stu-id="7348f-104">This procedure demonstrates how to look up loyalty card information and adjust loyalty reward points.</span></span> <span data-ttu-id="7348f-105">La empresa de datos de prueba utilizada para crear esta tarea es USRT.</span><span class="sxs-lookup"><span data-stu-id="7348f-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="7348f-106">Esta tarea está pensada para el rol Encargado de operaciones de Commerce o Director de servicio al cliente.</span><span class="sxs-lookup"><span data-stu-id="7348f-106">This task is intended for the Commerce operations manager role or a Customer service manager role.</span></span>

1. <span data-ttu-id="7348f-107">Vaya a Tarjetas de fidelización.</span><span class="sxs-lookup"><span data-stu-id="7348f-107">Go to Loyalty cards.</span></span>
2. <span data-ttu-id="7348f-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="7348f-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="7348f-109">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7348f-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="7348f-110">Haga clic en Transacciones con tarjeta.</span><span class="sxs-lookup"><span data-stu-id="7348f-110">Click Card transactions.</span></span>
    * <span data-ttu-id="7348f-111">En esta página puede ver todas las transacciones de fidelización para la tarjeta de fidelización seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7348f-111">On this page you can view all loyalty transactions for the selected loyalty card.</span></span>  
5. <span data-ttu-id="7348f-112">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7348f-112">Close the page.</span></span>
6. <span data-ttu-id="7348f-113">Haga clic en Ajustes de tarjeta.</span><span class="sxs-lookup"><span data-stu-id="7348f-113">Click Card adjustments.</span></span>
7. <span data-ttu-id="7348f-114">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="7348f-114">Click New.</span></span>
8. <span data-ttu-id="7348f-115">En el campo Punto de recompensa, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="7348f-115">In the Reward point field, enter or select a value.</span></span>
9. <span data-ttu-id="7348f-116">En el campo Importe o cantidad, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="7348f-116">In the Amount or quantity field, enter a number.</span></span>
    * <span data-ttu-id="7348f-117">Puede agregar o quitar puntos de la tarjeta de fidelización usando importes positivos o negativos.</span><span class="sxs-lookup"><span data-stu-id="7348f-117">You can add or remove points from the loyalty card by using positive or negative amounts.</span></span>  
10. <span data-ttu-id="7348f-118">En el campo Programa de fidelización, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="7348f-118">In the Loyalty program field, enter or select a value.</span></span>
11. <span data-ttu-id="7348f-119">En el campo Comentario, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7348f-119">In the Comment field, type a value.</span></span>
12. <span data-ttu-id="7348f-120">Haga clic en Registrar ajuste.</span><span class="sxs-lookup"><span data-stu-id="7348f-120">Click Post adjustment.</span></span>
13. <span data-ttu-id="7348f-121">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="7348f-121">Click Yes.</span></span>
14. <span data-ttu-id="7348f-122">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7348f-122">Close the page.</span></span>
    * <span data-ttu-id="7348f-123">Normalmente en este punto se actualizaría la página para ver el resultado del ajuste de los puntos de la recompensa en la pestaña de resumen de los puntos de la recompensa. Pero si ejecuta esto como una guía de tareas, le recomendamos que no actualice la página porque la guía de tareas podría pararse.</span><span class="sxs-lookup"><span data-stu-id="7348f-123">Normally at this point you'd refresh the page to see the result of the reward points adjustment in the Reward point summary tab. But if you are running this as a task guide, don't refresh now because if you do, the task guide will stop.</span></span>  
15. <span data-ttu-id="7348f-124">Haga clic en Transacciones con tarjeta.</span><span class="sxs-lookup"><span data-stu-id="7348f-124">Click Card transactions.</span></span>
16. <span data-ttu-id="7348f-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7348f-125">Close the page.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]