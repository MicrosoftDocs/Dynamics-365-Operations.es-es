---
title: Planificación maestra para cobertura de sitios y almacenes, almacén no obligatorio
description: Este artículo describe cómo se planifica un artículo que tiene la dimensión del sitio establecida para cobertura.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6b03bd1970aa7a2f3276186a0a9f8c2cd2880956
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741159"
---
# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a>Planificación maestra para cobertura de sitios y almacenes, almacén no obligatorio

[!include [banner](../includes/banner.md)]

Este artículo describe cómo se planifica un artículo que tiene la dimensión del sitio establecida para cobertura.

El escenario de planificación maestra implica las condiciones siguientes:

-   La dimensión del sitio está definida como obligatoria y se debe especificar en la transacción de demanda.
-   La dimensión Almacén no está configurada como obligatoria. El almacén puede ser conocido, pero no se usa en el cálculo de la planificación maestra.
-   La dimensión de sitio está definida para la planificación de la cobertura.
-   La dimensión de almacén no está definida para la planificación de la cobertura. Por lo tanto, el suministro y la demanda se agregan por sitio y, quizás, también otras dimensiones planificadas por cobertura.

El gráfico siguiente ilustra cómo tiene lugar la planificación maestra. Los parámetros a los que se hace referencia en el gráfico, así como sus ubicaciones, son los siguientes:
-   La cobertura de artículos está definida para el artículo. Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**. Seleccione el artículo y haga clic en **Planificar &gt; Cobertura de artículos**.
-   Están definidas relaciones de relleno para el almacén. Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**. En la ficha **Planificación maestra**, consulte el grupo de campos **Almacén principal**.
-   El tipo de pedido predeterminado está definido en Producción, Pedido de compra o Kanban. Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**. Seleccione el artículo y, a continuación, haga clic en **Planificar &gt; Configuración predeterminada de pedido**. En el formulario **Configuración predeterminada de pedido**, consulte el campo **Tipo de pedido predeterminado**.

![Demanda de cobertura de sitios, almacén no obligatorio.](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



## <a name="additional-resources"></a>Recursos adicionales

- [Información general de la planificación maestra y la funcionalidad multisitio](master-plan-multisite-functionality.md)
- [Planificación maestra de cobertura de sitios y almacén, almacén obligatorio](master-plan-site-coverage-warehouse-mandatory.md)
- [Planificación maestra para cobertura de sitios, almacén obligatorio](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)
- [Planificación maestra para cobertura de sitios, almacén no obligatorio](master-plan-site-warehouse-coverage-warehouse-mandatory.md)
- [Determinar la versión de L. MAT.](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]