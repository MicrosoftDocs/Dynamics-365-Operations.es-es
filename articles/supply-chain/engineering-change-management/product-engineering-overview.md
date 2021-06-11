---
title: Visión general de la gestión de cambios de ingeniería
description: Este tema proporciona una descripción general de la gestión de cambios de ingeniería, que le ayuda a planificar y gestionar el control de versiones del producto y gestionar los ciclos de vida del producto y los cambios de ingeniería.
author: t-benebo
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: d9430fe02abe58f37d2bfd1431b4da61527d0834
ms.sourcegitcommit: 588f8343aaa654309d2ff735fd437dba6acd9d46
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2021
ms.locfileid: "6115058"
---
# <a name="engineering-change-management-overview"></a><span data-ttu-id="cb87a-103">Visión general de la gestión de cambios de ingeniería</span><span class="sxs-lookup"><span data-stu-id="cb87a-103">Engineering change management overview</span></span>

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a><span data-ttu-id="cb87a-104">Resumen de características</span><span class="sxs-lookup"><span data-stu-id="cb87a-104">Feature summary</span></span>

<span data-ttu-id="cb87a-105">Los fabricantes actuales requieren una sólida gestión de datos de productos, control de versiones y gestión de cambios de ingeniería para tener éxito en un mundo en el que los ciclos de vida de los productos se reducen constantemente, los requisitos de calidad y fiabilidad aumentan y un mayor enfoque en la seguridad del producto.</span><span class="sxs-lookup"><span data-stu-id="cb87a-105">Today's manufacturers require strong product data management, version control, and engineering change management to succeed in a world of constantly shrinking product lifecycles, increased quality and reliability requirements, and an increased focus on product safety.</span></span>

<span data-ttu-id="cb87a-106">La gestión de cambios de ingeniería aporta estructura y disciplina al proceso de gestión de datos de productos y permite que los productos se definan, publiquen y revisen de una manera controlada que sea compatible con los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cb87a-106">Engineering change management brings structure and discipline to the product data management process, and enables products to be defined, released, and revised in a controlled manner that is supported by workflows.</span></span><span data-ttu-id="cb87a-107"> Mediante las versiones de productos y la gestión de cambios de ingeniería, puede documentar, evaluar el impacto y aplicar los cambios de ingeniería a lo largo de todo el ciclo de vida de un producto.</span><span class="sxs-lookup"><span data-stu-id="cb87a-107"> Through product versions and engineering change management, you can document, assess the impact of, and apply engineering changes throughout the whole lifecycle of a product.</span></span>

<span data-ttu-id="cb87a-108">La gestión de cambios de ingeniería le ayuda a planificar y gestionar el control de versiones del producto y gestionar los ciclos de vida del producto y los cambios de ingeniería.</span><span class="sxs-lookup"><span data-stu-id="cb87a-108">Engineering change management helps you plan and manage product versioning, and manage product lifecycles and engineering changes.</span></span> <span data-ttu-id="cb87a-109">A continuación se muestra una lista de sus principales características:</span><span class="sxs-lookup"><span data-stu-id="cb87a-109">Here is a list of its main features:</span></span>

- <span data-ttu-id="cb87a-110">Versiones de productos</span><span class="sxs-lookup"><span data-stu-id="cb87a-110">Product versioning</span></span>
- <span data-ttu-id="cb87a-111">Funcionalidad de lanzamiento de producto mejorada que le permite mantener los datos maestros del producto en una entidad legal (la empresa de ingeniería) y publicar el producto liberado completamente configurado para otras entidades legales</span><span class="sxs-lookup"><span data-stu-id="cb87a-111">Enhanced product release functionality that lets you maintain product master data in one legal entity (the engineering company) and publish the fully configured released product to other legal entities</span></span>
- <span data-ttu-id="cb87a-112">Reglas para validar que se ingrese la información requerida antes de que se active una versión del producto (verificaciones de preparación)</span><span class="sxs-lookup"><span data-stu-id="cb87a-112">Rules for validating that required information is entered before a product version is activated (readiness checks)</span></span>
- <span data-ttu-id="cb87a-113">Gestión mejorada del ciclo de vida del producto a través de un control detallado sobre cuándo se puede usar un producto lanzado en procesos comerciales específicos</span><span class="sxs-lookup"><span data-stu-id="cb87a-113">Improved product lifecycle management through fine-grained control over when a released product can be used in specific business processes</span></span>
- <span data-ttu-id="cb87a-114">Solicitudes de cambios de ingeniería que son compatibles con los flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="cb87a-114">Engineering change requests that are supported by workflows</span></span>
- <span data-ttu-id="cb87a-115">Pedidos de cambios de ingeniería que son compatibles con los flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="cb87a-115">Engineering change orders that are supported by workflows</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

<span data-ttu-id="cb87a-116">El video anterior ([Capacidades de gestión de cambios en Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) está incluido en la [lista de reproducción de Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible en YouTube.</span><span class="sxs-lookup"><span data-stu-id="cb87a-116">The preceding video ([Change management capabilities in Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="turn-on-the-engineering-change-management-and-version-dimension-features-for-your-system"></a><span data-ttu-id="cb87a-117">Active la gestión de cambios de ingeniería y las funciones de dimensión de versión para su sistema.</span><span class="sxs-lookup"><span data-stu-id="cb87a-117">Turn on the engineering change management and version dimension features for your system</span></span>

<span data-ttu-id="cb87a-118">Antes de que pueda usar la administración de cambios de ingeniería, debe activar la característica *Gestión de cambios de ingeniería* y su clave de configuración.</span><span class="sxs-lookup"><span data-stu-id="cb87a-118">Before you can use engineering change management, you must enable both the *Engineering Change Management* feature and its configuration key.</span></span> <span data-ttu-id="cb87a-119">Si también desea realizar un seguimiento de la dimensión de la versión de los productos en las transacciones (opcional), también debe habilitar la función *Dimensión de la versión del producto* y su clave de configuración.</span><span class="sxs-lookup"><span data-stu-id="cb87a-119">If you also want to track the version dimension of products in transactions (optional), then you must also enable the *Product version dimension* feature and its configuration key.</span></span>

<span data-ttu-id="cb87a-120">Primero, active esas funciones siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="cb87a-120">First, turn on the features by following these steps.</span></span>

1. <span data-ttu-id="cb87a-121">Vaya al espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cb87a-121">Go to the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace.</span></span>
1. <span data-ttu-id="cb87a-122">Busque actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="cb87a-122">Check for updates.</span></span>
1. <span data-ttu-id="cb87a-123">Active la característica llamada *Administración de cambios de ingeniería*.</span><span class="sxs-lookup"><span data-stu-id="cb87a-123">Turn on the feature that is named *Engineering Change Management*.</span></span>
1. <span data-ttu-id="cb87a-124">Si desea utilizarlo, active también la función que se denomina *Versión de dimensión del producto*.</span><span class="sxs-lookup"><span data-stu-id="cb87a-124">If you want to use it, also turn on the feature that is named *Product dimension version*.</span></span>

<span data-ttu-id="cb87a-125">Luego, active las claves de configuración siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="cb87a-125">Next, turn on the configuration keys by following these steps.</span></span>

1. <span data-ttu-id="cb87a-126">Coloque su sistema en modo de mantenimiento como se describe en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="cb87a-126">Put your system into maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="cb87a-127">Vaya a **Administración del sistema \> Configuración \> Configuración de licencias**.</span><span class="sxs-lookup"><span data-stu-id="cb87a-127">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="cb87a-128">Expanda el nodo **Comercio**.</span><span class="sxs-lookup"><span data-stu-id="cb87a-128">Expand the **Trade** node.</span></span>
1. <span data-ttu-id="cb87a-129">Habilite la clave de configuración para la función principal seleccionando la casilla **Gestión de cambios de ingeniería**.</span><span class="sxs-lookup"><span data-stu-id="cb87a-129">Enable the configuration key for the main feature by selecting the **Engineering Change Management** checkbox.</span></span>
1. <span data-ttu-id="cb87a-130">Expanda el nodo **Gestión de cambios de ingeniería** y seleccione o desmarque las siguientes casillas de verificación según sea necesario (según las funciones que desee utilizar):</span><span class="sxs-lookup"><span data-stu-id="cb87a-130">Expand the **Engineering Change Management** node, and select or clear the following checkboxes as required (depending on the features that you want to use):</span></span>

    - <span data-ttu-id="cb87a-131">**Búsqueda de atributos**: seleccione esta casilla de verificación para habilitar la [función de búsqueda de atributos](engineering-attributes-and-search.md).</span><span class="sxs-lookup"><span data-stu-id="cb87a-131">**Attribute search** – Select this checkbox to enable the [attribute search feature](engineering-attributes-and-search.md).</span></span> <span data-ttu-id="cb87a-132">Recomendamos habilitar esta función, pero puede desmarcar esta casilla de verificación si no la va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="cb87a-132">We recommend enabling this feature, but you can clear this checkbox if you won't use it.</span></span>
    - <span data-ttu-id="cb87a-133">**Gestión de cambios para la fabricación de procesos**: seleccione esta casilla de verificación si desea utilizar las funciones de administración de cambios de ingeniería para administrar los cambios en las fórmulas para el proceso de fabricación.</span><span class="sxs-lookup"><span data-stu-id="cb87a-133">**Change management for process manufacturing** – Select this checkbox if you want to use Engineering change management features to manage changes in formulas for process manufacturing.</span></span> <span data-ttu-id="cb87a-134">Si no tiene que administrar fórmulas, puede desmarcar esta casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="cb87a-134">If you don't have to manage formulas, you can clear this checkbox.</span></span> <span data-ttu-id="cb87a-135">Para más información, vea [Gestionar cambios en fórmulas y sus ingredientes](manage-formula-changes.md).</span><span class="sxs-lookup"><span data-stu-id="cb87a-135">For more information, see [Manage changes in formulas and their ingredients](manage-formula-changes.md).</span></span>

1. <span data-ttu-id="cb87a-136">Si también desea utilizar la dimensión de versión, seleccione también la casilla **Dimensión del producto: versión**.</span><span class="sxs-lookup"><span data-stu-id="cb87a-136">If you also want to use the version dimension, then select the **Product dimension - Version** checkbox.</span></span> <span data-ttu-id="cb87a-137">(Esta casilla está más abajo en la lista, no anidada debajo del nodo **Gestión de cambios de ingeniería**).</span><span class="sxs-lookup"><span data-stu-id="cb87a-137">(This checkbox is further down the list, not nested under the **Engineering Change Management** node.)</span></span>
1. <span data-ttu-id="cb87a-138">Desactive el modo de mantenimiento como se describe en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="cb87a-138">Turn off maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb87a-139">A partir de abril de 2022, las claves de licencia para **Gestión de cambios de ingeniería** y **Dimensión del producto: versión** estará habilitado de forma predeterminada para todas las instalaciones nuevas, pero seguirá pudiendo deshabilitarlas si es necesario.</span><span class="sxs-lookup"><span data-stu-id="cb87a-139">Starting in April 2022, the license keys for both **Engineering Change Management** and **Product dimension - Version** will be enabled by default for all new installations, but you will still be able to disable them if needed.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
