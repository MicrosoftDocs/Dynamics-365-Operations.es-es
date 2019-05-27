---
title: Configuración de cobertura
description: Este tema proporciona información acerca de la configuración de cobertura que la programación maestra usa para calcular los requisitos de artículos.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 99e094a7131b6d3a299fc72abd0141529908ddd2
ms.sourcegitcommit: 9e50bee6a67f0fe2fa6f86e02c7e8de16d0e2482
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538903"
---
# <a name="coverage-settings"></a>Configuración de cobertura

[!include [banner](../includes/banner.md)]

La programación maestra utiliza la configuración de cobertura para calcular los requisitos de artículos.

Puede especificar la configuración de cobertura de varios modos:

- Especifique la configuración de cobertura para un grupo de cobertura.

    Puede crear un grupo de cobertura que contenga la configuración de todos los productos vinculados al grupo de cobertura. Para crear un grupo de cobertura, vaya a **Planificación maestra &gt; Configurar &gt; Cobertura &gt; Grupos de cobertura**. Puede vincular un grupo de cobertura a un producto. Si el vínculo es específico de un sitio, un almacén o una dimensión de producto, use el campo **Grupo de cobertura** de la página **Cobertura de artículos**. Si el vínculo es genérico, independientemente de las dimensiones de producto, use el campo **Grupo de cobertura** de la ficha desplegable **Plan** de la página **Detalles de producto**. De forma predeterminada, si no vincula ningún grupo de cobertura a un producto, la planificación maestra usa el grupo de cobertura general especificado en la página **Parámetros de planificación maestra** de forma predeterminada.

- Especifique la configuración de cobertura para un producto.

    Puede crear una configuración de cobertura para un producto específico. Vaya a **Gestión de información de productos &gt; Productos &gt; Productos emitidos**. Seleccione el producto y entonces, en el Panel de acciones, en la pestaña **Plan**, en el Grupo de **cobertura**, haga clic en **Cobertura de artículos** para abrir la página **Cobertura de artículos**. Si el producto ya está vinculado a un grupo de cobertura, puede anular la configuración del grupo de cobertura mediante el campo **Reemplazar**. Las opciones de cobertura en la página**Cobertura de artículos** prevalece sobre la configuración en la página **Grupo de cobertura**.

- Especifique la configuración de cobertura para un producto mediante un asistente.

    El asistente le guía paso a paso con el proceso de configurar los parámetros principales de la cobertura de artículos. En la página **Cobertura de artículos** del panel de acciones, seleccione **Asistente** para abrir el **Asistente de cobertura de artículos**.

- Especifique la configuración de cobertura para un grupo de dimensiones.

    Vaya a **Gestión de información de productos &gt; Productos &gt; Productos emitidos**. En la página **Detalles de producto emitido**, en la ficha desplegable **General**, en la sección **Administración**, seleccione el vínculo en el campo **Grupo de dimensiones de almacenamiento**. En la página **Grupos de dimensiones de almacenamiento**, seleccione la casilla de verificación **Plan de cobertura por dimensión** para crear la configuración de cobertura para una dimensión en el grupo de dimensiones de almacenamiento. Todas las dimensiones de producto, como configuración, color, tamaño, estilo, deben tener el campo **Plan de cobertura por dimensión** seleccionado.

## <a name="additional-resources"></a>Recursos adicionales

[Planes maestros](master-plans.md)
