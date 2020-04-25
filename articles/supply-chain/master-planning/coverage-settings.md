---
title: Configuración de cobertura
description: Este tema proporciona información acerca de la configuración de cobertura que la programación maestra usa para calcular los requisitos de artículos.
author: roxanadiaconu
manager: tfehr
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a7722921407eab2bf053761eec099d506ce4d67c
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203903"
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


## <a name="coverage-codes"></a>Códigos de cobertura

La planificación maestra se puede configurar para utilizar varios métodos de reabastecimiento. Los métodos de reabastecimiento o los métodos de medición de lotes son técnicas que utiliza el sistema para determinar el tamaño de lote para artículos comprados o producidos. 

Cada método de reabastecimiento se asigna a uno de los códigos de cobertura siguientes:

- **Manual** - El método de medición de lote donde el sistema no sugiere pedidos comprados, transferidos o de producción para el artículo. El planificador del artículo será responsable de realizar los pedidos necesarios para el reabastecimiento del artículo.
- **Por requisito** - El método de medición de lote en el que el sistema crea una compra, una transferencia, o un pedido de producción planificados de acuerdo con el requisito del artículo. Se usa normalmente para los artículos costosos con demanda intermitente.  
- **Por período** - el método de medición de lote que combina toda la demanda durante un período en un pedido del artículo. El pedido se planificará se para el primer día del período y la cantidad satisfará los requisitos netos durante el período establecido. El período comienza con la primera demanda del artículo y cubre la longitud definida de tiempo. El período siguiente comenzará con los siguientes requisitos del artículo.
- **Mín/Máx.** - El método de medición de lote que contiene el reaprovisionamiento de inventario hasta un nivel determinado cuando la entrega prevista está por debajo de un umbral. La cantidad de reabastecimiento será la diferencia entre el nivel máximo y el nivel disponible previsto.


## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los planes maestros](master-plans.md)
