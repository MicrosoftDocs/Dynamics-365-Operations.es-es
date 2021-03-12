---
title: Visión general de la gestión de cambios de ingeniería
description: Este tema proporciona una descripción general de la gestión de cambios de ingeniería, que le ayuda a planificar y gestionar el control de versiones del producto y gestionar los ciclos de vida del producto y los cambios de ingeniería.
author: t-benebo
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: b081cd8d56217b8cf76db824c29482d453fc9ea3
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001957"
---
# <a name="engineering-change-management-overview"></a><span data-ttu-id="b8c13-103">Visión general de la gestión de cambios de ingeniería</span><span class="sxs-lookup"><span data-stu-id="b8c13-103">Engineering change management overview</span></span>

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a><span data-ttu-id="b8c13-104">Resumen de características</span><span class="sxs-lookup"><span data-stu-id="b8c13-104">Feature summary</span></span>

<span data-ttu-id="b8c13-105">Los fabricantes actuales requieren una sólida gestión de datos de productos, control de versiones y gestión de cambios de ingeniería para tener éxito en un mundo en el que los ciclos de vida de los productos se reducen constantemente, los requisitos de calidad y fiabilidad aumentan y un mayor enfoque en la seguridad del producto.</span><span class="sxs-lookup"><span data-stu-id="b8c13-105">Today's manufacturers require strong product data management, version control, and engineering change management to succeed in a world of constantly shrinking product lifecycles, increased quality and reliability requirements, and an increased focus on product safety.</span></span>

<span data-ttu-id="b8c13-106">La gestión de cambios de ingeniería aporta estructura y disciplina al proceso de gestión de datos de productos y permite que los productos se definan, publiquen y revisen de una manera controlada que sea compatible con los flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b8c13-106">Engineering change management brings structure and discipline to the product data management process, and enables products to be defined, released, and revised in a controlled manner that is supported by workflows.</span></span><span data-ttu-id="b8c13-107"> Mediante las versiones de productos y la gestión de cambios de ingeniería, puede documentar, evaluar el impacto y aplicar los cambios de ingeniería a lo largo de todo el ciclo de vida de un producto.</span><span class="sxs-lookup"><span data-stu-id="b8c13-107"> Through product versions and engineering change management, you can document, assess the impact of, and apply engineering changes throughout the whole lifecycle of a product.</span></span>

<span data-ttu-id="b8c13-108">La gestión de cambios de ingeniería le ayuda a planificar y gestionar el control de versiones del producto y gestionar los ciclos de vida del producto y los cambios de ingeniería.</span><span class="sxs-lookup"><span data-stu-id="b8c13-108">Engineering change management helps you plan and manage product versioning, and manage product lifecycles and engineering changes.</span></span> <span data-ttu-id="b8c13-109">A continuación se muestra una lista de sus principales características:</span><span class="sxs-lookup"><span data-stu-id="b8c13-109">Here is a list of its main features:</span></span>

- <span data-ttu-id="b8c13-110">Versiones de productos</span><span class="sxs-lookup"><span data-stu-id="b8c13-110">Product versioning</span></span>
- <span data-ttu-id="b8c13-111">Funcionalidad de lanzamiento de producto mejorada que le permite mantener los datos maestros del producto en una entidad legal (la empresa de ingeniería) y publicar el producto liberado completamente configurado para otras entidades legales</span><span class="sxs-lookup"><span data-stu-id="b8c13-111">Enhanced product release functionality that lets you maintain product master data in one legal entity (the engineering company) and publish the fully configured released product to other legal entities</span></span>
- <span data-ttu-id="b8c13-112">Reglas para validar que se ingrese la información requerida antes de que se active una versión del producto (verificaciones de preparación)</span><span class="sxs-lookup"><span data-stu-id="b8c13-112">Rules for validating that required information is entered before a product version is activated (readiness checks)</span></span>
- <span data-ttu-id="b8c13-113">Gestión mejorada del ciclo de vida del producto a través de un control detallado sobre cuándo se puede usar un producto lanzado en procesos comerciales específicos</span><span class="sxs-lookup"><span data-stu-id="b8c13-113">Improved product lifecycle management through fine-grained control over when a released product can be used in specific business processes</span></span>
- <span data-ttu-id="b8c13-114">Solicitudes de cambios de ingeniería que son compatibles con los flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="b8c13-114">Engineering change requests that are supported by workflows</span></span>
- <span data-ttu-id="b8c13-115">Pedidos de cambios de ingeniería que son compatibles con los flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="b8c13-115">Engineering change orders that are supported by workflows</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

<span data-ttu-id="b8c13-116">El video anterior ([Capacidades de gestión de cambios en Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) está incluido en la [lista de reproducción de Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible en YouTube.</span><span class="sxs-lookup"><span data-stu-id="b8c13-116">The preceding video ([Change management capabilities in Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

## <a name="turn-on-engineering-change-management-for-your-system"></a><span data-ttu-id="b8c13-117">Active la gestión de cambios de ingeniería para su sistema</span><span class="sxs-lookup"><span data-stu-id="b8c13-117">Turn on engineering change management for your system</span></span>

<span data-ttu-id="b8c13-118">Primero, active la gestión de cambios de ingeniería siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b8c13-118">First, turn on engineering change management by following these steps.</span></span>

1. <span data-ttu-id="b8c13-119">Vaya a [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b8c13-119">Go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
1. <span data-ttu-id="b8c13-120">Busque actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="b8c13-120">Check for updates.</span></span>
1. <span data-ttu-id="b8c13-121">Active la característica llamada **Administración de cambios de ingeniería**.</span><span class="sxs-lookup"><span data-stu-id="b8c13-121">Turn on the feature that is named **Engineering Change Management**.</span></span>

<span data-ttu-id="b8c13-122">A continuación, active la clave de configuración de **Gestión de cambios de ingeniería** siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b8c13-122">Next, turn on the **Engineering Change Management** configuration key by following these steps.</span></span>

1. <span data-ttu-id="b8c13-123">Coloque su sistema en modo de mantenimiento como se describe en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="b8c13-123">Put your system into maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="b8c13-124">Vaya a **Administración del sistema \> Configuración \> Configuración de licencias**.</span><span class="sxs-lookup"><span data-stu-id="b8c13-124">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="b8c13-125">Expanda el nodo **Comercio** y seleccione la casilla **Gestión de cambios de ingeniería**.</span><span class="sxs-lookup"><span data-stu-id="b8c13-125">Expand the **Trade** node, and select the **Engineering Change Management** check box.</span></span>
1. <span data-ttu-id="b8c13-126">Desactive el modo de mantenimiento como se describe en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="b8c13-126">Turn off maintenance mode, as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
