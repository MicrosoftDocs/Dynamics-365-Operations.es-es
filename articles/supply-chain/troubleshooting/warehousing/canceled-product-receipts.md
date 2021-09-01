---
title: Los recibos de productos cancelados no actualizan el estado de transacción a Registrado
description: Después de cancelar las recepciones de productos en una carga entrante, el sistema actualiza automáticamente el estado de la transacción de inventario de Recibido a Pedido.
author: GalynaFedorova
ms.date: 06/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-11
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: eae703ce0b2c981518b18c4badd4f90031b902ece62f3ca0837427b306d618b1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731112"
---
# <a name="canceled-product-receipts-dont-update-transaction-status-to-registered"></a>Los recibos de productos cancelados no actualizan el estado de transacción a Registrado

## <a name="symptoms"></a>Síntomas

Después de ejecutar la acción para **cancelar recepciones de productos** en una carga entrante, el sistema actualiza automáticamente el estado de las transacciones de inventario de *Recibido* a *Pedido*.

## <a name="resolution"></a>Resolución

Cuando se cancelan los albaranes para las cargas salientes, el estado de las transacciones de inventario permanece *Escogido*. Sin embargo, cuando se cancelan las recepciones de productos de una carga entrante, el estado de las transacciones de inventario no se restaura a *Registrado*. Por lo tanto, después de que se cancela la recepción de un producto de una carga entrante, el trabajador del almacén debe volver a registrar las cantidades de artículos para las cargas.

Para más información, ver [Registrar cantidades de artículos que llegan en una carga entrante](/dynamics365/supply-chain/warehousing/inbound-load-handling#register-item-quantities-arriving).
