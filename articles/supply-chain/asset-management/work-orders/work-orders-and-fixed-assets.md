---
title: Órdenes de trabajo y activos fijos
description: En este tema se explica cómo crear órdenes de trabajo y activos fijos en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f03b7fa073c4e5338b7b5681ba7b8c9fe00a657b
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875876"
---
# <a name="work-orders-and-fixed-assets"></a>Órdenes de trabajo y activos fijos


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


En gestión de activos, los activos se pueden relacionar con los activos fijos, y puede crear órdenes de trabajo para dichos activos. Si utiliza esta funcionalidad, puede obtener una visión general completa de activos fijos, de proyectos de inversión relacionados, y los costes registrados en los proyectos de inversión en el módulo **Gestión de proyectos y contabilidad** y el módulo **Activos fijos** en Dynamics 365 for Finance and Operations.

>[!NOTE]
>El campo **Número de activo fijo** solo se completa en el proyecto de trabajo de la orden de trabajo si se selecciona el tipo “inversión” como tipo de proyecto en el proyecto de trabajo de la orden de trabajo.

![Figura 1](media/24-work-orders.png)

El siguiente procedimiento describe la relación entre los activos, órdenes de trabajo, proyectos de trabajo de la orden de trabajo, y activos fijos.

1. Se crea un activo que se relaciona con un activo fijo, tal y como se muestra en la siguiente ilustración.

![Figura 2](media/25-work-orders.png)

2. Al establecer tipos de pedido de trabajo (**Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Tipos de órdenes de trabajo**), cree un tipo de pedido de trabajo para gestionar inversiones. Consulte también [Tipos de orden de trabajo](../setup-for-work-orders/work-order-types.md).

![Figura 3](media/26-work-orders.png)

3. Al configurar grupos de proyectos de órdenes de trabajo (vínculo **Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Configuración de proyecto** > **Grupo de proyectos**), se crea una relación entre el tipo de pedido del trabajo usado para las inversiones y el grupo de proyectos creado para inversiones en el módulo **Gestión de proyectos y contabilidad** (**Gestión de proyectos y contabilidad** > **Configuración** > **Registro** > **Grupos de proyectos**).

![Figura 4](media/27-work-orders.png)

4. Al crear un pedido de trabajo relacionado con un objeto del activo fijo, seleccione el tipo de pedido del trabajo empleado para administrar inversiones, por ejemplo, “inversión”.

5. Cuando se crea la orden de trabajo, se mostrará el tipo de pedido de trabajo relacionado en **Todas las órdenes de trabajo**.

![Figura 5](media/28-work-orders.png)

6. Cuando se crea la orden de trabajo, el proyecto relacionado con al pedido de trabajo se crea en **Gestión de proyectos y contabilidad** > **Todos los proyectos**. Puede ver información relacionada con el proyecto haciendo clic en el vínculo **Id. de proyecto** en la orden de trabajo (en **Administración de activos**, abra la orden de trabajo en la vista Detalles > ficha desplegable **Detalles de línea** > pestaña **General** > campo **Identificador del proyecto**).

![Figura 6](media/29-work-orders.png)

7. En **Activos fijos**, podrá obtener una visión general de los proyectos asociados a un activo fijo (**Activos fijos** > **Activos fijos** > **Activos fijos** > hacer clic en el activo fijo en el campo **Número de activo fijo** > la vista de los contenidos en el panel **Información relacionada** > la sección **Proyectos asociados**).

