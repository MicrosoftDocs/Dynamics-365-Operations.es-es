---
title: Actualizaciones de albaranes para devoluciones
description: Antes de recibir los artículos devueltos en el inventario, es necesario actualizar el albarán del pedido al que pertenecen.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPackingSlipJournalHistory, SalesParmPackingSlipTrackingInformation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 021cf6c0ff606e4b5a7139285fe7508283fb9fe2
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675694"
---
# <a name="packing-slip-updates-for-returns"></a>Actualizaciones de albaranes para devoluciones  

[!include [banner](../includes/banner.md)]


Antes de recibir los artículos devueltos en el inventario, es necesario actualizar el albarán del pedido al que pertenecen. Del mismo modo que el proceso de actualización de facturas es la actualización de la transacción financiera, el proceso de actualización de albaranes es la actualización física del registro de inventario; es decir, envía los cambios al inventario. En el caso de las devoluciones, los pasos que se asignan a la acción de disposición se implementan durante la actualización del albarán.

La actualización del albarán se puede procesar en el diario de recepción de artículos o en el pedido de devolución.

Como parte del proceso de registro de albaranes, el número de referencia del albarán de los documentos de envío del cliente también se puede asociar a las líneas de pedido. Esta asociación es opcional y tiene una finalidad informativa. No crea ninguna actualización transaccional.

Si no llegan todos los artículos de la devolución que se esperaban, se recomienda incluir sólo la cantidad que se ha recibido en la actualización del albarán. Deje los artículos restantes en el pedido hasta que llegue el resto del envío de la devolución.

Si un artículo se devuelve de la cuarentena al departamento de envíos y recepciones, como sucede cuando el inspector de cuarentena no sabe dónde almacenar el artículo en el inventario, es necesario actualizar el albarán correspondiente para registrarlo correctamente y actuar sobre el código de disposición que se especifica como resultado de la cuarentena.

Cuando se actualiza el albarán de un artículo devuelto de un acuerdo de venta, el compromiso del acuerdo de venta de dicho artículo se actualiza automáticamente para reflejar el cambio en la cantidad o el importe. 

## <a name="see-also"></a>Consulte también

[Actualizaciones de facturas para devoluciones](perform-invoice-updates-for-returns.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]