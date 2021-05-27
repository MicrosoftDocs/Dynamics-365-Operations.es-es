---
title: La planificación maestra genera pedidos planificados para productos fantasma
description: Al ejecutar la planificación maestra, se crean pedidos planificados para productos fantasma.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: anderso
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ea4bdb3729d163126234e02524cef331051cd48
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026888"
---
# <a name="master-planning-generates-planned-orders-for-phantom-products"></a>La planificación maestra genera pedidos planificados para productos fantasma

Número de KB: 4614729

## <a name="symptoms"></a>Síntomas

Al ejecutar la planificación maestra, se crean pedidos planificados para productos fantasma.

## <a name="resolution"></a>Resolución

La configuración de la opción **Fantasma** para productos lanzados determina el tipo de línea predeterminado en la lista de materiales (BOM). Cuando la opción **Fantasma** está configurada en *Sí*, el sistema seguirá creando pedidos planificados para el artículo, pero la opción **Requisito derivado directamente** para cada pedido planificado se establecerá en *Sí*. Por lo tanto, el pedido de producción planificado no se puede confirmar por sí solo. En cambio, siempre se incluirá automáticamente cuando se confirme el pedido de producción principal. Además, las líneas de la L. MAT. del pedido fantasma planificado se incluirán en la L. MAT. del pedido de producción principal.
