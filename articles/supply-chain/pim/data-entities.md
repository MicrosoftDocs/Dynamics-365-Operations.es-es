---
title: Entidades de datos de producto
description: Este tema proporciona información sobre las diferentes entidades que se pueden usar para importar y exportar datos de productos.
author: cvocph
manager: tfehr
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: kamaybac
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2019-12-1
ms.openlocfilehash: 536e17088348f2a8b41818eccbe8da699c4189d5
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981850"
---
# <a name="product-data-entities"></a>Entidades de datos de producto

[!include [banner](../includes/banner.md)]

Para importar y exportar datos de producto debe usar entidades de datos. La siguiente tabla proporciona detalles sobre las entidades de datos relacionadas con el producto y describe el propósito de cada una.

| Entidad | Árbol de objetos de aplicación (AOT) nombre (tipo) | Notas |
|--------|-------------------------------------------|-------|
| Productos V2 | EcoResProductV2Entity | Esta entidad se utiliza para importar y exportar productos compartidos, productos distintos y productos maestros. Permite actualizaciones. No admite operaciones SQL basadas en conjuntos. Está habilitado para Open Data Protocol (OData). |
| Productos liberados V2 | EcoResReleasedProductV2Entity | Esta entidad se utiliza para importar y exportar productos publicados, productos distintos y productos maestros. Permite actualizaciones. Requiere que el producto compartido ya esté creado. Cuando se importa un nuevo producto lanzado, se produce un lanzamiento del producto compartido. También hay entidades separadas que pueden usarse para importar y exportar productos maestros lanzados y variantes distintas lanzadas. Esta entidad no admite operaciones SQL basadas en conjuntos ni operaciones de eliminación. Está habilitado para OData. |
| Creación de productos liberados V2 | EcoResReleasedProductCreationV2Entity | Esta entidad se utiliza para importar productos compartidos y productos lanzados en un solo paso. Aunque admite exportaciones, ese uso no se recomienda, porque el propósito de la entidad es la creación de productos. No admite actualizaciones. Admite un conjunto limitado de campos (campos que están disponibles en el cuadro de diálogo de creación del producto). No admite operaciones SQL basadas en conjuntos. No está expuesto a través de OData. |
| Variantes del producto | EcoResProductVariantEntity | Esta entidad se utiliza para importar y exportar variantes de productos compartidos. Permite actualizaciones. Requiere que los valores de dimensión ya estén creados. La clave de integración es el producto maestro más las dimensiones del producto. Esta entidad no admite operaciones SQL basadas en conjuntos. Está habilitado para OData. Soporta operaciones de borrado. No se puede ampliar mediante la adición de nuevas dimensiones de producto. |
| Identificación del número de producto derivado de las variantes de producto | EcoResProductNumberIdentifiedProductVariantEntity | Esta entidad se utiliza para importar y exportar variantes de productos compartidos. Permite actualizaciones. Requiere que los valores de dimensión ya estén creados. La clave de integración es el número de producto (mientras que la clave de integración para la entidad **Variantes del producto** es el producto maestro más las dimensiones del producto). |
| Variantes de productos emitidos | EcoResReleasedProductVariantEntity | Esta entidad se utiliza para importar y exportar variantes de productos lanzados. Permite actualizaciones. Requiere que las variantes del producto compartido ya estén creadas. Cuando se importa una variante del producto lanzada, se produce un lanzamiento de la variante del producto compartida. Esta entidad no admite operaciones SQL basadas en conjuntos. Está habilitado para OData. Aunque admite operaciones de eliminación, ese uso actualmente provoca daños en los datos debido a un error en la plataforma actual. Esta entidad no se puede ampliar mediante la adición de nuevas dimensiones de producto. |
| Identificación del número de producto derivado de las variantes de productos liberados | EcoResProductNumberIdentifiedReleasedProductVariantEntity | Esta entidad se parece a la entidad **Variantes del producto lanzadas** pero la clave de integración es el número del producto en lugar del producto maestro más las dimensiones del producto. Se puede ampliar mediante la adición de nuevas dimensiones de producto. |
| Productos liberados para ventas | EcoResSellableReleasedProductEntity | Esta entidad se utiliza para exportar solo productos vendibles. Los productos para ventas son productos que tienen la información que requieren para usarse en un pedido de ventas. Se aplican las mismas reglas cuando un producto se valida con la función **Validar** en la página **Productos lanzados**. |
| Productos únicos emitidos V2 | EcoResDistinctProductV2Entity | Esta entidad se utiliza para exportar productos únicos. Estos productos únicos pueden ser productos, subtipos de productos y variantes de producto. |
| Productos maestros emitidos V2 | EcoResProductMasterV2Entity | Esta entidad se utiliza para importar y exportar productos maestros. No está habilitado para la gestión de datos. |
| Artículo - Código de barras | EcoResProductBarcodeEntity | Esta entidad se utiliza para exportar productos y códigos de barras. |
| Estados de ciclo de vida de producto | EcoResProductLifecycleSateEntity | Esta entidad se utiliza para importar y exportar los diferentes estados del ciclo de vida del producto que se pueden asignar a un producto. |

> [!NOTE]
> Puedes usar la entidad de datos **Productos lanzados V2** para importar productos al sistema solo si el producto compartido ya se ha creado. De lo contrario, para importar productos al sistema, debe usar la entidad de datos **Creación de producto**.
