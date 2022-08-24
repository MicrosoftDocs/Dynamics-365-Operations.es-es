---
title: Fecha de registro de IVA de proveedor
description: Este artículo proporciona información sobre una característica para habilitar la fecha del registro de IVA del proveedor
author: AdamTrukawka
ms.date: 01/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: global
ms.author: atrukawk
ms.search.validFrom: 2022-01-15
ms.dyn365.ops.version: AX 10.0.24
ms.custom: intro-internal
ms.openlocfilehash: 4af770427f5b19eaf2a129b26d54aeacc6c2f148
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278290"
---
# <a name="date-of-vendor-vat-register"></a>Fecha de registro de IVA de proveedor

En la versión 10.0.24 de Microsoft Dynamics 365 Finance, el nuevo campo **Fecha de registro de IVA de proveedor** está disponible para facturas de proveedores. Este campo especifica la fecha del suministro sujeto a impuestos para una compra.

Para habilitar el nuevo campo, vaya al espacio de trabajo **Administración de características**, busque y seleccione la característica **Habilitar la fecha del registro de IVA de proveedor en las facturas de proveedor** y, a continuación, seleccione **Habilitar ahora**.

Las facturas entrantes de sus proveedores pueden tener dos fechas: la fecha en que el proveedor emitió la factura y la fecha del suministro imponible (es decir, la fecha en la que el proveedor cargó el impuesto al valor agregado [IVA] a pagar). En algunos escenarios, estas dos fechas pueden diferir.

Puede deducir el importe del IVA entrante de una factura de compra e incluir esa factura en los informes de IVA más adelante, en una fecha que difiera de las dos fechas mencionadas anteriormente. Esta fecha está controlada por las normas de la legislación local sobre la deducción del IVA entrante pospuesta para algunos escenarios. Varía según el país o región.

Algunos informes de IVA, como el [Informe de declaración de control de IVA](emea-cze-vat-declaration-tax-declaration-model.md#vat-control-statement) en la República Checa, requieren que la fecha del suministro imponible se informe para un documento de compra. Esta fecha debe informarse para que las autoridades fiscales puedan conciliar la declaración del IVA entre las contrapartes.

En Finance, puede definir fechas en los siguientes campos:

- **Fecha de la factura**: la fecha de emisión de la factura por parte del proveedor.
- **Fecha de registro de IVA**: la fecha de la deducción del importe del IVA de la factura de compra.
- **Fecha de registro de IVA del proveedor**: la fecha de la entrega gravable del vendedor.
- **Recibir fecha del documento**: la fecha en la que recibió la factura.

Estos campos se incluyen en las siguientes páginas:

- Factura del proveedor
- Registro de facturas de proveedor
- Aprobación de factura de proveedor
- Diario de facturas del proveedor

Después de registrar la factura de proveedor, puede revisar las fechas en las páginas **Diario de facturas** y **Transacciones de proveedor**.
