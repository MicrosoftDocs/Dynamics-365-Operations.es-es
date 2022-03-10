---
title: Estados de ciclo de vida de orden de trabajo
description: En este tema se explican los estados de ciclo de vida de las órdenes de trabajo en Administración de activos.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderLifecycleState, EntAssetWorkOrderLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fa0980438ec629ef7ae6bf711d5ae87efca131e6ab86dfcaa1f17d953725147a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768675"
---
# <a name="work-order-lifecycle-states"></a>Estados de ciclo de vida de orden de trabajo


[!include [banner](../../includes/banner.md)]

 

Los estados de ciclo de vida de la orden de trabajo definen los estados por los que puede pasar una orden de trabajo. Los ejemplos incluyen **Creada**, **Programada**, **En curso** y **Finalizada**. Los estados de ciclo de vida de la orden de trabajo pueden actualizarse manualmente en una orden de trabajo o bien, pueden actualizarse automáticamente (por ejemplo, durante la programación de la orden de trabajo).

Los estados de ciclo de vida de la orden de trabajo obligatorios para las órdenes de trabajo deben vincularse a las etapas de proyecto coincidentes en la página **Parámetros de gestión de proyectos y contabilidad** (**Gestión de proyectos y contabilidad** \> **Parámetros de gestión de proyectos y contabilidad**). Primero configure las etapas de proyecto en Gestión de proyectos y contabilidad. A continuación configure los estados del ciclo de vida de la orden de trabajo y los modelos del ciclo de vida de la orden de trabajo en administración de activos.

La siguiente tabla describe las opciones de las secciones **Orden de trabajo** y **Programación** en la ficha desplegable **General** de la página **Estado del ciclo de vida de la orden de trabajo** (**Administración de activos** \> **Configuración** \> **Órdenes de trabajo** \> **Estados del ciclo de vida**).

![Página Estado de ciclo de vida de orden de trabajo.](media/09-setup-for-work-orders.png)

| Nombre de la opción                   | Descripción |
|-------------------------------|-------------|
| Activa                        | Establezca esta opción en **Sí** si la orden de trabajo tiene que estar activa cuando se encuentra en este estado del ciclo de vida. |
| Agregar línea                      | Establezca esta opción en **Sí** si los trabajos de la orden de trabajo se pueden agregar a una orden de trabajo que se encuentre en este estado del ciclo de vida. |
| Borrar                        | Establezca esta opción en **Sí** si una orden de trabajo puede eliminarse cuando se encuentra en este estado del ciclo de vida. |
| Eliminar línea                   | Establezca esta opción en **Sí** si los trabajos de la orden de trabajo se pueden eliminar de una orden de trabajo que se encuentre en este estado del ciclo de vida. |
| Permitir programación              | Establezca esta opción en **Sí** si una orden de trabajo puede programarse cuando se encuentra en este estado del ciclo de vida. |
| Establecer el inicio real              | Establezca esta opción en **Sí** si se debe solicitar al usuario que seleccione una fecha inicial real y un tiempo para una orden de trabajo cuando se haya actualizado a este estado del ciclo de vida. |
| Establecer finalización real                | Establezca esta opción en **Sí** si se debe solicitar al usuario que seleccione una fecha final real y un tiempo para una orden de trabajo cuando se haya actualizado a este estado del ciclo de vida. |
| Registrar diarios                 | Establezca esta opción en **Sí** si los diarios de la orden de trabajo tienen que publicarse automáticamente cuando una orden de trabajo se actualice a este estado del ciclo de vida. Si se produce un error durante el registro de diario, se mostrará un mensaje, y la actualización del estado del ciclo de vida de la orden de trabajo se cancela. Para ver las líneas de diario para un pedido de trabajo, seleccione **Administración de activos** \> **Común** \> **Órdenes de trabajo** \> **Todas las órdenes de trabajo**, **Órdenes de trabajo activas**, o **Mis órdenes de trabajo activas**, seleccione la orden de trabajo en la lista y, a continuación, seleccione **Diarios**. Esta configuración del registro automático del diario de pedidos del trabajo en un ciclo de vida específico es la misma que cuando se selecciona **Registrar diarios** en la página **Diarios de órdenes de trabajo**.<p>**Nota:** Si se establece esta opción en **Sí**, los diarios se registran automáticamente si no se ha configurado ningún flujo de trabajo de aprobación. Si su empresa usa la configuración de aprobación de diario que está configurada en la página **Aprobación de diario** (**Gestión de proyectos y contabilidad** \> **Configuración** \> **Diarios** \> **Aprobación de diario**), un administrador o el vendedor debe validar y registrar los registros de consumo.</p> |
| Procesar lista de comprobación de mantenimiento | Establezca esta opción en **Sí** si todas las listas de comprobación de mantenimiento tienen que procesarse cuando una orden de trabajo se actualice a este estado del ciclo de vida. Como parte de este procesamiento, se registra cualquier registro contrario que se haya hecho en una lista de comprobación de mantenimiento, y se evalúa el resultado de la lista de comprobación completa de mantenimiento. Las líneas de la lista de comprobación de mantenimiento que tienen los resultados **Aprobado** o **Error** se evalúan, y si al menos una línea falla, la lista de comprobación completa de mantenimiento se marca como **No superado** en administración de activos. |
| Preparado                         | Establezca esta opción en **Sí** si se actualizará el estado de trabajo programado de la orden de trabajo para todos los trabajos de la orden de trabajo que se creen en un pedido de trabajo automáticamente a **Preparada** cuando la orden de trabajo se actualice a este estado del ciclo de vida. |
| Inicio                         | Establezca esta opción en **Sí** si se actualizará el estado de trabajo programado de la orden de trabajo para todos los trabajos de la orden de trabajo que se creen en un pedido de trabajo automáticamente a **Iniciada** cuando la orden de trabajo se actualice a este estado del ciclo de vida. |
| Fin                           | Establezca esta opción en **Sí** si se actualizará el estado de trabajo programado de la orden de trabajo para todos los trabajos de la orden de trabajo que se creen en un pedido de trabajo automáticamente a **Finalizado** cuando la orden de trabajo se actualice a este estado del ciclo de vida. |
| Eliminar líneas de programación         | Establezca esta opción en **Sí** si tiene que eliminarse la programación de todos los trabajos de la orden de trabajo que se creen en un pedido de trabajo que ya se ha programado cuando la orden de trabajo se actualice a este estado del ciclo de vida. Es decir las reservas de capacidad en el activo, el trabajador relacionado de mantenimiento, así como las herramientas relacionadas se eliminarán. Por ejemplo, se establece esta opción en **Sí** en un estado del ciclo de vida de la orden de trabajo que se llama **Estimado**. A continuación, cuando un pedido de trabajo vuelve de nuevo a este estado del ciclo de vida porque es necesario, la programación se puede eliminar en esta orden de trabajo. |

## <a name="set-up-project-stages-and-work-order-lifecycle-states"></a>Configurar estados del ciclo de vida y etapas de proyectos

1. Seleccione **Gestión de proyectos y contabilidad** \> **Configurar** \> **Parámetros de gestión de proyectos y contabilidad**.
2. En la pestaña **Etapa de proyecto**, para cada etapa que desea usar, seleccione la casilla para cada tipo de proyecto que se requiere para las órdenes de trabajo. Los tipos de proyecto definen reglas acerca de las tareas financieras que se permiten. Los ejemplos de tareas financieras incluyen crear una previsión, crear estimaciones, y crear los saldos iniciales.

    > [!IMPORTANT]
    > Si una etapa de proyecto no se selecciona para un tipo de proyecto, pero la etapa de proyecto se usa para un estado del ciclo de vida de la orden de trabajo, los proyectos de órdenes de trabajo no se actualizarán de la forma adecuada.

3. Cierre la página **Parámetros de gestión de proyectos y contabilidad**.
4. Seleccione **Administración de activos** \> **Configuración** \> **Órdenes de trabajo** \> **Estados de ciclo de vida**.
5. Seleccione **Nuevo** para crear un estado de ciclo de vida de orden de trabajo.
6. En el campo **Estado de ciclo de vida**, especifique un identificador para el estado de ciclo de vida.
7. Escriba un nombre en el campo **Nombre**.

    En la ficha desplegable **Detalles**, el campo **Modelos de ciclo de vida** muestra el número de modelos de ciclo de vida de orden de trabajo que utilizan este estado de ciclo de vida.

8. En la ficha desplegable **General**, en la sección **Orden de trabajo**, seleccione las funciones que deben estar disponibles para este estado del ciclo de vida estableciendo las opciones relevantes en **Sí**. Para obtener descripciones de las opciones, consulte la tabla anterior en este tema.
9. En la sección **Proyecto**, en el campo **Etapa**, seleccione la etapa de proyecto que debe estar relacionada con este estado del ciclo de vida.
10. En la sección **Proyecto**, establezca la opción **Cerrar actividades** en **Sí** si las actividades de proyecto que se relacionan con cada trabajo de la orden de trabajo deben cerrarse automáticamente cuando la orden de trabajo está en este estado del ciclo de vida.

    > [!NOTE]
    > Para buscar el número de la actividad del proyecto relacionada con un trabajo de órdenes de trabajo, seleccione **Administración de activos** \> **Común** \> **Órdenes de trabajo** \> **Todas las órdenes de trabajo**, **Órdenes de trabajo activas**, o **Mis órdenes de trabajo activas**. Abra la orden de trabajo, y seleccione el trabajo de la orden de trabajo. El número de actividad se muestra en el campo **Número de actividad** en la sección **Proyecto** en la pestaña **General** de la ficha desplegable **Detalles de línea**.

11. En la sección **Previsión**, establezca la opción **Copiar previsión de horas**, **Copiar previsión de artículo** o **Copiar previsión de gastos** en **Sí** si las previsiones de proyecto de la orden de trabajo tienen que copiarse automáticamente en diarios de la orden de trabajo cuando la orden de trabajo está en este estado del ciclo de vida.
12. En la sección **Programación**, establezca una de las opciones en **Sí** si tiene que actualizarse el estado de programación para los trabajos de la orden de trabajo cuando la orden de trabajo está en este estado del ciclo de vida. Para obtener descripciones de las opciones **Preparado**, **Inicio**, **Fin**, y **Eliminar líneas de la programación**, consulte la tabla anterior de este tema.

    > [!NOTE]
    > Para ver líneas de programación que están relacionadas con un trabajo de órdenes de trabajo, seleccione **Administración de activos** \> **Común** \> **Órdenes de trabajo** \> **Todas las órdenes de trabajo**, **Órdenes de trabajo activas**, o **Mis órdenes de trabajo activas**. Abra la orden de trabajo, seleccione el trabajo de la orden de trabajo en la ficha desplegable **Trabajos de órdenes de trabajo**, y vea la información relacionada en la ficha desplegable **Detalles de línea**. El campo **Estado** en la pestaña **Programación** muestra el estado del trabajo de la orden de trabajo. El campo **Estado** se puede establecer en los siguientes valores: **Programado**, **Preparado**, **Iniciado**, **Detenido**, y **Terminado**.

13. En la sección **Solicitudes de mantenimiento**, en el campo **Estado del ciclo de vida**, seleccione el estado del ciclo de vida de la solicitud de mantenimiento al que las solicitudes relacionadas de mantenimiento se deben actualizar. Esta actualización se produce automáticamente. Puede hacerse solo si se selecciona el estado del ciclo de vida de la solicitud de mantenimiento en el modelo del ciclo de vida de la solicitud de mantenimiento que se usa para la solicitud de mantenimiento.
14. En la sección **Activo**, establezca la opción **Actualizar L.MAT de activos** en **Sí** si todos los elementos que se usan en un pedido de trabajo tienen que actualizarse automáticamente en la página **L. MAT de activos** cuando la orden de trabajo se actualiza a este estado del ciclo de vida. Este valor puede ser importante si, por ejemplo, el estado del ciclo de vida de la orden de trabajo define la orden de trabajo como completada o finalizada.
15. En la sección **Grupo de órdenes de trabajo**, establezca la opción **Eliminar referencia del grupo** en **Sí** si las órdenes de trabajo que están en este estado del ciclo de vida deben eliminarse automáticamente de los conjuntos de órdenes de trabajo.
16. En la ficha desplegable **Validar**, seleccione los tipos de validación que deben activarse en este estado del ciclo de vida estableciendo las opciones relevantes **Sí**. A continuación, en el campo **tipo** para cada tipo de validación que seleccione, seleccione el tipo de mensaje que se debe mostrar si los campos obligatorios relacionados con el tipo de validación no se han validado. Si se selecciona **Error**, la actualización del estado del ciclo de vida de la orden de trabajo se cancela hasta que los campos obligatorios relacionados se hayan actualizado en la orden de trabajo.

    - Las opciones **Tiempo de inactividad por mantenimiento**, **Lista de comprobación de mantenimiento**, **Síntoma del error**, **Causa del error**, y **Soluciones a defectos** están relacionadas con las opciones de la sección **Obligatorio** en la página **Tipos de orden de trabajo** (**Administración de activos** \> **Configuración** \> **Órdenes de trabajo** \> **Tipos de órdenes de trabajo**). Para activar estas validaciones, las opciones relacionadas se deben establecer también en **Sí** en el tipo de pedido de trabajo que se usa para la orden de trabajo.
    - Si la opción **Lista de comprobación de mantenimiento** se establece en **Sí** para el estado de ciclo de vida al que se actualiza un pedido de trabajo, la validación se hace para comprobar que las líneas de la lista de comprobación de mantenimiento marcadas como **Obligatorio** se haya registrado como **Comprobado** o **No aplicable**. Si ninguno de estos registros se ha hecho en las líneas obligatorias, se mostrará un mensaje informativo, de error, o de advertencia cuando la orden de trabajo se actualice a este estado del ciclo de vida.
    - Si la opción **Gasto comprometido** se establece en **Sí** para el estado del ciclo de vida al que un pedido de trabajo se actualiza, el importe total de los gastos comprometidos (es decir, el importe total de los gastos que la entidad jurídica se ha comprometido a pagar) se calcula para cada trabajo de la orden de trabajo. Aparece un mensaje si el importe de gasto comprometido es más de 0 (cero). Puede seleccionar los tipos de compromiso de costes que se incluyen en la ficha desplegable **Compromisos de coste** en la pestaña **Control de costes** de la página **Parámetros de gestión de proyectos y contabilidad** (**Gestión de proyectos y contabilidad** \> **Configuración** \> **Parámetros de gestión de proyectos y contabilidad**).
    - Si la opción **Tiempo de inactividad de mantenimiento** se establece en **Sí** para el estado del ciclo de vida al que un pedido de trabajo se actualiza, la validación del tiempo de inactividad por mantenimiento se realiza en el activo relacionado con la orden de trabajo. Si se ha realizado un registro de tiempo de inactividad por mantenimiento, pero no hay ningún registro **Terminado**, se muestra un mensaje cuando la orden de trabajo se actualiza a este estado del ciclo de vida.
    - Si la configuración estándar del proyecto no incluye todas las etapas que necesita para la configuración de la gestión de activos, puede configurar etapas de proyecto definidas por el usuario en la pestaña **Etapa de proyecto** de la página **Parámetros de gestión de proyectos y contabilidad**. La ilustración siguiente muestra la pestaña **Etapa de proyecto** en la página **Parámetros de gestión de proyectos y contabilidad**.

    ![Página Configurar etapas del proyecto para varios tipos de proyectos.](media/10-setup-for-work-orders.png)

> [!NOTE]
> Si el estado del ciclo de vida al que actualiza un pedido de trabajo está inactivo, los diarios relacionados con la orden de trabajo pero que aún no se han registrado se eliminan automáticamente. Este comportamiento ayuda a garantizar la limpieza automática de datos no usados. (Un estado del ciclo de vida está inactivo si su opción **Activo** está establecida en **No** en la ficha desplegable **General** de la página **Estado del ciclo de vida de la orden de trabajo**).
>
> Sin embargo, si establece manualmente un pedido de trabajo para que esté inactivo, los diarios relacionados con la orden de trabajo pero que aún no se han registrado **no** se eliminan automáticamente. (Para desactivar manualmente un pedido de trabajo, seleccione **Administración de activos** \> **Común** \> **Órdenes de trabajo** \> **Todas las órdenes de trabajo** o **Órdenes de trabajo activas**. Abra la orden de trabajo, y cambie a la vista **Encabezado**. En la ficha desplegable **General**, seleccione **Editar** y, a continuación establezca la opción **Activo** en **No**.)

## <a name="relations-among-work-order-lifecycle-models-work-order-types-and-work-order-lifecycle-states"></a>Relaciones entre modelos de ciclo de vida de orden de trabajo, los tipos de orden de trabajo y estados de ciclo de vida de la orden de trabajo

Los modelos del ciclo de vida hacen referencia a flujos de trabajo, y los estados del ciclo de vida se seleccionan en un modelo del ciclo de vida en orden secuencial. Los modelos de ciclo de vida se establecen en tipos de órdenes de trabajo. Los tipos de pedido de trabajo determinan el tamaño o la extensión de los flujos de trabajo y los procesos laborales. Por ejemplo, **Mantenimiento**, que es un tipo de pedido estándar de trabajo, se puede relacionar con un modelo del ciclo de vida de la orden de trabajo que tiene varios estados del ciclo de vida. Por el contrario, puede tener un tipo de pedido de trabajo **Correctivo** que se usa para las órdenes de trabajo que no se han programado, o para las órdenes de trabajo donde se completa el trabajo antes de que la orden de trabajo se cree debido a una situación urgente. Este tipo de pedido del trabajo puede estar relacionado con un modelo del ciclo de vida de la orden de trabajo que tiene sólo algunos estados del ciclo de vida.

El motivo para usar tipos consiste reside en que cuando se define un tipo en, por ejemplo, un pedido de trabajo o un activo, los procesos laborales relacionados (estados del ciclo de vida) se definen automáticamente. Para obtener más información sobre cómo configurar tipos de órdenes de trabajo, consulte [Tipos de órdenes de trabajo](../setup-for-work-orders/work-order-types.md).

> [!NOTE]
> Los estados de ciclo de vida, los modelos de ciclo de vida y los tipos se aplican a ubicaciones funcionales, activos, y solicitudes de mantenimiento, además de órdenes de trabajo.

La ilustración siguiente muestra la relación entre los tipos de pedido de trabajo, los modelos de ciclo de vida, y los estados del ciclo de vida.

![Página Tipo de orden de trabajo en comparación con la página Modelos de ciclo de vida de orden de trabajo.](media/11-setup-for-work-orders.png)

## <a name="work-order-lifecycle-models"></a>Modelos de ciclo de vida de orden de trabajo

Una vez que haya creado los estados de ciclo de vida de la orden de trabajo necesarios para sus órdenes de trabajo, estos pueden dividirse en modelos de ciclo de vida de órdenes de trabajo. Como mínimo, debe crear un modelo estándar del ciclo de vida.

1. Seleccione **Administración de activos** \> **Configuración** \> **Órdenes de trabajo** \> **Modelos de ciclo de vida**.
2. Seleccione **Nuevo** para crear un modelo de ciclo de vida de orden de trabajo.
3. En el campo **Modelo de ciclo de vida**, especifique un identificador para el modelo de ciclo de vida.
4. Escriba un nombre en el campo **Nombre**.

    En la ficha desplegable **Detalles**, el campo **Estados de ciclo de vida** muestra el número de estados de ciclo de vida seleccionados en este modelo de ciclo de vida. El campo **Tipos de orden de trabajo** muestra el número de tipos de orden de trabajo que utilizan este modelo de ciclo de vida.

5. En el FastTab **Estados de ciclo de vida**, seleccione los estados de ciclo de vida que se deben incluir en el modelo de ciclo de vida:

    - Para incluir un estado de ciclo de vida en el modelo de ciclo de vida, selecciónelo en la sección **Estados de ciclo de vida restantes** y seleccione el botón de la ![flecha derecha.](media/12-setup-for-work-orders.png) para moverlo a la sección **Estados del ciclo de vida seleccionados**.
    - Para incluir todos los estados de ciclo de vida disponibles en el modelo de ciclo de vida, seleccione el botón **Seleccionar todas las etapas disponibles** ![Seleccionar todas las etapas disponibles.](media/13-setup-for-work-orders.png). Todos los estados de ciclo de vida se mueven a la sección **Estados de ciclo de vida seleccionados**.
    - Para quitar un estado de ciclo de vida del modelo de ciclo de vida, selecciónelo en la sección **Estados de ciclo de vida seleccionados** y seleccione el botón de flecha izquierda ![flecha izquierda.](media/14-setup-for-work-orders.png) para moverlo a la sección **Estados del ciclo de vida restantes**.

6. Seleccione **Actualizaciones de estado de ciclo de vida** para definir los estados de ciclo de vida que pueden seguir un estado de ciclo de vida seleccionado.
7. En la ficha desplegable **Actualizaciones**, en el campo **Estado programado**, seleccione el estado del ciclo de vida que debe seleccionarse siempre para un pedido de trabajo cuya programación de la orden de trabajo se ha completado, independientemente del estado del ciclo de vida anterior de la orden de trabajo.
8. En el campo **Estado no programado del ciclo de vida**, seleccione el estado del ciclo de vida que debe seleccionar siempre para un pedido de trabajo si se elimina la programación de la orden de trabajo.
9. Guarde el modelo del ciclo de vida de la orden de trabajo.

![Página Modelos de ciclo de vida de orden de trabajo.](media/15-setup-for-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]