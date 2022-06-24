---
title: Crear y procesar disconformidades
description: Este artículo describe cómo gestionar los casos de disconformidad, en función de un pedido de calidad existente.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd8a10e88ab4d1be24a11739dddd7619b3fa6bbc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901977"
---
# <a name="create-and-process-nonconformances"></a>Crear y procesar disconformidades

[!include [banner](../../includes/banner.md)]

Este artículo describe cómo gestionar los casos de disconformidad, en función de un pedido de calidad existente. Por lo general, la gestión de disconformidades la realiza un empleado de calidad. Como requisito previo, debe tener disponible un pedido de calidad. (Para obtener información sobre cómo crear un pedido de calidad, consulte [Inspeccionar la calidad de los productos](inspect-quality-goods.md)).

Antes de que un usuario pueda procesar la aprobación de una disconformidad, se le debe asignar un trabajador en el campo **Persona** de la página **Usuarios**. Además, antes de que el usuario pueda utilizar las notas del documento, la opción **Habilitar el manejo de documentos** debe establecerse en *Sí* en sus opciones de usuario.

## <a name="create-a-nonconformance"></a>Creación de una disconformidad

Para crear una disconformidad, siga estos pasos.

1. Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Disconformidades**.
1. En el panel de acciones, seleccione **Nueva**.
1. En el cuadro de diálogo **Crear disconformidad**, en el campo **Tipo de problema**, seleccione el tipo de problema que se encontró durante el proceso de inspección.
1. Seleccione **Aceptar**.

## <a name="approve-or-reject-a-nonconformance"></a>Aprobación o rechazo de una disconformidad

Para aprobar o rechazar una disconformidad, siga estos pasos.

1. Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Disconformidades**.
1. En la lista, seleccione la disconformidad que desee actualizar.

    > [!NOTE]
    > Puede agregar una corrección solo a las disconformidades aprobadas.

1. En el panel de acciones, seleccione **Funciones \> Aprobar disconformidad** para aprobar la disconformidad o **Funciones \> Rechazar la disconformidad** para rechazarla. Puede asociar disconformidades aprobadas con [operaciones relacionadas](../quality-operations.md). De esta manera, puede registrar el trabajo que se realiza como parte del manejo de disconformidades y el procesamiento del manejo de correcciones.
1. Se le pedirá que confirme su selección. Seleccione **Sí** para continuar.

## <a name="add-operations-and-other-details-to-nonconformances"></a>Agregar operaciones y otros detalles a las disconformidades

Una vez que haya creado una disconformidad, puede comenzar a agregar operaciones relacionadas y especificar información adicional sobre esas operaciones. Puede agregar operaciones relacionadas solo a las disconformidades aprobadas.

Además de la información básica, puede agregar los siguientes detalles a una operación:

- **Artículos**: puede crear una lista de elementos que se consumen para realizar la corrección. Por ejemplo, los artículos pueden ser productos necesarios para reparar equipos o ingredientes necesarios para reelaborar un producto terminado.
- **Cargos por calidad**: puede crear una lista de cargos incurridos o facturados a fuentes externas.
- **Hoja de tiempos**: puede crear un registro del tiempo que cada trabajador dedica a la operación.

Las opciones restantes son opcionales. El coste de cada artículo, los cargos por calidad y la hoja de tiempos se suman y se muestran en la operación. No puede editar directamente el campo **Coste** en la operación.

### <a name="create-an-operation-for-a-nonconformance"></a>Crear una operación para una disconformidad

Para crear una operación para una disconformidad, siga estos pasos.

1. Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Disconformidades**.
1. En la lista, seleccione la disconformidad que desee actualizar.

    > [!NOTE]
    > Puede agregar o actualizar operaciones solo para disconformidades aprobadas.

1. En el panel acciones, seleccione **Operaciones relacionadas**.
1. En la página **Operaciones relacionadas**, en el panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Operación**: seleccione el código de la operación que se realizará por la disconformidad.
    - **Razón**: introduzca una descripción detallada que explique por qué se requiere la operación.
    - **Pedido de ventas**: si el código de operación seleccionado está relacionado con el tipo de pedido de ventas, seleccione el pedido de ventas al que está vinculando la operación.
    - **Pedido de compra**: si el código de operación seleccionado está relacionado con el tipo de pedido de compra, seleccione el pedido de compra al que está vinculando la operación.

1. Cierre las páginas.

### <a name="add-items-to-an-operation"></a>Agregar artículos a una operación

Para agregar elementos a una operación, siga estos pasos.

1. Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Disconformidades**.
1. En la lista, seleccione la disconformidad que desee actualizar.

    > [!NOTE]
    > Puede agregar o actualizar operaciones solo para disconformidades aprobadas.

1. En el panel acciones, seleccione **Operaciones relacionadas**.
1. En la página **Operaciones rellacionadas**, seleccione la operación a la que desea agregar artículos.
1. En el panel de acciones, haga clic en **Artículos**.
1. En la página **Operaciones relacionadas**, en el panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Número de artículo**: seleccione el producto que se consumirá como parte de la operación seleccionada.
    - **Cantidad**: introduzca la cantidad de artículos que se consumirán.

    > [!NOTE]
    > Puede ver el coste del artículo en el campo **Coste** de la pestaña **General**. El coste que se muestra allí proviene del coste que se establece en la página **Producto liberado**. El coste no se puede actualizar directamente en la página **Artículo de operación relacionado**. El coste de todos los elementos que se agregan en la página **Artículos de operación relacionados** se agrega automáticamente al campo **Coste** en la página **Operaciones relacionadas**.

1. Repita el paso anterior para cada elemento adicional que deba agregar.
1. Cierre las páginas.

### <a name="add-quality-charges-to-an-operation"></a>Agregar cargos de calidad a una operación

Para agregar cargos de calidad a una operación, siga estos pasos.

1. Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Disconformidades**.
1. En la lista, seleccione la disconformidad que desee actualizar.

    > [!NOTE]
    > Puede agregar o actualizar operaciones solo para disconformidades aprobadas.

1. En el panel acciones, seleccione **Operaciones relacionadas**.
1. En la página **Operaciones rellacionadas**, seleccione la operación a la que desea agregar cargos de calidad.
1. En el panel acciones, seleccione **Cargos de calidad**.
1. En la página **Cargos de operaciones relacionadas**, en el panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Código de cargos**: seleccione el cargo de calidad que desea agregar.
    - **Descripción**: escriba una descripción detallada del cargo.
    - **Valor de cargos**: especifique el importe del cargo.

1. Repita el paso anterior para cada cargo adicional que deba agregar.
1. Cierre las páginas.

> [!NOTE]
> La cantidad en el campo **Valor de los cargos** se suma automáticamente para todos los cargos de calidad y se agrega a cualquier otra cantidad en el campo **Coste** de la página **Operaciones relacionadas**.

### <a name="create-a-timesheet-on-an-operation"></a>Crear una hoja de tiempo en una operación

Para agregar una hoja de tiempo a una operación, siga estos pasos.

1. Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Disconformidades**.
1. En la lista, seleccione la disconformidad que desee actualizar.

    > [!NOTE]
    > Puede agregar o actualizar operaciones solo para disconformidades aprobadas.

1. En el panel acciones, seleccione **Operaciones relacionadas**.
1. En la página **Operaciones rellacionadas**, seleccione la operación a la que desea agregar una hoja de tiempo.
1. En el panel de acciones, seleccione **Hoja de tiempo**.
1. En la página **Hojas de tiempo de operaciones relacionadas**, en el panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Fecha**: especifique la fecha en que se realizó el trabajo. De forma predeterminada, este campo es la fecha actual.
    - **Trabajador**: seleccione el trabajador que realizó el trabajo. De forma predeterminada, este campo está configurado para el trabajador que está asignado al usuario actual.
    - **Horas de operación**: introduzca el número de horas que se trabajaron en la operación seleccionada.
    - **Facturado**: seleccione esta casilla de verificación si el tiempo se ha cargado a un cliente o proveedor en una factura.

    > [!NOTE]
    > Puede ver el coste en el campo **Coste** de la pestaña **General**. El coste se calcula utilizando la tarifa que defina en la página **Parámetros de gestión de inventario**.

1. Repita el paso anterior para cada línea de hoja de tiempo adicional que deba agregar.
1. Cierre las páginas.

> [!NOTE]
> La cantidad del campo **Coste** se suma automáticamente para todas las líneas de hoja de tiempo y se agrega a cualquier otra cantidad en el campo **Coste** de la página **Operaciones relacionadas**.

## <a name="add-a-correction-to-a-nonconformance"></a>Agregar una corrección a una disconformidad

Para agregar una corrección a una disconformidad, siga estos pasos.

1. Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Disconformidades**.
1. En la lista, seleccione la disconformidad que desee actualizar.

    > [!NOTE]
    > Puede agregar una corrección solo a las disconformidades aprobadas.

1. En el panel de acciones, seleccione **Correcciones**.
1. En la página **Correcciones**, en el panel de acciones, seleccione **Nueva** para agregar una fila a la cuadrícula. Entonces establezca los siguientes campos para la fila nueva:

    - **Diagnóstico**: seleccione el tipo de diagnóstico que identifica el tipo de corrección que está creando.
    - **Trabajador**: seleccione la persona responsable de la corrección.
    - **Prioridad de corrección**: seleccione una opción para indicar cómo se debe priorizar la corrección (*Baja*, *Normal* o *Elevada*).
    - **Fecha solicitada**: introduzca la fecha en la que se solicitó la acción correctiva.
    - **Cita planeada**: introduzca la fecha en la que se espera que se complete la corrección.
    - **Solución a corto plazo**: seleccione esta casilla si la acción correctiva corrige la disconformidad solo por un período breve.

1. Cierre las páginas.

## <a name="mark-a-correction-as-completed"></a>Marcar una corrección como completada

Para marcar una corrección a una disconformidad como completada, siga estos pasos.

1. Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Disconformidades**.
1. En la lista, seleccione la disconformidad que desee actualizar.

    > [!NOTE]
    > Puede agregar una corrección solo a las disconformidades aprobadas.

1. En el panel de acciones, seleccione **Correcciones**.
1. En la página **Correcciones**, en la cuadrícula, seleccione la corrección que desea marcar como completada.
1. En el panel de acciones, seleccione **Marcar como completada**.
1. Se le pedirá que confirme su selección. Seleccione **Aceptar** para continuar. El campo **Fecha y hora de finalización** se establece en la fecha y hora actuales, y se selecciona la casilla **Completado**.
1. Cierre la página.

## <a name="reopen-a-completed-correction"></a>Reabrir una corrección completada

Para reabrir una corrección completada, siga estos pasos.

1. Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Disconformidades**.
1. En la lista, seleccione la disconformidad que desee actualizar.
1. En el panel de acciones, seleccione **Correcciones**.
1. En la página **Correcciones**, en la cuadrícula, seleccione la corrección que desea reabrir.
1. En el panel de acciones, haga clic en **Reabrir**.
1. Se le pedirá que confirme su selección. Seleccione **Aceptar** para continuar. El valor se borra del campo **Fecha y hora de finalización** y se desmarca la casilla **Completado**.
1. Cierre la página.

Ahora puede realizar modificaciones o actualizaciones adicionales a la corrección. Cuando haya terminado, puede volver a marcar la corrección como completada.

## <a name="close-a-nonconformance"></a>Cierre de una disconformidad

Para cerrar una disconformidad, siga estos pasos.

1. Vaya a **Gestión del inventario \> Tareas periódicas \> Administración de calidad \> Pedidos de calidad**.
1. Seleccione un pedido de calidad en la cuadrícula.
1. En el panel de acciones, seleccione **Consultas \> Disconformidades**.
1. En la página **Disconformidades**, seleccione la disconformidad del objetivo en la cuadrícula.
1. En el panel de acciones, seleccione **Funciones \> Cerrar disconformidad**.
1. Se le pedirá que confirme su selección. Seleccione **Sí** para continuar.
1. Cierre las páginas.

## <a name="additional-resources"></a>Recursos adicionales

- [Información general de la administración de la calidad](../quality-management-processes.md)
- [Habilitar la gestión de la calidad y las disconformidades](../enable-quality-management.md)
- [Trabajadores responsables de aprobar disconformidades](../quality-responsible-workers.md)
- [Zonas de cuarentena para disconformidades](../quality-quarantine-zones.md)
- [Tipos de diagnóstico de disconformidades](../quality-diagnostic-types.md)
- [Cargos de calidad para disconformidades](../quality-charges.md)
- [Operaciones para disconformidades](../quality-operations.md)
- [Administración de la calidad para procesos de almacén](../quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
