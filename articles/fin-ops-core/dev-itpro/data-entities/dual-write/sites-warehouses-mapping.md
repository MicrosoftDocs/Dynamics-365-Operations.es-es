---
title: Sitios y almacenes integrados
description: Este tema describe la integración de datos de sitios y almacenes entre Finance and Operations y Dataverse.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: d192343d78f9248e4d1232d6aee1a1f800383805
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679329"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="ddcc6-103">Sitios y almacenes integrados</span><span class="sxs-lookup"><span data-stu-id="ddcc6-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="ddcc6-104">Este tema describe la integración de datos de sitios y almacenes entre Finance and Operations y Dataverse.</span><span class="sxs-lookup"><span data-stu-id="ddcc6-104">This topic describes the integration of site and warehouse data between Finance and Operations and Dataverse.</span></span> <span data-ttu-id="ddcc6-105">Los sitios operativos y los almacenes son conceptos comunes en una aplicación de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ddcc6-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="ddcc6-106">Se usan para modelar a la cadena de suministro de la empresa.</span><span class="sxs-lookup"><span data-stu-id="ddcc6-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="ddcc6-107">Plantillas</span><span class="sxs-lookup"><span data-stu-id="ddcc6-107">Templates</span></span>

<span data-ttu-id="ddcc6-108">Con la integración con Dataverse, estos conceptos y toda la información relacionada están disponibles en Dataverse mediante el uso de las tablas de datos de sitios y almacenes en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ddcc6-108">With the integration with Dataverse, these concepts and all their related information are available in Dataverse using the sites and warehouses data tables in the following table.</span></span>

<span data-ttu-id="ddcc6-109">Aplicaciones de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ddcc6-109">Finance and Operations apps</span></span> | <span data-ttu-id="ddcc6-110">Otras aplicaciones de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ddcc6-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="ddcc6-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="ddcc6-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="ddcc6-112">Sitios</span><span class="sxs-lookup"><span data-stu-id="ddcc6-112">Sites</span></span> | <span data-ttu-id="ddcc6-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="ddcc6-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="ddcc6-114">Almacenes</span><span class="sxs-lookup"><span data-stu-id="ddcc6-114">Warehouses</span></span> | <span data-ttu-id="ddcc6-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="ddcc6-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]

