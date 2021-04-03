---
title: Faltan productos y categorías después de la copia del entorno
description: Este tema proporciona una guía de resolución de problemas que puede ayudar cuando faltan productos y categorías después de que un sitio se copia entre entornos o dentro del mismo entorno.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 35f2cbd98a91149395f40bf821c1d5d7e58eaf77
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585527"
---
# <a name="products-and-categories-missing-after-environment-copy"></a>Faltan productos y categorías después de la copia del entorno

[!include [banner](../../includes/banner.md)]

Este tema proporciona una guía de resolución de problemas que puede ayudar cuando faltan productos y categorías después de que un sitio se copia entre entornos o dentro del mismo entorno.

## <a name="description"></a>Descripción

Después de que un sitio se copia de un entorno a otro, o dentro del mismo entorno, faltan los productos y las categorías del sitio. Los productos y categorías faltarán en el escaparate de la tienda de comercio electrónico y en la pestaña **Productos** del creador de sitios de Commerce.

## <a name="resolution"></a>Resolución

### <a name="map-the-channel-operating-unit-number-to-a-newly-copied-site-in-commerce-site-builder"></a>Asigne el número de unidad operativa del canal a un sitio recién copiado en el creador de sitios de Commerce

Para asignar el número de unidad operativa del canal (OUN) a un sitio recién copiado en el creador de sitios de Commerce, siga estos pasos.

1. Seleccione el sitio recién copiado.
1. En **Configuración del sitio**, seleccione **Canales**.
1. Junto al nombre del canal, seleccione los puntos suspensivos (**...**) y luego seleccione **Cambiar el canal de la tienda en línea**.
1. En el cuadro de diálogo **Cambiar el canal de la tienda en línea**, seleccione el canal a asignar al sitio recién copiado, y luego seleccione **Aceptar**.
1. Seleccione **Guardar y publicar**.

## <a name="additional-resources"></a>Recursos adicionales

[Asociar un sitio de Dynamics 365 Commerce con un canal en línea](../associate-site-online-store.md)
