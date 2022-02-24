---
title: Opciones de configuración para la automatización de facturas de proveedores (versión preliminar)
description: Este tema describe las opciones que están disponibles para configurar y configurar la automatización de facturas de proveedores.
author: abruer
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ebab41d8b7697f20095d6d4654718b88c8b08a82
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665207"
---
# <a name="setup-options-for-vendor-invoice-automation"></a>Opciones de configuración para la automatización de facturas de proveedores

[!include [banner](../includes/banner.md)]

Este tema describe las opciones que están disponibles para configurar y configurar la automatización de facturas de proveedores. Las funciones de automatización de facturas utilizan los siguientes tipos de parámetros de configuración:

- Los parámetros para enviar facturas de proveedores importadas al sistema de flujo de trabajo y hacer coincidir las líneas de recepción de productos registradas con las líneas de facturas de proveedores pendientes.
- Parámetros para tareas de segundo plano de automatización de procesos. El marco de automatización de procesos se utiliza para enviar facturas de proveedores importadas al sistema de flujo de trabajo. También se utiliza para hacer coincidir automáticamente líneas de recepción de productos registradas con líneas de facturas de proveedores pendientes y para realizar la validación de conciliación de facturas para las facturas manuales que se conciliaron automáticamente con las líneas de recepción de productos. Diferentes procesos de negocios utilizan este marco para definir la frecuencia de ejecución de un proceso seleccionado. Las frecuencias disponibles para los procesos de fondo **Hacer coincidir la recepción del producto con las líneas de la factura** y **Enviar las facturas del proveedor al flujo de trabajo** incluyen **Hora** y **Diario**.

Para configurar o ver información sobre una tarea en segundo plano, vaya a **Administracion del sistema \> Preparar \> Automatizaciones de procesos** y seleccione la pestaña **Tarea de fondo**.

Para lograr la automatización sin contacto desde el proceso de importación a través de la contabilización de facturas de proveedores, debe configurar un flujo de trabajo de facturas de proveedores. Para configurar un flujo de trabajo, vaya a **Proveedores > Configuración > Flujos de trabajo de proveedores**. Para asegurarse de que la factura se pueda procesar de principio a fin sin intervención manual, debe incluir una tarea de registro automatizado en la configuración de su flujo de trabajo.

## <a name="parameters-for-submitting-imported-vendor-invoices-to-the-workflow-system"></a>Parámetros para enviar facturas de proveedores importados al sistema de flujo de trabajo

Se usan parámetros específicos para enviar facturas de proveedores importados al sistema de flujo de trabajo. Adicionalmente, se utilizan algunos parámetros para hacer coincidir automáticamente las líneas de recepción de productos registradas con las líneas de factura de proveedor pendientes. En la pestaña **Automatización de facturas de proveedores** de la página **Parámetros de cuentas por pagar**, los parámetros que debe establecer se dividen entre las siguientes secciones:

- Flujo de trabajo de facturas de proveedor
- Conciliar automáticamente las recepciones de productos

Están disponibles los siguientes parámetros:

- **Enviar automáticamente facturas importadas al flujo de trabajo** - Si configura esta opción en **Sí**, las facturas importadas se envían automáticamente al sistema de flujo de trabajo. Si esta opción se establece en **No**, las facturas deben enviarse manualmente. Al configurar esta opción en **Sí**, habilita un proceso sin contacto desde los resultados de la importación hasta la publicación.

    Puede configurar esta opción como **Sí** solo si se configura un flujo de trabajo de facturas de proveedor activo para su entidad legal. Para configurar un flujo de trabajo, vaya a **Proveedores \> Configuración \> Flujos de trabajo de proveedores**.

- **Hacer coincidir los recibos de productos con las líneas de factura antes de enviarlos automáticamente** - Si configura esta opción en **Sí**, la factura importada no se puede enviar automáticamente al sistema de flujo de trabajo hasta que la cantidad recibida del producto coincidente sea igual a la cantidad de la factura. Al configurar esta opción en **Sí**, habilita la coincidencia automática de los recibos de productos registrados con las líneas de facturación para las que se define una política de coincidencia de tres vías. Ese proceso se ejecutará hasta que la cantidad recibida del producto coincidente sea igual a la cantidad de la factura. En ese momento, la factura se envía automáticamente al sistema de flujo de trabajo.

    La opción 'Hacer coincidir los recibos de productos con las líneas de factura antes del envío automático está disponible solo si la opción **Habilitar la validación de coincidencia de facturas** está seleccionada. Cuando se selecciona esta opción, la opción **Hacer coincidir automáticamente los recibos de productos con las líneas de facturación** se selecciona automáticamente.

- **Exigir que los totales calculados sean iguales a los totales importados para el envío automático del flujo de trabajo** - Si configura esta opción en **Sí**, la factura no se puede enviar automáticamente al sistema de flujo de trabajo hasta que los totales que se calculan para la factura sean iguales a los totales importados. Si esta opción se establece en **No**, la factura puede enviarse automáticamente al sistema de flujo de trabajo, pero no puede contabilizarse hasta que los totales calculados se corrijan para que coincidan con los totales importados. Si no importa el monto de la factura o el monto del impuesto sobre las ventas, esta opción debe establecerse en **No**.
- **Hacer coincidir automáticamente los recibos de productos con las líneas de facturación** - Si configura esta opción en **Sí**, el procesamiento en segundo plano se puede utilizar para hacer una coincidencia automática de los recibos de productos registrados con las líneas de factura para las que se define una política de coincidencia de tres vías. Ese proceso se ejecutará hasta que la cantidad recibida del producto coincidente sea igual a la cantidad de la factura, o hasta que se alcance el valor del campo **Número de veces que se intenta la coincidencia automática**. El proceso se puede ejecutar hasta que la factura se haya enviado al sistema de flujo de trabajo.

    Esta opción solo está disponible si está activada la opción **Habilitar validación de conciliación de facturas**.

    Si configura la opción **Hacer coincidir los recibos de productos con las líneas de la factura antes de que coincidan automáticamente** en **Sí**, esta opción no se puede establecer en **No**. Para establecer esta opción en **No**, primero debe establecer la opción **Hacer coincidir los recibos de productos con las líneas de la factura antes de que coincidan** en **No**.

- **Número de veces que se intenta la coincidencia automática** - Seleccione la cantidad de veces que el sistema debe intentar hacer coincidir los recibos de productos con una línea de factura antes de concluir que el proceso falló. Cuando se alcanza el número especificado de intentos, la factura se elimina del procesamiento de automatización.

