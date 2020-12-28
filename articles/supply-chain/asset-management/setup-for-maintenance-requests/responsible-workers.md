---
title: Trabajadores de mantenimiento responsables
description: En este tema se explica cómo configurar trabajadores de mantenimiento responsables en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkerResponsible
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 113ee2b45c569c7dae3609f1027e31c4e5e5c54a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436963"
---
# <a name="responsible-maintenance-workers"></a><span data-ttu-id="ea81f-103">Trabajadores de mantenimiento responsables</span><span class="sxs-lookup"><span data-stu-id="ea81f-103">Responsible maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="ea81f-104">Los trabajadores de mantenimiento responsables pueden estar relacionados con tipos de activos, activos, ubicaciones funcionales, categorías de tipo de trabajo de mantenimiento, tipos de trabajo de mantenimiento, variantes de tipos de trabajo de mantenimiento y oficios.</span><span class="sxs-lookup"><span data-stu-id="ea81f-104">Responsible maintenance workers can be related to asset types, assets, functional locations, maintenance job type categories, maintenance job types, maintenance job type variants, and trades.</span></span> <span data-ttu-id="ea81f-105">Se pueden usar en órdenes de trabajo y en solicitudes de mantenimiento para indicar una preferencia sobre los trabajadores de mantenimiento que se deben responsables de una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ea81f-105">They can be used on work orders and maintenance requests to indicate a preference about the maintenance workers who should be responsible for a work order.</span></span> <span data-ttu-id="ea81f-106">(Sin embargo, esos trabajadores de mantenimiento no son necesariamente los mismos trabajadores programados para realizar la orden de trabajo). El uso de esta función es opcional.</span><span class="sxs-lookup"><span data-stu-id="ea81f-106">(However, those maintenance workers aren't necessarily the same workers who are scheduled to carry out the work order.) Use of this functionality is optional.</span></span> <span data-ttu-id="ea81f-107">Por ejemplo, puede usarse para seleccionar los trabajadores o grupos de trabajadores responsables para tipos o áreas de trabajo específicos.</span><span class="sxs-lookup"><span data-stu-id="ea81f-107">For example, it can be used to select responsible workers or worker groups for specific work types or work areas.</span></span>

<span data-ttu-id="ea81f-108">Durante el ciclo de vida de una orden de trabajo o el ciclo de vida de una solicitud de mantenimiento, los trabajadores de mantenimiento responsables se pueden modificar o actualizar.</span><span class="sxs-lookup"><span data-stu-id="ea81f-108">During a work order lifecycle or a maintenance request lifecycle, responsible maintenance workers can be changed or updated.</span></span> <span data-ttu-id="ea81f-109">Este cambio o actualización puede estar relacionado, por ejemplo, con un cambio del estado del ciclo de vida de la solicitud de mantenimiento o el estado del ciclo de vida de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ea81f-109">This change or update might be related to, for example, a change in the maintenance request lifecycle state or the work order lifecycle state.</span></span>

<span data-ttu-id="ea81f-110">La configuración de la página **Trabajadores de mantenimiento responsables** *no* se utiliza durante la programación de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ea81f-110">The setup on the **Responsible maintenance workers** page is *not* used during work order scheduling.</span></span>

> [!NOTE]
> <span data-ttu-id="ea81f-111">En Administración de activos, también puede configurar trabajadores del mantenimiento *preferidos* que pueden asignarse a órdenes de trabajo durante la programación de estas.</span><span class="sxs-lookup"><span data-stu-id="ea81f-111">In Asset Management, you can also set up *preferred* maintenance workers who might be allocated to work orders during work order scheduling.</span></span>

<span data-ttu-id="ea81f-112">Para poder configurar los trabajadores de mantenimiento responsables, debe configurar los trabajadores y grupos de trabajadores de mantenimiento que deben estar disponibles para la selección.</span><span class="sxs-lookup"><span data-stu-id="ea81f-112">Before you can set up responsible maintenance workers, you must set up the workers and maintenance worker groups that should be available for selection.</span></span> <span data-ttu-id="ea81f-113">Para obtener información sobre cómo configurar trabajadores y grupos de trabajadores de mantenimiento, consulte [Trabajadores de mantenimiento y grupos de trabajadores](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="ea81f-113">For information about how to set up workers and maintenance worker groups, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

## <a name="set-up-responsible-maintenance-workers"></a><span data-ttu-id="ea81f-114">Configurar trabajadores de mantenimiento responsables</span><span class="sxs-lookup"><span data-stu-id="ea81f-114">Set up responsible maintenance workers</span></span>

1. <span data-ttu-id="ea81f-115">Seleccione **Administración de activos** \> **Configuración** \> **Trabajadores** \> **Trabajadores de mantenimiento responsables**.</span><span class="sxs-lookup"><span data-stu-id="ea81f-115">Select **Asset management** \> **Setup** \> **Workers** \> **Responsible maintenance workers**.</span></span>
2. <span data-ttu-id="ea81f-116">Seleccione **Nuevo** para crear un registro.</span><span class="sxs-lookup"><span data-stu-id="ea81f-116">Select **New** to create a record.</span></span>
3. <span data-ttu-id="ea81f-117">Primero cree una configuración de trabajador de mantenimiento responsable o un grupo de trabajadores de mantenimiento responsables predeterminados donde solo establezca el campo **Grupo de trabajadores de mantenimiento responsables** y/o **Trabajador responsable** .</span><span class="sxs-lookup"><span data-stu-id="ea81f-117">First create a default responsible maintenance worker or responsible maintenance worker group setup, where you set only the **Responsible maintenance worker group** field and/or the **Responsible worker** field.</span></span> <span data-ttu-id="ea81f-118">Deje en blanco los campos restantes.</span><span class="sxs-lookup"><span data-stu-id="ea81f-118">Leave the remaining fields blank.</span></span> <span data-ttu-id="ea81f-119">Esta configuración predeterminada se usará durante la programación de la orden de trabajo si hay ninguna otra combinación más específica que coincida con el contenido de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ea81f-119">This default setup will be used during work order scheduling if no other, more specific combination matches the contents of the work order.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ea81f-120">Durante la creación de una solicitud de mantenimiento, cuando un trabajador de mantenimiento responsable o un grupo de trabajadores de mantenimiento responsables pasan a estar disponibles para su selección en la página **Todas las solicitudes de mantenimiento**, Administración de activos recorre todos los registros de trabajadores de mantenimiento responsables para buscar una coincidencia.</span><span class="sxs-lookup"><span data-stu-id="ea81f-120">During creation of a maintenance request, when a responsible maintenance worker or responsible maintenance worker group is made available for selection on the **All maintenance requests** page, Asset Management goes through all responsible maintenance worker records to check for a possible match.</span></span> <span data-ttu-id="ea81f-121">Comprueba siempre primero la combinación más específica.</span><span class="sxs-lookup"><span data-stu-id="ea81f-121">It always checks the most specific combination first.</span></span> <span data-ttu-id="ea81f-122">Es decir, Administración de activos primero busca una coincidencia para el campo **Oficio**.</span><span class="sxs-lookup"><span data-stu-id="ea81f-122">In other words, Asset Management first checks for a match for the **Trade** field.</span></span> <span data-ttu-id="ea81f-123">Si no se encuentra ninguna coincidencia, comprueba si hay una coincidencia para el campo **Variante de tipo de trabajo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="ea81f-123">If no match is found, it checks for a match for the **Maintenance job type variant** field.</span></span> <span data-ttu-id="ea81f-124">Si no se encuentra ninguna coincidencia, comprueba si hay una coincidencia para el campo **Tipo de trabajo de mantenimiento**, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="ea81f-124">If no match is found, it checks for a match for the **Maintenance job type** field, and so on.</span></span> <span data-ttu-id="ea81f-125">Como puede ver en el diseño de la página, este comportamiento significa que, para encontrar la combinación más específica, Administración de activos comprueba cada registro de derecha a izquierda en busca de una coincidencia (primero **Oficio**, después **Variante de tipo de trabajo de mantenimiento**, después **Tipo de trabajo de mantenimiento**, **Categoría de tipo de trabajo de mantenimiento**, **Ubicación funcional**, **Activo** y finalmente **Tipo de activo**).</span><span class="sxs-lookup"><span data-stu-id="ea81f-125">As you can see in the layout of the page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match (first **Trade**, then **Maintenance job type variant**, then **Maintenance job type**, then **Maintenance job type category**, then **Functional location**, then **Asset**, and finally **Asset type**).</span></span> <span data-ttu-id="ea81f-126">Si no se encuentra ninguna coincidencia, se utiliza el registro predeterminado que no tiene ninguna selección en esos siete campos.</span><span class="sxs-lookup"><span data-stu-id="ea81f-126">If no match is found, the default record that has no selections in those seven fields is used.</span></span>

<span data-ttu-id="ea81f-127">La ilustración siguiente muestra un ejemplo de la página **Trabajadores de mantenimiento responsables**.</span><span class="sxs-lookup"><span data-stu-id="ea81f-127">The following illustration shows an example of the **Responsible maintenance workers** page.</span></span>

![Página de trabajadores de mantenimiento responsables](media/08-setup-for-requests.png)
