---
title: Fechas de factura del proveedor
description: Este tema describe las fechas que aparecen en las facturas de proveedores. También explica cómo configurar el sistema para que ajuste automáticamente la fecha de registro.
author: sunfzam
ms.date: 08/30/2021
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
ms.openlocfilehash: a066f828b47f297b8ad520b9eb0f4f311d49b111
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647910"
---
# <a name="vendor-invoice-dates"></a>Fechas de factura del proveedor

[!include [banner](../includes/banner.md)]

Este tema describe las fechas que aparecen en las facturas de proveedores. También explica cómo configurar el sistema para que ajuste automáticamente la fecha de registro.

En la página **Factura de proveedor pendiente detallada**, el encabezado de la factura muestra cuatro fechas: la fecha de recepción de la factura, la fecha de la factura, la fecha de registro y la fecha de vencimiento. Cuando se crea una factura de proveedor, se introducen las siguientes fechas de manera predeterminada:

- **Fecha de recepción de la factura**: este campo se establece en la fecha actual del sistema.
- **Fecha de registro**: este campo se establece en la fecha actual del sistema. 
- **Fecha de vencimiento**: la fecha en este campo se calcula en función de la fecha de registro y las condiciones de pago.
- **Fecha de la factura**: de forma predeterminada, este campo está en blanco. Sin embargo, puede introducir un valor si es necesario. En ese caso, la fecha en el campo **Fecha de vencimiento** se vuelve a calcular en función de la fecha de la factura y las condiciones de pago.

A veces, una factura de proveedor puede estar en estado pendiente durante mucho tiempo después del cierre del periodo. Cuando esté listo para el registro, se seguirá utilizando la fecha de registro anterior del periodo de registro anterior. Sin embargo, ese periodo ya se ha cerrado. Por lo tanto, un contable de proveedores (AP) debe cambiar manualmente todas las fechas de registro al nuevo periodo de registro para todas las facturas pendientes que se crearon anteriormente.

La característica que se describe en este tema le permite configurar el sistema para que ajuste automáticamente la fecha de registro de acuerdo con los requisitos comerciales.

## <a name="parameter-for-automatically-adjusting-the-vendor-invoice-posting-date"></a>Parámetro para ajustar automáticamente la fecha de registro de la factura del proveedor

Siga estos pasos para permitir que el sistema ajuste automáticamente la fecha de registro de las facturas de proveedores.

1.  Vaya a **Proveedor \> Configuración \> Parámetros de proveedor**.
2.  En la pestaña **Impuestos y contabilidad**, en el campo **Ajustar fecha de registro automáticamente**, seleccione uno de los siguientes valores:

    - **Ningún cambio**: el sistema no cambia automáticamente la fecha de registro durante el registro. Este valor se selecciona de forma predeterminada.
    - **Cambiar siempre la fecha de registro a la fecha del sistema**: el sistema cambia automáticamente la fecha de registro a la fecha del sistema durante el registro.
    - **Cambiar la fecha de registro a la fecha del sistema cuando el período de fecha de registro esté cerrado o en espera**: el sistema cambia la fecha de registro a la fecha del sistema durante el registro, pero solo si el periodo correspondiente de la fecha de registro tiene un estado de **Cerrado** o **En espera**.
    - **Cambiar la fecha de registro al primer día del nuevo período cuando el período de fecha de registro esté cerrado o en espera**: el sistema cambia la fecha de registro al primer día del nuevo periodo abierto, pero solo si el periodo correspondiente de la fecha de registro tiene un estado de **Cerrado** o **En espera**.

## <a name="impact-of-posting-date-changes"></a>Impacto de los cambios en la fecha de registro

Cuando se cambia la fecha de registro en una factura de proveedor pendiente, el cambio tiene los siguientes efectos:

- **Fecha de vencimiento**

    - Si el campo **Fecha de factura** está en blanco, la fecha de vencimiento se vuelve a calcular en función de la nueva fecha de registro y de las condiciones de pago.
    - Si el campo **Fecha de factura** se configuró previamente, el cambio de fecha de registro no afecta la fecha de vencimiento.

- **Fecha del descuento por pronto pago**

    - Si el campo **Fecha de factura** está en blanco, la nueva fecha de registro se utiliza para calcular el descuento por pronto pago.
    - Si el campo **Fecha de factura** se configuró previamente, el descuento por pronto pago no cambia.

- **Tipo de cambio**: la fecha del tipo de cambio está determinada por la configuración de la opción **Actualizar la contabilidad del proveedor utilizando la fecha de la factura** en la pestaña **Factura** de la página **Parámetros de proveedores** (**Proveedor \> Configuración \> Parámetros de proveedor**).

    - Si esta opción se establece en **Sí**, se utiliza la fecha de la factura y el cambio de la fecha de registro no afecta el tipo de cambio.
    - Si esta opción se establece en **No**, la fecha de registro se utiliza para calcular el tipo de cambio. Cuando se actualiza la fecha de registro, se recalculan los importes de contabilidad y de informes. Por lo tanto, la validación coincidente debe realizarse nuevamente.

## <a name="validation"></a>Validación

Otros dos campos en la pestaña **Factura** de la página **Parámetros de proveedores** (**Proveedor \> Configuración \> Parámetros de proveedor**) afectan al procesamiento de facturas:

- Si el campo **Comprobar el número de factura utilizado** está configurado en **Rechazar duplicados dentro del ejercicio**, el sistema utiliza la fecha de registro para comprobar si hay facturas duplicadas durante el registro de facturas.
- Si el campo **Requerir fecha de documento en factura de proveedor** está configurado en **Opción de error**, el campo **Fecha de la factura en el encabezado de la factura pendiente** es obligatorio. Si la fecha de la factura es posterior a la fecha de registro, el sistema muestra un mensaje de error.
