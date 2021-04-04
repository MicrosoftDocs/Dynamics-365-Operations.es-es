---
title: Sitios y almacenes integrados
description: Este tema describe la integración de datos de sitios y almacenes entre Finance and Operations y Dataverse.
author: t-benebo
manager: AnnBe
ms.date: 10/09/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: b93e5f15e281c20f8688d496fc78f8b46b8aa996
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560370"
---
# <a name="integrated-sites-and-warehouses"></a><span data-ttu-id="1d147-103">Sitios y almacenes integrados</span><span class="sxs-lookup"><span data-stu-id="1d147-103">Integrated sites and warehouses</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="1d147-104">Este tema describe la integración de datos de sitios y almacenes entre Finance and Operations y Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1d147-104">This topic describes the integration of site and warehouse data between Finance and Operations and Dataverse.</span></span> <span data-ttu-id="1d147-105">Los sitios operativos y los almacenes son conceptos comunes en una aplicación de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="1d147-105">Operational sites and warehouses are common concepts in a Supply Chain Management application.</span></span> <span data-ttu-id="1d147-106">Se usan para modelar a la cadena de suministro de la empresa.</span><span class="sxs-lookup"><span data-stu-id="1d147-106">They are used to model the supply chain of your company.</span></span>

## <a name="templates"></a><span data-ttu-id="1d147-107">Plantillas</span><span class="sxs-lookup"><span data-stu-id="1d147-107">Templates</span></span>

<span data-ttu-id="1d147-108">Con la integración con Dataverse, estos conceptos y toda la información relacionada están disponibles en Dataverse mediante el uso de las tablas de datos de sitios y almacenes en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="1d147-108">With the integration with Dataverse, these concepts and all their related information are available in Dataverse using the sites and warehouses data tables in the following table.</span></span>

<span data-ttu-id="1d147-109">Aplicaciones de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1d147-109">Finance and Operations apps</span></span> | <span data-ttu-id="1d147-110">Otras aplicaciones de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="1d147-110">Other Dynamics 365 apps</span></span> | <span data-ttu-id="1d147-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d147-111">Description</span></span>
--------------------------|---------------------------|---
<span data-ttu-id="1d147-112">Sitios</span><span class="sxs-lookup"><span data-stu-id="1d147-112">Sites</span></span> | <span data-ttu-id="1d147-113">msdyn_operationalsites</span><span class="sxs-lookup"><span data-stu-id="1d147-113">msdyn_operationalsites</span></span> | 
<span data-ttu-id="1d147-114">Almacenes</span><span class="sxs-lookup"><span data-stu-id="1d147-114">Warehouses</span></span> | <span data-ttu-id="1d147-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="1d147-115">msdyn_warehouses</span></span> | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]