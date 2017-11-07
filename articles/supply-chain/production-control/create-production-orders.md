---
title: "Crear pedidos de producción"
description: "Al crear un pedido de producción, se inicia una solicitud para iniciar la producción de un artículo. El pedido de producción contiene información acerca de qué se producirá, qué cantidad y la fecha de finalización planificada. También contiene información relativa a qué materiales se van a consumir y qué proceso seguir para producir el artículo."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 58213d4d6e8c29ab6605eb7aa5c6cb9ca6ba4a10
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="create-production-orders"></a>Crear pedidos de producción

[!include[banner](../includes/banner.md)]


Al crear un pedido de producción, se inicia una solicitud para iniciar la producción de un artículo. El pedido de producción contiene información acerca de qué se producirá, qué cantidad y la fecha de finalización planificada. También contiene información relativa a qué materiales se van a consumir y qué proceso seguir para producir el artículo.

Un pedido de producción pasa por las etapas del ciclo de vida de producción. Cuando se crea un pedido, se le asigna el estado **Creado**. Cuando se termina un pedido, se le asigna el estado **Finalizado**. Un parámetro en cada etapa permite al usuario configurar cada paso. El parámetro se puede configurar para un único usuario o para todos los usuarios.

La lista de materiales de producción y la ruta de producción son las entidades principales del pedido de producción. Se copian en el pedido de producción según el artículo y la cantidad seleccionados que se van a producir. Antes de iniciar el pedido de producción se pueden editar la lista de materiales y la ruta de producción.

El pedido de producción se puede crear en las siguientes situaciones:

-   Se crean al ejecutarse la planificación maestra según la demanda de material.
-   Se crean directamente a partir de una línea de pedido de ventas o cuando se crea y se estima un pedido de producción de alto nivel (suministro asegurado).
-   Se crea manualmente.





