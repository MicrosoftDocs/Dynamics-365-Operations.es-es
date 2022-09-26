---
title: Use códigos de disposición de lotes para marcar lotes como disponibles o no disponibles
description: Este artículo describe cómo configurar y usar códigos de disposición de lotes para marcar lotes como disponibles o no disponibles para su uso en planificación maestra, reserva, recogida o envío.
author: t-benebo
ms.date: 09/16/2022
ms.topic: article
ms.search.form: PdsDispositionMaster, InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-16
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: cfb0743a573550de93d75063df517e0c143f2568
ms.sourcegitcommit: 20ce54cb40290dd116ab8b157c0a02d6757c13f5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "9542477"
---
# <a name="use-batch-disposition-codes-to-mark-batches-as-available-or-unavailable"></a>Use códigos de disposición de lotes para marcar lotes como disponibles o no disponibles

Este artículo describe cómo configurar y utilizar los *códigos de disposición de lotes*. Cada código de disposición de lotes tiene un estado de *Disponible* o *No disponible*. Asigne códigos de disposición de lotes a los lotes de inventario para indicar si cada lote está disponible para planificación maestra, reserva, recogida o envío.

Para usar códigos de disposición de lotes, debe configurar los códigos y asignarlos a los lotes que desea administrar.

## <a name="set-up-batch-disposition-codes"></a>Configurar códigos de disposición de lotes

Debe configurar cada código de disposición de lotes que desee utilizar en su sistema. Puede crear tantos códigos como quiera. (Por ejemplo, puede crear códigos para identificar las diferentes razones por las que un lote puede estar disponible o no). Sin embargo, a menudo tendrá solo dos códigos: uno para *disponible* y uno para *indisponible*. También puede crear códigos personalizados que permitan usar un lote para algunas operaciones pero no para otras.

Siga estos pasos para configurar códigos de disposición de lotes.

1. Vaya a **Gestión del inventario \> Configurar \> Lote \> Modelo de disposición de lotes**.
1. La página **Modelo de disposición de lotes** enumera sus códigos de disposición de lote actuales y le permite crearlos, eliminarlos y editarlos. Siga uno de estos pasos:

    - Para editar un código existente, selecciónelo en el panel de lista.
    - Para crear un nuevo código, seleccione **Nueva** en el panel de acciones.

1. Establezca los siguientes campos en la cabecera del código nuevo o seleccionado:

    - **Código de disposición de lotes** – Escriba el nombre para mostrar del código.
    - **Descripción** – Describe cómo se debe utilizar el código.
    - **Estado de disposición de lotes** – Seleccione el estado que se aplica a los lotes a los que se asigna el código:

        - *No disponible* – Los lotes no pueden utilizarse para la planificación maestra, la reserva, la recogida o el envío. Al seleccionar este valor, todas las opciones **Bloquear** en la ficha desplegable **Configuración** están configuradas para *Sí*, y todas las opciones **Netas** están configuradas para *No*. Sin embargo, puede cambiar algunas de estas configuraciones para agregar excepciones.
        - *Disponible* – Los lotes no pueden utilizarse para la planificación maestra, la reserva, la recogida o el envío. Al seleccionar este valor, todas las opciones **Bloquear** en la ficha desplegable **Configuración** están configuradas para *No*, y todas las opciones **Netas** están configuradas para *Sí*. Estos ajustes serán de solo lectura mientras el **Estado de disposición del lote** el campo se establece en *Disponible*.

1. Si configura el campo **Estado de disposición del lote** como *No disponible*, puede personalizar el estado de bloqueo de cada operación (reserva, recolección y envío) para cada tipo de pedido (venta, transferencia y producción). En el caso de las órdenes de fabricación, puede optar por bloquear o desbloquear el diario de recogida de producción. También puede optar por bloquear o desbloquear la planificación maestra. Utilice las opciones de la pestaña desplegable **Configuración** para bloquear o desbloquear cada operación según lo requiera. Seleccione la opción **Neto** como *Sí* para habilitar la planificación maestra, o configúrela como *No* para bloquear la planificación maestra.

## <a name="assign-batch-disposition-codes-to-batches"></a>Asignar códigos de disposición de lotes a lotes

Después de definir los códigos de disposición de lotes que necesita, siga estos pasos para asignarlos a los lotes.

1. Vaya a **Warehouse management \> Configurar \> Inventario \> Lotes**.
1. Seleccione uno o más lotes para asignarles un código de disposición de lote.
1. En el panel de acciones, en la pestaña **Restablecer**, seleccione **Restablecer código de disposición de lotes**.
1. En el cuadro de diálogo **Cambiar las restricciones en el lote de inventario**, configure el campo **Nuevo código de disposición de lotes** con el nombre del código que desea asignar.
1. Seleccione **Aceptar** para aplicar la nueva configuración y guarde el cambio.

    En la página **Lotes**, los valores en las columnas **Código de disposición del lote** y **Estado de disposición del lote** se actualizan para reflejar la nueva configuración de los lotes seleccionados.

## <a name="master-planning-example"></a>Ejemplo de planificación maestra

Este ejemplo muestra cómo los códigos de disposición de lotes pueden afectar la planificación maestra.

Para este ejemplo, los códigos de disposición de lotes se configuran de la siguiente manera:

- *P-Disponible:*

    - **Estado de disposición de lotes:** *Disponible*
    - **Neto:** *Sí*

- *P-No disponible:*

    - **Estado de disposición de lotes:** *No disponible*
    - **Neto:** *No*

Hay un producto (*Producto-1*) que tiene dos lotes: *Lote-A* y *Lote-B*. Estos lotes se configuran de la siguiente manera:

- *Lote-A:*

    - **Código de disposición de lotes:** *P-Disponible*
    - **Cantidad disponible** 1

- *Lote-B:*

    - **Código de disposición de lotes:** *P-No Disponible*
    - **Cantidad disponible** 1

Hay un pedido de ventas (*SO1*) para una cantidad de 2 productos *Producto-1*. La fecha de entrega es de tres días a partir de hoy.

Ejecuta la planificación maestra y establece los siguientes valores que son relevantes para este ejemplo:

- **Pedido previsto:** *Pedido de compra*
- **Estrategia de reposición:** *Requisito*
- **Plazo:** *0*

Como resultado del proceso de planificación, el sistema utiliza el lote disponible (*Lote-A*) para cubrir una cantidad de 1 producto *Producto-1* para el pedido de venta *SO1*. Sin embargo, no puede usar el lote *Lote-B* porque ese lote está marcado como no disponible para la planificación. Por lo tanto, para cubrir la cantidad restante, el sistema crea un pedido de compra planificado (*PPO1*) para un nuevo lote de producto *Producto-1*.

La siguiente ilustración muestra una línea de tiempo para el resultado de la planificación.

![Ejemplo que muestra cómo los códigos de disposición de lotes pueden afectar la planificación maestra.](media/batch-codes-planning-example.png "Ejemplo que muestra cómo los códigos de disposición de lotes pueden afectar la planificación maestra.")
