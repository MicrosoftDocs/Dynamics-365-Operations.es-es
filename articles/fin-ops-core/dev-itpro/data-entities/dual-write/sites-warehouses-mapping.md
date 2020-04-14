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
ms.openlocfilehash: 1b9181211bbb65cdfc46e63f3cee0e9f5bc9f6a4
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173071"
---
# <a name="integrated-sites-and-warehouses"></a>Sitios y almacenes integrados

[!include [banner](../../includes/banner.md)]



Este tema describe la integración de datos de sitios y almacenes entre Finance and Operations y Common Data Service. Los sitios operativos y los almacenes son conceptos comunes en una aplicación de Supply Chain Management. Se usan para modelar a la cadena de suministro de la empresa.

## <a name="templates"></a>Plantillas

Con la integración con Common Data Service, estos conceptos y toda la información relacionada están disponibles en Common Data Service mediante el uso de las entidades de datos de sitios y almacenes en la tabla siguiente.

Aplicaciones de Finance and Operations | Otras aplicaciones de Dynamics 365 | Descripción
--------------------------|---------------------------|---
Sitios | msdyn_operationalsites | 
Almacenes | msdyn_warehouses | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]

