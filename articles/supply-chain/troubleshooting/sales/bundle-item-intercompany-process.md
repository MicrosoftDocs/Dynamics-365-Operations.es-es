---
title: Artículo de agrupación no admitido en un proceso de empresas vinculadas
description: El artículo del paquete no está disponible para su compra. La orden de venta solo compra los componentes del artículo del paquete, no el artículo del paquete en sí.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 21adc7d071837b762157364f6f8ed370c69c7fd3
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477526"
---
# <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a>Un proceso de empresas vinculadas no admite artículos de agrupación

## <a name="symptoms"></a>Síntomas

El artículo de agrupación no está disponible para el pedido de compra porque, si examina las líneas del pedido de ventas del artículo de la agrupación, notará que la cantidad es *0* (cero) y el estado es *Cancelado*.

## <a name="resolution"></a>Resolución

Este comportamiento se debe al diseño. El pedido de cliente compra solo los componentes del artículo de agrupación. No compra el artículo de agrupación en sí. Si tiene que comprar una agrupación, considere si debe marcarlo como artículo de agrupación, ya que esta funcionalidad está diseñada para escenarios de reconocimiento de ingresos. Para obtener más información acerca de los artículos de agrupación, consulte [Agrupaciones](/dynamics365/finance/accounts-receivable/revenue-recognition-setup).
