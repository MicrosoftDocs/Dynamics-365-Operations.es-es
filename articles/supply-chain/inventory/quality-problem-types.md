---
title: Tipos de problemas para disconformidades
description: Este tema describe cómo crear y utilizar tipos de problemas para disconformidades.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventProblemType, InventProblemTypeSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df509365f5c900898921acfbda380b5e20c7a251
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956824"
---
# <a name="problem-types-for-nonconformances"></a>Tipos de problemas para disconformidades

[!include [banner](../includes/banner.md)]

Este tema describe cómo crear y utilizar tipos de problemas para disconformidades.

Use la página **Tipos de problemas** para definir una clasificación de los problemas de calidad que podrían ocurrir en los distintos tipos de disconformidad. Para cada tipo de problema que cree, debe especificar los tipos de disconformidades con las que se puede utilizar el tipo de problema. Puede configurar los siguientes tipos de disconformidad:

- **Interno**: las disconformidades de este tipo están relacionadas con el inventario disponible (por ejemplo, pedidos de calidad o pedidos de cuarentena).
- **Cliente**: las no conformidades de este tipo están relacionadas con pedidos de ventas.
- **Proveedor**: las no conformidades de este tipo están relacionadas con pedidos de compra.
- **Solicitud de servicio**: las no conformidades de este tipo están relacionadas con pedidos de servicio.
- **Producción**: las disconformidades de este tipo están relacionadas con pedidos de lote o pedidos de producción.
- **Producción de coproducto**: las disconformidades de este tipo están relacionadas con pedidos de lote para coproductos.

Cuando cree un nuevo tipo de problema, seleccione **Tipos de disconformidad** en el panel de acciones para crear una lista de uno o más tipos de disconformidad autorizados para el tipo de problema. Por ejemplo, un tipo de problema relacionado con un código defectuoso podría aplicarse a todos los tipos de disconformidad. Sin embargo, un tipo de problema relacionado con las quejas de los clientes puede aplicarse solo a los tipos de disconformidad **Cliente** y **Solicitud de servicio**.

## <a name="examples-of-problem-types"></a>Ejemplos de tipos de problemas

A continuación, se muestran algunos ejemplos de escenarios para tipos de problemas que se pueden utilizar con los diferentes tipos de no conformidad:

- **Cliente:** un cliente presentó una queja, un cliente hizo una devolución o no se cumplieron las especificaciones de calidad.
- **Proveedor:** el producto estaba dañado, no se cumplieron las especificaciones de calidad o se recibió un producto incorrecto.
- **Solicitud de servicio:** no se cumplieron las especificaciones de calidad, un cliente presentó una queja o se requiere mantenimiento de la máquina.
- **Producción:** no se cumplieron las especificaciones de calidad, se requiere mantenimiento de la máquina o el producto estaba dañado.
- **Producción de coproducto:** no se cumplieron las especificaciones de calidad, se requiere mantenimiento de la máquina o el producto estaba dañado.

## <a name="create-a-problem-type-and-assign-it-to-nonconformance-types"></a>Crear un tipo de problema y asignarlo a tipos de disconformidad

1. Vaya a **Gestión del inventario \> Configurar \> Administración de calidad \> Tipos de problemas**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Tipo de problema**: introduzca un id. o nombre único para el tipo de problema.
    - **Descripción**: escriba una descripción detallada del tipo de problema.

1. Mientras la nueva fila aún está seleccionada, seleccione **Tipos de no conformidad** en el panel de acciones.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Luego, para la nueva fila, establezca el campo **Tipo de disconformidad** en el tipo de disconformidad que desea permitir para el tipo de problema.
1. Repita el paso anterior para cada tipo de disconformidad adicional que desee autorizar para el tipo de problema.
1. Cierre las páginas.

## <a name="additional-resources"></a>Recursos adicionales

- [Información general de la administración de la calidad](quality-management-processes.md)
- [Habilitar la gestión de la calidad y las no conformidades](enable-quality-management.md)
- [Trabajadores responsables de aprobar no conformidades](quality-responsible-workers.md)
- [Zonas de cuarentena para disconformidades](quality-quarantine-zones.md)
- [Tipos de diagnóstico de disconformidades](quality-diagnostic-types.md)
- [Cargos de calidad para disconformidades](quality-charges.md)
- [Operaciones para disconformidades](quality-operations.md)
- [Administración de la calidad para procesos de almacén](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
