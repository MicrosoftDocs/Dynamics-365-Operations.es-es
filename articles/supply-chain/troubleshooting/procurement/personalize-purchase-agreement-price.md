---
title: No puede agregar el campo Unidad de precio a la página Acuerdo de compra
description: Cuando abre la página "Acuerdo de compra" en un modo de vista de línea, no puede personalizar la página agregando el campo "Unidad de precio" en la descripción general de la línea
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 56d2ce94fb4b74d982cb6a052cca71c18190cd04
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477496"
---
# <a name="you-cant-add-the-price-unit-field-to-the-purchase-agreement-page"></a>No puede agregar el campo Unidad de precio a la página Acuerdo de compra

## <a name="symptoms"></a>Síntomas

Cuando abre la página **Acuerdo de compra** en un modo de vista de línea, no puede personalizar la página agregando el campo **Unidad de precio** en la descripción general de la línea.

## <a name="resolution"></a>Resolución

Algunos campos compartidos en el marco del acuerdo no se pueden incluir en las personalizaciones. Esta limitación se produce debido al modelo de datos implementado. Por lo tanto, no puede personalizar el campo **Precio unitario**.
