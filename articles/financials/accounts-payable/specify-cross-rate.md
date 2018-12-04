---
title: Especificar el tipo de cambio cruzado
description: "Este tema proporciona información sobre cambios cruzados en Microsoft Dynamics 365 for Finance and Operations."
author: abruer
manager: AnnBe
ms.date: 05/16/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cf531c3a8f3bdb17314d1de436b98249169f82a3
ms.openlocfilehash: 112f77738b33aae94babe0cf8e9e61ff2ea3d004
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---

# <a name="specify-the-cross-rate"></a>Especificar el tipo de cambio cruzado

[!include [banner](../includes/banner.md)]

En este tema se explica el propósito de un tipo de cambio cruzado y cómo especificar el tipo de cambio cruzado al liquidar un pago con una factura. Usar un tipo de cambio cruzado cuando se cumplan todos los criterios siguientes: 
-   Está liquidando un pago con una factura. 
-   La línea de pago y la línea de factura usan divisas distintas. 
-   Ninguna divisa es la divisa de contabilidad. 

No se usará el tipo de cambio cruzado para calcular la conversión de la divisa de la transacción de pago en la divisa de contabilidad de pago. En su lugar, se recuperan los tipos de cambio de las tablas de tipos de cambio para calcular el valor del importe de divisa de la transacción de pago y el importe de la divisa de contabilidad de pago. 

Por ejemplo, la divisa de contabilidad es USD, la divisa de la factura es CAD y la divisa de pago es EUR. El tipo de cambio cruzado permite especificar un tipo de cambio para convertir directamente entre dólares canadienses y euros sin tener que convertir a través de dólares estadounidenses. Al seleccionar una factura y pago principal, puede especificar un tipo de cambio cruzado para la línea de factura. Éste es el tipo de cambio entre divisas para esas transacciones a partir de la fecha de liquidación.

1.  Vaya a una de las páginas siguientes:
- **Clientes > Común > Clientes > Todos los clientes** 
- **Proveedores > Común > Proveedores > Todos los proveedores**. 
- **Adquisición y abastecimiento > Común > Proveedores > Todos los proveedores.**
2.  Seleccione el cliente o proveedor cuyas transacciones abiertas esté liquidando. 
3.  Para un cliente, en la página de lista **Todos los clientes**, vaya a **Cobrar > Liquidar transacciones abiertas**. Para un proveedor, en la página de lista **Todos los proveedores**, vaya a **Factura > Liquidar transacciones abiertas**. 
4.  Seleccione la transacción que es el pago principal y haga clic en en **Marcar pago**. Se selecciona la casilla de la columna **Marcar** y se muestra un icono de información en la columna **Pago principal**. 
5.  En el campo **Tipo de cambio cruzado**, especifique el tipo de cambio entre la divisa de la factura y la divisa de pago, en la fecha de liquidación. 

