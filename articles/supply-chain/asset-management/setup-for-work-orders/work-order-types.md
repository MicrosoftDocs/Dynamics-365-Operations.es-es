---
title: Tipos de orden de trabajo
description: En este tema se explican los tipos de órdenes de trabajo en Administración de activos.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderType
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d89d7c652837e881f7fcb6014fe017eedc2f876c
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6351474"
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

![Tipos de pedido de trabajo.](media/16-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]