---
title: Planificación maestra para cobertura de sitios y almacenes, almacén no obligatorio
description: Este artículo describe cómo se planifica un artículo que tiene el sitio y el almacén como dimensiones de cobertura. La dimensión Almacén no es obligatoria.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2514
ms.assetid: 92d47bdd-df68-4f60-ac9a-96aa08236c26
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b4989a05f4647ac836b78692da7f63396dbef788
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741022"
---
# <a name="master-planning-for-site-and-warehouse-coverage-warehouse-not-mandatory"></a>Planificación maestra para cobertura de sitios y almacenes, almacén no obligatorio

[!include [banner](../includes/banner.md)]

Este artículo describe cómo se planifica un artículo que tiene el sitio y el almacén como dimensiones de cobertura. La dimensión Almacén no es obligatoria.

El escenario de planificación maestra implica las condiciones siguientes:

-   La dimensión del sitio está definida como obligatoria y se debe especificar en la transacción de demanda. Este ajuste no se puede modificar.
-   La dimensión Almacén no está configurada como obligatoria. El almacén puede ser conocido, pero no se usa en el cálculo de la planificación maestra.
-   La dimensión Sitio y Almacén están configuradas para la planificación de cobertura. Se pueden configurar otras dimensiones también para la planificación de cobertura. Sin embargo, no se ven afectadas por la funcionalidad de multisitio.

El gráfico siguiente ilustra cómo tiene lugar la planificación maestra. Los parámetros a los que se hace referencia en el gráfico, así como sus ubicaciones, son los siguientes:
-   El almacén se establece en Manual. Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**. En la ficha desplegable **Planificación maestra**, consulte el campo **Manual**.
-   La cobertura de artículos está definida para el artículo. Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos despachados**. Seleccione el artículo y, a continuación, en el panel Acciones, en la pestaña **Plan**, haga clic en **Cobertura de artículos**.
-   Están definidas relaciones de relleno para el almacén. Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**. En la ficha desplegable **Planificación maestra**, consulte el grupo de campos **Almacén principal**.
-   El tipo de pedido predeterminado está definido en Producción, Pedido de compra o Kanban. Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos despachados**. Seleccione el artículo y, a continuación, en panel Acciones, en la pestaña **Plan**, haga clic en **Configuración predeterminada de pedidos**. En el formulario **Configuración predeterminada de pedido** consulte **Tipo de pedido predeterminado**.

![Demanda para el sitio y el almacén, almacén no.](./media/multisitedemandexplosionscenarioforsiteandwarehousecoveragewarehousenotmandatory.jpg)



## <a name="additional-resources"></a>Recursos adicionales

- [Información general de la planificación maestra y la funcionalidad multisitio](master-plan-multisite-functionality.md)
- [Planificación maestra para cobertura de sitios, almacén obligatorio](master-plan-site-warehouse-coverage-warehouse-mandatory.md)
- [Planificación maestra de cobertura de sitios y almacén, almacén obligatorio](master-plan-site-coverage-warehouse-mandatory.md)
- [Planificación maestra de cobertura de sitios y almacén, almacén no obligatorio](master-plan-site-coverage-warehouse-not-mandatory.md)
- [Determinar la versión de L. MAT.](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]