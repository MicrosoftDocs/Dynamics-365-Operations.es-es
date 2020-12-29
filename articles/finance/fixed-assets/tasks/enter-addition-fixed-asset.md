---
title: Especificar una adición para un activo fijo
description: Este procedimiento muestra cómo agregar una adición a un activo fijo existente.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetAddition
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dc1e13863ae13daaa641f52f7a55e01fc1353dc1
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447618"
---
# <a name="enter-an-addition-to-a-fixed-asset"></a><span data-ttu-id="38d62-103">Especificar una adición para un activo fijo</span><span class="sxs-lookup"><span data-stu-id="38d62-103">Enter an addition to a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="38d62-104">Este procedimiento muestra cómo agregar una adición a un activo fijo existente.</span><span class="sxs-lookup"><span data-stu-id="38d62-104">This procedure shows how to add an addition to an existing fixed asset.</span></span> <span data-ttu-id="38d62-105">El propósito de las adiciones de activos fijos es el seguimiento de las adiciones, el mantenimiento o las mejoras de artículo para un activo y es únicamente informativo.</span><span class="sxs-lookup"><span data-stu-id="38d62-105">The purpose of Fixed asset additions is to track item additions, maintenance, or improvements for an asset, and is informational only.</span></span> <span data-ttu-id="38d62-106">Cualquier cambio en el valor o el tiempo de vida del activo fijo debe llevarse a cabo de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="38d62-106">Any changes to the fixed asset value or service life must be made separately.</span></span>   

<span data-ttu-id="38d62-107">El procedimiento usa el rol de contable y los datos de prueba de la entidad jurídica USMF.</span><span class="sxs-lookup"><span data-stu-id="38d62-107">The procedure uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="38d62-108">En el panel de navegación, vaya a **Módulos > activos fijos > activos fijos > activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="38d62-108">In the Navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="38d62-109">En la lista, busque y seleccione el activo fijo para el accesorio.</span><span class="sxs-lookup"><span data-stu-id="38d62-109">In the list, find and select the fixed asset for the addition.</span></span>
3. <span data-ttu-id="38d62-110">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="38d62-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="38d62-111">En el panel de acciones, haga clic en **Activo fijo.**</span><span class="sxs-lookup"><span data-stu-id="38d62-111">On the Action Pane, click **Fixed asset**.</span></span>
5. <span data-ttu-id="38d62-112">Haga clic en **Accesorios de activo fijo**.</span><span class="sxs-lookup"><span data-stu-id="38d62-112">Click **Fixed asset additions**.</span></span>
6. <span data-ttu-id="38d62-113">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="38d62-113">Click **New**.</span></span>
7. <span data-ttu-id="38d62-114">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="38d62-114">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="38d62-115">En el campo **Fecha de adquisición** , defina la fecha de la compra o el servicio de adición.</span><span class="sxs-lookup"><span data-stu-id="38d62-115">In the **Acquisition date** field, set the date of the addition purchase or service.</span></span>
9. <span data-ttu-id="38d62-116">En el campo **Coste unitario**, escriba el coste del artículo, mantenimiento u otra mejora del activo.</span><span class="sxs-lookup"><span data-stu-id="38d62-116">In the **Unit cost** field, enter the cost of the item, maintenance, or other improvement for the asset.</span></span>
10. <span data-ttu-id="38d62-117">En el campo **Cantidad**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="38d62-117">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="38d62-118">El coste total no sufrirá ningún impacto en el valor del activo fijo y solo sirve para realizar el seguimiento y para fines informativos.</span><span class="sxs-lookup"><span data-stu-id="38d62-118">The total cost will have no impact on the value of the fixed asset and is for tracking and informational purposes only.</span></span> <span data-ttu-id="38d62-119">Si el coste se capitalizará, debe registrarse una transacción de ajuste de revalorización por separado.</span><span class="sxs-lookup"><span data-stu-id="38d62-119">If the cost will be capitalized, then a write-up adjustment transaction must be posted separately.</span></span>  
11. <span data-ttu-id="38d62-120">Haga clic en la pestaña **General**.</span><span class="sxs-lookup"><span data-stu-id="38d62-120">Click the **General** tab.</span></span>

    * <span data-ttu-id="38d62-121">Establezca **Aumenta el tiempo de vida** en **Sí** si la adición incrementa el tiempo de vida del activo.</span><span class="sxs-lookup"><span data-stu-id="38d62-121">Set **Increases service life** to **Yes** if the addition increases the service life of the asset.</span></span>  
    * <span data-ttu-id="38d62-122">Este campo es únicamente informativo.</span><span class="sxs-lookup"><span data-stu-id="38d62-122">This field is informational only.</span></span> <span data-ttu-id="38d62-123">Para aumentar el tiempo de vida, modifíquelo en los modelos de valor y/o en los libros de amortización del activo.</span><span class="sxs-lookup"><span data-stu-id="38d62-123">To increase the service life, modify the Service life on the Value models and/or Depreciation books for the asset.</span></span>  

