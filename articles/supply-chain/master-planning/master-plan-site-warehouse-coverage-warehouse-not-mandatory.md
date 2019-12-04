---
title: Planificación maestra para cobertura de sitios y almacenes, almacén no obligatorio
description: Este tema describe cómo se planifica un artículo que tiene el sitio y el almacén como dimensiones de cobertura. La dimensión Almacén no es obligatoria.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cea228e04632bd61f60771b09481241df5d16bd3
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813716"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a>Planificación maestra para cobertura de sitios y almacenes, almacén no obligatorio

[!include [banner](../includes/banner.md)]

Este tema describe cómo se planifica un artículo que tiene el sitio y el almacén como dimensiones de cobertura. La dimensión Almacén no es obligatoria.

El escenario de planificación maestra implica las condiciones siguientes:

-   La dimensión del sitio está definida como obligatoria y se debe especificar en la transacción de demanda. Este ajuste no se puede modificar.
-   La dimensión Almacén no está configurada como obligatoria. El almacén puede ser conocido, pero no se usa en el cálculo de la planificación maestra.
-   La dimensión Sitio y Almacén están configuradas para la planificación de cobertura. Se pueden configurar otras dimensiones también para la planificación de cobertura. Sin embargo, no se ven afectadas por la funcionalidad de multisitio.

El gráfico siguiente ilustra cómo tiene lugar la planificación maestra. Los parámetros a los que se hace referencia en el gráfico, así como sus ubicaciones, son los siguientes:
-   El almacén se establece en Manual. Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**. En la ficha desplegable **Planificación maestra**, consulte el campo **Manual**.
-   La cobertura de artículos está definida para el artículo. Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**. Seleccione el artículo y, a continuación, en Panel de acciones, en la pestaña **Plan**, haga clic en **Cobertura de artículos**.
-   Están definidas relaciones de relleno para el almacén. Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**. En la ficha desplegable **Planificación maestra**, consulte el grupo de campos **Almacén principal**.
-   El tipo de pedido predeterminado está definido en Producción, Pedido de compra o Kanban. Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**. Seleccione el artículo y, a continuación, en Panel de acciones, en la pestaña **Plan**, haga clic en **Configuración predeterminada de pedido**. En el formulario **Configuración predeterminada de pedido** consulte **Tipo de pedido predeterminado**.

![Demanda para el sitio y el almacén, almacén no](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)



<a name="additional-resources"></a>Recursos adicionales
--------

[Visión general de la planificación maestra y la funcionalidad multisitio](master-plan-multisite-functionality.md)

[Planificación maestra para cobertura de sitios, almacén obligatorio](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planificación maestra de cobertura de sitios y almacén, almacén obligatorio](master-plan-site-coverage-warehouse-mandatory.md)

[Planificación maestra de cobertura de sitios y almacén, almacén no obligatorio](master-plan-site-coverage-warehouse-not-mandatory.md)

[Determinar la versión de L. MAT.](master-plan-bom-version-determined.md)



