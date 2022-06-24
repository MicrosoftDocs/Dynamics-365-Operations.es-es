---
title: Impuesto condicional para pagarés o letras de cambio protestados
description: Este artículo proporciona información acerca de los pagarés o letras de cambio para las entidades jurídicas en España.
author: ShylaThompson
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankBillOfExchangeTable, BankPromissoryNoteTable
audience: Application User
ms.reviewer: kfend
ms.custom: 271503
ms.search.region: Spain
ms.author: kfend
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: ae77d25ec294e5074ffbbc47d2e9661e822df247
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8845169"
---
# <a name="conditional-sales-tax-for-protested-promissory-notes-or-bills-of-exchange"></a>Impuesto condicional para pagarés o letras de cambio protestados
[!include [banner](../includes/banner.md)]

Para las entidades jurídicas en España, si un pago de pagaré para un proveedor o un pago de letra de cambio para un cliente se liquida contra una factura que incluye impuestos condicionales, y se protesta el acuerdo, la cancelación del impuesto se registra con un comprobante relacionado con el asiento de la cancelación del acuerdo.

El *impuesto condicional* es un impuesto que se paga de forma proporcional al importe real que se paga en una factura. Para obtener más información acerca de un impuesto condicional, vea [Visión general de impuestos](../general-ledger/indirect-taxes-overview.md). Un *pagaré* es un acuerdo escrito en el que el emisor del pagaré promete pagar una cantidad concreta en un momento concreto. Una *letra de cambio* es una orden escrita o electrónica de un cliente que especifica que otra parte (normalmente un banco) debe pagar un importe establecido a la empresa. Para obtener más información acerca de letras de cambio, consulte [Configurar letras de cambio](../accounts-receivable/set-up-bills-exchange.md).

## <a name="conditional-sales-tax-for-protested-promissory-notes"></a>Impuesto condicional para los pagarés impagados
Cuando un usuario registra un diario de renegociación de pagarés, se anulan las transacciones registradas anteriormente si un pagaré se ha liquidado contra la factura de proveedor. Si la factura incluía impuestos condicionales cuando se liquidó con un pagaré, se registra una transacción de impuestos para los impuestos condicionales. Para las entidades jurídicas de España, si el pagaré se ha liquidado con una factura que incluye impuestos condicionales, se invierte la transacción de impuestos cuando se registra un diario de pagarés renegociados. Para ver las transacciones invertidas, vaya a **Transacciones de asiento** &gt; **Asientos relacionados**.

## <a name="conditional-sales-tax-for-protested-bills-of-exchange"></a>Impuesto condicional para letras de cambio impagadas
Cuando un usuario registra un diario de impago de letras de cambio, se anulan las transacciones registradas anteriormente si una letra de cambio se ha liquidado con la factura de cliente. Si la factura incluía impuestos condicionales cuando se liquidó con una letra de cambio, se registra una transacción de impuestos para los impuestos condicionales. Para las entidades jurídicas de España, si la letra de cambio se ha liquidado con una factura que incluye impuestos condicionales, se invierte la transacción de impuestos cuando se registra un diario de impago de letras de cambio. Para ver las transacciones invertidas, vaya a **Transacciones de asiento** &gt; **Asientos relacionados**.




[!INCLUDE[footer-include](../../includes/footer-banner.md)]