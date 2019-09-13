---
title: Configurar trabajadores de mantenimiento preferidos
description: En este tema se explica cómo configurar trabajadores de mantenimiento preferidos en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f26be81e7057d0cea1473d81452216251633ad9
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887420"
---
# <a name="preferred-maintenance-workers"></a>Trabajadores de mantenimiento preferidos

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Puede crear una preferencia en cuanto a qué trabajadores de mantenimiento se asignan para completar órdenes de trabajo durante la programación de órdenes de trabajo. El uso de esta función es opcional, pero puede ayudarle a elegir al trabajador de mantenimiento más cualificado para que complete un trabajo en función de las aptitudes y competencias del trabajador. Por lo tanto, durante la programación de una orden de trabajo, la configuración en **Trabajadores de mantenimiento preferidos** se utiliza para determinar si debe programarse un determinado trabajador o grupo de trabajadores de mantenimiento para una orden de trabajo. Solo se programarán trabajadores de mantenimiento que estén disponibles en el momento de la programación. Si una configuración de trabajador de mantenimiento preferido coincide con una orden de trabajo durante la programación, pero el trabajador de mantenimiento está asignado a otros trabajos, la orden de trabajo se programará a otro trabajado de mantenimiento, en caso de que esté disponible.

Para poder configurar trabajadores de mantenimiento preferidos, primero debe configurar los trabajadores y grupos de trabajadores de mantenimiento que deben estar disponibles para la selección. Consulte [Trabajadores y grupos de trabajadores de mantenimiento](../setup-for-objects/workers-and-worker-groups.md) para ver una descripción acerca de cómo configurar trabajadores y grupos de trabajadores de mantenimiento.

## <a name="set-up-preferred-workers"></a>Configurar trabajadores preferidos

Un trabajador o un grupo de trabajadores de mantenimiento preferido puede estar relacionado con un determinado

- comercio  
- variante de tipo de trabajo de mantenimiento  
- tipo de trabajo de mantenimiento  
- categoría de tipo de trabajo de mantenimiento  
- activo  
- tipo de activo  

o una combinación de dichas selecciones. Cuantas más selecciones haga para el mismo registro, más específica será la configuración.

1. Haga clic en **Administración de activos** > **Configuración** > **Trabajadores** > **Trabajadores de mantenimiento preferidos**.

2. Haga clic en **Nuevo** para crear un nuevo registro.

3. Empiece por crear un trabajador de mantenimiento "predeterminado" o una configuración de un grupo de trabajadores que no tenga selecciones en los campos que se muestran en la lista de viñetas de abajo. Esto significa que solo crea una selección en el campo **Grupo de trabajadores de mantenimiento preferido** o en el campo **Trabajador de mantenimiento preferido**. En la siguiente ilustración, verá un ejemplo en el primer registro en el que se selecciona "Solicitudes" como grupo de trabajadores de mantenimiento preferido.

>[!NOTE]
>La configuración predeterminada se usará durante la programación de la orden de trabajo en caso de que no haya ninguna otra combinación más específica que coincida con el contenido de la orden de trabajo durante la programación de la orden de trabajo.

4. Repita el paso 2 para crear un nuevo registro. Haga las selecciones necesarias en función del nivel de detalle del trabajador o grupo de trabajadores preferido. *Ejemplo:* en la ilustración siguiente, en el sexto registro, el trabajador de mantenimiento Shawn Richardson es seleccionado como trabajador preferido. Será seleccionado automáticamente durante la programación de una orden de trabajo que incluya el activo "CH-BP1-03-02" y el tipo de trabajo de mantenimiento "Evaluación de la instalación", si este está disponible a la hora programada.

>[!NOTE]
>Por lo general, cuando se selecciona un trabajador de mantenimiento preferido durante la programación de una orden de trabajo, la Administración de activos pasa por todos los registros **Trabajadores de mantenimiento preferidos** para comprobar si existe una coincidencia posible, comprobando siempre en primer lugar la combinación más específica. Si no se encuentra ninguna coincidencia, se utiliza el registro "predeterminado" con una selección en el campo **Grupo de trabajadores de mantenimiento preferido** o en el campo **Trabajador de mantenimiento preferido**.


![Figura 1](media/02-work-order-scheduling.png)

También puede configurar los trabajadores responsables del mantenimiento que se pueden seleccionar cuando se crea una solicitud de mantenimiento o una orden de trabajo. Si es necesario, puede editar la selección en **Todas las órdenes de trabajo** y **Todas las solicitudes de mantenimiento**. Consulte [Trabajadores responsables del mantenimiento](../setup-for-maintenance-requests/responsible-workers.md) para obtener más información.

Durante la programación de órdenes de trabajo, se calculan distintas puntuaciones para determinar qué trabajadores deben completar los trabajos relacionados con una orden de trabajo (esas puntuaciones se configuran en el vínculo **Parámetros de administración de activos** > **Programación de órdenes de trabajo**). Si dos o más trabajadores de mantenimiento preferidos o trabajadores responsables del mantenimiento obtienen la misma puntuación durante la programación de órdenes de trabajo, se selecciona a un trabajador al azar. De lo contrario, se asignará siempre al trabajador con la puntuación más alta para que complete una orden de trabajo.

