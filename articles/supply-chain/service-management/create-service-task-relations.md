---
title: Crear relaciones de tareas de servicio
description: Puede asociar tareas de servicio con contratos de servicio o pedidos de servicio para describir la tarea de servicio para completar el contrato o pedido.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e50b4322c65097ab4f8aba9c36e4d5e6cc4c01b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436976"
---
# <a name="create-service-task-relations"></a>Crear relaciones de tareas de servicio    

[!include [banner](../includes/banner.md)]

Puede asociar tareas de servicio con contratos de servicio o pedidos de servicio para describir la tarea de servicio para completar el contrato o pedido. Esta información está disponible para técnicos de servicio y clientes.

## <a name="create-a-relation-with-a-service-agreement"></a>Crear una relación con un acuerdo de servicio

1.  Haga clic en **Gestión de servicio** \> **Común** \> **Contratos de servicio** \> **Contratos de servicio**.

2.  Seleccione un acuerdo de servicio existente o cree uno nuevo.

3.  En el panel de acciones, haga clic en el botón **Tareas de servicio**.

4.  En el formulario **Tareas de servicio**, pulse CTRL+N para crear una nueva línea y, a continuación, seleccione una tarea de servicio desde la lista **Tarea de servicio** para adjuntar la tarea de servicio al acuerdo de servicio.

5.  En los campos de texto sin formato de la ficha **Descripción**, especifique las descripciones de nota interna o externa.

6.  Cierre el formulario para guardar el registro.

Repita este procedimiento hasta haber creado todas las relaciones de tarea de servicio para el acuerdo de servicio. A continuación, podrá especificar estas tareas para cualquiera de las líneas del acuerdo vinculadas.

Una relación de tareas de servicio creada en un acuerdo de servicio estará disponible en todos los pedidos de servicio vinculados al acuerdo de servicio.

## <a name="create-a-relation-with-a-service-order"></a>Crear una relación con un pedido de servicio

1.  Haga clic en **Gestión de servicio** \> **Común** \> **Pedidos de servicio** \> **Pedidos de servicio**.

2.  Seleccione un pedido de servicio existente o cree uno nuevo.

3.  En el panel de acciones, haga clic en el botón **Tareas de servicio**.

4.  En el formulario **Tareas de servicio**, pulse CTRL+N para crear una nueva línea y, a continuación, seleccione una tarea de servicio desde la lista **Tarea de servicio** para adjuntar las tareas de servicio al pedido de servicio.

5.  En los campos de texto sin formato de la ficha **Descripción**, especifique las descripciones de nota interna o externa.

6.  Cierre el formulario para guardar el registro.

Repita este procedimiento hasta haber creado todas las relaciones de tarea de servicio para el acuerdo de servicio. A continuación, podrá seleccionar la tarea de servicio para la que creó la relación al crear las líneas de pedido de servicio.

Las relaciones de tarea de servicio creadas en un pedido de servicio estarán disponibles en el pedido de servicio específico.

## <a name="see-also"></a>Consulte también

[Visión general de las tareas de servicio](service-tasks.md)


  


