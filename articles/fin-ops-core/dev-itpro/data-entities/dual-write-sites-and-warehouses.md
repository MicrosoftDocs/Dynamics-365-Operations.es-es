---
title: Sitios y almacenes integrados
description: Este tema describe la integración de datos de sitios y almacenes entre Finance and Operations y Common Data Service.
author: t-benebo
manager: AnnBe
ms.date: 10/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: 4cf402e2811aaf92ddfa78eaf6d8887d88d93cbc
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771006"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="64d12-103">Sitios y almacenes integrados</span><span class="sxs-lookup"><span data-stu-id="64d12-103">Integrated sites and warehouses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64d12-104">Este tema describe la integración de datos de sitios y almacenes entre Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="64d12-104">This topic describes the integration of site and warehouse data between Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="64d12-105">Los sitios operativos y los almacenes son conceptos comunes en una aplicación de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="64d12-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="64d12-106">Se usan para modelar a la cadena de suministro de la empresa.</span><span class="sxs-lookup"><span data-stu-id="64d12-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="64d12-107">Plantillas</span><span class="sxs-lookup"><span data-stu-id="64d12-107">Templates</span></span>

<span data-ttu-id="64d12-108">Con la integración con Common Data Service, estos conceptos y toda la información relacionada están disponibles en Common Data Service mediante el uso de las entidades de datos de sitios y almacenes en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="64d12-108">With the integration with Common Data Service, these concepts and all their related information are available in Common Data Service using the sites and warehouses data entities in the following table.</span></span>

<span data-ttu-id="64d12-109">Aplicaciones de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="64d12-109">Finance and Operations apps</span></span> | <span data-ttu-id="64d12-110">Otras aplicaciones de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="64d12-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="64d12-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="64d12-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="64d12-112">Sitios</span><span class="sxs-lookup"><span data-stu-id="64d12-112">Sites</span></span> | <span data-ttu-id="64d12-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="64d12-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="64d12-114">Almacenes</span><span class="sxs-lookup"><span data-stu-id="64d12-114">Warehouses</span></span> | <span data-ttu-id="64d12-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="64d12-115">msdyn_warehouses</span></span> | 

[!include [symbols](../includes/dual-write-symbols.md)]

[!include [operational sites](dual-write/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](dual-write/InventWarehouseEntity-msdyn-warehouse.md)]

