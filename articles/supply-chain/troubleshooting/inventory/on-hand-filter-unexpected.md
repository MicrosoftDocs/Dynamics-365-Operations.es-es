---
title: El panel de filtro de la página Lista disponible no funciona como como esperaba.
description: Los filtros del panel de filtro de la página "Lista disponible" no filtra los resultados como se espera.
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 2b2b233e22378c8710a63dce83d168bfd89eba7f
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920507"
---
# <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-work-as-expected"></a>El panel de filtro de la página Lista disponible no funciona como como esperaba.

## <a name="symptoms"></a>Síntomas

Los filtros del panel de filtro de la página **Lista disponible** no filtra los resultados como se espera.

## <a name="resolution"></a>Resolución

La página **Lista disponible** se obtiene de una tabla detallada de inventario disponible que incluye todas las dimensiones disponibles. Sin embargo, la lista en esta página es un resumen. Por lo tanto, podría combinar filas de la tabla de origen agregando valores de acuerdo con las dimensiones que se muestran.

Los filtros que se configuran en el panel de filtro se aplican a la tabla de origen, no a la lista agregada. Este comportamiento a veces puede conllevar resultados inesperados, como se muestra en [estos ejemplos](/dynamics365/supply-chain/inventory/inventory-on-hand-list.md#examples).

Sin embargo, los [filtros que se proporcionan en la cuadrícula](/dynamics365/supply-chain/inventory/inventory-on-hand-list.md#grid-filters) *sí* se aplican a la lista agregada. Estos filtros incluyen tanto el filtro rápido en la parte superior de la cuadrícula como el filtro para cada encabezado de columna.