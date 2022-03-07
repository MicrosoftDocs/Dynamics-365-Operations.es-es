---
title: Faltan productos y categorías después de la copia del entorno
description: Este tema proporciona una guía de resolución de problemas que puede ayudar cuando faltan productos y categorías después de que un sitio se copia entre entornos o dentro del mismo entorno.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: 4964b9623a91286d4f8260bcae7941feb48f8962
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022407"
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
