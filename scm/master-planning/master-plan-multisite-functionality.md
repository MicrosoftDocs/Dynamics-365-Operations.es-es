---
title: "Planificación maestra y funcionalidad multisitio"
description: "La planificación maestra tiene en cuenta la configuración del sitio y las dimensiones de inventario de almacén."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d45cc1e69696fbc22078d0f1cd7f089fd322b440
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017

---

# <a name="master-planning-and-multisite-functionality"></a>Planificación maestra y funcionalidad multisitio

[!include[banner](../includes/banner.md)]


La planificación maestra tiene en cuenta la configuración del sitio y las dimensiones de inventario de almacén. 

La dimensión de sitio es obligatoria, y también puede establecer la dimensión de almacén como obligatoria.

Si una dimensión es obligatoria, se debe especificar un valor de dimensión en todas las transacciones de inventario. Por lo tanto, durante la planificación maestra, se conocen el sitio y el almacén para la demanda inicial. La dimensión de sitio también es coherente de modo que, durante la expansión de la demanda de bajo nivel, el valor del sitio no cambia.

Si el almacén no se configura como obligatorio, es posible que no se conozca a partir de la demanda inicial. El sistema de planificación deberá determinar qué almacén utilizar en función de la configuración definiaa para el artículo, los almacenes individuales y los detalles de la línea de pedido.

En los siguientes temas se describe el funcionamiento del motor de planificación, cuando hay diferentes configuraciones definidas, para determinar el almacén que hay que utilizar.

[Planificación maestra: cobertura de sitios y almacenes, almacén obligatorio](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planificación maestra: cobertura de sitios y almacenes, almacén obligatorio](master-plan-site-coverage-warehouse-mandatory.md)

[Planificación maestra: cobertura de sitios y almacenes, almacén no obligatorio](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planificación maestra: cobertura de sitios y almacenes, almacén no obligatorio](master-plan-site-coverage-warehouse-not-mandatory.md)

[Planificación maestra: cómo se establece la versión de la lista de materiales](master-plan-bom-version-determined.md)




