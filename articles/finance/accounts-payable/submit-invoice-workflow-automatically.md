---
title: Enviar facturas al sistema de flujo de trabajo y conciliar líneas de recepción de productos
description: Este artículo explica el proceso de enviar facturas de proveedores al sistema de flujo de trabajo y hacer coincidir automáticamente las líneas de recepción de productos registradas con las facturas de proveedores.
author: abruer
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 960a08eb5e98cac034bbd41335b616ff41bf6fd4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861629"
---
# <a name="submit-invoices-to-the-workflow-system-and-match-product-receipt-lines"></a>Enviar facturas al sistema de flujo de trabajo y conciliar líneas de recepción de productos

[!include [banner](../includes/banner.md)]

Este artículo explica el proceso de enviar facturas de proveedores al sistema de flujo de trabajo y hacer coincidir automáticamente las líneas de recepción de productos registradas con las facturas de proveedores.

## <a name="submitting-imported-vendor-invoices-to-the-workflow-system-and-matching-posted-product-receipt-lines-to-pending-vendor-invoice-lines"></a>Enviar facturas de proveedores importadas al sistema de flujo de trabajo y hacer coincidir las líneas de recepción de productos registradas con las líneas de facturas de proveedores pendientes

Como parte de un proceso de facturación de Proveedores sin contacto, se puede enviar automáticamente una factura importada al sistema del flujo de trabajo. Puede configurar el proceso de envío de facturas importadas al sistema de flujo de trabajo en la pestaña **Automatización de facturas de proveedores** de la página **Parámetros de cuentas por pagar** (**Cuentas por pagar \> Preparar \> Parámetros de cuentas por pagar**). El proceso de envío al flujo de trabajo se ejecutará en segundo plano, con la frecuencia que especifique (ya sea por hora o por día).

Cuando envía facturas automáticamente al sistema de flujo de trabajo, debe comenzar con una factura importada. Para asegurarse de que la factura se pueda procesar de principio a fin sin intervención manual, debe incluir una tarea de registro automatizado en la configuración del flujo de trabajo. Las facturas relacionadas con las órdenes de compra (PO) y las facturas que contienen una categoría de aprovisionamiento sin orden de compra y líneas no almacenadas se pueden enviar automáticamente al sistema de flujo de trabajo. Las facturas que se ingresan manualmente deben enviarse manualmente al sistema de flujo de trabajo.

El valor **Presentado por** en el flujo de trabajo es el ID de usuario que se ingresó para la tarea en segundo plano **Enviar las facturas del proveedor al flujo de trabajo** en la página **Automatización de procesos**. El usuario que tenga esa identificación de usuario podrá recuperar la factura del sistema de flujo de trabajo según sea necesario.

## <a name="matching-posted-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Hacer coincidir los recibos de productos registrados con las líneas de factura que tienen una política de coincidencia de tres vías

Como parte de un proceso de facturación de Proveedores sin contacto, se pueden hacer coincidir automáticamente los recibos de productos registrados con las líneas de facturación. Se debe definir una política de coincidencia de tres vías para esta tarea. Esta función está disponible si la función **Automatización de facturas de proveedores** se ha habilitado en la página **Gestión de funciones**.

El proceso de correspondencia se ejecutará hasta que la cantidad recibida del producto correspondiente sea igual a la cantidad de la factura. Sin embargo, si hay varios recibos de productos para una sola línea de factura, deberá ejecutar el proceso varias veces para lograr la coincidencia total de la cantidad. Puede especificar el número máximo de veces que el sistema debe intentar hacer coincidir los recibos de productos con una línea de factura antes de concluir que el proceso falló. El proceso se ejecutará en segundo plano, ya sea cada hora o diariamente. 

Puede ejecutar el proceso de comparación automatizado como parte del proceso para enviar facturas al sistema de flujo de trabajo. Alternativamente, puede ejecutarlo como un proceso independiente. Los ajustes del proceso match-product-receipts-to-invoice-lines se configuran en la pestaña **Automatización de facturas de proveedores** de la página **Parámetros de cuentas por pagar** (**Cuentas por pagar \> Preparar \> Parámetros de cuentas por pagar**).

Las líneas de factura que tienen una política de coincidencia de tres vías, donde la cantidad de recibo coincidente es menor que la cantidad de la factura, se incluirán en el proceso automatizado de coincidencia de recepción de producto.

Para ver el estado de la **última conciliación** de facturas que no forman parte del proceso automatizado de envío al flujo de trabajo, abra la factura en la página **Facturas de proveedores**. Cuando ve la factura, se actualiza la información de validación coincidente. El estado **Última conciliación** se puede actualizar automáticamente mediante la tarea en segundo plano **Validar la conciliación de facturas**. Puede configurar el proceso de actualización automática del estado **Última conciliación** en la pestaña **Procesos en segundo plano** de la página **Automatizaciones de procesos** (**Administración del sistema \> Configuración \> Automatizaciones de procesos**).

Una línea de factura se excluirá del procesamiento automatizado si se cumple alguna de las siguientes condiciones:

- El valor **Estado de coincidencia de recibo automatizado** de la línea de la factura es **Error**.
- Se está utilizando la factura.
- La factura está en el sistema de flujo de trabajo.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
