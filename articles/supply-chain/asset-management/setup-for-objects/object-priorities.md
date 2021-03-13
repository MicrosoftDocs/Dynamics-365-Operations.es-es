---
title: Niveles de servicio de activos
description: Este tema explica los niveles de servicio de activos en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 83b195add44927d847491e6394e72637323117b3
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021638"
---
# <a name="asset-service-levels"></a><span data-ttu-id="48f9c-103">Niveles de servicio de activos</span><span class="sxs-lookup"><span data-stu-id="48f9c-103">Asset service levels</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="48f9c-104">Este tema explica los niveles de servicio de activos en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="48f9c-104">This topic explains asset service levels in Asset Management.</span></span> <span data-ttu-id="48f9c-105">Los niveles de servicio de activos están relacionados con los activos y se transfieren a las solicitudes de mantenimiento y a las órdens de trabajo.</span><span class="sxs-lookup"><span data-stu-id="48f9c-105">Asset service levels are related to assets, and are transferred to maintenance requests and work orders.</span></span> <span data-ttu-id="48f9c-106">Se utilizan para calcular la prioridad de las órdenes de trabajo durante la programación de estas.</span><span class="sxs-lookup"><span data-stu-id="48f9c-106">They are used to calculate the priority of work orders during work order scheduling.</span></span> <span data-ttu-id="48f9c-107">Los niveles de servicio de activo se pueden cambiar, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="48f9c-107">Asset service levels can be changed, if changes are required.</span></span>

<span data-ttu-id="48f9c-108">Para obtener más información sobre la configuración relacionada con el cálculo de puntuaciones para la programación de órdenes de trabajo, consulte [Parámetros de administración de activos](../setup-for-objects/enterprise-asset-management-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="48f9c-108">For more information about the setup that is related to the calculation of rating scores for work order scheduling, see [Asset Management parameters](../setup-for-objects/enterprise-asset-management-parameters.md).</span></span> <span data-ttu-id="48f9c-109">Debe configurar al menos un registro predeterminado para el nivel de servicio de activo.</span><span class="sxs-lookup"><span data-stu-id="48f9c-109">You must set up at least one default record for the asset service level.</span></span> <span data-ttu-id="48f9c-110">Este registro predeterminado se usa si no se encuentra ninguna otra coincidencia durante la programación de las órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="48f9c-110">This default record is used if no other match is found during work order scheduling.</span></span>

<span data-ttu-id="48f9c-111">**Ejemplo 1:** el nivel de servicio predeterminado que se usa si no se encuentra ninguna otra coincidencia.</span><span class="sxs-lookup"><span data-stu-id="48f9c-111">**Example 1:** The default service level that is used if no other match is found.</span></span> <span data-ttu-id="48f9c-112">En este registro, solo se selecciona un nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="48f9c-112">In this record, you select only a service level.</span></span>

<span data-ttu-id="48f9c-113">**Ejemplo 2:** alto nivel de servicio que se usa para programar los trabajos para un motor de camión Volvo.</span><span class="sxs-lookup"><span data-stu-id="48f9c-113">**Example 2:** A high service level that is used to schedule jobs for a Volvo truck engine.</span></span> <span data-ttu-id="48f9c-114">En este registro, debe seleccionar un tipo de activo relevante (como **Motor de camión**), un fabricante (**Volvo**) y un nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="48f9c-114">In this record, you select a relevant asset type (such as **Truck Engine**), a manufacturer (**Volvo**), and a service level.</span></span>

## <a name="set-up-asset-service-levels"></a><span data-ttu-id="48f9c-115">Configurar niveles de servicio de activos</span><span class="sxs-lookup"><span data-stu-id="48f9c-115">Set up asset service levels</span></span>

1. <span data-ttu-id="48f9c-116">Seleccione **Administración de activos** \> **Configuración** \> **Niveles de servicio de activos**.</span><span class="sxs-lookup"><span data-stu-id="48f9c-116">Select **Asset management** \> **Setup** \> **Asset service levels**.</span></span>
2. <span data-ttu-id="48f9c-117">Seleccione **Nuevo** para crear un registro.</span><span class="sxs-lookup"><span data-stu-id="48f9c-117">Select **New** to create a record.</span></span>
3. <span data-ttu-id="48f9c-118">En función del nivel de detalle necesario para el nivel de servicio de activo, realice las selecciones relevantes en **Ubicación funcional**, **Tipo de activo**, **Fabricante**, **Modelo**, **Activo**, **Tipo de pedido de trabajo** y **Nivel de servicio**.</span><span class="sxs-lookup"><span data-stu-id="48f9c-118">Depending on the detail level that is required for the asset service level, make relevant selections in the **Functional location**, **Asset type**, **Manufacturer**, **Model**, **Asset**, **Work order type**, and **Service level** fields.</span></span>

    > [!NOTE]
    > <span data-ttu-id="48f9c-119">Cuando se usa el nivel de servicio de activo para las solicitudes de mantenimiento y las órdenes de trabajo, la gestión de activos recorre todos los registros de nivel de servicio de activo para comprobar si hay una coincidencia posible.</span><span class="sxs-lookup"><span data-stu-id="48f9c-119">When the asset service level is used for maintenance requests and work orders, Asset Management goes through all asset service level records to check for a possible match.</span></span> <span data-ttu-id="48f9c-120">Comprueba siempre primero la combinación más específica.</span><span class="sxs-lookup"><span data-stu-id="48f9c-120">It always checks the most specific combination first.</span></span> <span data-ttu-id="48f9c-121">Es decir, Administración de activos primero busca una coincidencia para el campo **Tipo de orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="48f9c-121">In other words, Asset Management first checks for a match for the **Work order type** field.</span></span> <span data-ttu-id="48f9c-122">Si no se encuentra ninguna coincidencia, comprueba si hay una coincidencia para el campo **Activo**, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="48f9c-122">If no match is found, it checks for a match for the **Asset** field, and so on.</span></span> <span data-ttu-id="48f9c-123">Como puede ver en el diseño de la página **Niveles de servicio de activos**, este comportamiento significa que, para encontrar la combinación más específica, Administración de activos comprueba cada registro de derecha a izquierda en busca de una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="48f9c-123">As you can see in the layout of the **Asset service levels** page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="48f9c-124">Si no se encuentra ninguna coincidencia, se utiliza el registro predeterminado que no tiene ninguna selección en esos campos.</span><span class="sxs-lookup"><span data-stu-id="48f9c-124">If no match is found, the default record that has no selections in those fields is used.</span></span>

4. <span data-ttu-id="48f9c-125">En el campo **Nivel de servicio**, seleccione un número que indique el nivel de servicio (la prioridad).</span><span class="sxs-lookup"><span data-stu-id="48f9c-125">In the **Service level** field, select a number that indicates the service level (priority).</span></span>


> [!NOTE]
> <span data-ttu-id="48f9c-126">Si cambia un registro de nivel de servicio de activo en la página **Niveles de servicio de activos** después de haberlo utilizado en una orden de trabajo, el nivel de servicio de las solicitudes de mantenimiento y las órdenes de trabajo no se actualiza como corresponde.</span><span class="sxs-lookup"><span data-stu-id="48f9c-126">If you change an asset service level record on the **Asset service levels** page after you've already used it on a work order, the service level on maintenance requests and work orders isn't updated accordingly.</span></span>
