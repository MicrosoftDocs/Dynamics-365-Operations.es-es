---
title: Aplicar anticipo automáticamente para facturas de proveedores
description: Este tema describe la capacidad para aplicar automáticamente los prepagos a las facturas de los proveedores.
author: sunfzam
ms.date: 10/19/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 5b07c1d4c2189184b2ad29d46ec2aef0ee03c1c0
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2022
ms.locfileid: "7985371"
---
# <a name="automatically-apply-to-vendor-invoices"></a>Aplicar automáticamente para facturas de proveedores

[!include [banner](../includes/banner.md)]

Este tema describe la capacidad para aplicar automáticamente los prepagos a las facturas de los proveedores. Se puede crear un pago por adelantado para una orden de compra como parte de un acuerdo de compra. Después de recibir una factura de proveedor, el anticipo se puede utilizar para liquidar los proveedores de la factura de proveedor. La nueva función permite al sistema utilizar automáticamente los números de orden de compra en una factura de proveedor para buscar los anticipos correspondientes cuando se importa la factura de proveedor.

Si se encuentran pagos anticipados y se pueden aplicar, se agregan líneas a las líneas de factura existentes para aplicar los anticipos. Las líneas de anticipo nunca se consideran durante el proceso de conciliación de facturas.

Los siguientes puntos describen cómo se aplican los anticipos cuando se siguen diferentes procesos de compra:

- **Una factura de proveedor por pedido de compra** - El anticipo del pedido de compra se aplicará a la factura del proveedor.
- **Una factura de proveedor para múltiples pedidos de compra** - Los anticipos de todos los pedidos de compra se aplicarán a la factura del proveedor.
- **Múltiples facturas de proveedor por pedido de compra** - El anticipo del pedido de compra se aplicará a la primera factura importada del proveedor. Si el importe del prepago excede el importe de la factura, la aplicación del anticipo falla y debe aplicar el anticipo manualmente.
- **Múltiples facturas de proveedor para múltiples pedidos de compra** - Los anticipos de los pedidos de compra se aplicarán a la primera factura relevante. Si el importe del anticipo excede el importe de la factura, la aplicación del anticipo falla y debe aplicar los anticipos manualmente. Si los anticipos que quedan después de los pagos anticipados se aplican a la primera factura, se pueden aplicar a las facturas siguientes.

Si el sistema intenta aplicar un anticipo pero la aplicación falla, el comportamiento depende de la configuración de la opción **Bloquear el proceso de automatización de seguimiento en caso de fallo de la aplicación de anticipo**:

- **Sí** - El mensaje de error "Solicitud automática de anticipo: fallida" se agrega al historial de automatización y la factura permanece en la lista de facturas de proveedor pendientes. La factura permanecerá bloqueada hasta que aplique manualmente el anticipo.

    Para aplicar anticipos manualmente, vaya a la factura de proveedor pendiente. En la página **Detalles de la factura**, configure la opción **Incluir en procesamiento automatizado** para la factura bloqueada en **No**. Ahora puede aplicar manualmente el anticipo. Después de que se haya aplicado el anticipo, establezca la opción **Incluir en procesamiento automatizado** otra vez en **Sí** para que la factura se pueda procesar automáticamente.

    También puede omitir la aplicación automática del anticipo configurando la opción **Incluir en procesamiento automatizado** en **No** y luego configurándolo de nuevo en **Sí**. Recibirá el siguiente mensaje: "Ya existe un anticipo para el pedido de compra. ¿Desea ignorarlo para la factura del proveedor seleccionado?" Seleccione **Sí**. El mensaje "Aplicación de anticipo omitido manualmente" se agrega al historial de automatización y la factura del proveedor no se bloqueará cuando el proceso automatizado se ejecute nuevamente.

- **No** - Continuarán los procesos de automatización de seguimiento. Aún puede aplicar el anticipo durante la liquidación.
