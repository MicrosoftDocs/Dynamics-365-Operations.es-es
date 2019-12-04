---
title: Visión general de la planificación maestra y la funcionalidad multisitio
description: La planificación maestra tiene en cuenta la configuración del sitio y las dimensiones de inventario de almacén.
author: roxanadiaconu
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventSite
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2434
ms.assetid: 7f05c031-a446-4168-8cce-03a6305f5c4d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d0b715e0c17263519a9bb1b3780170812271d93d
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813762"
---
# <a name="master-planning-and-multisite-functionality-overview"></a>Visión general de la planificación maestra y la funcionalidad multisitio

[!include [banner](../includes/banner.md)]

La planificación maestra tiene en cuenta la configuración del sitio y las dimensiones de inventario de almacén. 

La dimensión de sitio es obligatoria, y también puede establecer la dimensión de almacén como obligatoria.

Si una dimensión es obligatoria, se debe especificar un valor de dimensión en todas las transacciones de inventario. Por lo tanto, durante la planificación maestra, se conocen el sitio y el almacén para la demanda inicial. La dimensión de sitio también es coherente de modo que, durante la expansión de la demanda de bajo nivel, el valor del sitio no cambia.

Si el almacén no se configura como obligatorio, es posible que no se conozca a partir de la demanda inicial. El sistema de planificación deberá determinar qué almacén utilizar en función de la configuración definiaa para el artículo, los almacenes individuales y los detalles de la línea de pedido.

En los siguientes temas se describe el funcionamiento del motor de planificación, cuando hay diferentes configuraciones definidas, para determinar el almacén que hay que utilizar.

[Planificación maestra de cobertura de sitios y almacén, almacén obligatorio](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planificación maestra para cobertura de sitios, almacén obligatorio](master-plan-site-coverage-warehouse-mandatory.md)

[Planificación maestra de cobertura de sitios y almacén, almacén no obligatorio](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planificación maestra para cobertura de sitios, almacén no obligatorio](master-plan-site-coverage-warehouse-not-mandatory.md)

[Determinar la versión de L. MAT.](master-plan-bom-version-determined.md)



