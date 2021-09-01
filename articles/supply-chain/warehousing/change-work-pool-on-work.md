---
title: Cambiar grupo de trabajo en trabajo
description: Este tema explica cómo puede usar el botón Cambiar grupo de trabajo para elementos de trabajo, para cambiar el grupo de trabajo existente.
author: mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkPool,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 513d74af52c9b3581827b653d58c95d7d1f2f78a75bea03296495fed0ea85de7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6771140"
---
# <a name="change-work-pool-on-work"></a>Cambiar grupo de trabajo en trabajo

[!include [banner](../includes/banner.md)]

Puede usar grupos de trabajo para organizar el trabajo en grupos. Por ejemplo, puede crear un grupo de trabajo para clasificar el trabajo que se produce en una ubicación específica del almacén.

La característica *Cambiar grupo de trabajo en el trabajo* agrega un botón **Cambiar grupo de trabajo** al Panel de acciones para elementos de trabajo. Por lo tanto, los responsables de almacén pueden cambiar fácilmente el grupo de trabajo del trabajo existente. Esta característica permite a los responsables reaccionar rápidamente a los cambios en la planta del almacén, y ayuda a mejorar su capacidad de adaptarse a situaciones cambiantes y a la necesidad de transferir el trabajo a otro grupo de trabajo.

## <a name="turn-on-the-change-work-pool-on-work-feature"></a>Activar la función Cambiar grupo de trabajo en trabajo

Antes de comenzar a configurar o utilizar esta función, debe asegurarse de que está disponible en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de la característica:** *Cambiar grupo de trabajo en trabajo*

## <a name="set-up-the-change-work-pool-on-work-feature"></a>Configurar la característica Cambiar grupo de trabajo en trabajo

Para usar esta característica, debe tener configurados algunos grupos de trabajo. También puede configurar sus plantillas de trabajo para que asignen automáticamente un grupo. Si desea trabajar en el escenario de ejemplo que se proporciona más adelante en este tema, configure su sistema como se describe en esta sección.

### <a name="set-up-work-pools"></a>Configurar grupos de trabajo

Los grupos de trabajo le permiten organizar los elementos de trabajo por tipo. Para trabajar con la característica *Cambiar grupo de trabajo en trabajo*, debe tener al menos dos grupos de trabajo disponibles. Siga estos pasos para ver y agregar grupos de trabajo:

1. Vaya a **Gestión de almacenes \> Configurar \> Trabajo \> Grupos de trabajo**.
1. Si está trabajando con datos de demostración de la empresa **USMF** y trabajará en el escenario de ejemplo más adelante en este tema, agregue dos grupos de trabajo que tengan la siguiente configuración:

    - Grupo de trabajo 1:

        - **Id. del grupo de trabajo:** *Tiendaweb*
        - **Descripción:** *Tienda web*

    - Grupo de trabajo 2:

        - **Id. del grupo de trabajo:** *CentroLlamadas*
        - **Descripción:** *Centro de llamadas*

1. En el panel Acciones, seleccione **Guardar**.

### <a name="set-up-work-templates"></a>Configurar plantillas de trabajo

Puede establecer un grupo de trabajo predeterminado para cada una de sus plantillas de trabajo, según lo necesite. Asigne un grupo de trabajo para cada plantilla relevante en la columna **Id. del grupo de trabajo**. En este caso, todos los elementos de trabajo que se generan utilizando una plantilla determinada heredan automáticamente el grupo de trabajo asignado. Si está trabajando con datos de demostración de la empresa **USMF** y trabajará en el escenario de ejemplo más adelante en este tema, siga los siguientes pasos:

1. Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.
1. En el Panel de acciones, seleccione **Editar** para poner la página en modo de edición.
1. Edite la plantilla estableciendo los siguientes valores:

    - **Plantilla de trabajo:** *62 Selección para empaquetar*
    - **Id. del grupo de trabajo:** *Tiendaweb*

1. Seleccione **Guardar**.

## <a name="example-scenario"></a>Supuesto de ejemplo

Este escenario muestra cómo cambiar la secuencia de procesamiento de un elemento de trabajo existente cambiando su grupo de trabajo. Utiliza datos de muestra de la empresa **USMF** y las configuraciones sugeridas anteriormente en este tema.

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a>Crear un pedido de ventas y liberarlo en el almacén

1. Confirme que hay suficiente inventario disponible para los artículos *A0001* y *A0002* en el almacén *62*. Vaya a **Gestión de inventarios \> Consultas e informes \> Lista disponible** y edite los filtros como se muestra aquí:

    - El valor **Almacén** comienza con *62*.
    - El valor **Número de artículo** es *A001* o *A002*.

    Los datos de demostración deben tener una cantidad de 10 cada uno.

    A continuación, debe crear un pedido de ventas.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - **Cuenta de cliente:** *US-007*
    - **Almacén**: *62*

1. Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.
1. Se abre el nuevo pedido de ventas. Debe incluir una nueva línea vacía en la cuadrícula en la ficha desplegable **Líneas de pedido de venta**. En esta línea, establezca los siguientes valores:

    - **Código de artículo:** *A0001*
    - **Cantidad:** *2*

1. En el menú **Inventario** sobre la cuadrícula, seleccione **Reserva**.
1. En la página **Reserva**, en el Panel de acciones, seleccione **Reservar lote** para reservar inventario.
1. Cierre la página.
1. En la ficha desplegable **Líneas de pedido de venta**, seleccione **Agregar línea** para agregar otra línea a su pedido de ventas. En esta línea, establezca los siguientes valores:

    - **Código de artículo:** *A0002*
    - **Cantidad:** *2*

1. En el menú **Inventario** sobre la cuadrícula, seleccione **Reserva**.
1. En la página **Reserva**, en el Panel de acciones, seleccione **Reservar lote** para reservar inventario.
1. Cierre la página.
1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.
1. Recibirá mensajes informativos que muestran el id. de oleada y el id. de envío que se crearon a partir del lanzamiento. Anote el id. de la oleada.

### <a name="review-the-outbound-wave"></a>Revisar la oleada de salida

1. Vaya a **Gestión de almacenes \> Oleadas de salida \> Oleadas de envío \> Todas las oleadas**.
1. En la cuadrícula, busque el id. de oleada que se creó a partir del lanzamiento del pedido de ventas.
1. Seleccione el id. de oleada para ver los detalles.
1. En la ficha desplegable **Líneas de oleadas**, asegúrese de que se muestre un id. de envío para el pedido de ventas.

    > [!TIP]
    > Si la opción **Procesar oleada para su liberación al almacén** está establecida en *No* en la configuración de la plantilla de envío de oleada, debe procesarla manualmente seleccionando **Procesar** desde la pestaña **Oleada** en el Panel de acciones para crear trabajo.

1. Asegúrese de que se ha procesado la oleada. Este procesamiento crea el trabajo necesario.

### <a name="view-work-details-and-change-the-work-pool"></a>Ver detalles de trabajo y cambiar el grupo de trabajo

Puede usar la página **Detalles del trabajo** para ver el trabajo que se creó y para administrar el grupo de trabajo.

1. Vaya a **Gestión de almacenes \> Trabajo \> Detalles de trabajo**.
1. Seleccione la fila para el trabajo que acaba de crear. La columna **Número de pedido** mostrará el número de pedido de ventas.

    El campo **Id. del grupo de trabajo** se establecerá en el id. del grupo de trabajo que se configuró en la plantilla de trabajo.

    > [!TIP]
    > Si no ve el **Id. del grupo de trabajo**, agregue la columna a la cuadrícula y luego actualice la página.

1. Para cambiar el grupo de trabajo asociado al id. de trabajo, en el Panel de acciones, seleccione **Cambiar ID de grupo de trabajo** en la pestaña **Trabajo**.
1. En el cuadro de diálogo **Cambiar grupo de trabajo**, en la ficha desplegable **Parámetros**, en el campo **ID de grupo de trabajo**, seleccione *Centro de llamadas*.
1. Seleccione **Aceptar** para aplicar su cambio.
1. Tenga en cuenta que el valor del campo **Id. del grupo de trabajo** se ha cambiado a *CentroLlamadas*.

> [!IMPORTANT]
> Cuando aparece el cuadro de diálogo **Cambiar grupo de trabajo**, el campo **Id. del grupo de trabajo** puede estar en blanco de forma predeterminada. Si el campo está en blanco cuando selecciona **Aceptar** para aplicar cambios, eliminará el grupo de trabajo completamente del trabajo.
>
> Además de cambiar los grupos de trabajo, puede utilizar este procedimiento para agregar un grupo de trabajo a cualquier elemento de trabajo que no tenga uno, o para eliminar un grupo de trabajo de cualquier elemento de trabajo que sí lo tenga.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]