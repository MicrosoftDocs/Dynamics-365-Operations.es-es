---
title: Visión general de la gestión del ciclo de vida del pedido de producción
description: Al crear un pedido de producción, se inicia una solicitud para iniciar la producción de un artículo. El pedido de producción contiene información acerca de qué se producirá, qué cantidad y la fecha de finalización planificada. También contiene información relativa a qué materiales se van a consumir y qué proceso seguir para producir el artículo.
author: johanhoffmann
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "19741"
- intro-internal
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f0e3d15cbb522dd4a9322a8bac64e1a14e8432d3aff6722907a7f14fa3fefb2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773234"
---
# <a name="production-order-lifecycle-overview"></a>Visión general de la gestión del ciclo de vida del pedido de producción

[!include [banner](../includes/banner.md)]

Al crear un pedido de producción, se inicia una solicitud para iniciar la producción de un artículo. El pedido de producción contiene información acerca de qué se producirá, qué cantidad y la fecha de finalización planificada. También contiene información relativa a qué materiales se van a consumir y qué proceso seguir para producir el artículo.

Un pedido de producción pasa por las etapas del ciclo de vida de producción. Cuando se crea un pedido, se le asigna el estado **Creado**. Cuando se termina un pedido, se le asigna el estado **Finalizado**. Un parámetro en cada etapa permite al usuario configurar cada paso. El parámetro se puede configurar para un único usuario o para todos los usuarios.

La lista de materiales de producción y la ruta de producción son las entidades principales del pedido de producción. Se copian en el pedido de producción según el artículo y la cantidad seleccionados que se van a producir. Antes de iniciar el pedido de producción se pueden editar la lista de materiales y la ruta de producción.

El pedido de producción se puede crear en las siguientes situaciones:

-   Se crean al ejecutarse la planificación maestra según la demanda de material.
-   Se crean directamente a partir de una línea de pedido de ventas o cuando se crea y se estima un pedido de producción de alto nivel (suministro asegurado).
-   Se crea manualmente.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]