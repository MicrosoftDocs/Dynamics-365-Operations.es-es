--- 
title: "Especificar una adición para un activo fijo"
description: "Este procedimiento muestra cómo agregar una adición a un activo fijo existente."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 3579148033023f648e1a78a3dd009018f153fdad
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="enter-an-addition-to-a-fixed-asset"></a><span data-ttu-id="6aecd-103">Especificar una adición para un activo fijo</span><span class="sxs-lookup"><span data-stu-id="6aecd-103">Enter an addition to a fixed asset</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6aecd-104">Este procedimiento muestra cómo agregar una adición a un activo fijo existente.</span><span class="sxs-lookup"><span data-stu-id="6aecd-104">This procedure shows how to add an addition to an existing fixed asset.</span></span> <span data-ttu-id="6aecd-105">El propósito de las adiciones de activos fijos es el seguimiento de las adiciones, el mantenimiento o las mejoras de artículo para un activo y es únicamente informativo.</span><span class="sxs-lookup"><span data-stu-id="6aecd-105">The purpose of Fixed asset additions is to track item additions, maintenance, or improvements for an asset, and is informational only.</span></span> <span data-ttu-id="6aecd-106">Cualquier cambio en el valor o el tiempo de vida del activo fijo debe llevarse a cabo de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="6aecd-106">Any changes to the fixed asset value or service life must be made separately.</span></span>   



<span data-ttu-id="6aecd-107">El procedimiento usa el rol de contable y los datos de prueba de la entidad jurídica USMF.</span><span class="sxs-lookup"><span data-stu-id="6aecd-107">The procedure uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="6aecd-108">Vaya a Activos fijos > Activos fijos > Activos fijos.</span><span class="sxs-lookup"><span data-stu-id="6aecd-108">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="6aecd-109">En la lista, busque y seleccione el activo fijo para el accesorio.</span><span class="sxs-lookup"><span data-stu-id="6aecd-109">In the list, find and select the fixed asset for the addition.</span></span>
3. <span data-ttu-id="6aecd-110">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6aecd-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="6aecd-111">En el panel de acciones, haga clic en Activo fijo.</span><span class="sxs-lookup"><span data-stu-id="6aecd-111">On the Action Pane, click Fixed asset.</span></span>
5. <span data-ttu-id="6aecd-112">Haga clic en Accesorios de activo fijo.</span><span class="sxs-lookup"><span data-stu-id="6aecd-112">Click Fixed asset additions.</span></span>
6. <span data-ttu-id="6aecd-113">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="6aecd-113">Click New.</span></span>
7. <span data-ttu-id="6aecd-114">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6aecd-114">In the Name field, type a value.</span></span>
8. <span data-ttu-id="6aecd-115">Defina la fecha de la compra o servicio del accesorio.</span><span class="sxs-lookup"><span data-stu-id="6aecd-115">Set the date of the addition purchase or service.</span></span>
9. <span data-ttu-id="6aecd-116">Escriba el coste del artículo, mantenimiento u otra mejora del activo.</span><span class="sxs-lookup"><span data-stu-id="6aecd-116">Enter the cost of the item, maintenance, or other improvement for the asset.</span></span>
10. <span data-ttu-id="6aecd-117">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="6aecd-117">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="6aecd-118">El coste total no sufrirá ningún impacto en el valor del activo fijo y solo sirve para realizar el seguimiento y para fines informativos.</span><span class="sxs-lookup"><span data-stu-id="6aecd-118">The total cost will have no impact on the value of the fixed asset and is for tracking and informational purposes only.</span></span> <span data-ttu-id="6aecd-119">Si el coste se capitalizará, debe registrarse una transacción de ajuste de revalorización por separado.</span><span class="sxs-lookup"><span data-stu-id="6aecd-119">If the cost will be capitalized, then a write-up adjustment transaction must be posted separately.</span></span>  
11. <span data-ttu-id="6aecd-120">Haga clic en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="6aecd-120">Click the General tab.</span></span>
    * <span data-ttu-id="6aecd-121">Establezca Aumenta el tiempo de vida si la adición incrementa el tiempo de vida del activo.</span><span class="sxs-lookup"><span data-stu-id="6aecd-121">Set Increases service life if the addition increases the service life of the asset.</span></span>  
    * <span data-ttu-id="6aecd-122">Este campo es únicamente informativo.</span><span class="sxs-lookup"><span data-stu-id="6aecd-122">This field is informational only.</span></span> <span data-ttu-id="6aecd-123">Para aumentar el tiempo de vida, modifíquelo en los modelos de valor y/o en los libros de amortización del activo.</span><span class="sxs-lookup"><span data-stu-id="6aecd-123">To increase the service life, modify the Service life on the Value models and/or Depreciation books for the asset.</span></span>  


