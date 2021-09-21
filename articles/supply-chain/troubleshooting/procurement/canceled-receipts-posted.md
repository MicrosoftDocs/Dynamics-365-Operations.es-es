---
title: Las transacciones no se pueden registrar en una cuenta de libro mayor suspendida
description: Si se cancela la recepción de un producto, el sistema permite que las transacciones se registren en cuentas contables suspendidas, aunque las cuentas principales estén suspendidas
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 20df0ee4107ad62bec0dd9a683660fe2375a3dd1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477572"
---
# <a name="transactions-can-be-posted-to-a-suspended-ledger-account"></a>Las transacciones no se pueden registrar en una cuenta de libro mayor suspendida

## <a name="symptoms"></a>Síntomas

Si se cancela la recepción de un producto, el sistema permite que las transacciones se registren en cuentas contables suspendidas, aunque las cuentas principales estén suspendidas.

## <a name="reproduce-the-issue"></a>Reproducir el problema

El siguiente procedimiento muestra una manera de reproducir el problema.

1. En la página **Parámetros de proveedores**, en la pestaña **General**, asegúrese de que la opción **Registrar recepción de producto en el libro mayor** está establecida en *Sí*.
1. Cree un pedido de compra y agregue una línea de pedido que tenga como cantidad *1000* para un producto.
1. Confirme el pedido de compra.
1. Registre la recepción del producto y compruebe los asientos.
1. Suspenda las cuentas principales relevantes, *200140* y *140200*.
1. Cancele la recepción de producto registrada.
1. Tenga en cuenta que las transacciones se pueden registrar en las cuentas de libro mayor suspendidas.

## <a name="resolution"></a>Resolución

Las transacciones se pueden contabilizar en las cuentas de libro mayor suspendidas cuando se cancelan recepciones de productos, ya que este comportamiento permite contabilizaciones correctas.
