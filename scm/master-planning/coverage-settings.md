---
title: "Configuración de cobertura"
description: "La programación maestra utiliza la configuración de cobertura para calcular los requisitos de artículos."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c1c5654afa6b592e178af052e3e4a7e246a94c9f
ms.lasthandoff: 03/31/2017


---

# <a name="coverage-settings"></a>Configuración de cobertura

La programación maestra utiliza la configuración de cobertura para calcular los requisitos de artículos. 

Puede especificar la configuración de cobertura de varios modos:

-   Especifique la configuración de cobertura para un grupo de cobertura. Puede crear un grupo de cobertura que contenga la configuración de todos los productos vinculados al grupo de cobertura. Haga clic en ** grupos &gt; de cobertura de &gt; configuración de cobertura &gt; de la planificación maestra ** para crear un grupo de cobertura. Puede vincular un grupo de cobertura a un producto. Si el vínculo es específico de un sitio, un almacén o una dimensión de producto, use el campo **Grupo de cobertura** de la página **Cobertura de artículos**. Si el vínculo es genérico, independientemente de las dimensiones de producto, use **Grupo de cobertura** en la ficha desplegable **Plan** de la página **Detalles de producto**. Si no vincula ningún grupo de cobertura a un producto, la planificación maestra usa el **Grupo de cobertura general** especificado en la página **Parámetros de planificación maestra** de forma predeterminada.

-   Especifique la configuración de cobertura para un producto. Puede crear una configuración de cobertura para un producto específico. Haga clic en ** productos &gt; emitidos de los productos &gt; de la Gestión de información de productos **. Seleccione el producto, en ** panel de acciones, en ** ** plan ** ficha, en ** grupo de cobertura **, haga clic ** cobertura de artículos para abrir ** ** cobertura de artículos ** la página. Si el producto ya está vinculado a un grupo de cobertura, puede anular la configuración del grupo de cobertura mediante el campo **Reemplazar**. Las opciones de cobertura en la página** Cobertura de artículos** prevalece sobre la configuración en la página **Grupo de cobertura**.

<!-- -->

-   Especifique la configuración de cobertura para un producto mediante un asistente. El asistente le guía paso a paso para ayudarle a configurar los parámetros de cobertura de los artículos principales. En la página **Cobertura de artículos**, haga clic en **Asistente** para abrir el **Asistente de cobertura de artículos**.

<!-- -->

-   Especifique la configuración de cobertura para un grupo de dimensiones. Haga clic en ** productos &gt; emitidos comunes &gt; de la Gestión de información de productos **. En ** Detalle de producto emitido ** pagine, en general ** ** ficha, en la gestión ** ** el grupo, haga clic en ** grupo de dimensiones de almacenamiento ** el vínculo. En la página **Grupo de dimensiones de almacenamiento**, seleccione el campo **Plan de cobertura por dimensión** para crear la configuración de cobertura para una dimensión en el grupo de dimensiones de almacenamiento. Todas las dimensiones de producto, como la configuración, color, tamaño, estilo, debe hacer ** Plan de cobertura por dimensión ** seleccionar el campo.



<a name="see-also"></a>Consulte también
--------

[Master plans](master-plans.md)


