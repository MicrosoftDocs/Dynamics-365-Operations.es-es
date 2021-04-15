---
title: Configurar las reglas y los parámetros para el tránsito directo y la estrategia de presión
description: Este procedimiento muestra los pasos para crear Reglas de reabastecimiento.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailReplenishmentRuleTable, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a2d8e561273c2a573182259c2ceb45cebc072eca
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5804170"
---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a><span data-ttu-id="b8c45-103">Configurar las reglas y los parámetros para el tránsito directo y la estrategia de presión</span><span class="sxs-lookup"><span data-stu-id="b8c45-103">Set up rules and parameters for cross docking and buyer's push</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b8c45-104">Este procedimiento muestra los pasos para crear Reglas de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="b8c45-104">This procedure demonstrates the steps to create Replenishment rules.</span></span> <span data-ttu-id="b8c45-105">Las reglas de reabastecimiento se pueden usar para controlar la manera en que los productos se distribuyen a los almacenes al usar tránsito directo y estrategia de presión.</span><span class="sxs-lookup"><span data-stu-id="b8c45-105">Replenishment rules can be used to control how products are distributed to stores when using Cross-docking and Buyer´s push.</span></span> <span data-ttu-id="b8c45-106">Las reglas de reabastecimiento se pueden configurar para tiendas o grupos de tiendas.</span><span class="sxs-lookup"><span data-stu-id="b8c45-106">Replenishment rules can be set up for stores or store groups.</span></span> <span data-ttu-id="b8c45-107">El peso definido para cada línea en una regla controlará la manera en que las cantidades de productos se distribuirán entre almacenes al usar reglas de reabastecimiento como el método de distribución en tránsito directo o estrategia de presión.</span><span class="sxs-lookup"><span data-stu-id="b8c45-107">The weight defined for each line in a rule will control how the quantities of products will get distributed between the stores when using Replenishment rules as the distribution method in Cross-docking or Buyer´s push.</span></span> <span data-ttu-id="b8c45-108">Este procedimiento usa la empresa de prueba USRT.</span><span class="sxs-lookup"><span data-stu-id="b8c45-108">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="b8c45-109">Vaya a Reglas de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="b8c45-109">Go to Replenishment rules.</span></span>
2. <span data-ttu-id="b8c45-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="b8c45-110">Click New.</span></span>
3. <span data-ttu-id="b8c45-111">En el campo Regla de reabastecimiento, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="b8c45-111">In the Replenishment rule field, type a value.</span></span>
4. <span data-ttu-id="b8c45-112">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="b8c45-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="b8c45-113">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b8c45-113">Click Save.</span></span>
6. <span data-ttu-id="b8c45-114">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="b8c45-114">Click Add.</span></span>
7. <span data-ttu-id="b8c45-115">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b8c45-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="b8c45-116">Puede elegir Jerarquía de reabastecimiento o Canal para el tipo.</span><span class="sxs-lookup"><span data-stu-id="b8c45-116">You can choose Replenishment hierarchy or Channel for the type.</span></span> <span data-ttu-id="b8c45-117">El valor controla si la selección en Nombre será una jerarquía de canales o un canal específico.</span><span class="sxs-lookup"><span data-stu-id="b8c45-117">The value controls whether the selection in Name will be a hierarchy of channels or a specific channel.</span></span>  <span data-ttu-id="b8c45-118">Para este ejemplo, déjelo establecido como una Jerarquía de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="b8c45-118">For this example, leave it set as Replenishment hierarchy.</span></span>  
8. <span data-ttu-id="b8c45-119">En el campo Nombre, seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="b8c45-119">In the Name field, select a value.</span></span>
    * <span data-ttu-id="b8c45-120">El valor del peso predeterminado se rellena con el peso definido en el almacén.</span><span class="sxs-lookup"><span data-stu-id="b8c45-120">The default weight value is populated from the weight defined on the warehouse.</span></span>  <span data-ttu-id="b8c45-121">Este peso se puede usar para la Regla de reabastecimiento o puede especificar un nuevo peso en el campo Peso.</span><span class="sxs-lookup"><span data-stu-id="b8c45-121">This weight can be used for the Replenishment rule or you can enter a new weight in the Weight field.</span></span>  
9. <span data-ttu-id="b8c45-122">En el campo Peso, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="b8c45-122">In the Weight field, enter a number.</span></span>
10. <span data-ttu-id="b8c45-123">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="b8c45-123">Click Add.</span></span>
11. <span data-ttu-id="b8c45-124">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b8c45-124">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="b8c45-125">En el campo Tipo, seleccione "Canal".</span><span class="sxs-lookup"><span data-stu-id="b8c45-125">In the Type field, select 'Channel'.</span></span>
13. <span data-ttu-id="b8c45-126">En el campo Nombre, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="b8c45-126">In the Name field, enter or select a value.</span></span>
14. <span data-ttu-id="b8c45-127">En el campo Peso, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="b8c45-127">In the Weight field, enter a number.</span></span>
15. <span data-ttu-id="b8c45-128">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b8c45-128">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]