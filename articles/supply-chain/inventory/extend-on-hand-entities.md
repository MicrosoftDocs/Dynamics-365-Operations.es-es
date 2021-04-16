---
title: Ampliar las entidades de datos disponibles de inventario
description: Este tema proporciona un ejemplo que muestra cómo agregar campos extendidos a las vistas INVENTORSITEONHANDENTITY e INVENTWAREHOUSEONHANDENTITY, de modo que las capacidades de las entidades de datos disponibles del inventario puedan funcionar con las extensiones.
author: sherry-zheng
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-27
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 7863f37e66727e2e80ea8c8b013ee49930e7c684
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829917"
---
# <a name="extend-inventory-on-hand-data-entities"></a>Ampliar las entidades de datos disponibles de inventario

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management proporciona características de [extensibilidad](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) que le permiten [agregar campos a tablas mediante la extensión](../../fin-ops-core/dev-itpro/extensibility/add-field-extension.md). Este tema proporciona un ejemplo que muestra cómo agregar campos extendidos a las vistas `INVENTORSITEONHANDENTITY` e `INVENTWAREHOUSEONHANDENTITY`, de modo que las capacidades de las entidades de datos disponibles del inventario puedan funcionar con las extensiones. Para obtener más información sobre las entidades de datos, consulte [Descripción general de la administración de datos](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

> [!NOTE]
> A continuación, se muestra una lista de algunas de las entidades de datos disponibles del inventario:
>
> - Inventario disponible por sitio
> - Inventario disponible por sitio V2
> - Inventario disponible por almacén
> - Inventario disponible por almacén v2

Después de agregar campos a las tablas utilizadas por la vista `inventSiteOnHandView` debe sincronizar el motor para que las extensiones se reconozcan correctamente.

1. Extienda la vista `InventSiteOnHandView` agregando el campo de extensión.
1. Extienda la vista `InventSiteOnHandAggregatedView` con los campos de extensión.
1. Extienda la clase viewBuilder de `InventSiteOnHandAggregatedViewBuilder` modificando el método `getExtensionFields()`. De esta manera, asigna campos de vista antiguos a campos de vista nuevos cuando se ejecuta la sincronización de viewBuilder.

Por ejemplo, ha agregado los siguientes cuatro campos a la tabla `InventTable` mediante extensión:

- Campo personalizado 1
- Campo personalizado 2
- Campo personalizado 3
- Campo personalizado 4

En este caso, debe modificar el método `getExtensionFields()` de la siguiente manera.

```xpp
[ExtensionOf(classStr(InventSiteOnHandAggregatedViewBuilder))]
public final class InventOnHandAggregatedViewBuilder\_Extension
{
    protected Map getExtensionFields()
    {
        next getExtensionFields();
        Map extensionFields = new Map(Types::Int64, Types::Int64);
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 1), fieldNum(InventSiteOnHandAggregatedView, Custom field 1));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 2), fieldNum(InventSiteOnHandAggregatedView, Custom field 2));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 3), fieldNum(InventSiteOnHandAggregatedView, Custom field 3));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 4), fieldNum(InventSiteOnHandAggregatedView, Custom field 4));
        return extensionFields;
    }
}
```

Después de completar estos pasos, puede ampliar el inventario disponible por sitio y el inventario disponible por entidades de datos de almacén agregando los nuevos campos. De esta manera, se asegura de que se reconozcan los campos extendidos y se incluyan durante la migración de datos que usa esas entidades de datos.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]