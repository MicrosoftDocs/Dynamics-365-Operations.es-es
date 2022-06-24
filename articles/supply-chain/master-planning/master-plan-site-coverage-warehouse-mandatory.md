---
title: Planificación maestra para cobertura de sitios, almacén obligatorio
description: Este artículo describe cómo se planifica un artículo que tiene el sitio como dimensión de cobertura. El almacén es una dimensión obligatoria.
author: t-benebo
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2454
ms.assetid: aa135030-f98c-48bf-902c-e52f680dc247
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b6e9cb9362fcafab5738e0a1887366e5fd1efbab
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863980"
---
# <a name="master-planning-for-site-coverage-mandatory-warehouse"></a>Planificación maestra para cobertura de sitios, almacén obligatorio

[!include [banner](../includes/banner.md)]

Este artículo describe cómo se planifica un artículo que tiene el sitio como dimensión de cobertura. El almacén es una dimensión obligatoria.

El escenario de planificación maestra implica las condiciones siguientes:

-   La dimensión del sitio está definida como obligatoria y se debe especificar en la transacción de demanda. Este ajuste no se puede modificar.
-   La dimensión de almacén está definida como obligatoria y se debe especificar en la transacción de demanda.
-   La dimensión de sitio está definida para la planificación de la cobertura. También se pueden definir otras dimensiones para la planificación de la cobertura. Sin embargo, no se verán afectadas por la funcionalidad multisitio.
-   La dimensión de almacén no está definida para la planificación de la cobertura. Por lo tanto, el suministro y la demanda se agregan por sitio y, quizás, también otras dimensiones planificadas por cobertura.

El gráfico siguiente ilustra cómo tiene lugar la planificación maestra. Los parámetros a los que se hace referencia en el gráfico, así como sus ubicaciones, son los siguientes:
-   La cobertura de artículos está definida para el artículo. Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**. Seleccione el artículo y haga clic en **Planificar &gt; Cobertura de artículos**.
-   Están definidas relaciones de relleno para el almacén. Haga clic en **Gestión del inventario &gt; Configurar &gt; Desglose del inventario &gt; Almacenes**. En la ficha **Planificación maestra**, consulte el grupo de campos **Almacén principal**.
-   El tipo de pedido predeterminado está definido en Producción, Pedido de compra o Kanban. Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**. Seleccione el artículo y, a continuación, haga clic en **Planificar &gt; Configuración predeterminada de pedido**. En el formulario **Configuración predeterminada de pedido** consulte **Tipo de pedido predeterminado**.

![Demanda de cobertura de sitios, almacén obligatorio.](./media/multisitedemandexplosionscenarioforsitecoveragewarehousemandatory.jpg)



## <a name="additional-resources"></a>Recursos adicionales

[Información general de la planificación maestra y la funcionalidad multisitio](master-plan-multisite-functionality.md)

[Planificación maestra de cobertura de sitios y almacén, almacén obligatorio](master-plan-site-warehouse-coverage-warehouse-mandatory.md)

[Planificación maestra para cobertura de sitios, almacén obligatorio](master-plan-site-coverage-warehouse-mandatory.md)

[Planificación maestra de cobertura de sitios y almacén, almacén no obligatorio](master-plan-site-warehouse-coverage-warehouse-not-mandatory.md)

[Determinar la versión de L. MAT.](master-plan-bom-version-determined.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]