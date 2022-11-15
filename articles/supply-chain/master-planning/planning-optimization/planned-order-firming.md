---
title: Poner en firme pedidos planificados
description: Este artículo explica cómo confirmar pedidos planificados. Cuando se confirman los pedidos planificados, se convierten en pedidos de compra, pedidos de transferencia o pedidos de producción reales.
author: t-benebo
ms.date: 08/09/2022
ms.search.form: ReqTransPo, ReqTransFirmLog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-04-22
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c2e4294cb54e9ba41467f505e361d5ee45f1f27d
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740532"
---
# <a name="firm-planned-orders"></a>Poner en firme pedidos planificados

[!include [banner](../../includes/banner.md)]

Los pedidos planificados deben ser *confirmados* (es decir, liberados) como parte del proceso de planificación maestra. Cuando se confirman los pedidos planificados, se convierten en pedidos de compra, pedidos de transferencia o pedidos de producción reales. Estos pedidos también se llaman *pedidos liberados* o *pedidos abiertos*.

Hay tres métodos para confirmar los pedidos planificados:

- **Confirmación manual**: seleccione pedidos planificados específicos en una lista y luego inicie manualmente el proceso.
- **Confirmación automática**: defina un límite de tiempo de confirmación predeterminado para grupos de cobertura, artículos individuales y combinaciones de artículos y planes maestros. Luego, durante las ejecuciones de planificación maestra, las órdenes planificadas se confirmarán automáticamente si la fecha del pedido se encuentra dentro del límite de tiempo especificado para la confirmación.
- **Confirmación basada en consulta**: defina una consulta para seleccionar pedidos planificados en función de sus propiedades. Puede configurar un trabajo por lotes para ejecutar la consulta y confirmar los pedidos coincidentes con programación regular.

Este artículo describe cada método en detalle.

## <a name="enable-the-features-that-are-described-in-this-article"></a><a name="enable-features"></a>Habilitar las funciones que se describen en este artículo

La mayoría de las funciones de pedidos planificados están disponibles en todas las instalaciones estándar de Microsoft Dynamics 365 Supply Chain Management. Sin embargo, algunas de las funciones que se describen en este artículo deben estar activadas en Administración de funciones antes de poder utilizarlas.

### <a name="turn-parallelized-firming-of-planned-orders-on-or-off"></a>Activar o desactivar la confirmación en paralelo de pedidos planificados

La confirmación en paralelo ayuda a acelerar el proceso de confirmación al paralelizarlo en varias conversaciones. Este enfoque puede resultar útil cuando se confirman muchos pedidos planificados. Para utilizar esta funcionalidad, la característica *Puesta en firme en paralelo de pedidos planificados* debe estar activada para su sistema. 

A partir de la versión 10.0.21 de Supply Chain Management, esta función está activada de forma predeterminada. A partir de la versión 10.0.25 de Supply Chain Management, esta característica es obligatoria y no se puede desactivar. Si está ejecutando una versión anterior a la 10.0.25, los administradores pueden activar o desactivar esta funcionalidad en [Administración de características](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y buscando la característica *Puesta en firme en paralelo de pedidos planificados*.

### <a name="turn-planned-order-firming-with-filtering-on-or-off"></a>Activar o desacivar la confirmación de pedidos planificados con filtrado

La confirmación de pedidos planificados con filtrado le permite definir criterios lógicos para seleccionar qué pedidos planificados confirmar. También puede obtener una vista previa de los pedidos planificados que se seleccionaron, ejecutar el proceso en segundo plano y/o programarlo como un trabajo por lotes.

Para usar esta característica, debe estar activada para su sistema. A partir de la versión 10.0.25 de Supply Chain Management, la característica está activada de forma predeterminada. A partir de la versión 10.0.29 de Supply Chain Management, la característica es obligatoria y no se puede desactivar. Si está ejecutando una versión anterior a la 10.0.29, los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Puesta en firme de pedido planificado con filtrado* en el espacio de trabajo [Administración de características](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="turn-auto-firming-for-planning-optimization-on-or-off"></a>Activar o desactivar la confirmación automática para Optimización de planificación

La puesta en firme automática permite confirmar los pedidos planificados como parte del proceso de planificación maestra durante el intervalo de tiempo de confirmación. La confirmación automática siempre es compatible con el motor de planificación integrado en Supply Chain Management. Sin embargo, para usarlo también con Optimización de planificación, debe activar la función.

A partir de la versión 10.0.21 de Supply Chain Management, esta función está activada de forma predeterminada. A partir de la versión 10.0.29 de Supply Chain Management, esta característica es obligatoria y no se puede desactivar. Si está ejecutando una versión anterior a la 10.0.29, los administradores pueden activar o desactivar esta funcionalidad en [Administración de características](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y buscando la característica *Puesta en firme automática para la Optimización de la planificación*.

## <a name="manually-firm-planned-orders"></a>Confirmar manualmente pedidos planificados

Para confirmar manualmente los pedidos planificados, busque y seleccione los pedidos planificados que desee confirmar y, a continuación, inicie manualmente el proceso de confirmación.

1. [Abrir página de lista de pedidos planificados](approved-planned-order.md#view-planned-orders).
1. Utilice el campo **Filtrar**, el campo **Plan** y los encabezados de columna para filtrar y ordenar la lista de modo que pueda encontrar los pedidos planificados que está buscando.
1. Seleccione la casilla para cada pedido planificado que desee confirmar. Si desea confirmar todos los pedidos planificados que se enumeran actualmente en la página (según los filtros que aplicó), omita este paso.
1. En el panel de acciones, seleccione uno de los siguientes botones:

    - **Confirmar**: confirme solo los pedidos planificados seleccionados.
    - **Confirmar todo**: confirme todos los pedidos planificados que se enumeran actualmente en la página (según los filtros que aplicó), independientemente de las casillas de verificación que estén seleccionadas. Esta opción resulta útil si está confirmando muchos pedidos planificados.

1. En el cuadro de diálogo **Confirmar**, en la ficha desplegable **Parámetros**, establezca los siguientes campos. (Muchos de estos campos toman sus valores predeterminados de la pestaña **Actualización estándar** en la página **Parámetros de planificación maestra**).

    - **Actualizar marcado**: seleccione la directiva de marcado del inventario que desea utilizar al confirmar los pedidos planificados.
    - **Dejar de confirmar si ocurre un error**; establezca esta opción en *Sí* para dejar de confirmar todos los pedidos planificados seleccionados si se produce un error en uno de ellos. Esta opción debe establecerse en *No* si la opción **Parlelizar confirmación** está configurada en *Sí*.
    - **Confirmación paralelizada**: esta opción está disponible solo si la [Función *Confirmación paralela de pedidos planificados*](#enable-features) está activada para su sistema, y si ha seleccionado dos o más pedidos planificados para confirmar. Establézcala en *Sí* para ejecutar los procesos de confirmación en paralelo. La confirmación en paralelo puede ayudar a mejorar el rendimiento.
    - **Number of subprocesos**: esta opción está disponible solo si la [Función *Confirmación paralela de pedidos planificados*](#enable-features) está activada para su sistema, y si ha seleccionado la opción **Confirmación en paralelo** en *Sí*. Introduzca el el número de subprocesos que se utilizarán para paralelizar el proceso de confirmación. Para obtener consejos sobre cómo utilizar esta opción en la planificación maestra, consulte [Mejorar el rendimiento de la planificación maestra](../master-planning-performance.md#number-of-threads).

        > [!NOTE]
        > Un valor de *0* (cero) para el campo **Número de subprocesos** aumenta el tiempo de ejecución de la planificación maestra. Por lo tanto, recomendamos que siempre establezca este campo en un valor que sea superior a 0.

    - **Agrupar por proveedor**: establezca esta opción en *Sí* para agrupar pedidos de compra planificadas y crear un pedido de compra por proveedor durante la confirmación. También puede crear un pedido de compra que tenga una línea para cada pedido planificado.
    - **Agrupar por grupo de compradores**: establezca esta opción en *Sí* para agrupar los pedidos de compra planificados y crear un pedido de compra que combine el grupo de compradores y de proveedores. Para utilizar esta opción, también debe seleccionar la opción **Agrupar por proveedor** en *Sí*.
    - **Agrupar por acuerdo de compra**: establezca esta opción en *Sí* para agrupar órdenes de compra planificadas que tienen el mismo proveedor que los acuerdos de compra existentes y crear una orden de compra por acuerdo de compra. Esta opción se habilita automáticamente cuando **Agrupar por proveedor** está habilitado. Para usar **Agrupar por acuerdo de compra**, **Encontrar acuerdo de compra** debe establecerse en *Sí* en la página **Parámetros de planificación maestra**.
    - **Agrupar por período** (en la sección **Pedidos de compra**): seleccione el período por el que agrupar los pedidos de compra planificados. Para utilizar esta opción, también debe seleccionar la opción **Agrupar por proveedor**.
    - **Agrupar por período** (en la sección **Transferencias**): seleccione el período por el que agrupar los pedidos de transferencia planificados. Los pedidos se agruparán en función de los valores **Desde el almacén** y **Al almacén**.

    > [!NOTE]
    > Cada una de las opciones de "Agrupar por" hace que el sistema convierta cada orden planificada en una línea en la orden de compra única que resulta de la agrupación.

    ![Ficha desplegable Parámetros en el cuadro de diálogo Confirmación.](./media/manual-firming.png "Ficha desplegable Parámetros en el cuadro de diálogo Confirmación")

1. En la ficha desplegable **Ejecutar en segundo plano**, configure el trabajo para que se ejecute en modo por lotes. Sin embargo, no tiene sentido establecer una programación periódica si está haciendo confirmación manual. Los campos funcionan igual que para otros tipos de [trabajos en segundo plano](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) en Supply Chain Management. Sin embargo, para confirmación manual, el trabajo por lotes procesará solo los pedidos planificados seleccionados actualmente. No procesará ningún pedido que se ajuste a los filtros que se aplican actualmente en la página.
1. Seleccione **Aceptar** para aplicar su configuración y generar los pedidos confirmados.

## <a name="auto-firm-planned-orders"></a>Confirmación automática de pedidos planificados

La confirmación automática permite confirmar los pedidos planificados como parte del proceso de planificación maestra. Puede definir un límite de tiempo de confirmación predeterminado para grupos de cobertura, artículos individuales y combinaciones de artículos y planes maestros. Luego, durante las ejecuciones de planificación maestra, las órdenes planificadas se confirmarán automáticamente si la fecha del pedido se encuentra dentro del límite de tiempo especificado para la confirmación. Los pedidos planificados que se generan mediante Optimización de planificación y el motor de planificación maestra incorporada manejan la fecha del pedido (es decir, la fecha de inicio) de manera diferente.

> [!NOTE]
> La confirmación automática de los pedidos de compra planificados solo puede producirse para artículos asociados a un proveedor.
> 
> Los pedidos derivados (es decir, pedidos de compra subcontratados) que estén confirmados mostrarán un estado de *En revisión* cuando el seguimiento de cambios esté habilitado.

> [!IMPORTANT]
> Antes de que la función que se describe en esta sección se pueda utilizar con Optimización de planificación, la [función *Confirmación automática de Optimización de planificación*](#enable-features) debe estar activada para su sistema, como se describe al principio de este artículo. La confirmación automática siempre se puede utilizar con el motor de planificación maestra en desuso.

### <a name="auto-firming-with-planning-optimization-vs-the-deprecated-master-planning-engine"></a>Confirmación automática con Optimización de planificación frente al motor de planificación maestra en desuso

La Optimización de planificación y el motor de planificación maestra en desuso pueden utilizarse para confirmación automática de pedidos planificados. Sin embargo, existen algunas diferencias importantes. Por ejemplo, mientras que Optimización de planificación utiliza la fecha del pedido (es decir, la fecha inicial) para determinar qué pedidos planificados confirmar, el motor de planificación maestra en desuso usa la fecha de requisito (es decir, la fecha final). En la tabla siguiente se resumen las diferencias.

| Característica | Optimización de planificación | Motor de planificación maestra en desuso |
|---|---|---|
| **Base de fecha** | La puesta en firme automática se basa en la fecha del pedido (fecha inicial). | La puesta en firme automática en la fecha de requisito (fecha final). |
| **Plazo** | Dado que la fecha del pedido (fecha inicial) activa la puesta en firme, no tiene que tener e cuenta el plazo como parte del límite de tiempo de la puesta en firme. | Para ayudar a garantizar que los pedidos se confirmen puntualmente, el límite de tiempo de confirmación debe ser superior al plazo. |
| **Pedidos de la semana actual** | Para confirmar todos los pedidos que deben iniciarse durante la semana actual, el límite de tiempo de la confirmación debe ser de una semana. | Para confirmar todos los pedidos que deben iniciarse durante la semana actual, el límite de tiempo de confirmación debe ser el plazo más una semana. |

### <a name="set-up-auto-firming-and-the-firming-time-fence"></a>Configurar la confirmación automática y el límite de tiempo de confirmación

Puede activar la confirmación automática asignando un límite de tiempo de confirmación automático a la configuración de cobertura relevante, como se describe más adelante en esta sección. Si la confirmación automática no está activada para ninguna configuración de cobertura, o si la planificación se inicia desde una página específica, como la página **Requisitos netos** de un producto lanzado, se omite el proceso de reafirmación automática.

Las opciones de agrupamiento y marcado para confirmación automática toman sus valores de la pestaña **Actualización estándar** de la página **Parámetros de planificación maestra**.

El límite de tiempo de confirmación automática se define por la cantidad de días que introduce para la configuración de cobertura relevante. Puede activar la confirmación automática y controlar el límite de tiempo de confirmación de las siguientes formas:

- Para definir el límite de tiempo de confirmación predeterminado para un grupo de cobertura, vaya a **Planificación maestra \> Configuración \> Cobertura \> Grupos de cobertura**, y seleccione un grupo de cobertura. A continuación, en la pestaña desplegable **Otro**, en el campo **Límite de tiempo de puesta en firme automática (días)**, especifique el número de días.
- Para sobrescribir el límite de tiempo de confirmación que se define para el grupo de cobertura para un artículo específico, vaya a **Gestión de la información del producto \> Productos liberados**. En el panel de acciones, seleccione **Plan** y, a continuación, seleccione **Cobertura de artículos**. A continuación, en la pestaña **General**, seleccione **Sobrescribir límite de tiempo** y en el campo **Límite de tiempo de confirmación automática (días)**, especifique el número de días.
- Para sobrescribir el límite de tiempo de confirmación que se define para el grupo de cobertura y la cobertura de artículos para un plan maestro específico, vaya a **Planificación maestra \> Configuración \> Planes maestros** y seleccione un plan maestro. A continuación, en la pestaña desplegable **Límite de tiempo en días**, establezca la opción **Confirmación** en *Sí* y escriba el número de días.

Si establece todos los límites de tiempo mencionados anteriormente en *0* (cero), la confirmación automática queda efectivamente deshabilitada para los artículos cubiertos relevantes.

## <a name="firm-planned-orders-by-using-a-query"></a>Confirmar pedidos planificados mediante una consulta

La confirmación basada en consultas le permite planificar la confirmación en función de criterios que se definen de antemano. A diferencia de la confirmación automática, la confirmación basada en consultas permite la confirmación automática de diferentes subconjuntos de pedidos en diferentes momentos. Además, puede utilizar operaciones manuales o automatizadas para confirmar diferentes tipos de pedidos planificados. También puede obtener una vista previa de los pedidos confirmados seleccionados en función de su configuración. Por lo tanto, puede confirmar que la selección se ajusta a sus expectativas.

Puede combinar la confirmación automática con la confirmación basada en consultas. Por ejemplo, un trabajo de confirmación basado en consultas tiene un límite de tiempo hacia adelante que es más largo que el límite de tiempo para una configuración de cobertura de confirmación automática coincidente. Por lo tanto, el trabajo de confirmación basado en consultas procesará sus pedidos planificados antes de que se desencadene la confirmación automática. Puede aprovechar este comportamiento para programar pedidos para proveedores específicos de manera diferente a los pedidos de productos similares de otros proveedores.

> [!IMPORTANT]
> Antes de que la función que se describe en esta sección se pueda utilizar, la [función *Confirmación de pedidos planificados con fitrado*](#enable-features) debe estar activada para su sistema, como se describe al principio de este artículo.

Para confirmar un pedido planificado mediante el proceso de confirmación basado en consultas, siga estos pasos.

1. Vaya a **Planificación maestra \> Planificación maestra \> Ejecutar \> Confirmación de pedidos planificados**.
1. En el cuadro de diálogo **Confirmación de pedidos planificados** en la ficha desplegable **Parámetros** , establezca las opciones básicas de procesamiento, marcado y agrupación. Estas opciones funcionan igual que en el cuadro de diálogo **Confirmación**. (Consulte la sección anterior para obtener descripciones). Luego, en la sección **Plan**, configure los siguientes campos que son exclusivos del cuadro de diálogo **Confirmación de pedidos planificados**:

    - **Plan**: seleccione el plan maestro que se debe aplicar durante la confirmación de los pedidos planificados que se encuentran en esta consulta.
    - **Días hacia adelante del límite de tiempo de confirmación**: seleccione hasta qué punto del futuro la planificación maestra debe calcular los distintos requisitos y otras consideraciones.
    - **Días hacia atrás del límite de tiempo de confirmación**: seleccione hasta qué punto del pasado la planificación maestra debe calcular los distintos requisitos y otras consideraciones.

    ![Ficha desplegable Parámetros en el cuadro de diálogo Confirmación de pedidos planificados.](./media/planned-order-firming-main-1.png "Ficha desplegable Parámetros en el cuadro de diálogo Confirmación de pedidos planificados")

1. Para especificar qué registros deben incluirse en el pedido, seleccione el botón **Filtrar** en la ficha desplegable **Registros a incluir**. Aparece un cuadro de diálogo de consulta estándar, donde puede definir criterios de selección, criterios de clasificación y combinaciones. Los campos funcionan igual que para otros tipos de consultas en Supply Chain Management. Los campos aquí son de solo lectura y muestran valores relacionados con su consulta.

    ![Ficha desplegable Registros a incluir en el cuadro de diálogo Confirmación de pedidos planificados.](./media/planned-order-firming-main-2.png "Ficha desplegable Registros a incluir en el cuadro de diálogo Confirmación de pedidos planificados")

1. Seleccione **Vista previa** para obtener una vista previa del contenido de su pedido confirmado, según su configuración hasta el momento. La lista de pedidos planificados que se confirmarán se muestra como un mensaje. A continuación, puede ajustar la configuración según sea necesario hasta que la vista previa muestre el pedido confirmado como lo desea.

    ![Ejemplo de vista previa de un pedido confirmado.](./media/planned-order-firming-preview.png "Ejemplo de vista previa de un pedido confirmado")

    > [!WARNING]
    > Esta función confirmará todos los pedidos planificados que coincidan con los criterios del filtro. La confirmación no crítica de los pedidos planificados puede provocar la creación de un gran número de pedidos de compra, transferencia y producción no deseados. Antes de continuar, utilice siempre el botón **Vista previa** para validar los registros que se incluirán.

1. En la ficha desplegable **Ejecutar en segundo plano**, configure el trabajo para que se ejecute en modo por lotes y/o establezca una programación periódica. Los campos funcionan igual que o hacen para otros tipos de [trabajos en segundo plano](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) en Supply Chain Management.
1. Seleccione **Aceptar** para aplicar su configuración y generar los pedidos confirmados.

## <a name="track-firmed-orders"></a>Seguir pedidos confirmados

Para realizar un seguimiento de un pedido planificado que se ha confirmado, siga estos pasos.

1. [Abrir página de lista de pedidos planificados](approved-planned-order.md#view-planned-orders).
1. Abra o seleccione el pedido planificado que desee seguir.
1. En el panel de acciones, en la pestaña **Ver**, del grupo **Vista**, seleccione **Historial de confirmaciones**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
