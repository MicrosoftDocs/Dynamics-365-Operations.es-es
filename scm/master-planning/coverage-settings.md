---
title: "Configuración de cobertura"
description: "La programación maestra utiliza la configuración de cobertura para calcular los requisitos de artículos."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: b42f0515823bd42ec260aa1d175855a923162b62
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="coverage-settings"></a>Configuración de cobertura

[!include[banner](../includes/banner.md)]


La programación maestra utiliza la configuración de cobertura para calcular los requisitos de artículos. 

Puede especificar la configuración de cobertura de varios modos:

-   Especifique la configuración de cobertura para un grupo de cobertura. Puede crear un grupo de cobertura que contenga la configuración de todos los productos vinculados al grupo de cobertura. Haga clic en **Planificación maestra &gt; Configurar &gt; Cobertura &gt; Grupos de cobertura** para crear un grupo de cobertura. Puede vincular un grupo de cobertura a un producto. Si el vínculo es específico de un sitio, un almacén o una dimensión de producto, use el campo **Grupo de cobertura** de la página **Cobertura de artículos**. Si el vínculo es genérico, independientemente de las dimensiones de producto, use **Grupo de cobertura** en la ficha desplegable **Plan** de la página **Detalles de producto**. Si no vincula ningún grupo de cobertura a un producto, la planificación maestra usa el **Grupo de cobertura general** especificado en la página **Parámetros de planificación maestra** de forma predeterminada.

-   Especifique la configuración de cobertura para un producto. Puede crear una configuración de cobertura para un producto específico. Haga clic en **Gestión de información de productos &gt; Productos &gt; Productos emitidos**. Seleccione el producto, en el **Panel de acciones**, en la pestaña **Plan**, en el **Grupo de cobertura**, haga clic en **Cobertura de artículos** para abrir la página **Cobertura de artículos**. Si el producto ya está vinculado a un grupo de cobertura, puede anular la configuración del grupo de cobertura mediante el campo **Reemplazar**. Las opciones de cobertura en la página**Cobertura de artículos** prevalece sobre la configuración en la página **Grupo de cobertura**.

<!-- -->

-   Especifique la configuración de cobertura para un producto mediante un asistente. El asistente le guía paso a paso para ayudarle a configurar los parámetros de cobertura de los artículos principales. En la página **Cobertura de artículos**, haga clic en **Asistente** para abrir el **Asistente de cobertura de artículos**.

<!-- -->

-   Especifique la configuración de cobertura para un grupo de dimensiones. Haga clic en **Gestión de información de productos &gt; Común &gt; Productos emitidos**. En la página **Detalles de producto emitido**, en la ficha **General**, en el grupo **Administración**, haga clic en el vínculo **Grupo de dimensiones de almacenamiento**. En la página **Grupo de dimensiones de almacenamiento**, seleccione el campo **Plan de cobertura por dimensión** para crear la configuración de cobertura para una dimensión en el grupo de dimensiones de almacenamiento. Todas las dimensiones de producto, como configuración, color, tamaño, estilo, deben tener el campo **Plan de cobertura por dimensión** seleccionado.



<a name="see-also"></a>Consulte también
--------

[Planes maestros](master-plans.md)




