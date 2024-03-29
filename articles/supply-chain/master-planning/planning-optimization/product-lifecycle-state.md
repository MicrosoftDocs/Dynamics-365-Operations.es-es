---
title: Excluir productos que tienen estados del ciclo de vida del producto específicos
description: Este artículo explica cómo excluir productos según su estado de ciclo de vida.
author: t-benebo
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 647e2cf4f14dbdfc3e7f04f43dcbd7115f19e8dc
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740775"
---
# <a name="exclude-products-that-have-specific-product-lifecycle-states"></a>Excluir productos que tienen estados del ciclo de vida del producto específicos

[!include [banner](../../includes/banner.md)]

Los productos lanzados y las versiones de productos lanzados incluyen un campo **Estado del ciclo de vida del producto**. Este campo le permite controlar, entre otras cosas, qué productos se incluyen durante la planificación maestra. Puede agregar, eliminar y editar estados del ciclo de vida según sea necesario yendo a **Gestión de información de producto \> Preparar \> Estado del ciclo de vida del producto**. Para cada estado del ciclo de vida del producto, establezca la opción **Está activo para planificar** en *Sí* si los productos que tienen ese estado deben incluirse durante la planificación maestra. Cuando la opción se establece en *No*, los productos y variantes asociados se excluirán de toda la planificación maestra y todos los cálculos en el nivel de lista de materiales (BOM).

Productos y variantes lanzados donde el campo **Estado del ciclo de vida del producto** se deja en blanco se tratan como si tuvieran un estado de ciclo de vida del producto donde la opción **Está activo para planificar** está configurada en *Sí*. En otras palabras, se incluirán durante la planificación maestra.

> [!NOTE]
> Para ayudar a evitar sugerencias de suministro innecesarias, le recomendamos encarecidamente que asocie todos los productos y variantes lanzados obsoletos con un estado del ciclo de vida del producto donde la opción **Está activo para planificar** está configurada en *No*. Este enfoque es especialmente importante cuando trabaja con variantes de configuración de productos que no son reutilizables, porque ayudará a evitar el desperdicio.

## <a name="related-resources"></a>Recursos relacionados

Para obtener más información acerca de los estados de ciclo de vida de producto, consulte la [Información general sobre el estado de ciclo de vida de producto](../../pim/product-lifecycle.md).

Para obtener información detallada que incluye los pasos para usar estados de ciclo de vida del producto para excluir productos de la planificación maestra y cálculos a nivel de LM, vea [Crear un estado de ciclo de vida del producto para excluir productos de la planificación maestra](../../pim/tasks/exclude-products-master-planning.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]