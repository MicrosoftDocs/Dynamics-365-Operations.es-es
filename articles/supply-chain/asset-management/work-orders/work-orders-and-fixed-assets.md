---
title: Órdenes de trabajo y activos fijos
description: En este tema se explica cómo crear órdenes de trabajo y activos fijos en Administración de activos.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ad4af6bb0df557314f844d3e7a6c5fb84a6331d86f16e1bc76150f78ce3039e4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752811"
---
# <a name="work-orders-and-fixed-assets"></a>Órdenes de trabajo y activos fijos

[!include [banner](../../includes/banner.md)]


En gestión de activos, los activos se pueden relacionar con los activos fijos, y puede crear órdenes de trabajo para dichos activos. Si utiliza esta funcionalidad, puede obtener una visión general completa de activos fijos, de proyectos de inversión relacionados, y los costes registrados en los proyectos de inversión en los módulos **Gestión de proyectos y contabilidad** y **Activos fijos** en Microsoft Dynamics 365 for Finance and Operations.

>[!NOTE]
>El campo **Número de activo fijo** del proyecto de trabajo de la orden de trabajo solo se establece si la opción **Inversión** está seleccionada como el tipo de proyecto en el proyecto de trabajo de la orden de trabajo.

En la ilustración siguiente se muestra la relación entre un proyecto de inversión en el módulo **Gestión de proyectos y contabilidad** y un proyecto de trabajo de orden de trabajo.

![Figura 1.](media/24-work-orders.png)

El siguiente procedimiento describe la relación entre los activos, órdenes de trabajo, proyectos de trabajo de la orden de trabajo, y activos fijos.

1. Cree un activo que relacione con un activo fijo.

![Figura 2.](media/25-work-orders.png)

2. Al configurar tipos de órdenes de trabajo en la página **Tipos de orden de trabajo** (**Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Tipos de órdenes de trabajo**), cree un tipo de pedido de trabajo para gestionar inversiones. Consulte también [Tipos de orden de trabajo](../setup-for-work-orders/work-order-types.md).

![Figura 3.](media/26-work-orders.png)

3. Al configurar grupos de proyectos de órdenes de trabajo en la pestaña **Grupo de proyectos** de la página **Configuración de proyecto de orden de trabajo** (**Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Configuración de proyecto**), se crea una relación entre el tipo de orden de trabajo que se usa para las inversiones y el grupo de proyectos que se creó para inversiones en la página **Grupos de proyectos** del módulo **Gestión de proyectos y contabilidad** (**Gestión de proyectos y contabilidad** > **Configuración** > **Registro** > **Grupos de proyectos**).

![Figura 4.](media/27-work-orders.png)

4. Al crear una orden de trabajo relacionada con un activo fijo, seleccione el tipo de orden de trabajo que se usa para administrar inversiones, como **Inversión**.

5. Cuando se cree la orden de trabajo, se mostrará el tipo de pedido de trabajo relacionado en la página **Todas las órdenes de trabajo**.

![Figura 5.](media/28-work-orders.png)

6. Cuando se crea la orden de trabajo, se crea el proyecto relacionado con la orden de trabajo en la página **Todos los proyectos** del módulo **Gestión de proyectos y contabilidad** (**Gestión de proyectos y contabilidad** > **Proyectos** > **Todos los proyectos**). Para ver información relacionada con el proyecto, seleccione el vínculo en el campo **Id. de proyecto** de la pestaña **General** de la ficha desplegable **Detalles de línea** de la vista de detalles de la página **Todas las órdenes de trabajo** del módulo **Administración de activos** (**Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo**).

![Figura 6.](media/29-work-orders.png)

7. Para ver una visión general de los proyectos asociados a un activo fijo, seleccione **Activos fijos** > **Activos fijos** > **Activos fijos** y, a continuación, en el campo **Número de activo fijo** , seleccione el vínculo para que el activo fijo abra la vista de detalles. Expanda el panel **Información relacionada** que se encuentra a la derecha de la página y seleccione la ficha desplegable **Proyectos asociados**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]