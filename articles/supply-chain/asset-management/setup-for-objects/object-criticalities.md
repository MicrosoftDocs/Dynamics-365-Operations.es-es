---
title: Tipos de importancia de los activos
description: En este tema se explican los tipos de importancia de los activos en Administración de activos.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetCriticality, EntAssetObjectCriticality
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bb2da2d58b7f98fad80d0ea63bf4445ec4d08163
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808361"
---
# <a name="asset-criticality-types"></a><span data-ttu-id="135e1-103">Tipos de importancia de los activos</span><span class="sxs-lookup"><span data-stu-id="135e1-103">Asset criticality types</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="135e1-104">En este tema se explican los tipos de importancia de los activos en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="135e1-104">The topic explains asset criticality types in Asset Management.</span></span> <span data-ttu-id="135e1-105">La importancia de los activos está relacionada con los activos y se transfiere a las órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="135e1-105">Asset criticality is related to assets and is transferred to work orders.</span></span> <span data-ttu-id="135e1-106">No se puede modificar en una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="135e1-106">It can't be changed on a work order.</span></span> <span data-ttu-id="135e1-107">La importancia de los activos se usa para calcular la importancia de la orden de trabajo durante la programación de esta.</span><span class="sxs-lookup"><span data-stu-id="135e1-107">Asset criticality is used to calculate work order criticality during work order scheduling.</span></span> <span data-ttu-id="135e1-108">Es decir, se usa para calcular hasta qué grado un trabajo de mantenimiento de un activo afecta a la programación de producción y la productividad de la empresa.</span><span class="sxs-lookup"><span data-stu-id="135e1-108">In other words, it's used to calculate the extent to which a maintenance job on an asset affects the production schedule and productivity in your company.</span></span> <span data-ttu-id="135e1-109">Para obtener más información sobre la configuración relacionada con el cálculo de puntuaciones para la programación de órdenes de trabajo, consulte [Parámetros de administración de activos](../setup-for-objects/enterprise-asset-management-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="135e1-109">For more information about the setup that is related to the calculation of rating scores for work order scheduling, see [Asset Management parameters](../setup-for-objects/enterprise-asset-management-parameters.md).</span></span>

<span data-ttu-id="135e1-110">Para configurar la importancia, primero se crean los tipos de importancia que se usarán en la configuración del activo.</span><span class="sxs-lookup"><span data-stu-id="135e1-110">To set up criticality, you first create the criticality types that should be used in the asset setup.</span></span> <span data-ttu-id="135e1-111">A continuación se configuran las imporatncias de los activos.</span><span class="sxs-lookup"><span data-stu-id="135e1-111">You then set up asset criticalities.</span></span>

## <a name="set-up-criticality-types"></a><span data-ttu-id="135e1-112">Configurar tipos de importancia</span><span class="sxs-lookup"><span data-stu-id="135e1-112">Set up criticality types</span></span>

1. <span data-ttu-id="135e1-113">Seleccione **Administración de activos** \> **Configuración** \> **Activos** \> **Tipos de importancia**.</span><span class="sxs-lookup"><span data-stu-id="135e1-113">Select **Asset management** \> **Setup** \> **Assets** \> **Criticality types**.</span></span>
2. <span data-ttu-id="135e1-114">Seleccione **Nuevo** para crear un registro.</span><span class="sxs-lookup"><span data-stu-id="135e1-114">Select **New** to create a record.</span></span>
3. <span data-ttu-id="135e1-115">En el campo **Importancia** especifique un número que indique la importancia.</span><span class="sxs-lookup"><span data-stu-id="135e1-115">In the **Criticality** field, enter a number that indicates the criticality.</span></span>
4. <span data-ttu-id="135e1-116">En el campo **Nombre**, especifique un nombre para el tipo de importancia.</span><span class="sxs-lookup"><span data-stu-id="135e1-116">In the **Name** field, enter a name for the criticality type.</span></span>
5. <span data-ttu-id="135e1-117">En el campo **Factor**, escriba un factor.</span><span class="sxs-lookup"><span data-stu-id="135e1-117">In the **Factor** field, enter a factor.</span></span> <span data-ttu-id="135e1-118">Este factor se utiliza durante el cálculo de la programación de órdenes de trabajo para determinar el registro de importancia que se debe utilizar.</span><span class="sxs-lookup"><span data-stu-id="135e1-118">This factor is used during the calculation of work order scheduling to determine the criticality record that should be used.</span></span> <span data-ttu-id="135e1-119">(Siempre se usa el registro que tiene el factor más alto). Este valor es relevante si, como se muestra en la siguiente ilustración, se crean líneas de importancia con el mismo valor de criticalidad.</span><span class="sxs-lookup"><span data-stu-id="135e1-119">(The record that has the highest factor is always used.) This setting is relevant if, as shown in the following illustration, criticality lines are created that have the same criticality value.</span></span>

    ![Página de tipos de criticidad](media/23-setup-for-objects.png)

## <a name="set-up-asset-criticalities"></a><span data-ttu-id="135e1-121">Configurar importancias de activos</span><span class="sxs-lookup"><span data-stu-id="135e1-121">Set up asset criticalities</span></span>

1. <span data-ttu-id="135e1-122">Seleccione **Administración de activos** \> **Configuración** \> **Importancias de activos**.</span><span class="sxs-lookup"><span data-stu-id="135e1-122">Select **Asset management** \> **Setup** \> **Asset criticalities**.</span></span>
2. <span data-ttu-id="135e1-123">Seleccione **Nuevo** para crear un registro.</span><span class="sxs-lookup"><span data-stu-id="135e1-123">Select **New** to create a record.</span></span>
3. <span data-ttu-id="135e1-124">En función del nivel de detalle necesario para la importancia de activo, realice las selecciones relevantes en **Ubicación funcional**, **Tipo de activo**, **Fabricante**, **Modelo**, **Activo**, **Categoría del tipo de trabajo**, **Tipo de trabajo**, **Variante del tipo de trabajo** y **Requisito de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="135e1-124">Depending on the required level of detail for asset criticality, make relevant selections in the **Functional location**, **Asset type**, **Manufacturer**, **Model**, **Asset**, **Job type category**, **Job type**, **Job type variant**, and **Job requirement** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="135e1-125">Si se selecciona una importancia de activo, Administración de activos recorre todos los registros de importancia de activo para comprobar si hay una coincidencia posible.</span><span class="sxs-lookup"><span data-stu-id="135e1-125">When an asset criticality is selected, Asset Management goes through all asset criticality records to check for a possible match.</span></span> <span data-ttu-id="135e1-126">Comprueba siempre primero la combinación más específica.</span><span class="sxs-lookup"><span data-stu-id="135e1-126">It always checks the most specific combination first.</span></span> <span data-ttu-id="135e1-127">Es decir, Administración de activos comprueba en primer lugar **Requisito de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="135e1-127">In other words, Asset Management first checks **Job requirement**.</span></span> <span data-ttu-id="135e1-128">Si no se encuentra ninguna coincidencia, comprueba **Variante del tipo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="135e1-128">If no match is found, it checks **Job type variant**.</span></span> <span data-ttu-id="135e1-129">Si no se encuentra ninguna coincidencia, comprueba **Tipo de trabajo**, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="135e1-129">If no match is found, it checks **Job type**, and so on.</span></span> <span data-ttu-id="135e1-130">Como puede ver en el diseño de la página, este comportamiento significa que, para encontrar la combinación más específica, Administración de activos comprueba cada registro de derecha a izquierda en busca de una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="135e1-130">As you can see in the layout of the page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="135e1-131">Si no se encuentra ninguna coincidencia, se utiliza el registro "predeterminado" que no tiene ninguna selección.</span><span class="sxs-lookup"><span data-stu-id="135e1-131">If no match is found, the "default" record that has no selections is used.</span></span>

4. <span data-ttu-id="135e1-132">En el campo **Importancia**, seleccione uno de los valores de importancia que creó en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="135e1-132">In the **Criticality** field, select one of the criticality values that you created in the previous procedure.</span></span>

### <a name="notes-about-criticality-setup"></a><span data-ttu-id="135e1-133">Notas sobre la configuración de la importancia</span><span class="sxs-lookup"><span data-stu-id="135e1-133">Notes about criticality setup</span></span>

- <span data-ttu-id="135e1-134">Si modifica una importancia de activo en esta configuración después de utilizarla en una orden de trabajo, la importancia de la orden de trabajo no se actualiza como corresponde.</span><span class="sxs-lookup"><span data-stu-id="135e1-134">If you change an asset criticality in this setup after you've already used it on a work order, the criticality on the work order isn't updated accordingly.</span></span>
- <span data-ttu-id="135e1-135">La importancia de una orden de trabajo se actualiza cada vez que se agrega o se elimina una línea de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="135e1-135">The criticality on a work order is recalculated every time that a work order line is added to or deleted from the work order.</span></span>
- <span data-ttu-id="135e1-136">Si una orden de trabajo contiene varios trabajos, siempre se usará la importancia más alta, según el campo **Factor** de la página **Tipos de importancia**, en la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="135e1-136">If a work order contains several work order jobs, the highest criticality, according to the **Factor** field on the **Criticality types** page, is always used on the work order.</span></span>
- <span data-ttu-id="135e1-137">Normalmente, la importancia de activo puede cambiar durante un período.</span><span class="sxs-lookup"><span data-stu-id="135e1-137">Generally, asset criticality can change over a period.</span></span> <span data-ttu-id="135e1-138">La importancia se puede ver afectada por la compra de nuevo equipo, restauraciones y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="135e1-138">Criticality can be affected by the purchase of new equipment, refurbishments, and so on.</span></span> <span data-ttu-id="135e1-139">Considere reevaluar las importancias de los activos a intervalos regulares (por ejemplo, una vez al año o cada dos años) para asegurarse de que las definiciones de importancia coinciden con la configuración de la producción actual.</span><span class="sxs-lookup"><span data-stu-id="135e1-139">Consider reevaluating your asset criticalities at regular intervals (for example, once per year or every other year) to make sure that your criticality definitions match your current production setup.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]