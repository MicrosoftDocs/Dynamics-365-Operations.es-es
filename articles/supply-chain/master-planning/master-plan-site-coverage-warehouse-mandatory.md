---
title: "Planificación maestra para cobertura de sitios, almacén obligatorio"
description: "Este tema describe cómo se planifica un artículo que tiene el sitio como dimensión de cobertura. El almacén es una dimensión obligatoria."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 14df626025a22237afe30cc5b08d42b475fc3a4f
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a>Planificación maestra para cobertura de sitios, almacén obligatorio

[!include[banner](../includes/banner.md)]


Este tema describe cómo se planifica un artículo que tiene el sitio como dimensión de cobertura. El almacén es una dimensión obligatoria.

El escenario de planificación maestra implica las condiciones siguientes:

-   La dimensión del sitio está definida como obligatoria y se debe especificar en la transacción de demanda. Este ajuste no se puede modificar.
-   La dimensión de almacén está definida como obligatoria y se debe especificar en la transacción de demanda.
-   La dimensión de sitio está definida para la planificación de la cobertura. También se pueden definir otras dimensiones para la planificación de la cobertura. Sin embargo, no se verán afectadas por la funcionalidad multisitio.
-   La dimensión de almacén no está definida para la planificación de la cobertura. Por lo tanto, el suministro y la demanda se agregan por sitio y, quizás, también otras dimensiones planificadas por cobertura.

El gráfico siguiente ilustra cómo tiene lugar la planificación maestra. Los parámetros a los que se hace referencia en el gráfico, así como sus ubicaciones, son los siguientes:
-   La cobertura de artículos está definida para el artículo. Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**. Seleccione el artículo y haga clic en **Planificar &gt; Cobertura de artículos**.
-   Están definidas relaciones de relleno para el almacén. Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**. En la ficha **Planificación maestra**, consulte el grupo de campos **Almacén principal**.
-   El tipo de pedido predeterminado está definido en Producción, Pedido de compra o Kanban. Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**. Seleccione el artículo y, a continuación, haga clic en **Planificar &gt; Configuración predeterminada de pedido**. En el formulario **Configuración predeterminada de pedido** consulte **Tipo de pedido predeterminado**.

![Demanda de cobertura de sitios, almacén obligatorio](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



<a name="see-also"></a>Consulte también
--------

[Planificación maestra y funcionalidad multisitio](master-plan-multisite-functionality.md)

[Planificación maestra: cobertura de sitios y almacenes, almacén obligatorio](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planificación maestra: cobertura de sitios y almacenes, almacén obligatorio](master-plan-site-coverage-warehouse-mandatory.md)

[Planificación maestra: cobertura de sitios y almacenes, almacén no obligatorio](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Planificación maestra: cómo se establece la versión de la lista de materiales](master-plan-bom-version-determined.md)




