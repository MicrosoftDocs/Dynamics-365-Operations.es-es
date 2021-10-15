---
title: Grupos de administración de devoluciones
description: Este tema describe cómo configurar grupos de administración de devoluciones. Los grupos de administración de devoluciones se pueden utilizar durante los cálculos de descuentos y se pueden adjuntar a un registro maestro.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1f9deeedef504d1b2d0ba3431902c50bc65d62ba
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572706"
---
# <a name="rebate-management-groups"></a>Grupos de gestión de devoluciones

[!include [banner](../includes/banner.md)]

Los cálculos de administración de devoluciones pueden realizarse por grupos. Se pueden crear grupos de administración de devoluciones para clientes, proveedores y artículos. Se pueden adjuntar a un registro maestro.

## <a name="rebate-management-customer-groups"></a>Grupos de administración de devoluciones de cliente

El cálculo para un grupo de clientes a menudo se crea para una cadena de empresas, como una cadena de supermercados o una empresa de franquicia. Este tipo de cálculo suele estar relacionado con una devolución.

A menudo, una deducción se calcula sin tener en cuenta a quién se vendió el pedido calificado. Sin embargo, hay excepciones. Por ejemplo, un licenciatario puede crear un esquema de deducción en el que el grupo de clientes A recibirá el 4 por ciento, pero el grupo de clientes B recibirá solo el 3 por ciento.

### <a name="set-up-customer-groups"></a>Configurar grupos de clientes

Para trabajar con grupos de clientes de gestión de devoluciones , vaya a **Gestión de devoluciones \> Configuración de grupos de administración de devoluciones \> Grupos de clientes**. Puede utilizar los botones del Panel de acciones para agregar y quitar grupos según sea necesario. Para cada grupo, establezca los siguientes campos:

- **Grupo de administración de devoluciones**: especifique un nombre único para el grupo.
- **Descripción**: introduzca una descripción del grupo para proporcionar más información sobre cómo debe usarse.

### <a name="manage-customer-group-assignments"></a>Gestionar asignaciones de grupos de clientes

Cada cliente puede pertenecer a cualquier número de grupos de administración de devoluciones. Para ver y asignar miembros a un grupo, puede comenzar desde la lista de grupos o desde la lista de clientes.

Para ver, agregar o eliminar clientes de un grupo seleccionado, siga estos pasos.

1. Vaya a **Gestión de devoluciones \> Configuración de grupos de administración de devoluciones \> Grupos de clientes**.
1. Seleccione el grupo para administrar.
1. En el panel Acciones, seleccione **Clientes**. Aparece la página **Grupos de administración de devoluciones** y muestra una lista de clientes que ya son miembros del grupo seleccionado.
1. Para agregar un cliente nuevo al grupo, seleccione **Nuevo** en el panel de acciones para añadir una fila a la cuadrícula. Entonces establezca el siguiente campo para la fila nueva:

    - **Cuenta de cliente**: seleccione el identificador de la cuenta de cliente.

1. Para eliminar un cliente del grupo, seleccione el cliente y luego seleccione **Borrar** en el Panel de acciones.

Para ver, agregar o eliminar asignaciones de grupo de un cliente seleccionado, siga estos pasos.

1. Vaya a **Clientes \> Clientes \> Todos los clientes**.
1. Seleccione el cliente con el que trabajar.
1. En el panel de acciones, en la pestaña **Cliente**, en el grupo **Administración de devoluciones**, seleccione **Grupos de administración de devoluciones**. Aparece la página **Grupos de administración de devoluciones** y muestra una lista de grupos a los que ya pertenece el cliente seleccionado.
1. Para agregar el cliente a un grupo nuevo, seleccione **Nuevo** en el panel de acciones para añadir una fila a la cuadrícula. Entonces establezca el siguiente campo para la fila nueva:

    - **Grupo de gestión de devoluciones**: seleccione el grupo al que agregar el cliente.

1. Para eliminar un cliente de un grupo, seleccione el grupo y luego seleccione **Borrar** en el Panel de acciones.

## <a name="rebate-management-vendor-groups"></a>Grupos de administración de devoluciones de proveedor

El cálculo para un grupo de proveedores a menudo se crea para un grupo de puntos de entrega. Este tipo de cálculo suele estar relacionado con una devolución.

### <a name="set-up-vendor-groups"></a>Configuración de grupos de proveedor

Para trabajar con grupos de proveedores de gestión de devoluciones , vaya a **Gestión de devoluciones \> Configuración de grupos de administración de devoluciones \> Grupos de proveedores**. Puede utilizar los botones del Panel de acciones para agregar y quitar grupos según sea necesario. Para cada grupo, establezca los siguientes campos:

- **Grupo de administración de devoluciones**: especifique un nombre único para el grupo.
- **Descripción**: introduzca una descripción del grupo para proporcionar más información sobre cómo debe usarse.

### <a name="manage-vendor-group-assignments"></a>Gestionar asignaciones de grupos de proveedores

Cada proveedor puede pertenecer a cualquier número de grupos de administración de devoluciones. Para ver y asignar miembros a un grupo, puede comenzar desde la lista de grupos o desde la lista de proveedores.

Para ver, agregar o eliminar proveedores de un grupo seleccionado, siga estos pasos.

1. Vaya a **Gestión de devoluciones \> Configuración de grupos de administración de devoluciones \> Grupos de proveedores**.
1. Seleccione el grupo para administrar.
1. En el panel de acciones, seleccione **Proveedores**. Aparece la página **Grupos de administración de devoluciones** y muestra una lista de proveedores que ya son miembros del grupo seleccionado.
1. Para agregar el proveedor a un grupo, seleccione **Nuevo** en el panel de acciones para añadir una fila a la cuadrícula. Entonces establezca el siguiente campo para la fila nueva:

    - **Cuenta de proveedor**: seleccione el identificador de la cuenta de proveedor.

1. Para eliminar un proveedor del grupo, seleccione el proveedor y luego seleccione **Borrar** en el Panel de acciones.

Para ver, agregar o eliminar asignaciones de grupo de un proveedor seleccionado, siga estos pasos.

1. Vaya a **Proveedores \> Proveedores \> Todos los proveedores**.
1. Seleccione el proveedor con el que trabajar.
1. En el panel de acciones, en la pestaña **Proveedor**, en el grupo **Administración de devoluciones**, seleccione **Grupos de administración de devoluciones**. Aparece la página **Grupos de administración de devoluciones** y muestra una lista de grupos a los que ya pertenece el proveedor seleccionado.
1. Para agregar el proveedor a un grupo nuevo, seleccione **Nuevo** en el panel de acciones para añadir una fila a la cuadrícula. Entonces establezca el siguiente campo para la fila nueva:

    - **Grupo de gestión de devoluciones**: seleccione el grupo al que agregar el proveedor.

1. Para eliminar un proveedor de un grupo, seleccione el grupo y luego seleccione **Borrar** en el Panel de acciones.

## <a name="item-rebate-groups"></a>Grupos de devoluciones de artículos

Al agrupar artículos, tiene más flexibilidad cuando se calculan los reembolsos y las deducciones. Este enfoque suele ser una forma más eficaz de configurar devoluciones y deducciones para clientes y proveedores.

### <a name="set-up-item-groups"></a>Configurar grupos de artículos

Para trabajar con grupos de artículos de gestión de devoluciones , vaya a **Gestión de devoluciones \> Configuración de grupos de administración de devoluciones \> Grupos de artículos**. Puede utilizar los botones del Panel de acciones para agregar y quitar grupos según sea necesario. Para cada grupo, establezca los siguientes campos:

- **Grupo de administración de devoluciones**: especifique un nombre único para el grupo.
- **Descripción**: introduzca una descripción del grupo para proporcionar más información sobre cómo debe usarse.

### <a name="manage-item-group-assignments"></a>Gestionar asignaciones de grupos de artículos

Cada artículo puede pertenecer a cualquier número de grupos de administración de devoluciones. Para ver y asignar miembros a un grupo, puede comenzar desde la lista de grupos o desde la lista de artículos. También puede agregar elementos según la jerarquía de su categoría.

Para ver, agregar o eliminar artículos de un grupo seleccionado, siga estos pasos.

1. Vaya a **Gestión de devoluciones \> Configuración de grupos de administración de devoluciones \> Grupos de artículos**.
1. Seleccione el grupo para administrar.
1. En el panel de acciones, haga clic en **Artículos**. Aparece la página **Grupos de administración de devoluciones** y muestra una lista de artículos que ya son miembros del grupo seleccionado.
1. Para agregar el artículos al grupo, seleccione **Nuevo** en el panel de acciones para añadir una fila a la cuadrícula. Entonces establezca el siguiente campo para la fila nueva:

    - **Cuenta de artículo**: seleccione el identificador de la cuenta de artículo.

1. Para eliminar un artículo del grupo, seleccione el artículo y luego seleccione **Borrar** en el Panel de acciones.

Para ver, agregar o eliminar asignaciones de grupo de un artículo seleccionado, siga estos pasos.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Seleccione el artículo con el que trabajar.
1. En el panel de acciones, en la pestaña **Producto**, en el grupo **Administración de devoluciones**, seleccione **Grupos de administración de devoluciones**. Aparece la página **Grupos de administración de devoluciones** y muestra una lista de grupos a los que ya pertenece el artículo seleccionado.
1. Para agregar el artículo a un grupo nuevo, seleccione **Nuevo** en el panel de acciones para añadir una fila a la cuadrícula. Entonces establezca el siguiente campo para la fila nueva:

    - **Grupo de gestión de devoluciones**: seleccione el grupo al que agregar el artículo.

1. Para eliminar un artículo de un grupo, seleccione el grupo y luego seleccione **Borrar** en el Panel de acciones.

Para agregar elementos a un grupo según la jerarquía de su categoría, siga estos pasos.

1. Vaya a **Gestión de devoluciones \> Configuración de grupos de administración de devoluciones \> Grupos de artículos**.
1. Seleccione el grupo para administrar.
1. En el panel de acciones, haga clic en **Agregar artículos**.
1. En el cuadro de diálogo **Agregar artículos**, en el campo **Jerarquía de categorías**, seleccione una categoría de nivel superior.
1. La jerarquía de artículos se abre en el panel izquierdo. Seleccione el nivel de jerarquía que está buscando. 
1. Los artículos de la jerarquía seleccionada y el nivel de jerarquía ahora se enumeran en el panel derecho. Siga estos pasos para trabajar con el panel:

    - Seleccione la casilla para cada artículo que desee agregar.
    - Seleccione la casilla de verificación en el encabezado de la cuadrícula para seleccionar todos los elementos que se enumeran.
    - Seleccione el botón **Mostrar seleccionados** para filtrar la cuadrícula de modo que muestre solo los artículos que ha seleccionado hasta ahora. Vuelva a seleccionar el botón para volver a la lista completa.

1. Seleccione **Aceptar** para aplicar su selección de artículo al grupo seleccionado.
