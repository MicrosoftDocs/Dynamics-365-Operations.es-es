---
title: Visión general de los procesos automatizados de facturación de proveedores
description: Este tema describe la capacidad para automatizar el procesamiento de facturas de su proveedor y los beneficios de utilizar un proceso automatizado.
author: abruer
manager: AnnBe
ms.date: 08/30/2020
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
ms.openlocfilehash: 187b3c4f1a8b2c9ec6df95c19b261756ec4562dc
ms.sourcegitcommit: 6ffbae02de2eee1f3be9bab2da37a3771aae8bec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2020
ms.locfileid: "3905033"
---
# <a name="automated-vendor-invoicing-processes-overview"></a>Visión general de los procesos automatizados de facturación de proveedores

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tema describe la capacidad para automatizar el procesamiento de facturas de su proveedor y los beneficios de utilizar un proceso automatizado. Esta capacidad consta de funciones que están activadas en la gestión de funciones. Estas funciones se aplican solo a las facturas de proveedores, no a las facturas que se procesan a través de la página **Diario de facturas** o **Diario de registro de facturas**.

A menudo las organizaciones trabajan con terceros para procesar las facturas de papel mediante un proveedor de servicios de reconocimiento de caracteres ópticos (OCR). El proveedor de servicios devuelve metadatos de facturas legibles por máquina. Para ayudar con la automatización, las funciones de automatización de Cuentas por pagar le permiten consumir estos artefactos de Cuentas por pagar.

Puede automatizar algunos procesos de facturación de proveedores de Cuentas a pagar. Estos procesos incluyen enviar facturas de proveedores importadas al sistema de flujo de trabajo y hacer coincidir las líneas de recepción de productos registradas con las líneas de facturas de proveedores pendientes. El proceso automatizado muestra información sobre el progreso de la factura de un proveedor a medida que avanza por cada uno de los procesos. Esta capacidad puede ayudar a los empleados y gerentes de cuentas a pagar a procesar las facturas de los proveedores de manera más eficiente. También ayuda a reducir los errores y las ineficiencias que pueden ocurrir cuando la información se ingresa y procesa manualmente.

Los procesos de automatización se pueden utilizar para realizar estas tareas:

- Envíe automáticamente facturas importadas al sistema de flujo de trabajo.
- Concilia recepciones de productos con líneas de factura de proveedor pendientes.
- Simule la contabilización antes de que se contabilice una factura de proveedor.
- Vea el historial del flujo de trabajo de manera rápida y eficiente.
- Vea y analice los resultados de la automatización del procesamiento de facturas de proveedores.

## <a name="vendor-invoice-automation--submit-imported-vendor-invoices-to-the-workflow-system"></a>Automatización de facturas de proveedores: envíe facturas de proveedores importadas al sistema de flujo de trabajo

Como parte de un proceso de facturación de Cuentas por pagar sin contacto, puede hacer que el sistema envíe automáticamente una factura importada al sistema de flujo de trabajo. El proceso se ejecutará en segundo plano, con la frecuencia que especifique (ya sea por hora o por día). La capacidad de enviar automáticamente facturas importadas al sistema de flujo de trabajo requiere que su proceso comience con una factura importada. Para asegurarse de que la factura se pueda procesar de principio a fin sin intervención manual, se debe incluir una tarea de registro automatizado en la configuración del flujo de trabajo.

Las facturas relacionadas con las órdenes de compra (PO) y las facturas que contienen una categoría de aprovisionamiento sin orden de compra y líneas no almacenadas se pueden enviar automáticamente al sistema de flujo de trabajo. Las facturas que se ingresan manualmente y las que se crean a través del espacio de trabajo **Facturación de colaboración con proveedores** deben enviarse manualmente al sistema de flujo de trabajo.

La función de automatización proporciona un marco flexible que le permite definir reglas específicas de la empresa para enviar facturas de proveedores importadas al sistema de flujo de trabajo y hacer coincidir las líneas de recibo de productos registrados con las líneas de facturas de proveedores pendientes.

## <a name="vendor-invoice-automation--match-product-receipts-to-invoice-lines-that-have-a-three-way-matching-policy"></a>Automatización de facturas de proveedor: hacer coincidir los recibos de productos registrados con las líneas de factura que tienen una política de coincidencia de tres vías

El sistema puede hacer coincidir automáticamente los recibos de productos registrados con las líneas de factura para las que se define una política de coincidencia de tres vías. El proceso se ejecutará hasta que la cantidad recibida del producto coincidente sea igual a la cantidad de la factura. Como parte de este proceso, puede especificar el número máximo de veces que el sistema debe intentar hacer coincidir los recibos de productos con una línea de factura antes de concluir que el proceso falló. El proceso se ejecutará en segundo plano, ya sea cada hora o diariamente. Puede ejecutar el proceso de comparación automatizado como parte del proceso para enviar facturas al sistema de flujo de trabajo. Alternativamente, puede ejecutarlo como un proceso independiente.

## <a name="vendor-invoice-automation--pre-validate-vendor-invoice-posting"></a>Automatización de facturas de proveedores: validación previa del registro de facturas de proveedores

La simulación de contabilización completa los pasos de validación que se realizan durante el proceso de contabilización de facturas de proveedor, pero no se actualizan cuentas. Para ejecutar el proceso, puede seleccionar una sola factura o varias facturas en la página **Facturas de proveedores pendientes**.

## <a name="vendor-invoice-automation--enhanced-experience-for-viewing-workflow-historical-information-for-vendor-invoices"></a>Automatización de facturas de proveedores: experiencia mejorada para ver la información histórica del flujo de trabajo para las facturas de proveedores

Se proporciona una vista fácil de leer del historial del flujo de trabajo de las facturas del proveedor. Se puede acceder al historial del flujo de trabajo de la factura del proveedor directamente desde la factura del proveedor. Por lo tanto, se requieren menos clics para encontrar esa información.

## <a name="vendor-invoice-automation--analytics-and-metrics"></a>Automatización de facturas de proveedores: análisis y métricas

El espacio de trabajo **Entrada de factura de proveedor** le permite concentrarse en las facturas de los proveedores que no pasaron por el proceso automatizado. Los mosaicos en el espacio de trabajo muestran información sobre las facturas de los proveedores que no se enviaron correctamente al sistema de flujo de trabajo, no se importaron o coincidieron con los recibos de productos. Las métricas de Microsoft Power BI también se proporcionan para brindar a los gerentes de Cuentas por pagar información sobre las eficiencias de la automatización de facturas de proveedores.
