---
title: Conversión de unidad de medida por variante del producto
description: Este tema explica cómo las conversiones de unidad de medida se pueden configurar en variantes de producto.
author: johanhoffmann
manager: AnnBe
ms.date: 12/18/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: 9d5d6fd65717cd886f1c6576aabf2bc59ca4fcaf
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "345936"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a>Conversión de unidad de medida por variante del producto

[!include [banner](../includes/banner.md)]

[!include [pivate-preview](../includes/pivate-preview-banner.md)]

Este tema explica cómo las conversiones de unidad de medida se pueden configurar en variantes de producto. Incluye un ejemplo de configuración.

Esta función permite a las empresas definir una conversión de unidad diferente entre las variantes del mismo producto. El siguiente ejemplo se usa en este tema. Una empresa vende camisetas de tamaños pequeños, medios, grande y extragrande. La camiseta se define como producto, y los distintos tamaños se definen como variantes del producto. Las camisetas están embaladas en cajas y puede haber cinco camisetas en una caja, excepto el tamaño extragrande donde solo hay espacio para cuatro camisetas. La empresa desea realizar un seguimiento de las distintos variantes de camisetas en la unidad **Piezas** pero está vendiendo las camisetas en la unidad **Cajas**. La conversión entre la unidad de inventario y la unidad de ventas es 1 caja = 5 unidades, excepto la variante extragrande, donde la conversión es 1 caja = 4 piezas.

## <a name="setup"></a>Configurar

Puede configurar los parámetros para usar la función de productos habilitados para **Todos los procesos** o solo al producto habilitado para **Procesos de almacén** mediante la opción **Habilitar las conversiones de unidad de medida** en la página **Parámetros de la información de producto**.

### <a name="set-up-a-product-for-unit-conversion-per-variant"></a>Configurar un producto para la conversión de unidades por variante

Las variantes de producto solo se pueden crear para productos del **subtipo producto**: **producto maestro**. Para obtener más información, consulte [Crear un producto maestro](tasks/create-product-master.md).

La característica no está habilitada para los productos configurados para procesos de peso capturado. 

Durante la creación de un producto maestro habilite la conversión de unidades de medida mediante la opción **Habilitar las conversiones de unidad de medida** en la página **Detalles de producto**.

Cuando se crea el producto maestro con variantes de productos emitidos, las conversiones de unidades por variantes se pueden configurar. Puede encontrar el elemento de menú para abrir la página de conversión de unidades en el contexto de un producto o una variante del producto en las siguientes páginas.

-   Página **Detalles de producto**
-   Página **Administrar detalles de productos**
-   Página **Variantes del producto publicadas**

Al abrir la página **Conversión de unidades** en el contexto de una variante del producto maestro o de producto liberado, puede seleccionar si desea configurar la conversión de unidades del producto o de la variante del producto. Esto se hace seleccionando **Variante del producto** o **Producto** en el campo **Crear para la conversión**.

### <a name="product-variant"></a>Variante del producto

Si se selecciona **Variante del producto,** puede seleccionar para qué variante desea configurar la conversión de unidades en el campo **Variante del producto**.

### <a name="product"></a>Producto

Si se selecciona **Producto**, puede configurar una conversión de unidades para el producto maestro. Esta conversión de unidades se aplicará a todas las variantes de producto sin conversión de unidad definida.

### <a name="example"></a>Ejemplo

Un producto maestro, **Camiseta**, tiene cuatro variantes de producto liberadas: pequeños, medios, grande y extragrande. Las camisetas están embaladas en cajas y puede haber cinco camisetas en una caja, excepto el tamaño extragrande donde solo hay espacio para cuatro camisetas.

Primero, abra la página la página **Conversión de unidades** en la página de liberación de detalles de producto para **Camiseta.**

En la página **Conversión de unidades**, configure la conversión de unidades para la variante del producto extragrande liberada.

| **Campo**             | **Configuración**             |
|-----------------------|-------------------------|
| Crear conversión para | Variante del producto         |
| Variante del producto       | Camiseta : : extragrande : : |
| Desde unidad             | Cajas                   |
| Factor                | 4                       |
| Hasta unidad               | Piezas                  |

Las variantes del producto liberado: pequeños, medios y grandes tienen la misma conversión de unidades entre la caja de unidades y las piezas, lo que significa que puede definir la conversión de unidades de estas variantes de producto en el producto maestro.

| **Campo**             | **Configuración** |
|-----------------------|-------------|
| Crear conversión para | Producto     |
| Producto               | Camiseta     |
| Desde unidad             | Cajas       |
| Factor                | 5           |
| Hasta unidad               | Piezas      |

### <a name="using-excel-to-update-the-unit-conversions"></a>Uso de Excel para actualizar las conversiones de unidades

Si un producto tiene numerosas variantes de producto con conversiones de unidad diferente, es recomendable exportar las conversiones de unidades de la página **Conversión de unidades** a una hoja de cálculo de Excel, actualizar las conversiones y, a continuación publicarlas de nuevo en Finance and Operations.

La opción para exportar a Excel y publicar las ediciones de nuevo en Finance and Operations se habilita en el elemento de menú **Abrir en Microsoft Office** en el panel de acciones de la página **Conversión de unidades**.
