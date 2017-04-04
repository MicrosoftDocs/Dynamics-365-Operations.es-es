---
title: "Planificación maestra para la cobertura de sitios, almacén obligatorio"
description: "Este tema describe cómo se planifica un artículo que tiene el sitio como dimensión de cobertura. El almacén es una dimensión obligatoria."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 4c595aa9809e37ba752b76f559ef909c071eb303
ms.lasthandoff: 03/31/2017


---

# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a>Planificación maestra para la cobertura de sitios, almacén obligatorio

Este tema describe cómo se planifica un artículo que tiene el sitio como dimensión de cobertura. El almacén es una dimensión obligatoria.

El escenario de planificación maestra implica las condiciones siguientes:

-   La dimensión del sitio está definida como obligatoria y se debe especificar en la transacción de demanda. Este ajuste no se puede modificar.
-   La dimensión de almacén está definida como obligatoria y se debe especificar en la transacción de demanda.
-   La dimensión de sitio está definida para la planificación de la cobertura. También se pueden definir otras dimensiones para la planificación de la cobertura. Sin embargo, no se verán afectadas por la funcionalidad multisitio.
-   La dimensión de almacén no está definida para la planificación de la cobertura. Por lo tanto, el suministro y la demanda se agregan por sitio y, quizás, también otras dimensiones planificadas por cobertura.

El gráfico siguiente ilustra cómo tiene lugar la planificación maestra. Los parámetros a los que se hace referencia en el gráfico, así como sus ubicaciones, son los siguientes:
-   La cobertura de artículos está definida para el artículo. Haga clic en ** productos &gt; emitidos de los productos&gt; de la Gestión de información de productos **. Seleccione el artículo, y haga clic en ** cobertura &gt; de artículos del plan **.
-   Están definidas relaciones de relleno para el almacén. Haga clic en ** almacenes de &gt; instalación de descomposición &gt; de inventario de gestión &gt; de inventario **. En la ficha **Planificación maestra**, consulte el grupo de campos **Almacén principal**.
-   El tipo de pedido predeterminado está definido en Producción, Pedido de compra o Kanban. Haga clic en ** productos &gt; emitidos de los productos&gt; de la Gestión de información de productos **. Seleccione el artículo, y haga clic en ** planee &gt; la configuración de pedido predeterminada **. En el formulario **Configuración predeterminada de pedido** consulte **Tipo de pedido predeterminado**.

![Demanda de cobertura de sitios, almacén obligatorio](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



<a name="see-also"></a>Consulte también
--------

[Master planning and multisite functionality](master-plan-multisite-functionality.md)

[Planificación maestra: cobertura de sitios y almacenes, almacén obligatorio](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[- Planificación maestra cobertura de sitios. almacén obligatorio] (master-plan-site-coverage-warehouse-mandatory.md)

[Planificación maestra: cobertura de sitios y almacenes, almacén no obligatorio](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planificación maestra: cómo se establece la versión de la lista de materiales](master-plan-bom-version-determined.md)


