---
title: Crear requisito del artículo desde el pedido de servicio
description: Si necesita reservar artículos específicos para un pedido de servicio, puede crear requisitos de artículo de inventario para él.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5a730ae945af15c7bd4020c734bac971d8186e2
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "312218"
---
# <a name="create-item-requirements-for-service-orders"></a>Crear requisito del artículo desde el pedido de servicio 

[!include [banner](../includes/banner.md)]


Puede crear un pedido de servicio para administrar y realizar un seguimiento de los servicios que proporciona a sus clientes. Si necesita reservar artículos específicos para un pedido de servicio, puede crear requisitos de artículo de inventario para él. Un requisito de artículo se puede usar inmediatamente del inventario o bien, puede iniciar un pedido de producción para el artículo.

Si usa un requisito de artículo en lugar de una transacción de artículos, podrá planificar la entrega justo antes del uso real del artículo, crear un pedido de compras, incluir el artículo en el marco del acuerdo comercial e incluir el requisito de artículo en la planificación de producción.

Los requisitos de artículo para los pedidos de servicio se procesan a través de un proyecto. Para crear un requisito de artículo en un pedido de servicio, este último debe estar asignado a un proyecto. Tras crear un requisito de artículo para un pedido de servicio, puede ver los requeridos de artículos en el formulario **Proyectos** para el proyecto seleccionado.

## <a name="create-an-item-requirement-for-a-service-order"></a>Crear un requisito de artículo para un pedido de servicio

1.  Haga clic en **Gestión de servicio** \> **Común** \> **Pedidos de servicio** \> **Pedidos de servicio**.

2.  Seleccione el pedido de servicio para el que desea crear un requisito de artículo.

3.  A continuación, en el **panel de acciones**, en la ficha **Distribución**, haga clic en **Requisito de artículo**.

4.  En el formulario **Requisitos de artículos**, especifique la información para el artículo requerido. Para obtener más información acerca de campos específicos, vea [Requisitos de artículos (formulario)](https://technet.microsoft.com/en-us/library/aa552021\(v=ax.60\)).

## <a name="create-an-item-requirement-for-a-service-agreement"></a>Crear un requisito de artículo para un acuerdo de servicio

1.  Haga clic en **Gestión de servicio** \> **Común** \> **Contratos de servicio** \> **Contratos de servicio**.

2.  Abra el acuerdo de servicio para el que desea crear un requisito de artículo.

3.  En la ficha desplegable **Líneas**, haga clic en **Agregar** para crear una línea nueva.

4.  En el campo **Tipo de transacción**, seleccione **Artículo**.

5.  En el campo **Configuración del artículo**, seleccione **Requisito de artículo**.

6.  En el campo **Código de artículo**, seleccione el artículo que se requiere para el acuerdo de servicio.

7.  En la ficha desplegable **Detalles de línea** , en la pestaña **Dimensiones del producto** , en el campo **sitio** , seleccione el sitio del inventario del artículo.

8.  Para crear un pedido de servicio a partir de la línea del acuerdo de servicio, en la ficha desplegable **Líneas**, haga clic en **Crear pedidos de servicio** y especifique la información pertinente en el formulario **Crear pedidos de servicio**. 


## <a name="see-also"></a>Consulte también

[Crear pedidos de servicio automáticamente](create-service-orders-automatically.md).

  


