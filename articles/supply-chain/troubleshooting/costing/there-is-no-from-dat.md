---
title: No hay un valor de Fecha inicial en la pestaña Precios activos de la página Precio de artículo
description: No hay un valor de Fecha inicial en la pestaña Precios activos de la página Precio de artículo.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dd13f6a3e5ce3c894e96f420358d337f2e43dba
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026896"
---
# <a name="there-is-no-from-date-value-on-the-active-prices-tab-of-the-item-price-page"></a>No hay un valor de Fecha inicial en la pestaña Precios activos de la página Precio de artículo

Número de KB: 4613548

## <a name="symptoms"></a>Síntomas

No hay un valor de **Fecha inicial** en la pestaña **Precios activos** de la página **Precio de artículo**.

## <a name="resolution"></a>Resolución

El valor **Fecha inicial** (fecha de vigencia) que se establece en el precio pendiente no se transfiere al precio activo.

La primera vez que se especifica un registro de coste de artículo, presenta un estado de *Pendiente* y una fecha de vigencia prevista. Al activar el registro de costes de artículo, se actualiza el estado a *Activo* y la fecha de vigencia a la fecha de activación. Por lo tanto, la fecha de activación del precio activo es siempre la fecha real de activación.

Para obtener más información, consulte [Información general de las versiones de gestión de costes](../../cost-management/costing-versions.md).
