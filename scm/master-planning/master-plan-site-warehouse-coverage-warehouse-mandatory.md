---
title: "La planificación maestra para el alcance del sitio y el almacén, almacén obligatorio"
description: "Este tema describe cómo se planifica un artículo que tiene el sitio y el almacén como dimensiones de cobertura. La dimensión de almacén es obligatoria."
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
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: a0931d88f84544160803e42466575c02f47588a4
ms.lasthandoff: 03/31/2017


---

# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a>La planificación maestra para el alcance del sitio y el almacén, almacén obligatorio

Este tema describe cómo se planifica un artículo que tiene el sitio y el almacén como dimensiones de cobertura. La dimensión de almacén es obligatoria.

El escenario de planificación maestra implica las condiciones siguientes:

-   La dimensión del sitio está definida como obligatoria y se debe especificar en la transacción de demanda.
-   La dimensión de almacén está definida como obligatoria y se debe especificar en la transacción de demanda.
-   Las dimensiones de sitio y de almacén están definidas para la planificación de la cobertura. Se pueden configurar otras dimensiones también para la planificación de cobertura. Sin embargo, no se ven afectadas por la funcionalidad de multisitio.

El gráfico siguiente ilustra cómo tiene lugar la planificación maestra. Los parámetros a los que se hace referencia en el gráfico, así como sus ubicaciones, son los siguientes:
-   The warehouse is set to **Manual**. Haga clic en ** almacenes de &gt; instalación de descomposición &gt; de inventario de gestión &gt; de inventario **. En la ficha desplegable **Planificación maestra**, consulte el campo **Manual**.
-   La cobertura de artículos está definida para el artículo. Haga clic en ** productos &gt; emitidos de los productos&gt; de la Gestión de información de productos **. Seleccione el artículo y, a continuación, en el panel de acciones, en ** plan ** la ficha, haga clic en ** cobertura de artículos **.
-   Están definidas relaciones de relleno para el almacén. Haga clic en ** almacenes de &gt; instalación de descomposición &gt; de inventario de gestión &gt; de inventario **. En la ficha desplegable **Planificación maestra**, consulte el grupo de campos **Almacén principal**.
-   El tipo de pedido predeterminado está definido en Producción, Pedido de compra o Kanban. Haga clic en ** productos &gt; emitidos de los productos&gt; de la Gestión de información de productos **. Seleccione el artículo y, a continuación, en el panel de acciones, en ** plan ** la ficha, haga clic en ** configuración de pedido predeterminada **. En el formulario **Configuración predeterminada de pedido** consulte **Tipo de pedido predeterminado**.

![Sitio de demanda y cobertura de almacén, almacén obligatorio](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



<a name="see-also"></a>Consulte también
--------

[Master planning and multisite functionality](master-plan-multisite-functionality.md)

[Planificación maestra: cobertura de sitios y almacenes, almacén obligatorio](master-plan-site-coverage-warehouse-mandatory.md)

[Planificación maestra: cobertura de sitios y almacenes, almacén no obligatorio](master-plan-site-coverage-warehouse-not-mandatory.md)

[Planificación maestra: cobertura de sitios y almacenes, almacén no obligatorio](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planificación maestra: cómo se establece la versión de la lista de materiales](master-plan-bom-version-determined.md)


