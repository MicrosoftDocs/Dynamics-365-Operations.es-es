---
title: Generar líneas de factura al importar facturas de proveedores
description: Este tema describe la funcionalidad para generar automáticamente líneas de factura en facturas de proveedor cuando se importan facturas.
author: sunfzam
ms.date: 09/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 87dec3c142ae296975ab98432421be4548085c80
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647909"
---
# <a name="generate-invoice-lines-when-you-import-vendor-invoices"></a>Generar líneas de factura al importar facturas de proveedores

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tema describe la funcionalidad para generar automáticamente líneas de factura en facturas de proveedor cuando se importan facturas.

A veces, las facturas de los proveedores contienen información limitada, como información del destinatario y subtotales. Sin embargo, no contienen información para los artículos de línea. Cuando importa facturas, el sistema puede generar automáticamente líneas de factura, basándose en la información del pedido de compra correspondiente.

Para habilitar la creación automática de líneas de factura, siga estos pasos.

1.  Vaya a **Proveedores \> Configuración \> Parámetros de proveedores**.
2.  En la pestaña **Automatización de facturas de proveedores**, en **Creación automática de líneas para facturas importadas**, configure la opción **Crear líneas de factura automáticamente** en **Sí**. 
4.  En el campo **Elija la cantidad predeterminada para la creación automática de líneas de factura**, seleccione la cantidad que el sistema debe usar para generar automáticamente líneas de factura:

    - **Cantidad pedida** - El sistema generará líneas a partir de líneas de pedidos de compra. Este valor es el valor predeterminado.
    - **Cantidad de recepción de producto** - El sistema utilizará los números de pedido de compra para encontrar los recibos de productos relevantes. A continuación, utilizará las cantidades recibidas del producto para generar líneas de factura.

## <a name="data-entity-changes"></a>Cambios de entidad de datos

Para admitir la funcionalidad que se describe en este tema, la entidad de datos **Encabezado de la factura del proveedor** se ha mejorado. Se han agregado tres campos:

- **HeaderOnlyImport** - Este campo debe establecerse en **Sí** para que el sistema genere líneas para los encabezados de las facturas.
- **PurchIdRange** - La lista de números de pedidos de compra. Los números de factura pueden ser un rango, como **INV0001..INV0009** (donde los dos puntos separan el inicio y el final del rango), o valores discretos, como **INV0001, INV0003, INV0006**. Todos los pedidos de compra deben pertenecer a la misma cuenta de proveedor en el encabezado de la factura. De lo contrario, recibirá el siguiente mensaje de error: "Error al generar líneas de factura. Los pedidos de compra tienen diferentes cuentas de proveedores ".
- **PackingslipRange** - La lista de números de recibo de producto. Se pueden crear líneas de factura de proveedor a partir de recibos de productos. Sin embargo, los números de recibo de los productos no suelen incluirse en las facturas de los proveedores. Solo introduzca los números de recibo de producto en este campo si puede identificar claramente para qué facturas específicas son los recibos de producto. Se pueden generar líneas de factura a partir de recibos de productos. Y si se utiliza este campo, la configuración del campo **Elija la cantidad predeterminada para la creación automática de líneas de factura** en la página **Parámetros de proveedores** se ignora. 

**Limitación** : Si introduce varios números de recibo de producto, se crearán varias facturas de proveedor pendientes con el mismo número de factura. Debe consolidarlos manualmente antes de seguir procesando la factura. En versiones futuras, planeamos habilitar el sistema para consolidar las facturas automáticamente, por lo que se eliminará la limitación.

Todos los recibos de productos deben pertenecer a la misma cuenta de proveedor en el encabezado de la factura.

## <a name="result"></a>Resultado

Si el sistema genera líneas con éxito, el siguiente mensaje se registra en el historial de automatización de facturas del proveedor: "Crear líneas de factura automáticamente: correcto".

Si el sistema no genera líneas, se registra el siguiente mensaje de error: "Crear líneas de factura automáticamente: error".
