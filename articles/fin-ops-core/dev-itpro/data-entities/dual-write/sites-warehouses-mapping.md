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