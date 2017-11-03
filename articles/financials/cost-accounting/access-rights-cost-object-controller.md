---
title: Definir los derechos de acceso de un controlador de objeto de coste
description: "Este tema proporciona información sobre los derechos de acceso para los controladores de objeto de coste."
author: AndersGirke
manager: AnnBe
ms.date: 06/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: YuyuScheller
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 2ba38ddc5c717df29462e4316dc5045d0eef8c1a
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="access-rights-of-a-cost-object-controller"></a><span data-ttu-id="f39e7-103">Derechos de acceso de un controlador de objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f39e7-103">Access rights of a cost object controller</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f39e7-104">El área de trabajo **Control de costes** es un punto central donde los administradores pueden ver el rendimiento de los objetos de coste.</span><span class="sxs-lookup"><span data-stu-id="f39e7-104">The **Cost control** workspace is a central point where managers can view the performance of their cost objects.</span></span> <span data-ttu-id="f39e7-105">Este espacio de trabajo permite a los administradores consumir datos de contabilidad de costes aunque no sean contables de costes.</span><span class="sxs-lookup"><span data-stu-id="f39e7-105">This workspace lets managers consume Cost accounting data even though they aren't cost accountants.</span></span> <span data-ttu-id="f39e7-106">Por razones de seguridad, los administradores deben poder ver únicamente los datos de la contabilidad de costes relacionados con los objetos de coste específicos de los que sean responsables.</span><span class="sxs-lookup"><span data-stu-id="f39e7-106">For security reasons, managers should be allowed to see only the Cost accounting data that is related to the specific cost objects that they are responsible for.</span></span>

<span data-ttu-id="f39e7-107">Existen cuatro roles únicos en contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="f39e7-107">There are four unique roles in Cost accounting.</span></span>

| <span data-ttu-id="f39e7-108">Nombre de rol</span><span class="sxs-lookup"><span data-stu-id="f39e7-108">Role name</span></span>               | <span data-ttu-id="f39e7-109">Licencia</span><span class="sxs-lookup"><span data-stu-id="f39e7-109">License</span></span>      |
|-------------------------|--------------|
| <span data-ttu-id="f39e7-110">Administrador de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="f39e7-110">Cost accounting manager</span></span> | <span data-ttu-id="f39e7-111">Actividad</span><span class="sxs-lookup"><span data-stu-id="f39e7-111">Activity</span></span>     |
| <span data-ttu-id="f39e7-112">Contable de costes</span><span class="sxs-lookup"><span data-stu-id="f39e7-112">Cost accountant</span></span>         | <span data-ttu-id="f39e7-113">Operations</span><span class="sxs-lookup"><span data-stu-id="f39e7-113">Operations</span></span>   |
| <span data-ttu-id="f39e7-114">Contable de costes</span><span class="sxs-lookup"><span data-stu-id="f39e7-114">Cost accountant clerk</span></span>   | <span data-ttu-id="f39e7-115">Operations</span><span class="sxs-lookup"><span data-stu-id="f39e7-115">Operations</span></span>   |
| <span data-ttu-id="f39e7-116">Controlador de objeto de coste</span><span class="sxs-lookup"><span data-stu-id="f39e7-116">Cost object controller</span></span>  | <span data-ttu-id="f39e7-117">Miembros del equipo</span><span class="sxs-lookup"><span data-stu-id="f39e7-117">Team members</span></span> |

<span data-ttu-id="f39e7-118">Este tema explica cómo asignar el rol **Controlador de objeto de coste** a un administrador.</span><span class="sxs-lookup"><span data-stu-id="f39e7-118">This topic explains how to assign the **Cost object controller** role to a manager.</span></span>

<span data-ttu-id="f39e7-119">Cuando el rol **Controlador de objeto de coste** se asigna a un administrador, este puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="f39e7-119">When the **Cost object controller** role is assigned to a manager, the manager can perform the following tasks:</span></span>

- <span data-ttu-id="f39e7-120">Acceder al espacio de trabajo **Control de costes** (en el cliente).</span><span class="sxs-lookup"><span data-stu-id="f39e7-120">Access the **Cost control** workspace (in the client).</span></span>

    - <span data-ttu-id="f39e7-121">Explorar y tener acceso de vista a las páginas que admiten exploración.</span><span class="sxs-lookup"><span data-stu-id="f39e7-121">Drill through and have view access to the pages that support the drill-through experience.</span></span>

- <span data-ttu-id="f39e7-122">Acceder al espacio de trabajo **Control de costes** (en el la aplicación móvil).</span><span class="sxs-lookup"><span data-stu-id="f39e7-122">Access the **Cost control** workspace (in the mobile application).</span></span>

> [!NOTE]
> <span data-ttu-id="f39e7-123">El rol **Controlador de objeto de coste** no controla a qué objetos de coste puede el usuario acceder y ver sus datos.</span><span class="sxs-lookup"><span data-stu-id="f39e7-123">The **Cost object controller** role doesn't control which cost objects the user can access and view data for.</span></span> <span data-ttu-id="f39e7-124">La seguridad de filas se proporciona mediante jerarquías de dimensión y la jerarquía de listas de acceso.</span><span class="sxs-lookup"><span data-stu-id="f39e7-124">Row-level security is provided via dimension hierarchies and the Access list hierarchy.</span></span>

## <a name="grant-access-rights"></a><span data-ttu-id="f39e7-125">Conceder derechos de acceso</span><span class="sxs-lookup"><span data-stu-id="f39e7-125">Grant access rights</span></span>
<span data-ttu-id="f39e7-126">El siguiente ejemplo muestra cómo puede ser el aspecto de las jerarquías de dimensión.</span><span class="sxs-lookup"><span data-stu-id="f39e7-126">The following example shows what a dimension hierarchy can look like.</span></span>

<span data-ttu-id="f39e7-127">**Detalles de jerarquía de dimensión**</span><span class="sxs-lookup"><span data-stu-id="f39e7-127">**Dimension hierarchy details**</span></span>

| <span data-ttu-id="f39e7-128">Nombre de jerarquía de dimensión</span><span class="sxs-lookup"><span data-stu-id="f39e7-128">Dimension hierarchy name</span></span> | <span data-ttu-id="f39e7-129">Dimensión</span><span class="sxs-lookup"><span data-stu-id="f39e7-129">Dimension</span></span>    | <span data-ttu-id="f39e7-130">Nombre de tipo de jerarquía de dimensión</span><span class="sxs-lookup"><span data-stu-id="f39e7-130">Dimension hierarchy type name</span></span>      | <span data-ttu-id="f39e7-131">Jerarquía de listas de acceso</span><span class="sxs-lookup"><span data-stu-id="f39e7-131">Access list hierarchy</span></span> |
|--------------------------|--------------|------------------------------------|-----------------------|
| <span data-ttu-id="f39e7-132">Organización</span><span class="sxs-lookup"><span data-stu-id="f39e7-132">Organization</span></span>             | <span data-ttu-id="f39e7-133">Centros de coste</span><span class="sxs-lookup"><span data-stu-id="f39e7-133">Cost centers</span></span> | <span data-ttu-id="f39e7-134">Jerarquía de clasificación de dimensiones</span><span class="sxs-lookup"><span data-stu-id="f39e7-134">Dimension classification hierarchy</span></span> | <span data-ttu-id="f39e7-135">**Sí**</span><span class="sxs-lookup"><span data-stu-id="f39e7-135">**Yes**</span></span>               |

<span data-ttu-id="f39e7-136">Puede usar el FastTab **Usuarios** en el diseñador de jerarquías para insertar uno o más Id. de usuarios en cada nodo.</span><span class="sxs-lookup"><span data-stu-id="f39e7-136">You can use the **Users** FastTab in the hierarchy designer to insert one or more user IDs on each node.</span></span>

|                                   | <span data-ttu-id="f39e7-137">Usuarios</span><span class="sxs-lookup"><span data-stu-id="f39e7-137">Users</span></span>            | <span data-ttu-id="f39e7-138">Intervalos de miembros de dimensión</span><span class="sxs-lookup"><span data-stu-id="f39e7-138">Dimension member ranges</span></span>   |                         |
|-----------------------------------|------------------|---------------------------|-------------------------|
| <span data-ttu-id="f39e7-139">**Nodos**</span><span class="sxs-lookup"><span data-stu-id="f39e7-139">**Nodes**</span></span>                         | <span data-ttu-id="f39e7-140">**Id. de usuario**</span><span class="sxs-lookup"><span data-stu-id="f39e7-140">**User ID**</span></span>      | <span data-ttu-id="f39e7-141">**Desde miembro de dimensión**</span><span class="sxs-lookup"><span data-stu-id="f39e7-141">**From dimension member**</span></span> | <span data-ttu-id="f39e7-142">**Hasta miembro de dimensión**</span><span class="sxs-lookup"><span data-stu-id="f39e7-142">**To dimension member**</span></span> |
| <span data-ttu-id="f39e7-143">Organización</span><span class="sxs-lookup"><span data-stu-id="f39e7-143">Organization</span></span>                      | <span data-ttu-id="f39e7-144">Benjamin, Claire</span><span class="sxs-lookup"><span data-stu-id="f39e7-144">Benjamin, Claire</span></span> |                           |                         |
| <span data-ttu-id="f39e7-145">&nbsp;&nbsp;Administrador</span><span class="sxs-lookup"><span data-stu-id="f39e7-145">&nbsp;&nbsp;Admin</span></span>                 | <span data-ttu-id="f39e7-146">Abril</span><span class="sxs-lookup"><span data-stu-id="f39e7-146">April</span></span>            |                           |                         |
| <span data-ttu-id="f39e7-147">&nbsp;&nbsp;&nbsp;&nbsp;Finanzas</span><span class="sxs-lookup"><span data-stu-id="f39e7-147">&nbsp;&nbsp;&nbsp;&nbsp;Finance</span></span>   | <span data-ttu-id="f39e7-148">Alicia</span><span class="sxs-lookup"><span data-stu-id="f39e7-148">Alicia</span></span>           | <span data-ttu-id="f39e7-149">CC002</span><span class="sxs-lookup"><span data-stu-id="f39e7-149">CC002</span></span>                     | <span data-ttu-id="f39e7-150">CC003</span><span class="sxs-lookup"><span data-stu-id="f39e7-150">CC003</span></span>                   |
|                                   |                  | <span data-ttu-id="f39e7-151">CC007</span><span class="sxs-lookup"><span data-stu-id="f39e7-151">CC007</span></span>                     | <span data-ttu-id="f39e7-152">CC007</span><span class="sxs-lookup"><span data-stu-id="f39e7-152">CC007</span></span>                   |
| <span data-ttu-id="f39e7-153">&nbsp;&nbsp;&nbsp;&nbsp;RR. HH.</span><span class="sxs-lookup"><span data-stu-id="f39e7-153">&nbsp;&nbsp;&nbsp;&nbsp;HR</span></span>        | <span data-ttu-id="f39e7-154">Arnie</span><span class="sxs-lookup"><span data-stu-id="f39e7-154">Arnie</span></span>            | <span data-ttu-id="f39e7-155">CC001</span><span class="sxs-lookup"><span data-stu-id="f39e7-155">CC001</span></span>                     | <span data-ttu-id="f39e7-156">CC001</span><span class="sxs-lookup"><span data-stu-id="f39e7-156">CC001</span></span>                   |
| <span data-ttu-id="f39e7-157">&nbsp;&nbsp;Producción</span><span class="sxs-lookup"><span data-stu-id="f39e7-157">&nbsp;&nbsp;Production</span></span>            | <span data-ttu-id="f39e7-158">David</span><span class="sxs-lookup"><span data-stu-id="f39e7-158">David</span></span>            |                           |                         |
| <span data-ttu-id="f39e7-159">&nbsp;&nbsp;&nbsp;&nbsp;Empaquetado</span><span class="sxs-lookup"><span data-stu-id="f39e7-159">&nbsp;&nbsp;&nbsp;&nbsp;Packaging</span></span> | <span data-ttu-id="f39e7-160">Ellen</span><span class="sxs-lookup"><span data-stu-id="f39e7-160">Ellen</span></span>            | <span data-ttu-id="f39e7-161">CC005</span><span class="sxs-lookup"><span data-stu-id="f39e7-161">CC005</span></span>                     | <span data-ttu-id="f39e7-162">CC005</span><span class="sxs-lookup"><span data-stu-id="f39e7-162">CC005</span></span>                   |
| <span data-ttu-id="f39e7-163">&nbsp;&nbsp;&nbsp;&nbsp;Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f39e7-163">&nbsp;&nbsp;&nbsp;&nbsp;Assembly</span></span>  | <span data-ttu-id="f39e7-164">Chris</span><span class="sxs-lookup"><span data-stu-id="f39e7-164">Chris</span></span>            | <span data-ttu-id="f39e7-165">CC006</span><span class="sxs-lookup"><span data-stu-id="f39e7-165">CC006</span></span>                     | <span data-ttu-id="f39e7-166">CC006</span><span class="sxs-lookup"><span data-stu-id="f39e7-166">CC006</span></span>                   |

> [!NOTE]
> <span data-ttu-id="f39e7-167">Los contables de coste debe asignarse al nivel superior de la jerarquía, de modo que puedan ver todas las entradas de contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="f39e7-167">Cost accountants should be assigned to the top level of the hierarchy, so that they can see all entries in Cost accounting.</span></span>

<span data-ttu-id="f39e7-168">Antes de que se puedan aplicar la jerarquía de listas de acceso y sus configuraciones de seguridad, debe establecer la opción **Habilitar acceso de visualización para los miembros de dimensión de objeto de coste** en **Sí** en la pestaña **General** de la página **Parámetros de la contabilidad de costes** (**Contabilidad de costes** > **Configuración** > **Parámetros**).</span><span class="sxs-lookup"><span data-stu-id="f39e7-168">Before the Access list hierarchy and its security settings can be applied, the **Enable view access for cost object dimension members** option must be set to **Yes** on the **General** tab of the **Cost accounting parameters** page (**Cost accounting** > **Setup** > **Parameters**).</span></span>

<span data-ttu-id="f39e7-169">Los valores para la jerarquía de listas de acceso se utilizan para controlar los datos que se muestran en siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="f39e7-169">The settings for the Access list hierarchy are used to control the data that is shown in following areas:</span></span>

- <span data-ttu-id="f39e7-170">Espacio de trabajo **Control de costes** (en el cliente):</span><span class="sxs-lookup"><span data-stu-id="f39e7-170">**Cost control** workspace (in the client):</span></span>

    - <span data-ttu-id="f39e7-171">Datos en las páginas para las que se usan para la obtención de detalles</span><span class="sxs-lookup"><span data-stu-id="f39e7-171">Data on the pages that are used for drill-through</span></span>

- <span data-ttu-id="f39e7-172">Espacio de trabajo **Control de costes** (en el la aplicación móvil):</span><span class="sxs-lookup"><span data-stu-id="f39e7-172">**Cost control** workspace (in the mobile application):</span></span>

    - <span data-ttu-id="f39e7-173">Saldos en tarjetas</span><span class="sxs-lookup"><span data-stu-id="f39e7-173">Balances in cards</span></span>

- <span data-ttu-id="f39e7-174">Microsoft Power BI:</span><span class="sxs-lookup"><span data-stu-id="f39e7-174">Microsoft Power BI:</span></span>

    - <span data-ttu-id="f39e7-175">Datos que se muestran en las visualizaciones de Power BI</span><span class="sxs-lookup"><span data-stu-id="f39e7-175">Data that is shown in Power BI visualizations</span></span>
    - <span data-ttu-id="f39e7-176">Visualizaciones de datos de Power BI que se insertan en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (cliente)</span><span class="sxs-lookup"><span data-stu-id="f39e7-176">Data Power BI visualizations that are embedded in the Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, client</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="f39e7-177">Antes de que la jerarquía de listas de acceso pueda afectar a los datos de Power BI, se deben emparejar la jerarquía de listas de acceso y la seguridad en Power BI.</span><span class="sxs-lookup"><span data-stu-id="f39e7-177">Before the Access list hierarchy can affect data in Power BI, the Access list hierarchy and row-level security in Power BI must be paired.</span></span> <span data-ttu-id="f39e7-178">Para obtener más información, consulte [Configurar la seguridad del paquete del contenido de contabilidad de costes](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).</span><span class="sxs-lookup"><span data-stu-id="f39e7-178">For more information, see [Set up security for Cost accounting content pack](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).</span></span>
> - <span data-ttu-id="f39e7-179">Este tema muestra los requisitos previos que deben estar presentes antes de poder usar el espacio de trabajo **Control de costes**.</span><span class="sxs-lookup"><span data-stu-id="f39e7-179">This topic shows the prerequisites that must be in place before you can use the **Cost control** workspace.</span></span>

<span data-ttu-id="f39e7-180">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f39e7-180">See also</span></span>

- [<span data-ttu-id="f39e7-181">Espacio de trabajo de control de costes</span><span class="sxs-lookup"><span data-stu-id="f39e7-181">Cost control workspace</span></span>](cost-control-workspace.md)
- [<span data-ttu-id="f39e7-182">Jerarquía de dimensiones</span><span class="sxs-lookup"><span data-stu-id="f39e7-182">Dimension hierarchy</span></span>](dimension-hierarchy.md)
- [<span data-ttu-id="f39e7-183">Configurar la seguridad del paquete contenido de contabilidad de costes</span><span class="sxs-lookup"><span data-stu-id="f39e7-183">Set up security for Cost accounting content pack</span></span>](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)

