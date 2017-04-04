---
title: "La planificación maestra para la cobertura de sitios, almacén no obligatorio"
description: "Este tema describe cómo se planifica un artículo que tiene la dimensión del sitio establecida para cobertura."
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
ms.custom: 2474
ms.assetid: 316da918-67ae-43c5-baea-00ae559e29b0
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 28607f0fc8db99c9fc8e96b4514763b8cf589dd8
ms.lasthandoff: 03/31/2017


---

# <a name="master-planning-for-site-coverage-warehouse-not-mandatory"></a>La planificación maestra para la cobertura de sitios, almacén no obligatorio

Este tema describe cómo se planifica un artículo que tiene la dimensión del sitio establecida para cobertura.

El escenario de planificación maestra implica las condiciones siguientes:

-   La dimensión del sitio está definida como obligatoria y se debe especificar en la transacción de demanda.
-   La dimensión Almacén no está configurada como obligatoria. El almacén puede ser conocido, pero no se usa en el cálculo de la planificación maestra.
-   La dimensión de sitio está definida para la planificación de la cobertura.
-   La dimensión de almacén no está definida para la planificación de la cobertura. Por lo tanto, el suministro y la demanda se agregan por sitio y, quizás, también otras dimensiones planificadas por cobertura.

El gráfico siguiente ilustra cómo tiene lugar la planificación maestra. Los parámetros a los que se hace referencia en el gráfico, así como sus ubicaciones, son los siguientes:
-   La cobertura de artículos está definida para el artículo. Haga clic en ** productos &gt; emitidos de los productos&gt; de la Gestión de información de productos **. Seleccione el artículo, y haga clic en ** cobertura &gt; de artículos del plan **.
-   Están definidas relaciones de relleno para el almacén. Haga clic en ** almacenes de &gt; instalación de descomposición &gt; de inventario de gestión &gt; de inventario **. En la ficha **Planificación maestra**, consulte el grupo de campos **Almacén principal**.
-   El tipo de pedido predeterminado está definido en Producción, Pedido de compra o Kanban. Haga clic en ** productos &gt; emitidos de los productos&gt; de la Gestión de información de productos **. Seleccione el artículo, y haga clic en ** planee &gt; la configuración de pedido predeterminada **. En el formulario **Configuración predeterminada de pedido**, consulte el campo **Tipo de pedido predeterminado**.

![Demanda de cobertura de sitios, almacén no obligatorio](./media/multisitedemandexplosionscenarioforsitecoveragewarehousenotmandatory.jpg)



<a name="see-also"></a>Consulte también
--------

[Master planning and multisite functionality](master-plan-multisite-functionality.md)

[Planificación maestra: cobertura de sitios y almacenes, almacén obligatorio](master-plan-site-coverage-warehouse-mandatory.md)

[Planificación maestra: cobertura de sitios y almacenes, almacén no obligatorio](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planificación maestra: cobertura de sitios y almacenes, almacén obligatorio](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[- Planificación maestra cómo se determina la versión de L master-plan-bom-version-determined.md] ()


