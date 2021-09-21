---
title: Los pedidos de compra no reflejan la configuración de idioma de la entidad jurídica
description: El nombre del producto en un pedido de compra se muestra en el idioma del sistema, no en el idioma establecido para la entidad jurídica donde se creó el pedido de compra
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
ms.openlocfilehash: 4deec493b5480dc570ac82876243bc31a2ae87aa
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477513"
---
# <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a>Los pedidos de compra no reflejan la configuración de idioma de la entidad jurídica


## <a name="symptoms"></a>Síntomas

El nombre del producto en un pedido de compra se muestra en el idioma del sistema, no en el idioma establecido para la entidad jurídica donde se creó el pedido de compra.

## <a name="reproduce-the-issue"></a>Reproducir el problema

El siguiente procedimiento muestra una manera de reproducir el problema.

1. Establezca el idioma del sistema en *EN-US* (inglés americano).
1. Asegúrese de que haya un producto donde se mantienen los idiomas *EN-US* y *DE* (alemán) para las traducciones del nombre del producto.
1. Cambie el idioma de una entidad jurídica a *DE*.
1. En la entidad jurídica donde *DE* está configurado como idioma, cree un pedido de compra que incluya el producto.
1. Tenga en cuenta que el nombre del producto se sigue mostrando en inglés de EE.UU. (el idioma del sistema).

## <a name="resolution"></a>Resolución

Este comportamiento se debe al diseño. En los pedidos de compra, el producto siempre se muestra en el idioma del sistema. El idioma del pedido de compra se utiliza cuando se crea un diario de confirmación.
