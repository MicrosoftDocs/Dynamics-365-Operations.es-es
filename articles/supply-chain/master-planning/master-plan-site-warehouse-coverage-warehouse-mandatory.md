---
title: "Planificación maestra para cobertura de sitios y almacenes, almacén obligatorio"
description: "Este tema describe cómo se planifica un artículo que tiene el sitio y el almacén como dimensiones de cobertura. La dimensión de almacén es obligatoria."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2554
ms.assetid: 3211e95f-b91a-4d27-8d92-f328ae2bcf12
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 61c007711c593df063a497b980f501589d88470c
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-mandatory"></a>Planificación maestra para cobertura de sitios y almacenes, almacén obligatorio

[!include [banner](../includes/banner.md)]

Este tema describe cómo se planifica un artículo que tiene el sitio y el almacén como dimensiones de cobertura. La dimensión de almacén es obligatoria.

El escenario de planificación maestra implica las condiciones siguientes:

-   La dimensión del sitio está definida como obligatoria y se debe especificar en la transacción de demanda.
-   La dimensión de almacén está definida como obligatoria y se debe especificar en la transacción de demanda.
-   Las dimensiones de sitio y de almacén están definidas para la planificación de la cobertura. Se pueden configurar otras dimensiones también para la planificación de cobertura. Sin embargo, no se ven afectadas por la funcionalidad de multisitio.

El gráfico siguiente ilustra cómo tiene lugar la planificación maestra. Los parámetros a los que se hace referencia en el gráfico, así como sus ubicaciones, son los siguientes:
-   El almacén se establece en **Manual**. Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**. En la ficha desplegable **Planificación maestra**, consulte el campo **Manual**.
-   La cobertura de artículos está definida para el artículo. Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**. Seleccione el artículo y, a continuación, en Panel de acciones, en la pestaña **Plan**, haga clic en **Cobertura de artículos**.
-   Están definidas relaciones de relleno para el almacén. Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**. En la ficha desplegable **Planificación maestra**, consulte el grupo de campos **Almacén principal**.
-   El tipo de pedido predeterminado está definido en Producción, Pedido de compra o Kanban. Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**. Seleccione el artículo y, a continuación, en Panel de acciones, en la pestaña **Plan**, haga clic en **Configuración predeterminada de pedido**. En el formulario **Configuración predeterminada de pedido** consulte **Tipo de pedido predeterminado**.

![Sitio de demanda y cobertura de almacén, almacén obligatorio](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousemandatory.jpg)



<a name="additional-resources"></a>Recursos adicionales
--------

[Planificación maestra y funcionalidad multisitio](master-plan-multisite-functionality.md)

[Planificación maestra: cobertura de sitios y almacenes, almacén obligatorio](master-plan-site-coverage-warehouse-mandatory.md)

[Planificación maestra: cobertura de sitios y almacenes, almacén no obligatorio](master-plan-site-coverage-warehouse-not-mandatory.md)

[Planificación maestra: cobertura de sitios y almacenes, almacén no obligatorio](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planificación maestra: cómo se establece la versión de la lista de materiales](master-plan-bom-version-determined.md)




