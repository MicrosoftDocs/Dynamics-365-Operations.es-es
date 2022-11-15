---
title: Automatización del suministro de fabricación contra pedido
description: En este artículo se describe cómo configurar y utilizar las diversas mejoras que se agregan con la función de automatización de suministro Fabricación sobre pedido.
author: t-benebo
ms.date: 07/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-07-27
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: d376c2f4d8514a4e6122e2e94455d57a39d2babf
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740204"
---
# <a name="make-to-order-supply-automation"></a>Automatización del suministro de fabricación contra pedido

[!include [banner](../includes/banner.md)]

La característica *Automatización de suministro bajo pedido* agrega varias mejoras a Microsoft Dynamics 365 Supply Chain Management. Estas mejoras permiten realizar las tareas siguientes:

- Vea la carga de capacidad de recursos para un período definido por el usuario y, por lo tanto, habilite la evaluación a largo plazo de la carga de capacidad.
- Mejore la flexibilidad controlando la tolerancia de retraso (días negativos) para cada plan maestro.
- Mantenga los productos disponibles para pedidos de última hora y optimice el uso del suministro existente vinculando el último suministro posible a una demanda en lugar de utilizar el primer suministro posible.
- Mantenga la asignación de componentes flexible para las órdenes de producción después de la puesta en firme, de modo que el sistema pueda optimizarse para los cambios de demanda de último momento. En otras palabras, limite el marcado a un nivel.
- Controle la política de cumplimiento para cada orden de venta. Los ajustes predeterminados se toman de la configuración del cliente.
- Mejorar el flujo de información de empresas vinculadas. Las órdenes de compra se actualizan para que incluyan campos para el modo de entrega, las condiciones de entrega y el número de artículo externo. Este cambio garantiza que la información detallada de la demanda pueda fluir a la empresa proveedora.

Este artículo describe cómo configurar y utilizar cada mejora.

## <a name="turn-on-the-make-to-order-supply-automation-feature"></a>Activar la función de automatización de suministro de fabricación bajo pedido

Antes de poder usar la función que se describe en este artículo, debe activarla para su sistema. Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), donde la función aparece de la siguiente forma:

- **Módulo:** *Planificación maestra*
- **Nombre de la caracteristica**: *Automatización de suministro de fabricación bajo pedido*

## <a name="set-the-number-of-days-to-show-on-capacity-load-page"></a>Establecer el número de días para mostrar en la página de carga de capacidad

La página **Carga de capacidad** le permite revisar la capacidad disponible de un recurso. La función *Automatización de suministro bajo pedido* mejora la página **Carga de capacidad** agregando un campo **Número de días**. Puede utilizar este campo para limitar el número de días que muestra la cuadrícula **Visión general**. El valor que establece se guarda en la memoria. Por lo tanto, si abandona la página y vuelve más tarde, la cuadrícula **Visión general** seguirá mostrando el número de días que especificó por última vez.

Para abrir la página **Carga de capacidad** para que pueda revisar la capacidad disponible para un recurso individual, siga estos pasos.

1. Vaya a **Administración de la organización \> Recursos \> Recursos**.
1. Seleccionar un recurso para inspeccionar.
1. En el panel de acciones, en la ficha **Recurso**, en el grupo **Ver**, seleccione **Carga de capacidad**.
1. Use el filtro **Número de días** para limitar el número de días que muestra la cuadrícula **Visión general**.

Para abrir la página **Carga de capacidad** para que pueda revisar la capacidad disponible para un grupo de recursos, siga estos pasos.

1. Vaya a **Administración de la organización \> Recursos \> Grupos de recursos**.
1. Seleccionar un grupo de recursos para inspeccionar.
1. En el panel de acciones, en la ficha **Grupo de recursos**, en el grupo **Ver**, seleccione **Carga de capacidad**.
1. Use el filtro **Número de días** para limitar el número de días que muestra la cuadrícula **Visión general**.

## <a name="apply-a-single-level-of-marking-when-you-firm-planned-orders"></a>Aplique un solo nivel de marcado cuando firme pedidos planificados

*Calificación* se utiliza para vincular la oferta y la demanda. Se parece a la *vinculación*, que indica cómo la planificación maestra espera cubrir la demanda. Sin embargo, el marcado es más permanente que la vinculación. La función *Automatización de suministro bajo pedido* agrega la capacidad de limitar el marcado de inventario a un solo nivel cuando se confirman los pedidos planificados. Añade las siguientes opciones nuevas al campo **Actualizar marcado** en el cuadro de diálogo **Puesta en firme** cuando está consolidando una orden planificada:

- *Estándar de un solo nivel* – Se utiliza el marcado de un solo nivel. El marcado de un solo nivel marca solo el artículo principal, no sus componentes de la lista de materiales (BOM). Por lo tanto, puede mantener flexible la asignación de componentes para órdenes de fabricación después de la puesta en firme. El marcado de un solo nivel permite que el sistema se optimice para los cambios de demanda de última hora. En el marcado de un solo nivel *estándar*, los pedidos de requisitos se marcan con respecto a sus pedidos de cumplimiento, pero los pedidos de cumplimiento no se marcan si tienen una cantidad restante.
- *Un solo nivel extendido* – Se utiliza el marcado de un solo nivel. En el marcado de un solo nivel *extendido*, los pedidos de requisitos se marcan con respecto a sus pedidos de cumplimiento y los pedidos de cumplimiento siempre se marcan sin importar si tienen una cantidad restante.

Estas opciones también están disponibles en el campo **Actualizar marcado** en la ficha **Actualización estándar** de la página **Parámetros de planificación maestra**, donde se define la selección predeterminada para el cuadro de diálogo **Puesta en firme**.

Para obtener más información, consulte [Marcado de inventario](planning-optimization/marking.md).

## <a name="set-delay-tolerance-negative-days-at-the-master-plan-level"></a>Establecer la tolerancia de retraso (días negativos) en el nivel del plan maestro

La característica *Automatización de suministro bajo pedido* agrega la capacidad de configurar la tolerancia de retraso (días negativos) en el nivel del plan maestro. La configuración también está disponible en los niveles de cobertura de artículos y grupo de cobertura. Si se asignan días negativos en más de un nivel, el sistema aplica la siguiente jerarquía para decidir qué configuración usar:

- Si se configuran días negativos en la página **Planes maestros**, esa configuración anula todas las demás configuraciones de días negativos cuando se ejecuta el plan.
- Si se configuran días negativos en la página **Cobertura de artículos**, esa configuración anula la configuración del grupo de cobertura.
- Los días negativos que se configuran en la página **Grupos de cobertura** se aplica solo si los días negativos no se han configurado para un artículo o plan maestro relevante.

Para establecer días negativos para un plan maestro, siga estos pasos.

1. Vaya a **Planificación maestra \> Configurar \> Planes \> Planes maestros**.
1. Seleccione un plan maestro en el panel de lista o cree uno nuevo.
1. En la ficha desplegable **Límites de tiempo en días**, establezca la opción **Días negativos** en *Sí*.
1. En el campo cercano, introduzca el número de días negativos para permitir.

Para obtener más información sobre cómo utilizar los días negativos, consulte [Tolerancia de retraso (días negativos)](planning-optimization/delay-tolerance.md).

## <a name="control-the-pegging-sequence-used-during-master-planning"></a>Control de la secuencia de trazabilidad que se utiliza durante la planificación maestra

La planificación maestra utiliza una *secuencia de vinculación* para determinar qué oferta cubrirá qué demanda. La característica *Automatización de suministro bajo pedido* agrega una nueva opción **Utilizar el último suministro posible** que le da más control sobre la secuencia de vinculación. La nueva opción permite mantener los productos disponibles para pedidos de última hora y optimice el uso del suministro existente vinculando el último suministro posible a una demanda en lugar de utilizar el primer suministro posible.

Puede establecer la secuencia de trazabilidad en el plan maestro, la cobertura de artículos o el nivel de grupo de cobertura. Si se configura una secuencia de trazabilidad en más de un nivel, el sistema aplica la siguiente jerarquía para decidir qué configuración usar:

- Si se configura una secuencia de vinculación en la página **Planes maestros**, esa configuración anula todas las demás configuraciones de secuencia de trazabilidad cuando se ejecuta el plan.
- Si se configura una secuencia de vinculación en la página **Cobertura de artículos**, esa configuración anula la configuración del grupo de cobertura.
- La secuencia de vinculación que se establece en la página **Grupos de cobertura** solo se aplica si la configuración de la secuencia de trazabilidad no se ha configurado para un artículo o plan maestro relevante.

Para configurar la vinculación en el nivel de grupo de cobertura, siga estos pasos.

1. Vaya **Planificación maestra \> Configurar \> Cobertura \> Grupos de cobertura**.
1. Seleccione un grupo en el panel de lista o cree uno nuevo.
1. Sobre la ficha desplegable **General**, en la sección **Secuencia de vinculación**, utilice los campos **Consumir inventario disponible** y **Utilice el último suministro** para configurar su secuencia de vinculación. La tabla que aparece más adelante en esta sección muestra cómo se combinan estas configuraciones para definir su secuencia de vinculación.

Para configurar la vinculación en el nivel de cobertura de artículo, siga estos pasos.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Seleccione un producto en la cuadrícula o cree uno nuevo.
1. En el panel de acciones, en la pestaña **Plan**, seleccione **Cobertura de artículos**.
1. La página **Cobertura de artículos** proporciona filas que le permiten definir las reglas de cobertura que se aplican al artículo en cada almacén. Seleccione una fila existente en la cuadrícula o cree una nueva.
1. En la pestaña **General**, seleccione la casilla **Anular secuencia de vinculación**.
1. Utilice los campos **Consumir inventario disponible** y **Utilice el último suministro** para configurar su secuencia de vinculación. La tabla que aparece más adelante en esta sección muestra cómo se combinan estas configuraciones para definir su secuencia de vinculación.

Para configurar la vinculación en el nivel de plan maestro, siga estos pasos.

1. Vaya a **Planificación maestra \> Configurar \> Planes \> Planes maestros**.
1. Seleccione un plan maestro en el panel de lista o cree uno nuevo.
1. En la ficha desplegable **General**, configure la opción **Anular secuencia de diagrama de árbol** en *Sí*.
1. Utilice los campos **Consumir inventario disponible** y **Utilice el último suministro** para configurar su secuencia de vinculación. La tabla que aparece más adelante en esta sección muestra cómo se combinan estas configuraciones para definir su secuencia de vinculación.

La siguiente tabla muestra cómo los ajustes **Consumir inventario disponible** y **Utilice el último suministro** se combinan para establecer su secuencia de vinculación.

| | Usar el último suministro posible = Sí | Usar el último suministro posible = No |
|---|---|---|
| **Consumir inventario disponible** = *Antes de todo suministro* | <ol><li>Disponible</li><li>Oferta existente que puede satisfacer la fecha de demanda</li><li>Oferta existente que no puede cumplir con la fecha de demanda, pero aún dentro de los días negativos</li><li>Crear nuevo suministro (pedido planificado)</li></ol> | <ol><li>Disponible</li><li>Oferta existente que puede satisfacer la fecha de demanda</li><li>Oferta existente que no puede cumplir con la fecha de demanda, pero aún dentro de los días negativos</li><li>Crear nuevo suministro (pedido planificado)</li></ol> |
| **Consumir inventario disponible** = *Después de todo suministro* | <ol><li>Oferta existente que puede satisfacer la fecha de demanda</li><li>Disponible</li><li>Oferta existente que no puede cumplir con la fecha de demanda, pero aún dentro de los días negativos</li><li>Crear nuevo suministro (pedido planificado)</li></ol> | <ol><li>Oferta existente que puede satisfacer la fecha de demanda</li><li>Oferta existente que no puede cumplir con la fecha de demanda, pero aún dentro de los días negativos</li><li>Disponible</li><li>Crear nuevo suministro (pedido planificado)</li></ol> |

## <a name="review-and-set-the-fulfillment-policy-that-applies-to-each-sales-order"></a>Revisar y establecer la política de cumplimiento que se aplica a cada pedido de ventas

Las directivas de cumplimiento controlan el porcentaje del precio total o la cantidad de un pedido que debe reservarse físicamente antes de que un pedido de ventas se pueda liberar al almacén. Puede establecer una política de cumplimiento predeterminada global y luego anularla para clientes específicos según lo requiera. La función *Automatización de suministro bajo pedido* agrega la capacidad de ver qué política predeterminada se aplica realmente a cualquier pedido y aplica una anulación específica del pedido según sea necesario.

- Para establecer el valor predeterminado de la política de cumplimiento global para pedidos de ventas, vaya a **Cuentas por cobrar \> Configuración \> Parámetros de cuentas por cobrar**. Entonces, la pestaña **Gestion de almacenes**, configure el campo **Política de cumplimiento de pedidos de ventas** con el nombre de la política que desea utilizar. 
- Para establecer una política de cumplimiento específica del cliente para pedidos de ventas, vaya a **Cuentas por cobrar \> Clientes \> Todos los clientes**. Entonces, en la pestaña **Almacén**, configure el campo **Política de cumplimiento** con el nombre de la política que desea utilizar.

Para ver la política predeterminada que se aplica a cualquier pedido y aplicar una anulación específica del pedido, siga estos pasos.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Abra el pedido de venta planificado que desee inspeccionar o editar.
1. Seleccione la vista **Encabezado**.
1. En la ficha desplegable **Almacén**, revise y edite los siguientes campos según sea necesario:

    - **Política de cumplimiento de pedidos** – Seleccione la política de cumplimiento que se usará para el pedido seleccionado. La política predeterminada se anulará. Para usar la política de cumplimiento predeterminada que se muestra en el campo **Política de cumplimiento predeterminada**, deje este campo en blanco.
    - **Política de cumplimiento predeterminada** – Este campo muestra la política de cumplimiento predeterminada que se aplica si el campo **Política de cumplimiento de pedidos** está en blanco. Este campo es de sólo lectura. Si está en blanco, no se define ninguna política de cumplimiento predeterminada global o específica del cliente.

    Si los campos **Política de cumplimiento predeterminada** y **Política de cumplimiento de pedidos** están en blanco, no se aplica ninguna política de cumplimiento. Sin embargo, pueden existir otras restricciones y pueden requerir que se cumplan las reservas u otras condiciones antes de que se pueda liberar la orden de venta.

## <a name="set-the-delivery-mode-and-terms-on-individual-purchase-order-lines"></a>Establecer el modo de entrega y los términos en líneas de orden de compra individuales

Todas las órdenes de compra incluyen ajustes **Terminos de entrega** y **Modo de entrega** en el encabezado del pedido. La función *Automatización de suministro bajo pedido* agrega esta configuración a cada línea de pedido. Por lo tanto, puede definir anulaciones del valor **Terminos de entrega** y/o **Modo de entrega** para cualquiera o todas las líneas de pedido según sea necesario. Para las líneas en las que no se define ninguna anulación, se utiliza el valor del encabezado. Puede especificar si un cambio en el valor de uno o ambos campos en el encabezado del pedido también debe actualizar todas las líneas.

Para especificar lo que debería suceder con la configuración de línea si un usuario cambia el valor **Terminos de entrega** o **Modo de entrega** en un encabezado de pedido, siga estos pasos.

1. Vaya a **Adquisición y abastecimiento \> Configuración \> Parámetros de adquisición y abastecimiento**.
1. Sobre la pestaña **General**, en la ficha desplegable **Valores y parámetros predeterminados**, seleccione el vínculo **Actualizar líneas de pedido**.
1. En el cuadro de diálogo **Actualizar líneas de pedido**, en los campos **Actualización de las condiciones de entrega** y **Actualizar Modo de entrega**, seleccione uno de los siguientes valores:

    - *Nunca* – Nunca actualice las líneas del pedido después de cambiar la configuración en el encabezado del pedido.
    - *Siempre* – Siempre actualizar todas las líneas del pedido después de cambiar la configuración en el encabezado del pedido.
    - *Inmediato* – Si un usuario cambia una o ambas configuraciones en el encabezado del pedido, abra un bot de diálogo que pregunte si el usuario desea actualizar todas las líneas para que coincidan con el cambio en una o ambas configuraciones.

Para configurar la información de entrega en el encabezado de una orden de compra, siga estos pasos.

1. Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**.
1. Abra el pedido de compra planificado que desee editar.
1. Seleccione la vista **Encabezado**.
1. En la ficha desplegable **Entrega**, establezca los campos **Modo de entrega** y **Terminos de entrega** según sea necesario.
1. Dependiendo de la configuración de la página **Parámetros de adquisición y abastecimiento**, es posible que se le pregunte si desea aplicar los cambios a todas las líneas de pedido.

Para configurar la anulación de la información de entrega para una línea de orden de compra, siga estos pasos.

1. Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**.
1. Abra el pedido de compra planificado que desee editar.
1. Seleccione la vista **Líneas**.
1. En la ficha desplegable **Líneas de pedido de compra**, seleccione la línea para editar.
1. En la ficha desplegable **Detalles de línea**, en la pestaña **Entrega**, establezca los campos **Modo de entrega** y **Terminos de entrega** según sea necesario. Borre uno o ambos campos para usar la configuración coincidente en el encabezado.

Para pedidos de empresas vinculadas, los valores para los campos **Modo de entrega** y **Terminos de entrega** de cada línea de orden de compra se sincronizarán entre la orden de compra y su orden de venta relacionada.

## <a name="sync-external-item-ids-and-descriptions-for-intercompany-orders"></a>Sincronice ID de artículos externos y descripciones para pedidos de empresas vinculadas

Para pedidos intercompañía, la característica *Automatización de suministro bajo pedido* permite que los ID de artículos externos y las descripciones de texto en las líneas de pedido de compra se sincronicen con las líneas de pedido de ventas de empresas vinculadas relacionadas, independientemente de si el pedido de compra es para entrega directa. La función también agrega la capacidad de especificar la cuenta del cliente externo final en una orden de compra de empresas vinculadas. Luego, el sistema tomará automáticamente los ID de artículos externos y las descripciones de texto del registro de cliente externo en lugar del registro de proveedor (interno) de empresas vinculadas.

Para configurar un proveedor de empresas vinculadas para sincronizar ID de artículos externos y nombres de artículos entre pedidos de compra de empresas vinculadas y sus pedidos de ventas de empresas vinculadas relacionados, siga estos pasos.

1. Vaya a **Adquisición y abastecimiento \> Proveedores \> Todos los proveedores**.
1. Seleccione el proveedor de empresas vinculadas que desea configurar.
1. En el panel de acciones, en la pestaña **General**, en el grupo **Configurar**, seleccione **Empresas vinculadas**.
1. En la página **Intercompañía**, en la pestaña **Políticas de orden de compra**, en la sección **Orden de compra intercompañía -\> Orden de venta de empresas vinculadas**, seleccione la casilla **ID de artículo externo y nombre de artículo**.

Para especificar la cuenta del cliente externo final para una orden de compra de empresas vinculadas, siga estos pasos. El campo **Cuenta de cliente** solo se aplica a las órdenes de compra de empresas vinculadas. Úselo para especificar el número de cuenta del cliente que eventualmente recibirá los bienes. Cuando se establece este campo, las líneas de orden de compra tomarán descripciones y números de artículos externos de la cuenta de cliente especificada en lugar del proveedor de empresas vinculadas que se especifica en la orden de compra. Si cambia la cuenta del cliente más adelante, las descripciones e ID de artículos externos se actualizarán para que coincidan con los valores de la nueva cuenta. Las descripciones de artículos externos y los ID de cada línea también se sincronizarán con el pedido de ventas de empresas vinculadas coincidente.

1. Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**.
1. Abra la orden de compra que desea configurar o cree una nueva.
1. Seleccione la vista **Encabezado**.
1. En la sección **Referencia**, configure el campo **Cuenta de cliente** con la cuenta de cliente externo relevante.

Para especificar Id. de artículos externos y descripciones de texto para una línea de pedido de compra para un pedido de empresas vinculadas, siga estos pasos. Los valores que establezca se sincronizarán con las líneas de pedido de ventas de empresas vinculadas relacionadas, independientemente de si el pedido de compra es para entrega directa.

1. Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**.
1. Abra la orden de compra que desea configurar o cree una nueva.
1. Seleccione la vista **Líneas**.
1. En la ficha desplegable **Líneas de pedido de compra**, seleccione la línea para editar.
1. En la ficha desplegable **Detalles de línea**, en la pestaña **General**, en la sección **Fila para ordenar**, en el campo **Texto**, proporcione una descripción externa del artículo que se especifica en la línea de pedido seleccionada. Este valor se sincronizará con la línea de pedido de ventas de empresas vinculadas relacionada.
1. En la sección **Referencia**, en el campo **Externo**, proporcione un ID de artículo externo para el artículo que se especifica en la línea de pedido seleccionada. Este valor se sincronizará con la línea de pedido de ventas de empresas vinculadas relacionada.

Para más información, consulte [Crear y facturar un pedido de ventas de empresas vinculadas para un cliente externo](../sales-marketing/intercompany-sales-order-for-external-customer.md).
