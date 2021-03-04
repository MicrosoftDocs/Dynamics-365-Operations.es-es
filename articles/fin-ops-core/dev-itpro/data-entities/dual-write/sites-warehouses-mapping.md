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
# <a name="integrated-sites-and-warehouses"></a>Sitios y almacenes integrados

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Este tema describe la integración de datos de sitios y almacenes entre Finance and Operations y Dataverse. Los sitios operativos y los almacenes son conceptos comunes en una aplicación de Supply Chain Management. Se usan para modelar a la cadena de suministro de la empresa.

## <a name="templates"></a>Plantillas

Con la integración con Dataverse, estos conceptos y toda la información relacionada están disponibles en Dataverse mediante el uso de las tablas de datos de sitios y almacenes en la tabla siguiente.

Aplicaciones de Finance and Operations | Otras aplicaciones de Dynamics 365 | Descripción
--------------------------|---------------------------|---
Sitios | msdyn_operationalsites | 
Almacenes | msdyn_warehouses | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]