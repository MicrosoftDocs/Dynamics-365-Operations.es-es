--- 
title: "Definir puntos de recompensa de fidelización"
description: "Este procedimiento le muestra la definición de puntos de recompensa de fidelización."
author: scott-tucker
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 4f4c481f37fa1cb53c63e766219fb45a5d0dd3f8
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="define-loyalty-reward-points"></a><span data-ttu-id="3b7c1-103">Definir puntos de recompensa de fidelización</span><span class="sxs-lookup"><span data-stu-id="3b7c1-103">Define loyalty reward points</span></span>

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="3b7c1-104">Este procedimiento le muestra la definición de puntos de recompensa de fidelización.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-104">This procedure walks through defining loyalty reward points.</span></span> <span data-ttu-id="3b7c1-105">Debe configurar puntos de recompensa de fidelización antes de configurar un programa de fidelización.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-105">You should set up loyalty reward points before you set up a loyalty program.</span></span> <span data-ttu-id="3b7c1-106">Este procedimiento usa la empresa de datos de demostración USRT.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="3b7c1-107">Vaya a Venta minorista y comercio > Clientes > Fidelidad > Puntos de recompensa de fidelización.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-107">Go to Retail and commerce > Customers > Loyalty > Loyalty reward points.</span></span>
2. <span data-ttu-id="3b7c1-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-108">Click New.</span></span>
3. <span data-ttu-id="3b7c1-109">En el campo Id. de punto de recompensa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-109">In the Reward point ID field, type a value.</span></span>
4. <span data-ttu-id="3b7c1-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="3b7c1-111">En el campo Tipo de punto de recompensa, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-111">In the Reward point type field, select an option.</span></span>
    * <span data-ttu-id="3b7c1-112">Seleccione la cantidad si desea que los puntos de recompensa se redondeen al entero más próximo.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-112">Select Quantity if you want the reward points to be rounded to the nearest integer.</span></span> <span data-ttu-id="3b7c1-113">Seleccione Importe si desea que los puntos de recompensa se redondeen según las reglas de redondeo de divisas.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-113">Select Amount if you want the reward points to be rounded according to currency rounding rules.</span></span> <span data-ttu-id="3b7c1-114">Si selecciona Cantidad, omita el paso siguiente de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-114">If you select Quantity, skip the next step of this procedure..</span></span>  
6. <span data-ttu-id="3b7c1-115">En el campo Divisa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-115">In the Currency field, type a value.</span></span>
    * <span data-ttu-id="3b7c1-116">Para los puntos de recompensa de tipo de importe, todos los puntos emitidos tendrán la divisa seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-116">For Amount type reward points, all points issued will have the selected currency.</span></span> <span data-ttu-id="3b7c1-117">Para los puntos de recompensa del tipo de cantidad, no se aplica este campo; omita este paso.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-117">For Quantity type reward points, this field doesn't apply—skip this step.</span></span>  
7. <span data-ttu-id="3b7c1-118">Active o desactive la casilla Canjeable.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-118">Check or uncheck the Redeemable checkbox.</span></span>
8. <span data-ttu-id="3b7c1-119">En el campo Clasificación de canjes, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-119">In the Redeem ranking field, enter a number.</span></span>
    * <span data-ttu-id="3b7c1-120">Se usa Clasificación de canjes cuando se pueden usar dos o más puntos de recompensa canjeables para pagar productos.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-120">Redeem ranking is used when two or more redeemable reward points can be used to pay for products.</span></span> <span data-ttu-id="3b7c1-121">Si los dos puntos de recompensa tienen la misma clasificación de canjes, se usará el que necesita reducir el número de puntos.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-121">If the two reward points have the same redeem ranking, then the one that needs to lower number of points will be used.</span></span>  
9. <span data-ttu-id="3b7c1-122">En el campo Valor de tiempo de vencimiento, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-122">In the Expiration time value field, enter a number.</span></span>
    * <span data-ttu-id="3b7c1-123">Los puntos de recompensa expirarán el número especificado de días, semanas, meses o años tras la emisión de los puntos.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-123">The reward points will expire the specified number of days, months, or years after when the points are issued.</span></span> <span data-ttu-id="3b7c1-124">Un valor de "0"significa que nunca expirarán los puntos de recompensa de fidelización.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-124">A value of ‘0’ means the loyalty reward points will never expire.</span></span>  
10. <span data-ttu-id="3b7c1-125">En el campo Unidad de tiempo de vencimiento, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-125">In the Expiration time unit field, select an option.</span></span>
11. <span data-ttu-id="3b7c1-126">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3b7c1-126">Click Save.</span></span>


