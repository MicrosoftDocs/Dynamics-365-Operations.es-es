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
ms.openlocfilehash: 964db71efc9dc81d60199e37de8668de9d667496
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842090"
---
# <a name="engineering-change-management-overview"></a><span data-ttu-id="a6087-103">Visión general de la gestión de cambios de ingeniería</span><span class="sxs-lookup"><span data-stu-id="a6087-103">Engineering change management overview</span></span>

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a><span data-ttu-id="a6087-104">Resumen de características</span><span class="sxs-lookup"><span data-stu-id="a6087-104">Feature summary</span></span>

<span data-ttu-id="a6087-105">Los fabricantes actuales requieren una sólida gestión de datos de productos, control de versiones y gestión de cambios de ingeniería para tener éxito en un mundo en el que los ciclos de vida de los productos se reducen constantemente, los requisitos de calidad y fiabilidad aumentan y un mayor enfoque en la seguridad del producto.</span><span class="sxs-lookup"><span data-stu-id="a6087-105">Today's manufacturers require strong product data management, version control, and engineering change management to succeed in a world of constantly shrinking product lifecycles, increased quality and reliability requirements, and an increased focus on product safety.</span></span>

<span data-ttu-id="a6087-106">La gestión de cambios de ingeniería aporta estructura y disciplina al proceso de gestión de datos de productos y permite que los productos se definan, publiquen y revisen de una manera controlada que sea compatible con los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a6087-106">Engineering change management brings structure and discipline to the product data management process, and enables products to be defined, released, and revised in a controlled manner that is supported by workflows.</span></span><span data-ttu-id="a6087-107"> Mediante las versiones de productos y la gestión de cambios de ingeniería, puede documentar, evaluar el impacto y aplicar los cambios de ingeniería a lo largo de todo el ciclo de vida de un producto.</span><span class="sxs-lookup"><span data-stu-id="a6087-107"> Through product versions and engineering change management, you can document, assess the impact of, and apply engineering changes throughout the whole lifecycle of a product.</span></span>

<span data-ttu-id="a6087-108">La gestión de cambios de ingeniería le ayuda a planificar y gestionar el control de versiones del producto y gestionar los ciclos de vida del producto y los cambios de ingeniería.</span><span class="sxs-lookup"><span data-stu-id="a6087-108">Engineering change management helps you plan and manage product versioning, and manage product lifecycles and engineering changes.</span></span> <span data-ttu-id="a6087-109">A continuación se muestra una lista de sus principales características:</span><span class="sxs-lookup"><span data-stu-id="a6087-109">Here is a list of its main features:</span></span>

- <span data-ttu-id="a6087-110">Versiones de productos</span><span class="sxs-lookup"><span data-stu-id="a6087-110">Product versioning</span></span>
- <span data-ttu-id="a6087-111">Funcionalidad de lanzamiento de producto mejorada que le permite mantener los datos maestros del producto en una entidad legal (la empresa de ingeniería) y publicar el producto liberado completamente configurado para otras entidades legales</span><span class="sxs-lookup"><span data-stu-id="a6087-111">Enhanced product release functionality that lets you maintain product master data in one legal entity (the engineering company) and publish the fully configured released product to other legal entities</span></span>
- <span data-ttu-id="a6087-112">Reglas para validar que se ingrese la información requerida antes de que se active una versión del producto (verificaciones de preparación)</span><span class="sxs-lookup"><span data-stu-id="a6087-112">Rules for validating that required information is entered before a product version is activated (readiness checks)</span></span>
- <span data-ttu-id="a6087-113">Gestión mejorada del ciclo de vida del producto a través de un control detallado sobre cuándo se puede usar un producto lanzado en procesos comerciales específicos</span><span class="sxs-lookup"><span data-stu-id="a6087-113">Improved product lifecycle management through fine-grained control over when a released product can be used in specific business processes</span></span>
- <span data-ttu-id="a6087-114">Solicitudes de cambios de ingeniería que son compatibles con los flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="a6087-114">Engineering change requests that are supported by workflows</span></span>
- <span data-ttu-id="a6087-115">Pedidos de cambios de ingeniería que son compatibles con los flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="a6087-115">Engineering change orders that are supported by workflows</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

<span data-ttu-id="a6087-116">El video anterior ([Capacidades de gestión de cambios en Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) está incluido en la [lista de reproducción de Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible en YouTube.</span><span class="sxs-lookup"><span data-stu-id="a6087-116">The preceding video ([Change management capabilities in Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="turn-on-the-engineering-change-management-and-version-dimension-features-for-your-system"></a><span data-ttu-id="a6087-117">Active la gestión de cambios de ingeniería y las funciones de dimensión de versión para su sistema.</span><span class="sxs-lookup"><span data-stu-id="a6087-117">Turn on the engineering change management and version dimension features for your system</span></span>

<span data-ttu-id="a6087-118">Antes de que pueda usar la administración de cambios de ingeniería, debe activar la característica *Gestión de cambios de ingeniería* y su clave de configuración.</span><span class="sxs-lookup"><span data-stu-id="a6087-118">Before you can use engineering change management, you must enable both the *Engineering Change Management* feature and its configuration key.</span></span> <span data-ttu-id="a6087-119">Si también desea realizar un seguimiento de la dimensión de la versión de los productos en las transacciones (opcional), también debe habilitar la función *Dimensión de la versión del producto* y su clave de configuración.</span><span class="sxs-lookup"><span data-stu-id="a6087-119">If you also want to track the version dimension of products in transactions (optional), then you must also enable the *Product version dimension* feature and its configuration key.</span></span>

<span data-ttu-id="a6087-120">Primero, active esas funciones siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a6087-120">First, turn on the features by following these steps.</span></span>

1. <span data-ttu-id="a6087-121">Vaya a [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a6087-121">Go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
1. <span data-ttu-id="a6087-122">Busque actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="a6087-122">Check for updates.</span></span>
1. <span data-ttu-id="a6087-123">Active la característica llamada **Administración de cambios de ingeniería**.</span><span class="sxs-lookup"><span data-stu-id="a6087-123">Turn on the feature that is named **Engineering Change Management**.</span></span>
1. <span data-ttu-id="a6087-124">Si desea utilizarlo, active también la función que se denomina **Versión de dimensión del producto**.</span><span class="sxs-lookup"><span data-stu-id="a6087-124">If you want to use it, then also turn on the feature that is named **Product dimension version**.</span></span>

<span data-ttu-id="a6087-125">Luego, active las claves de configuración siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a6087-125">Next, turn on the configuration keys by following these steps.</span></span>

1. <span data-ttu-id="a6087-126">Coloque su sistema en modo de mantenimiento como se describe en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="a6087-126">Put your system into maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="a6087-127">Vaya a **Administración del sistema \> Configuración \> Configuración de licencias**.</span><span class="sxs-lookup"><span data-stu-id="a6087-127">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="a6087-128">Expanda el nodo **Comercio**.</span><span class="sxs-lookup"><span data-stu-id="a6087-128">Expand the **Trade** node</span></span>
1. <span data-ttu-id="a6087-129">Seleccione la casilla **Gestión de cambios de ingeniería**.</span><span class="sxs-lookup"><span data-stu-id="a6087-129">Select the **Engineering Change Management** check box.</span></span>
1. <span data-ttu-id="a6087-130">Si desea utilizarlo, seleccione también la casilla **Dimensión del producto - Versión**.</span><span class="sxs-lookup"><span data-stu-id="a6087-130">If you want to use it, then also select the **Product dimension - Version** check box.</span></span>
1. <span data-ttu-id="a6087-131">Desactive el modo de mantenimiento como se describe en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="a6087-131">Turn off maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
