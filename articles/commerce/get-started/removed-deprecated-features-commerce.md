---
title: Características quitadas u obsoletas de Dynamics 365 Commerce
description: En este tema se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Commerce.
author: josaw
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: c47c5430a8f5d67e13c95db609a95d5ad66933ae
ms.sourcegitcommit: a8b6cd799eddaf5be9aec9ea3c2b55e2c3231652
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "3335285"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a>Características quitadas u obsoletas de Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]

En este tema se describen las características que se han quitado (o cuya eliminación está prevista) de Dynamics 365 Commerce.

- Una función *quitada* dejará de estar disponible en el producto.
- Una función *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Esta lista está pensada para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación. 

> [!NOTE]
> La información detallada sobre los objetos de aplicaciones Finance and Operations se puede encontrar en los [Informes de referencia técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Se pueden comparar las diferentes versiones de estos informes para conocer los objetos que se han modificado o quitado en cada versión de aplicaciones Finance and Operations.

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a>Funciones quitadas o en desuso en la versión Commerce 10.0.10
### <a name="pos-operation-803---picking-and-receiving"></a>Operación POS 803: recogida y recepción
|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Las operaciones de recogida y recepción están en desuso debido al nuevo diseño de la operación. |
| **¿Reemplazado por otra característica?**   | Sí. Se reemplazan por dos nuevas operaciones POS: operación entrante (804) y operación saliente (805).|
| **Áreas de producto afectadas**         | Aplicación de punto de venta (POS) |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir de la versión 10.0.10, la operación de selección y recepción ya no recibirá actualizaciones de nuevas funciones. Solo se realizarán correcciones de errores críticos para esta operación en futuras versiones. Se anima a todos los clientes a cambiar a las nuevas [Operaciones de entrada](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) y [Operaciones de salida](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation), que seguirán formando parte de nuestra hoja de ruta de productos a largo plazo. |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a>Funciones quitadas o en desuso en la versión Commerce 10.0.7
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a>API de GetProductAvailabilities y GetAvailableInventoryNearby
|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Se han creado API nuevas y optimizadas para reemplazar las API de GetProductAvailabilities y GetAvailableInventoryNearby. |
| **¿Reemplazado por otra característica?**   | Sí: se reemplaza por las API de GetEstimatedAvailability y GetEstimatedProductWarehouseAvailability. |
| **Áreas de producto afectadas**         | SDK de aplicación de comercio electrónico |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: a partir de la versión 10.0.7, ya no se realizarán inversiones de ingeniería para GetProductAvailabilities y GetAvailableInventoryNearby. Las organizaciones que usan estas API en sus implementaciones de comercio electrónico deben convertirse a las nuevas API de GetEstimatedAvailability y GetEstimatedProductWarehouseAvailability y habilitar la [Función optimizada de cálculo de disponibilidad del producto](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Anuncios anteriores sobre funciones quitadas u obsoletas
Para obtener más información sobre las funciones que se han eliminado o desaprobado en versiones anteriores, consulte [Funciones eliminadas o en desuso en versiones anteriores](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).
