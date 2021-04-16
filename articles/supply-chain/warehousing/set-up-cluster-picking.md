---
title: Configurar picking en clúster
description: En este tema se describe cómo configurar el picking de clústeres y cómo aplicar la confirmación del artículo con el picking de clústeres.
author: Mirzaab
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSClusterProfile, WHSRFAutoConfirm, WHSWorkCluster
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 481db453656097de8eeb93c89306509493cce3c3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831203"
---
# <a name="set-up-cluster-picking"></a><span data-ttu-id="f401b-103">Configurar picking en clúster</span><span class="sxs-lookup"><span data-stu-id="f401b-103">Set up cluster picking</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f401b-104">Este tema describe cómo permitir a los trabajadores usar sus dispositivos móviles para agrupar el trabajo de picking en clústeres, de forma que puedan seleccionar artículos de una única ubicación para varios pedidos de trabajo al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="f401b-104">This topic describes how to enable workers to use their mobile devices to group picking work into clusters, so that they can pick items from a single location for multiple work orders at the same time.</span></span> <span data-ttu-id="f401b-105">A esto se le llama *picking en clúster*.</span><span class="sxs-lookup"><span data-stu-id="f401b-105">This is called *cluster picking*.</span></span>

## <a name="about-cluster-picking"></a><span data-ttu-id="f401b-106">Acerca del picking en clúster</span><span class="sxs-lookup"><span data-stu-id="f401b-106">About cluster picking</span></span>

<span data-ttu-id="f401b-107">Una vez que los pedidos de trabajo se liberan al almacén, el trabajador puede usar un dispositivo móvil para asignar los pedidos a un clúster.</span><span class="sxs-lookup"><span data-stu-id="f401b-107">After work orders are released to the warehouse, the worker can use a mobile device to assign the orders to a cluster.</span></span> <span data-ttu-id="f401b-108">El clúster organizará el trabajo de picking para el trabajador.</span><span class="sxs-lookup"><span data-stu-id="f401b-108">The cluster will organize the picking work for the worker.</span></span> <span data-ttu-id="f401b-109">Cuando un pedido de trabajo se asigna a un clúster, el trabajador debe usar el picking en clúster para realizar el trabajo de picking para el pedido.</span><span class="sxs-lookup"><span data-stu-id="f401b-109">When a work order is assigned to a cluster, the worker must use cluster picking to perform the picking work for the order.</span></span> <span data-ttu-id="f401b-110">El trabajador no puede utilizar otros métodos de picking.</span><span class="sxs-lookup"><span data-stu-id="f401b-110">The worker cannot use other picking methods.</span></span> <span data-ttu-id="f401b-111">Si un pedido de trabajo se asigna a un clúster por error, el trabajador debe interrumpir el clúster y reconstruirlo.</span><span class="sxs-lookup"><span data-stu-id="f401b-111">If a work order is assigned to a cluster by mistake, the worker must break the cluster and then re-create it.</span></span>

<span data-ttu-id="f401b-112">Si es necesario, un trabajador puede gastar un clúster a otro trabajador.</span><span class="sxs-lookup"><span data-stu-id="f401b-112">If needed, a worker can pass a cluster to another worker.</span></span> <span data-ttu-id="f401b-113">Esto cambia el estado del clúster a Pasado.</span><span class="sxs-lookup"><span data-stu-id="f401b-113">This changes the cluster status to Passed.</span></span> <span data-ttu-id="f401b-114">Cuando el trabajador usa un dispositivo móvil para indicar que el trabajo de picking y colocación se ha completado, el envío o la carga deben confirmarse en el cliente.</span><span class="sxs-lookup"><span data-stu-id="f401b-114">When the worker uses a mobile device to indicate that the picking and put away work is completed, the shipment or load must be confirmed in the client.</span></span>

## <a name="enable-cluster-picking"></a><span data-ttu-id="f401b-115">Habilitar selección de clústeres</span><span class="sxs-lookup"><span data-stu-id="f401b-115">Enable cluster picking</span></span>

<span data-ttu-id="f401b-116">Para habilitar el picking en clúster, debe configurar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f401b-116">To enable cluster picking, you must set up the following:</span></span>

- <span data-ttu-id="f401b-117">**Perfiles de clúster**: especifique si generar automáticamente id. de clúster, el número de posiciones a usar, cuándo interrumpir clústeres y cómo organizar por secuencias y comprobar el trabajo de selección.</span><span class="sxs-lookup"><span data-stu-id="f401b-117">**Cluster profiles** – Specify whether to automatically generate cluster   IDs, the number of positions to use, when to break clusters, and how to   sequence and verify the picking work.</span></span>

- <span data-ttu-id="f401b-118">**Plantillas de trabajo**: defina cómo crear el trabajo de selección para la selección de clústeres.</span><span class="sxs-lookup"><span data-stu-id="f401b-118">**Work templates** – Define how to create the picking work for cluster   picking.</span></span>

- <span data-ttu-id="f401b-119">**Directivas de ubicación**: permite especificar dónde seleccionar los artículos y dónde ponerlos.</span><span class="sxs-lookup"><span data-stu-id="f401b-119">**Location directives** – Specify where to pick items from, and where to put   them.</span></span>

- <span data-ttu-id="f401b-120">**Elementos de menú del dispositivo móvil**: permite configurar un elemento de menú del dispositivo móvil para usar el trabajo existente realizado mediante picking en clúster.</span><span class="sxs-lookup"><span data-stu-id="f401b-120">**Mobile device menu items** – Configure a mobile device menu item to use existing work that is directed by cluster picking.</span></span> <span data-ttu-id="f401b-121">A continuación debe agregar el elemento de menú a un menú del dispositivo móvil para que se muestre en dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="f401b-121">You must then add the menu item to a mobile device menu so that it is displayed on mobile devices.</span></span>

- <span data-ttu-id="f401b-122">**Parámetros de gestión de almacenes**: permite especificar la secuencia numérica que se usará si desea generar identificadores para los clústeres.</span><span class="sxs-lookup"><span data-stu-id="f401b-122">**Warehouse management parameters** – Specify the number sequence to use if   you want to generate identifiers for clusters.</span></span>

## <a name="set-up-a-cluster-profile"></a><span data-ttu-id="f401b-123">Configurar un perfil de clúster</span><span class="sxs-lookup"><span data-stu-id="f401b-123">Set up a cluster profile</span></span>

<span data-ttu-id="f401b-124">Para establecer un perfil de clúster, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f401b-124">To set up a cluster profile, follow these steps:</span></span>

1. <span data-ttu-id="f401b-125">Haga clic en **Gestión de almacenes** \> **Configuración** \> **Dispositivo móvil** \> **Perfiles de clúster**.</span><span class="sxs-lookup"><span data-stu-id="f401b-125">Click **Warehouse management** \> **Setup** \> **Mobile device** \>  **Cluster profiles**.</span></span>

1. <span data-ttu-id="f401b-126">Haga clic en **Nuevo** para crear un nuevo perfil.</span><span class="sxs-lookup"><span data-stu-id="f401b-126">Click **New** to create a new profile.</span></span>

1. <span data-ttu-id="f401b-127">Haga clic en **Crear clúster** y, en **Ordenación de clústeres**, haga clic en **Nuevo** para configurar los criterios de ordenación para el clúster.</span><span class="sxs-lookup"><span data-stu-id="f401b-127">Click **Create cluster** and, under **Cluster sorting**, click **New** to set up the sorting criteria for the cluster.</span></span> <span data-ttu-id="f401b-128">Los criterios de ordenación controlan el orden en que el trabajador debe realizar el trabajo de picking.</span><span class="sxs-lookup"><span data-stu-id="f401b-128">The sorting criteria control the order in which the worker will perform the picking work.</span></span> <span data-ttu-id="f401b-129">Puede agregar tantos criterios como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f401b-129">You can add as many criteria as needed.</span></span>

1. <span data-ttu-id="f401b-130">En el campo **Número de secuencia**, especifique un número para definir el orden en que se procesarán los criterios de ordenación.</span><span class="sxs-lookup"><span data-stu-id="f401b-130">In the **Sequence number** field, enter a number to define the order in  which the sorting criteria are processed.</span></span>

1. <span data-ttu-id="f401b-131">En el campo **Nombre de campo**, seleccione el campo que va a determinar la ordenación.</span><span class="sxs-lookup"><span data-stu-id="f401b-131">In the **Field name** field, select the field that will determine the sorting.</span></span> <span data-ttu-id="f401b-132">Por ejemplo, si selecciona el campo **WMSLocationId**, el trabajo se ordenará por ubicación.</span><span class="sxs-lookup"><span data-stu-id="f401b-132">For example, if you select the **WMSLocationId** field, the work will be sorted by location.</span></span>

1. <span data-ttu-id="f401b-133">En el campo **Ordenación**, seleccione una de las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="f401b-133">In the **Sorting** field, select one of the following options.</span></span>

| <span data-ttu-id="f401b-134">**Opción**</span><span class="sxs-lookup"><span data-stu-id="f401b-134">**Option**</span></span>     | <span data-ttu-id="f401b-135">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f401b-135">**Description**</span></span>                                                                                                                                                                                                                    |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f401b-136">**Ascendente**</span><span class="sxs-lookup"><span data-stu-id="f401b-136">**Ascending**</span></span>  | <span data-ttu-id="f401b-137">El trabajo de picking se ordena de forma ascendente según los criterios de ordenación.</span><span class="sxs-lookup"><span data-stu-id="f401b-137">Picking work is sequenced in ascending order based on the sorting criteria.</span></span> <span data-ttu-id="f401b-138">Por ejemplo, si usa el campo **WMSLocationId** como criterios de ordenación, y sus identificadores de la ubicación son 1, 2, 3 y 4, se seleccionará la ubicación 4 primero.</span><span class="sxs-lookup"><span data-stu-id="f401b-138">For example, if you use the **WMSLocationId** field as sorting criteria, and your location IDs are 1, 2, 3, and 4, you will pick from location 4 first.</span></span> |
| <span data-ttu-id="f401b-139">**Descendente**</span><span class="sxs-lookup"><span data-stu-id="f401b-139">**Descending**</span></span> | <span data-ttu-id="f401b-140">El trabajo de picking se ordena de forma descendente según los criterios de ordenación.</span><span class="sxs-lookup"><span data-stu-id="f401b-140">Picking work is sequenced in descending order based on the sorting criteria.</span></span> <span data-ttu-id="f401b-141">Por ejemplo, si usa el campo **WMSLocationId** como criterios de ordenación, y sus identificadores de la ubicación son 1, 2, 3 y 4, se seleccionará la ubicación 1 primero.</span><span class="sxs-lookup"><span data-stu-id="f401b-141">For example, if you use the **WMSLocationId** field as sorting criteria, and your location IDs are 1, 2, 3, and 4, you will pick from location 1 first.</span></span> |

## <a name="item-confirmation"></a><span data-ttu-id="f401b-142">Configuración del artículo</span><span class="sxs-lookup"><span data-stu-id="f401b-142">Item confirmation</span></span>

<span data-ttu-id="f401b-143">Cuando se aplica el picking en clúster, es esencial la confirmación del artículo para comprobar que los artículos se agregan a los clústeres.</span><span class="sxs-lookup"><span data-stu-id="f401b-143">When cluster picking is applied, item confirmation is crucial to verify the items that are added to clusters.</span></span> <span data-ttu-id="f401b-144">Puede comprobar los artículos del picking en clúster durante el proceso de picking en clúster.</span><span class="sxs-lookup"><span data-stu-id="f401b-144">You can verify items in cluster picking during the cluster picking process.</span></span> <span data-ttu-id="f401b-145">La configuración se basa en la configuración del código de barras del producto.</span><span class="sxs-lookup"><span data-stu-id="f401b-145">The setup is based on the product bar code setup.</span></span>

### <a name="set-up-item-verification-with-cluster-picking"></a><span data-ttu-id="f401b-146">Establecer la comprobación de artículos con picking en clúster</span><span class="sxs-lookup"><span data-stu-id="f401b-146">Set up item verification with cluster picking</span></span>

1. <span data-ttu-id="f401b-147">En un elemento de menú del dispositivo móvil, abra el formulario de configuración para la confirmación del trabajo: **Gestión de almacenes** \> **Gestión de almacén** \> **Configuración** \> **Dispositivo móvil** \> **Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="f401b-147">On a mobile device menu item, open the setup form for work confirmation:  **Warehouse management** \> **Warehouse management** \> **Setup** \>  **Mobile device** \> **Mobile device menu items**.</span></span>

1. <span data-ttu-id="f401b-148">En el elemento de menú del dispositivo móvil, abra **Configuración de la confirmación de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="f401b-148">From the mobile device menu item, open **Work confirmation setup**.</span></span> <span data-ttu-id="f401b-149">La opción **Confirmación del producto** le permite que se compruebe cada pieza de inventario desde el dispositivo móvil cuando se escanea.</span><span class="sxs-lookup"><span data-stu-id="f401b-149">The **Product confirmation** option allows you to verify each piece of inventory from the mobile device when scanned.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]