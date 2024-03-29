---
title: Solucione el error del motor de programación y capacidad limitada "No se pudo encontrar suficiente capacidad"
description: Este artículo proporciona información sobre las razones y resoluciones de la Orden de producción %1 no se pudo programar. No se pudo encontrar suficiente capacidad'.
author: t-benebo
ms.date: 7/29/2021
ms.topic: article
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d4f54c06a07b3cdd0b8fe2cc52614189ff31ba7f
ms.sourcegitcommit: 6b209919de39c15e0ebe4abc9cbcd30618f2af0b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2022
ms.locfileid: "9135611"
---
# <a name="fix-the-not-enough-capacity-could-be-found-scheduling-engine-error"></a>Solucione el error del motor de programación "No se pudo encontrar suficiente capacidad"

[!include [banner](../includes/banner.md)]

Al ejecutar la programación, es posible que reciba el siguiente mensaje de error:

> No se pudo programar el pedido de producción %1. No se pudo encontrar capacidad suficiente.

Hay varias razones por las que el motor de programación puede fallar y emitir este mensaje de error. Este artículo proporciona pautas que lo ayudarán a encontrar la causa raíz del error y luego mitigarlo.

## <a name="review-the-applicable-resources"></a>Revise los recursos aplicables

El error puede ocurrir si ningún recurso aplicable satisface los requisitos de operación en el sitio de la orden de producción.

Para revisar los recursos aplicables, siga estos pasos.

1. Vaya a **Control de producción \> Órdenes de producción \> Todas las órdenes de producción** y abra o seleccione la orden de producción que no se puede programar.
1. En el panel Acciones, en la pestaña **Pedido de producción**, en el grupo **Detalles de producción**, seleccione **Ruta**.
1. Sobre la página **Ruta de producción**, seleccione la operación y, a continuación, en el Panel de acciones, seleccione **Recursos aplicables**.
1. En el cuadro de diálogo **Recursos aplicables**, establezca el campo **Requisitos de uso para** a *Programación de operaciones* o *Programación de trabajos*, según el tipo de programación que esté utilizando.
1. Asegúrese de que haya recursos aplicables en el sitio de la orden de producción.

## <a name="review-the-calendars-that-are-associated-with-resources"></a>Revisar los calendarios asociados a los recursos

El error puede ocurrir si no hay un calendario asociado con el recurso o el grupo de recursos, o si el calendario asociado no está configurado correctamente (por ejemplo, no tiene horarios de trabajo o su eficiencia como porcentaje es 0 \[cero\]).

Para verificar que un calendario está asociado con el recurso o grupo de recursos, siga estos pasos.

1. Vaya a **Control de producción \> Órdenes de producción \> Todas las órdenes de producción** y abra o seleccione la orden de producción que no se puede programar.
1. En el panel Acciones, en la pestaña **Pedido de producción**, en el grupo **Detalles de producción**, seleccione **Ruta**.
1. Sobre la página **Ruta de producción**, seleccione la operación y, a continuación, en el Panel de acciones, seleccione **Recursos aplicables**.
1. En el cuadro de diálogo **Recursos aplicables**, seleccione el recurso y luego seleccione **Ver recurso**. Alternativamente, seleccione y mantenga presionado (o haga clic con el botón derecho) en el campo **Grupo de recursos** y luego seleccione **Ver detalles**.
1. Sobre la página **Recursos** o **Grupos de recursos**, en la ficha despelgable **Calendarios**, asegúrese de que haya un calendario asociado con el recurso o grupo de recursos.

> [!NOTE]
> Si el error ocurre durante la programación de la operación, debe asegurarse de que haya un calendario asociado con todos los grupos de recursos aplicables.

Para revisar la configuración del calendario, siga estos pasos.

1. Ir a **Administración de la organización \> Configuración \> Calendarios \> Calendarios** y seleccione el calendario asociado con el recurso o grupo de recursos.
1. En el panel de acciones, seleccione **Horas de trabajo**.
1. En la página **Tiempos de trabajo**, asegúrese de que la página no esté en blanco. Además, para los días que le interesan, asegúrese de que el campo **Control** no está configurado en *Cerrado*, existen tiempos de trabajo, y el campo **La eficiencia es un porcentaje** no está configurado en *0* (cero).

Si el calendario está asociado con el calendario base, también debe revisar la configuración del calendario base.

> [!NOTE]
> En la programación de operaciones, el calendario del grupo de recursos se utiliza para determinar las horas y fechas de inicio y finalización de cada operación. También limita la cantidad de tiempo que el sistema puede programar para una operación específica para un día específico en un grupo de recursos específico. Por ejemplo, si los horarios de trabajo para un grupo de recursos en un día específico son de 8:00 a. M. A 4:00 p. M., La carga que una operación coloca en el grupo de recursos no puede exceder la carga que se puede ajustar en ocho horas., independientemente de la cantidad de capacidad disponible que tenga el grupo de recursos ese día. Sin embargo, la capacidad disponible puede limitar aún más la carga.

## <a name="review-the-scheduling-parameters"></a>Revisar los parámetros de programación

Para garantizar un buen rendimiento, el motor de programación buscará un recurso solo durante un período de tiempo específico y una cantidad específica de conflictos de programación.

Para revisar los parámetros de programación, siga estos pasos.

1. Vaya a **Administración de la organización \> Configurar \> Parámetros de programación**.
1. Siga uno de estos pasos:

    - Si la opción **Programación de tiempo de espera habilitado** está configurada en *No*, continúe con el paso 3.
    - Si la opción **Programación de tiempo de espera habilitado** está configurada en *Sí*, aumente el valor del campo **Tiempo máximo de programación por secuencia** para que el procesamiento tenga más tiempo para completarse.

1. Siga uno de estos pasos:

    - Si la opción **Programación de tiempo de espera de optimización habilitado** está configurada en *No*, continúe con el paso 4.
    - Si la opción **Programación de tiempo de espera de optimización habilitado** está configurada en *Sí*, aumente el valor del campo **Tiempo de espera de intentos de optimización** para que el procesamiento tenga más tiempo para completarse.

1. Si cambió alguna de las configuraciones en la página, reprograme el pedido para volver a intentarlo.

## <a name="review-capacity"></a>Capacidad de revisión

El error puede ocurrir cuando realiza una programación finita, pero no hay capacidad libre.

Para realizar una programación de capacidad infinita, siga estos pasos.

1. Vaya a **Control de producción \> Órdenes de producción \> Todas las órdenes de producción** y seleccione o abra la orden de producción que no se puede programar.
1. En el panel de acciones, en la pestaña **Calendario**, en el grupo **Orden de producción**, seleccione **Programar operaciones** o **Programar trabajos**.
1. En el cuadro de diálogo **Programación de operaciones** o **Programación de trabajos**, establezca la opción **Capacidad finita** en *No*.
1. Seleccione **Aceptar** para programar la orden.

Para revisar la capacidad disponible en el recurso, siga estos pasos.

1. Ir a **Administración de la organización \> Recursos \> Recursos** y seleccione un recurso que sea aplicable al pedido que no se puede programar.
1. En el panel de acciones, en la pestaña **Recurso**, en el grupo **Vista**, seleccione **Carga de capacidad** o **Carga de capacidad, gráficamente** y asegúrese de que haya capacidad disponible.

Para revisar la capacidad disponible en el grupo de recursos, siga estos pasos.

1. Ir a **Administración de la organización \> Recursos \> Grupos de recursos** y seleccione un grupo de recursos que sea aplicable al pedido que no se puede programar.
1. En el panel de acciones, en la pestaña **Grupo de recursos**, en el grupo **Vista**, seleccione **Carga de capacidad** o **Carga de capacidad, gráficamente** y asegúrese de que haya capacidad disponible.

## <a name="master-planning-books-a-resource-when-the-resource-calendar-is-closed"></a>La planificación maestra reserva un recurso cuando el calendario de recursos está cerrado

Al utilizar la programación de operaciones, la planificación maestra planificará la capacidad de acuerdo con el calendario del grupo de recursos principal. Reserva la operación secundaria al mismo tiempo que la operación principal y no tiene en cuenta los calendarios ni la capacidad de la operación secundaria. Esto puede provocar que el pedido de producción se programe en un calendario cerrado o en un momento en que la operación secundaria no esté disponible (calendario cerrado, sin capacidad).

Al utilizar la programación de trabajos, la planificación maestra tendrá en cuenta la capacidad y el calendario de la operación principal y secundaria al programar el pedido. Para que se programe la orden, los calendarios de los recursos de ambas operaciones deben estar abiertos y tener capacidad disponible.

## <a name="maximum-job-lead-time-is-too-short"></a>El plazo máximo del trabajo es demasiado corto

El motor de programación no podrá programar un pedido si el **Plazo máximo del trabajo** establecido para su sitio es menor que el tiempo de entrega especificado para un artículo en su configuración de pedido predeterminada o configuración de cobertura.

Para ver o editar la configuración de **Plazo máximo del trabajo** para su sitio, vaya a **Control de producción \>Configuración \> Parámetros de control de producción** y abra la pestaña **General**.

Para ver o editar la configuración de pedido predeterminada para un artículo, siga estos pasos:

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Busque y seleccione el producto deseado en la lista.
1. En el Panel de acciones, abra la pestaña **Administrar inventario** y seleccione **Configuración predeterminada de pedido**.
1. Amplíe la ficha desplegable **Inventario** y vea o edite el ajuste **Plazo de inventario** según sea necesario.

Para ver o editar la configuración de cobertura para un artículo, siga estos pasos:

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Busque y seleccione el producto deseado en la lista.
1. En el panel de acciones, abra la pestaña **Plan** y seleccione **Cobertura de artículos**.
1. Abra la pestaña **Plazo** y vea o edite el valor de **Tiempo de producción** según sea necesario.

## <a name="excessive-quantity-of-required-resources"></a>Cantidad excesiva de recursos requeridos

Durante la programación, el motor intenta hacer coincidir la cantidad de recursos necesaria establecida para una operación de ruta con los recursos aplicables de acuerdo con los requisitos de recursos de la operación. Si establece la cantidad de recursos demasiado alta puede hacer que una ruta sea inviable, lo que producirá un error de programación.

Utilice el siguiente procedimiento para comprobar tanto la cantidad especificada como los recursos aplicables para un producto, una ruta y una operación de ruta seleccionados:

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Busque y seleccione el producto deseado en la cuadrícula.
1. En el Panel acciones, abra la pestaña **Ingeniero** y seleccione **Ruta**.
1. Busque y seleccione la ruta deseada en la cuadrícula.
1. Abra la pestaña **Visión general** en la parte inferior de la página.
1. Seleccione una operación de la lista de operaciones de ruta seleccionadas.
1. Seleccione **Recursos aplicables** para abrir un cuadro de diálogo donde puede ver los recursos aplicables para la operación de ruta seleccionada.
1. Abra la pestaña **Carga de recursos**. El campo **Cantidad** de aquí muestra la cantidad de recursos requerida para la operación de ruta seleccionada. Vea y edite si es necesario.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
