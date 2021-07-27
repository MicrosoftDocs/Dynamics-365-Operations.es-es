---
title: Visión general de los procesos automatizados de facturación de proveedores
description: Este tema describe la capacidad para automatizar el procesamiento de facturas de su proveedor y los beneficios de utilizar un proceso automatizado.
author: abruer
ms.date: 02/12/2021
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
ms.search.validFrom: 2017-08-30
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 778d00d777c44aa5cd19eced6d2d30e9b85500fd
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "6339069"
---
# <a name="automated-vendor-invoicing-processes-overview"></a>Visión general de los procesos automatizados de facturación de proveedores

[!include [banner](../includes/banner.md)]

Este tema describe la capacidad para automatizar el procesamiento de facturas de su proveedor y los beneficios de utilizar un proceso automatizado. Esta capacidad consta de funciones que están activadas en la gestión de funciones. Estas funciones se aplican solo a las facturas de proveedores, no a las facturas que se procesan con la página **Diario de facturas** o **Diario de registro de facturas**.

A menudo las organizaciones trabajan con terceros para procesar las facturas de papel mediante un proveedor de servicios de reconocimiento de caracteres ópticos (OCR). El proveedor de servicios devuelve metadatos de facturas legibles por máquina. Para ayudar con la automatización, las funciones de automatización de Cuentas por pagar le permiten consumir estos artefactos de Cuentas por pagar.

Puede automatizar algunos procesos de facturación de proveedores de Cuentas a pagar. Estos procesos incluyen enviar facturas de proveedores importadas al sistema de flujo de trabajo y hacer coincidir las líneas de recepción de productos registradas con las líneas de facturas de proveedores pendientes. El proceso automatizado muestra información sobre el progreso de la factura de un proveedor a medida que avanza por cada uno de los procesos. Esta capacidad puede ayudar a los empleados y gerentes de cuentas a pagar a procesar las facturas de los proveedores de manera más eficiente. También ayuda a reducir los errores y las ineficiencias que pueden ocurrir cuando la información se ingresa y procesa manualmente.

Los procesos de automatización se pueden utilizar para realizar estas tareas:

- Envíe automáticamente facturas importadas al sistema de flujo de trabajo.
- Concilia recepciones de productos con líneas de factura de proveedor pendientes.
- Simule la contabilización antes de que se contabilice una factura de proveedor.
- Vea el historial del flujo de trabajo y automatización de manera rápida y eficiente.
- Vea y analice los resultados de la automatización del procesamiento de facturas de proveedores.
- Reanude el procesamiento automatizado de varias facturas.

## <a name="submit-imported-vendor-invoices-to-the-workflow-system"></a>Enviar automáticamente facturas de proveedores importadas al sistema de flujo de trabajo

Como parte de un proceso de facturación de Cuentas por pagar sin contacto, puede hacer que el sistema envíe automáticamente una factura importada al sistema de flujo de trabajo. El proceso se ejecutará en segundo plano, con la frecuencia que especifique (ya sea por hora o por día). La capacidad de enviar automáticamente facturas importadas al sistema de flujo de trabajo requiere que su proceso comience con una factura importada. Para asegurarse de que la factura se pueda procesar de principio a fin sin intervención manual, se debe incluir una tarea de registro automatizado en la configuración del flujo de trabajo.


Las facturas relacionadas con las órdenes de compra (PO) y las facturas que contienen una categoría de aprovisionamiento sin orden de compra y líneas no almacenadas se pueden enviar automáticamente al sistema de flujo de trabajo. Las facturas que se introducen manualmente y las que se crean con el espacio de trabajo **Facturación de colaboración con proveedores** deben enviarse manualmente al sistema de flujo de trabajo. El procesamiento de la solicitud de pago anticipado debe realizarse manualmente para las facturas importadas. Puede aplicar prepagos manualmente antes o después de contabilizar la factura importada. Puede aplicar pagos por adelantado manualmente a facturas estándar no contabilizadas utilizando la página **Facturas de proveedores**. Después de la contabilización, el anticipo liquidado estará disponible para aplicarlo manualmente a otras facturas de este proveedor en la página **Proveedores** (**Proveedores \> Común \> Proveedores \> Todos los proveedores \> Pestaña Factura \> Aplicar**).

La función de automatización proporciona un marco flexible que le permite definir reglas específicas de la empresa para enviar facturas de proveedores importadas al sistema de flujo de trabajo y hacer coincidir las líneas de recibo de productos registrados con las líneas de facturas de proveedores pendientes.

## <a name="match-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Hacer coincidir los recibos de productos con líneas de factura que tienen una directiva de triple conciliación

El sistema puede hacer coincidir automáticamente los recibos de productos registrados con las líneas de factura para las que se define una política de coincidencia de tres vías. El proceso se ejecutará hasta que la cantidad recibida del producto coincidente sea igual a la cantidad de la factura. Como parte de este proceso, puede especificar el número máximo de veces que el sistema debe intentar hacer coincidir los recibos de productos con una línea de factura antes de concluir que el proceso falló. El proceso se ejecutará en segundo plano, ya sea cada hora o diariamente. Puede ejecutar el proceso de comparación automatizado como parte del proceso para enviar facturas al sistema de flujo de trabajo. Alternativamente, puede ejecutarlo como un proceso independiente.

## <a name="pre-validate-vendor-invoice-posting"></a>Validar previamente la contabilización de facturas de proveedor

La simulación de contabilización completa los pasos de validación que se realizan durante el proceso de contabilización de facturas de proveedor, pero no se actualizan cuentas. Para ejecutar el proceso, puede seleccionar una sola factura o varias facturas en la página **Facturas de proveedores pendientes**.

## <a name="enhanced-experience-for-viewing-workflow-and-automation-historical-information-for-vendor-invoices"></a>Experiencia mejorada para ver la información histórica del flujo de trabajo y la automatización para las facturas de proveedores

Se proporciona una vista fácil de leer del historial del flujo de trabajo de las facturas del proveedor. Se puede acceder al historial del flujo de trabajo de la factura del proveedor directamente desde la factura del proveedor. Por lo tanto, se requieren menos clics para encontrar esa información. Si su organización ha habilitado la capacidad de enviar automáticamente facturas de proveedores importadas al flujo de trabajo, se proporciona el historial de automatización para las facturas importadas. El historial de automatización le ayuda a identificar el paso del proceso actual, así como los pasos que ya se han completado. Cuando un paso no tiene éxito, el sistema proporciona información detallada para ayudarle a comprender el motivo del error.

## <a name="analytics-and-metrics"></a>Análisis y métricas

El espacio de trabajo **Entrada de factura de proveedor** le permite concentrarse en las facturas de los proveedores que no pasaron por el proceso automatizado. Los mosaicos en el espacio de trabajo muestran información sobre las facturas de los proveedores que no se enviaron correctamente al sistema de flujo de trabajo, no se importaron o coincidieron con los recibos de productos. Las métricas de Microsoft Power BI también se proporcionan para brindar a los gerentes de Proveedores información sobre las eficiencias de la automatización de facturas de proveedores.


## <a name="resume-automation-processing-for-multiple-invoices"></a>Reanudar el procesamiento automatizado de varias facturas

Cuando una factura importada no se envía correctamente al flujo de trabajo con el proceso automatizado, el sistema la eliminará del procesamiento automatizado adicional. Un empleado de la sección de proveedores puede revisar y editar la factura antes de que el proceso automatizado la vuelva a enviar al flujo de trabajo. Cuando un motivo de error se puede resolver con la misma solución para varias facturas, puede reiniciar el proceso automatizado en la página **Reanudar el procesamiento automatizado de facturas**. 

## <a name="tracking-the-invoice-received-date-value"></a>Seguimiento del valor de la fecha de recepción de la factura

El valor **Fecha de recepción de la factura** indica la fecha en que la empresa recibió la factura del proveedor. Proporciona un punto de partida para realizar un seguimiento del progreso de la factura a través de los procesos de automatización. Este valor se puede incluir en los datos importados para una factura de proveedor. Para las facturas que se crearon manualmente, puede especificar la fecha. Si no se introduce ningún valor, la fecha actual se usa por defecto.


## <a name="tracking-the-imported-invoice-amount-and-imported-sales-tax-amount-values"></a>Seguimiento del importe de la factura importada y los valores del importe del impuesto sobre ventas importado

Los valores **Importe de la factura importada** e **Importe del impuesto sobre las ventas importado** para las facturas de proveedores se pueden proporcionar en el archivo de importación de facturas de proveedores. Por lo general, estos valores provienen de una factura que fue escaneada por un proveedor externo e incluida en el archivo de importación. A medida que la factura se procesa en Proveedores, el sistema calcula los valores en función de los datos de la factura. La factura se puede contabilizar solo si los valores importados coinciden con los valores calculados. Los valores coincidentes garantizan que la factura refleje con precisión el importe adeudado al proveedor. Si su organización permite que las facturas importadas se envíen automáticamente al sistema de flujo de trabajo, puede solicitar opcionalmente que los totales importados coincidan con los totales calculados antes de que la factura se envíe al sistema de flujo de trabajo.

## <a name="vendor-invoice-automation---resume-automation-processing-for-multiple-invoices"></a>Automatización de facturas de proveedores: reanudar el procesamiento de automatización para varias facturas
Cuando una factura importada no se envía correctamente al flujo de trabajo a través del proceso automatizado, el sistema la eliminará del procesamiento automatizado adicional. Un empleado de la sección de proveedores puede revisar y editar la factura antes de que el proceso automatizado la vuelva a enviar al flujo de trabajo. Cuando un motivo de error se puede resolver con la misma solución para varias facturas, puede reiniciar el proceso automatizado en la página **Reanudar el procesamiento automatizado de facturas**. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
