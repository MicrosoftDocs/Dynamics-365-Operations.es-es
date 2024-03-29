---
title: Generar líneas de factura al importar facturas de proveedores
description: Este artículo describe la funcionalidad para generar automáticamente líneas de factura en facturas de proveedor cuando se importan facturas.
author: sunfzam
ms.date: 09/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 5cb2c1234de03e9777921c18e4cbb81eec7feef9
ms.sourcegitcommit: 9c637bcf4e2eb8f711290a861492f038feaf1568
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2022
ms.locfileid: "9462284"
---
# <a name="generate-invoice-lines-when-you-import-vendor-invoices"></a>Generar líneas de factura al importar facturas de proveedores

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este artículo describe la funcionalidad para generar automáticamente líneas de factura en facturas de proveedor cuando se importan facturas.

A veces, las facturas de los proveedores contienen información limitada, como información del destinatario y subtotales. Sin embargo, no contienen información para los artículos de línea. Cuando importa facturas, las líneas de factura se generará automáticamente, basándose en la información del pedido de compra correspondiente.

Para habilitar la creación automática de líneas de factura, siga estos pasos.

1.  Vaya a **Proveedores \> Configuración \> Parámetros de proveedores**.
2.  En la pestaña **Automatización de facturas de proveedores**, en **Creación automática de líneas para facturas importadas**, configure la opción **Crear líneas de factura automáticamente** en **Sí**. 
4.  En el campo **Elija la cantidad predeterminada para la creación automática de líneas de factura**, seleccione la cantidad que se debe usar para generar automáticamente líneas de factura:

    - **Cantidad pedida**: las líneas se generarán a partir de líneas de pedidos de compra. Este valor es el valor predeterminado.
    - **Cantidad de recepción de producto**: el número de pedido de compra se usará para encontrar los recibos de productos relevantes. A continuación, utilizará las cantidades recibidas del producto para generar líneas de factura.

## <a name="data-entity-changes"></a>Cambios de entidad de datos

Para admitir la funcionalidad que se describe en este artículo, la entidad de datos **Encabezado de la factura del proveedor** se ha mejorado. Se han agregado tres campos:

- **HeaderOnlyImport**: este campo debe establecerse en **Sí** para generar líneas para los encabezados de las facturas.
- **PurchIdRange** - La lista de números de pedidos de compra. Los números de factura pueden ser un rango, como **PO0001..PO0009** (donde los dos puntos separan el inicio y el final del rango), o valores discretos, como **PO0001, PO0003, PO0006**. Todos los pedidos de compra deben pertenecer a la misma cuenta de proveedor en el encabezado de la factura. De lo contrario, recibirá el siguiente mensaje de error: "Error al generar líneas de factura. Los pedidos de compra tienen diferentes cuentas de proveedores ".
- **PackingslipRange** - La lista de números de recibo de producto. Se pueden crear líneas de factura de proveedor a partir de recibos de productos. Sin embargo, los números de recibo de los productos no suelen incluirse en las facturas de los proveedores. Solo introduzca los números de recibo de producto en este campo si puede identificar claramente para qué facturas específicas son los recibos de producto. Se pueden generar líneas de factura a partir de recibos de productos. Si se utiliza este campo, la configuración del campo **Elija la cantidad predeterminada para la creación automática de líneas de factura** en la página **Parámetros de proveedores** se ignora. 

**Limitación** : Si introduce varios números de recibo de producto, se crearán varias facturas de proveedor pendientes con el mismo número de factura. Debe consolidarlos manualmente antes de seguir procesando la factura. En versiones futuras, planeamos consolidar las facturas automáticamente, por lo que se eliminará la limitación.

Todos los recibos de productos deben pertenecer a la misma cuenta de proveedor en el encabezado de la factura.

## <a name="result"></a>Resultado

Si las líneas se generan correctamente, el siguiente mensaje se registra en el historial de automatización de facturas del proveedor: "Crear líneas de factura automáticamente: correcto".

Si las líneas no se generan, se registra el siguiente mensaje de error: "Crear líneas de factura automáticamente: error".
