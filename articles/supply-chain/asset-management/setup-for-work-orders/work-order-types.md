---
title: Tipos de orden de trabajo
description: En este tema se explican los tipos de órdenes de trabajo en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderType
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b8e43908e3f13c9e4fd6fab6f1e17a171866b803
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436957"
---
# <a name="work-order-types"></a>Tipos de orden de trabajo

[!include [banner](../../includes/banner.md)]

 

Los tipos de pedido de trabajo se usan para clasificar órdenes de trabajo. Por ejemplo, puede que tenga órdenes de trabajo relacionadas con el mantenimiento preventivo o el mantenimiento correctivo.

Un tipo de pedido de trabajo define una afiliación a un modelo del ciclo de vida de pedido de trabajo. Un modelo del ciclo de vida de la orden de trabajo define los estados del ciclo de vida de la orden de trabajo que se pueden configurar en un pedido de trabajo. (Ejemplos de estados de ciclo de vida de vida de orden de trabajo son **Creado**, **En proceso** y **Finalizado**).

Para obtener más información sobre estados y etapas de proyecto del ciclo de vida de la orden de trabajo, consulte [Estados del ciclo de vida de la orden de trabajo](work-order-lifecycle-states.md).

1. Seleccione **Administración de activos** \> **Configuración** \> **Órdenes de trabajo** \> **Tipos de órdenes de trabajo**.
2. Seleccione **Nuevo** para crear un tipo de orden de trabajo.
3. En el campo **Tipo de orden de trabajo**, especifique un identificador para el tipo de orden de trabajo.
4. Escriba un nombre en el campo **Nombre**.
5. En el campo **Modelo de ciclo de vida de orden de trabajo**, seleccione un modelo del ciclo de vida.
5. Establezca la opción **Un trabajador de mantenimiento** en **Sí** si todos los trabajos de pedido de trabajo relacionados con un pedido de trabajo de este tipo tienen que programarse con el mismo trabajador mantenimiento.
6. En el campo **Tipo de coste**, seleccione **Correctivo**, **Preventivo**, o **Inversión**, según corresponda. Todos los trabajos de un pedido de trabajo deben tener el mismo tipo de coste.
7. En la sección **Obligatorio**, establezca las opciones relevantes en **Sí** para especificar qué información de tiempo de inactividad o de error se agrega a un pedido de trabajo de este tipo.

    > [!NOTE]
    > Las opciones de la sección **Obligatorio** están relacionadas con las opciones de la ficha desplegable **Validar** de la página **Estado del ciclo de vida de la orden de trabajo** (**Administración de activos** \> **Configuración** \> **Órdenes de trabajo** \> **Estados del ciclo de vida**).

8. Seleccione **Guardar**.

![Tipos de orden de trabajo](media/16-setup-for-work-orders.png)
