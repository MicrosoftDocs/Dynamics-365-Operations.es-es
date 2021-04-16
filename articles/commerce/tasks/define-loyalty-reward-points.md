---
title: Definir puntos de recompensa de fidelización
description: Este procedimiento le muestra la definición de puntos de recompensa de fidelización.
author: scott-tucker
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailLoyaltyRewardPoints
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e7f3b19513bb25d1976d2e4d0e235c347c38ccb4
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798474"
---
# <a name="define-loyalty-reward-points"></a><span data-ttu-id="2ecaa-103">Definir puntos de recompensa de fidelización</span><span class="sxs-lookup"><span data-stu-id="2ecaa-103">Define loyalty reward points</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2ecaa-104">Este procedimiento le muestra la definición de puntos de recompensa de fidelización.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-104">This procedure walks through defining loyalty reward points.</span></span> <span data-ttu-id="2ecaa-105">Debe configurar puntos de recompensa de fidelización antes de configurar un programa de fidelización.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-105">You should set up loyalty reward points before you set up a loyalty program.</span></span> <span data-ttu-id="2ecaa-106">Este procedimiento usa la empresa de datos de demostración USRT.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-106">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="2ecaa-107">Vaya a Retail y Commerce > Clientes > Fidelidad > Puntos de recompensa de fidelización.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-107">Go to Retail and Commerce > Customers > Loyalty > Loyalty reward points.</span></span>
2. <span data-ttu-id="2ecaa-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-108">Click New.</span></span>
3. <span data-ttu-id="2ecaa-109">En el campo Id. de punto de recompensa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-109">In the Reward point ID field, type a value.</span></span>
4. <span data-ttu-id="2ecaa-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="2ecaa-111">En el campo Tipo de punto de recompensa, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-111">In the Reward point type field, select an option.</span></span>
    * <span data-ttu-id="2ecaa-112">Seleccione la cantidad si desea que los puntos de recompensa se redondeen al entero más próximo.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-112">Select Quantity if you want the reward points to be rounded to the nearest integer.</span></span> <span data-ttu-id="2ecaa-113">Seleccione Importe si desea que los puntos de recompensa se redondeen según las reglas de redondeo de divisas.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-113">Select Amount if you want the reward points to be rounded according to currency rounding rules.</span></span> <span data-ttu-id="2ecaa-114">Si selecciona Cantidad, omita el paso siguiente de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-114">If you select Quantity, skip the next step of this procedure..</span></span>  
6. <span data-ttu-id="2ecaa-115">En el campo Divisa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-115">In the Currency field, type a value.</span></span>
    * <span data-ttu-id="2ecaa-116">Para los puntos de recompensa de tipo de importe, todos los puntos emitidos tendrán la divisa seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-116">For Amount type reward points, all points issued will have the selected currency.</span></span> <span data-ttu-id="2ecaa-117">Para los puntos de recompensa del tipo de cantidad, no se aplica este campo; omita este paso.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-117">For Quantity type reward points, this field doesn't apply—skip this step.</span></span>  
7. <span data-ttu-id="2ecaa-118">Active o desactive la casilla Canjeable.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-118">Check or uncheck the Redeemable checkbox.</span></span>
8. <span data-ttu-id="2ecaa-119">En el campo Clasificación de canjes, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-119">In the Redeem ranking field, enter a number.</span></span>
    * <span data-ttu-id="2ecaa-120">Se usa Clasificación de canjes cuando se pueden usar dos o más puntos de recompensa canjeables para pagar productos.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-120">Redeem ranking is used when two or more redeemable reward points can be used to pay for products.</span></span> <span data-ttu-id="2ecaa-121">Si los dos puntos de recompensa tienen la misma clasificación de canjes, se usará el que necesita reducir el número de puntos.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-121">If the two reward points have the same redeem ranking, then the one that needs to lower number of points will be used.</span></span>  
9. <span data-ttu-id="2ecaa-122">En el campo Valor de tiempo de vencimiento, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-122">In the Expiration time value field, enter a number.</span></span>
    * <span data-ttu-id="2ecaa-123">Los puntos de recompensa expirarán el número especificado de días, semanas, meses o años tras la emisión de los puntos.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-123">The reward points will expire the specified number of days, months, or years after when the points are issued.</span></span> <span data-ttu-id="2ecaa-124">Un valor de "0" significa que nunca expirarán los puntos de recompensa de fidelización.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-124">A value of '0' means the loyalty reward points will never expire.</span></span>  
10. <span data-ttu-id="2ecaa-125">En el campo Unidad de tiempo de vencimiento, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-125">In the Expiration time unit field, select an option.</span></span>
11. <span data-ttu-id="2ecaa-126">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="2ecaa-126">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]