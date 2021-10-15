---
title: Crear relaciones de tareas de servicio
description: Puede asociar tareas de servicio con contratos de servicio o pedidos de servicio para describir la tarea de servicio para completar el contrato o pedido.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b13309816af6984e77f828e827ecffe6266b3ede
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576553"
---
# <a name="create-service-task-relations"></a>Crear relaciones de tareas de servicio    

[!include [banner](../includes/banner.md)]

Puede asociar tareas de servicio con contratos de servicio o pedidos de servicio para describir la tarea de servicio para completar el contrato o pedido. Esta información está disponible para técnicos de servicio y clientes.

## <a name="create-a-relation-with-a-service-agreement"></a>Crear una relación con un acuerdo de servicio

1.  Vaya a **Gestión de servicio** \> **Común** \> **Contratos de servicio** \> **Contratos de servicio**.

2.  Seleccione un acuerdo de servicio existente o cree uno nuevo.

3.  En el panel de acciones, seleccione el botón **Tareas de servicio**.

4.  En el formulario **Tareas de servicio**, seleccione **Nuevo** para crear una nueva línea y, a continuación, seleccione una tarea de servicio desde la lista **Tarea de servicio** para adjuntar la tarea de servicio al acuerdo de servicio.

5.  En los campos de texto sin formato de la ficha **Descripción**, especifique las descripciones de nota interna o externa.

6.  Cierre el formulario para guardar el registro.

Repita este procedimiento hasta haber creado todas las relaciones de tarea de servicio para el acuerdo de servicio. A continuación, podrá especificar estas tareas para cualquiera de las líneas del acuerdo vinculadas.

Una relación de tareas de servicio creada en un acuerdo de servicio estará disponible en todos los pedidos de servicio vinculados al acuerdo de servicio.

## <a name="create-a-relation-with-a-service-order"></a>Crear una relación con un pedido de servicio

1.  Vaya a **Gestión de servicio** \> **Común** \> **Pedidos de servicio** \> **Pedidos de servicio**.

2.  Seleccione un pedido de servicio existente o cree uno nuevo.

3.  En el panel de acciones, seleccione el botón **Tareas de servicio**.

4.  En el formulario **Tareas de servicio**, seleccione **Nuevo** para crear una nueva línea y, a continuación, seleccione una tarea de servicio desde la lista **Tarea de servicio** para adjuntar las tareas de servicio al pedido de servicio.

5.  En los campos de texto sin formato de la ficha **Descripción**, especifique las descripciones de nota interna o externa.

6.  Cierre el formulario para guardar el registro.

Repita este procedimiento hasta haber creado todas las relaciones de tarea de servicio para el acuerdo de servicio. A continuación, podrá seleccionar la tarea de servicio para la que creó la relación al crear las líneas de pedido de servicio.

Las relaciones de tarea de servicio creadas en un pedido de servicio estarán disponibles en el pedido de servicio específico.

## <a name="see-also"></a>Consulte también

[Visión general de las tareas de servicio](service-tasks.md)


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]