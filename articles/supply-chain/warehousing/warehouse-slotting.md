---
title: Slotting de almacén
description: En este artículo se proporciona información acerca del slotting de almacén. El slotting de almacén le permite consolidar la demanda por artículo y unidad de medida de los pedidos que tienen un estado de Pedido, Reservado o Liberado. Ayuda a los directores de almacén a planificar de manera inteligente las ubicaciones de picking antes de liberar pedidos al almacén y crear trabajos de picking.
author: Mirzaab
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSInventFixedLocation, WHSSlotDemandLocated, WHSSlotDemand, WHSSlotUOMTier, WHSSlotTemplate, WHSLocDirHint, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: d319a1130facbc2988cc074960e6cdfbe053a2d6
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "9218956"
---
# <a name="warehouse-slotting"></a>Slotting de almacén

[!include [banner](../includes/banner.md)]

Se encuentran disponibles varias funciones de asignación de posiciones en el almacén para ayudar a los gerentes de almacén a planificar de manera inteligente las ubicaciones de picking antes de entregar los pedidos al almacén y crear el trabajo de picking.

La *característica de slotting de almacén* le permite consolidar la demanda por artículo y unidad de medida de los pedidos que tienen un estado de *Pedido*, *Reservado* o *Liberado*. La demanda generada se puede aplicar a las ubicaciones que se utilizarán para el picking, en función de la cantidad, la unidad, las dimensiones físicas, las ubicaciones fijas y más. Una vez que se ha establecido el plan de slotting, se puede crear un trabajo de reabastecimiento para llevar la cantidad adecuada de inventario a cada ubicación.

La función *Posicionamiento de almacén para órdenes de transferencia* permite a los gerentes de almacén reabastecer las ubicaciones de preparación de pedidos, según la demanda de los pedidos de transferencia que aún no se entregan al almacén. Asegura que las ubicaciones de picking incluyan todos los artículos que se requieren para las órdenes de transferencia después de que se entregan al almacén. Esta función requiere que también active la *Función de posicionamiento de almacén*.

La función *Mejoras en la asignación de espacios en el almacén* agrega una opción para las líneas de plantilla que son utilizadas por la *Función de posicionamiento de almacén*. La opción permite que el sistema considere el inventario disponible existente en una ubicación objetivo. Por lo tanto, se podrían generar menos reposiciones para la asignación. La función *Mejoras en la asignación de espacios en el almacén* requiere que también active la *Función de slotting de almacén*. Opcionalmente se puede utilizar junto con la característica *Posicionamiento de almacén para órdenes de transferencia*.

## <a name="turn-on-the-warehouse-slotting-features"></a>Activar las características de slotting de almacén

Antes de poder usar estas características, deben estar activadas en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de estas características y activarlas si es necesario. Active las siguientes funciones según sea necesario:

- Función de asignación de almacén
- Slotting de almacén para pedidos de transferencia

    > [!IMPORTANT]
    > La *Función de posicionamiento de almacén* debe estar activada antes de esta función.

- Mejoras de asignación de slotting de almacén

    > [!IMPORTANT]
    > La *Función de posicionamiento de almacén* debe estar activada antes de esta función.

## <a name="set-up-warehouse-slotting"></a>Configurar slotting de almacén

Antes de utilizar el slotting de almacén, debe configurar los siguiente elementos en su sistema:

- Niveles de unidad de medida de slotting
- Códigos de directiva
- Plantillas de slotting
- Directivas de ubicación

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a>Crear niveles de unidad de medida para slotting

Los niveles de unidad de medida permiten agrupar varias unidades de medida a efectos de slotting. Por ejemplo, si se seleccionan varios tamaños de cajas de la misma área de picking de cajas, se puede crear un nivel para todos los tamaños. **Se debe crear una línea para cada unidad de medida que debe formar parte del nivel.**

1. Vaya a **Gestión de almacenes \> Configuración \> Reabastecimiento \> Niveles de unidad de medida de slotting**.
1. Seleccione **Nuevo**.
1. Establezca los siguientes valores en el encabezado:

    - **Nivel de unidad de medida:** *EaBoxPl*
    - **Descripción:** *cada pallet de cajas*

1. Seleccione **Guardar**.
1. En la ficha desplegable **Unidades de medida**, seleccione **Nuevo** para agregar una línea a la cuadrícula.
1. En la nueva línea, establezca los siguientes valores:

    - **Unidad:** *caja*
    - **Descripción**: deje este campo en blanco. Se rellenará automáticamente cuando guarde los cambios.
    - **Clase de unidad:** *cantidad*

1. Seleccione **Nuevo** para agregar una segunda línea a la cuadrícula.
1. En la nueva línea, establezca los siguientes valores:

    - **Unidad**: *u*
    - **Descripción**: deje este campo en blanco. Se rellenará automáticamente cuando guarde los cambios.
    - **Clase de unidad:** *cantidad*

1. Seleccione **Nuevo** para agregar una tercera línea a la cuadrícula.
1. En la nueva línea, establezca los siguientes valores:

    - **Unidad:** *PL*
    - **Descripción**: deje este campo en blanco. Se rellenará automáticamente cuando guarde los cambios.
    - **Clase de unidad:** *Cantidad*

1. Seleccione **Guardar** para guardar el nivel.

### <a name="create-a-directive-code-for-slotting"></a>Crear un código de directiva para slotting

Debe seleccionar el código de directiva que debe asociarse a una plantilla.

1. Vaya a **Gestión de almacenes \> Configurar \> Códigos de directivas**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el campo **Código de la directiva**, introduzca *Slotting*.
1. En el campo **Descripción de la directiva**, introduzca *Slotting*.

### <a name="set-up-slotting-templates"></a>Configurar plantillas de slotting

Cada plantilla de slotting controla cómo se asigna el inventario a las ubicaciones de un determinado almacén. Cada plantilla debe incluir una línea para cada especificación de slotting. Use los procedimientos de esta sección para configurar plantillas de slotting.

1. Vaya a **Administración de almacenes \> Configurar \> Reabastecimiento \> Plantillas de reabastecimiento**.
1. Seleccione **Nuevo** para crear una página.

A continuación, debe configurar el encabezado de la plantilla, las especificaciones de slotting y las directivas de ubicación, como se explica en las subsecciones siguientes. La configuración de asignación para órdenes de transferencia se parece a la configuración para asignación de órdenes de venta, pero el campo **Tipo de demanda** está configurado como *Órdenes de transferencia* en lugar de *Órdenes de venta*.

#### <a name="set-up-the-header-for-a-sales-order-slotting-template"></a>Configurar el encabezado para una plantilla de asignación de pedidos de ventas

1. En el encabezado de la plantilla, establezca los siguientes valores:

    - **Plantilla de slotting:** _61_
    - **Descripción:** _61_
    - **Tipo de demanda:** *Pedido de ventas*

        > [!NOTE]
        > Actualmente, *Ordenes de venta* y *Órdenes de transferencia* son los únicos tipos de demanda admitidos. Puede elegir *Órdenes de transferencia* solo si la función *Slotting de almacén para órdenes de transporte* está activada.

    - **Estrategia de demanda:** _Pedido_

        Los siguientes valores están disponibles en este campo:

        - **Pedido**: la cantidad pedida completa en el pedido de ventas debe considerarse demanda.
        - **Reservado**: solo las cantidades de la línea de pedido de ventas que se reservan (físicas y pedidas) deben considerarse demanda.
        - **Liberado** - La cantidad liberada debe considerarse demanda.

    - **Almacén**: _61_
    - **Permitir demanda de oleadas para usar cantidades sin reservar:** _sí_

También puede especificar una consulta para reducir el alcance de la demanda que se evalúa.

#### <a name="set-up-slotting-specifications-for-each-template"></a>Configurar especificaciones de slotting para cada plantilla

Para cada plantilla de pedido de ventas que cree, siga estos pasos para agregar una línea para cada especificación de slotting.

1. En la ficha desplegable **Detalles de plantilla de slotting**, seleccione **Nuevo** para crear una línea de plantilla.
1. En la nueva línea, establezca los siguientes valores:

    - **Secuencia**: _1_
    - **Descripción:** _Ubicación fija_
    - **Cantidad mínima**: _1_

        Este campo define la cantidad mínima de demanda que se requiere para la línea.

    - **Cantidad máxima:** _1000000_

        Este campo define la cantidad máxima de demanda que es válida para la línea.

    - **Unidad:** deje este campo en blanco.

        Este campo define la unidad de medida a la que hacen referencia las cantidades mínima y máxima.

    - **Nivel de unidad de medida:** _EaBoxPl_

        Este campo define las unidades de medida de demanda que son válidas para la línea. (Para obtener más información, consulte la sección [Configurar niveles de unidad de medida para slotting](#unit-tiers) que se indica previamente en este artículo.)

    - **Asignar criterios de posición:** _Considere la cantidad_

        Los siguientes valores están disponibles en este campo:

        - **Asumir vacío**: este sistema debe asumir que todas las ubicaciones en el área de picking están vacías y no debe comprobar esas ubicaciones para el inventario.
        - **Considerar cantidad**: el sistema debe comprobar las ubicaciones en el área de picking para el inventario y no debe omitir las ubicaciones que estén vacías.
        - **Considerar disponible** - El sistema debe verificar si alguna ubicación de destino contiene cantidades no reservadas para el artículo en la línea de demanda. Si la cantidad es lo suficientemente grande para satisfacer al menos una unidad de la línea de demanda, el registro del plan de distribución generado se reduce por la cantidad disponible. Por ejemplo, si la demanda es de 10 cajas y hay una caja disponible, la demanda localizada será de nueve cajas. Si la demanda es de 10 cajas y hay una caja de cada disponible, la demanda localizada será de 10 cajas. Este valor solo está disponible cuando la función *Mejoras de asignación de slotting de almacén* está activada.

    - **Código de directiva:** _Slotting_

        Este campo define la directiva de ubicación que se utiliza para encontrar la ubicación de picking del trabajo de reabastecimiento.

    - **Ubicación de desbordamiento:** deje este campo en blanco.

        Este campo define la ubicación en la que se coloca el inventario si no se puede encontrar una ubicación para la cantidad cuando se procesa la línea.

    - **Permitir interrupción:** _Sí_

        Cuando esta opción se establece en *Sí*, si no se puede crear la posición de ninguna demanda, se creará un trabajo de movimiento para sacar el inventario de las ubicaciones donde hay inventario, pero donde no se creó la posición de nada. La plantilla se ejecuta de nuevo. Esta vez, ignora el inventario en las ubicaciones. Esta funcionalidad funciona mejor cuando el campo **Asignar criterios de posición** se establece en _Considerar cantidad_.

    - **Uso de ubicaciones fijas:** _Solo ubicaciones fijas para el producto_

        Los siguientes valores están disponibles en este campo:

        - **Ubicaciones fijas y no fijas**: el sistema no debe limitarse a usar solo ubicaciones fijas.
        - **Solo ubicaciones fijas para el producto:** el sistema debe colocarse solo en ubicaciones que son ubicaciones fijas para el producto.
        - **Solo ubicaciones fijas para la variante del producto:** el sistema debe colocarse solo en ubicaciones que son ubicaciones fijas para la variante del producto.

> [!NOTE]
> Si la plantilla de ranuras contiene al menos una línea donde el campo **Asignar criterios de espacio** está configurado en *Considerar disponible*, las pausas ya no están permitidas para ninguna línea en la plantilla.

1. Seleccione **Guardar**.
1. Seleccione **Nuevo** para crear una segunda línea de plantilla.
1. En la nueva línea, establezca los siguientes valores:

    - **Secuencia**: _2_
    - **Descripción:** _Otro_
    - **Cantidad mínima:** _1_
    - **Cantidad máxima:** _1000000_
    - **Unidad:** deje este campo en blanco.
    - **Nivel de unidad de medida:** _EaBoxPl_
    - **Asignar criterios de posición:** _Considere la cantidad_
    - **Código de directiva:** _Slotting_
    - **Ubicación de desbordamiento:** deje este campo en blanco.
    - **Permitir interrupción:** _Sí_
    - **Usar ubicaciones fijas:** _Ubicaciones fijas y no fijas_

    En la consulta de la segunda línea, ahora especificará los criterios que se utilizan para determinar a qué ubicaciones se puede crear la posición de la demanda para esa línea.

1. Seleccione la línea donde el campo **Secuencia** se establece en *2*.
1. Seleccione **Editar consulta**.
1. En la ficha **Rango**, seleccione **Nuevo** para agregar una línea a la cuadrícula.
1. En la nueva línea, establezca los siguientes valores:

    - **Tabla**: *Ubicaciones*
    - **Tabla derivada:** *Ubicaciones*
    - **Campo**: *ID de perfil de ubicación*
    - **Criterios:** *Pick-06* (Seleccione el signo más doble \[**++**\] en el campo para expandir la lista y luego seleccione *Pick-06* - *Sitio de picking 6*.)

1. Seleccione **Aceptar**.

#### <a name="set-up-location-directives"></a>Configurar directivas de ubicación

Se debe configurar al menos una directiva de ubicación para admitir selecciones de slotting. Use los procedimientos de esta sección para configurar una nueva *directiva de ubicación de reabastecimiento* para selecciones de slotting.

1. Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.
1. En el panel izquierdo, en el campo **Tipo de orden de trabajo**, seleccione *Reabastecimiento*.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el encabezado de la nueva directiva de ubicación, en el campo **Nombre**, introduzca *61 Selección de slotting*.
1. En el campo **Número de secuencia**, acepte el valor predeterminado.

##### <a name="configure-the-location-directives-fasttab"></a>Configurar la ficha desplegable Directivas de ubicación

1. En la ficha desplegable **Directivas generales**, establezca los valores siguientes. Acepte los valores predeterminados para el resto de campos.

    - **Tipo de trabajo**: _Recoger_
    - **Sitio**: _6_
    - **Almacén**: _61_
    - **Código de directiva:** _Slotting_

1. Seleccione **Guardar** para tener disponible la ficha desplegable **Líneas**.

##### <a name="configure-the-lines-fasttab"></a>Configurar la ficha desplegable Líneas

1. En la ficha desplegable **Líneas**, seleccione **Nuevo** para crear una línea.
1. En la nueva línea, establezca los siguientes valores.

    - **Cantidad inicial**: _0_
    - **Cantidad final**: _1000000_

1. Acepte los valores predeterminados del resto de campos.
1. Seleccione **Guardar** para tener disponible la ficha desplegable **Acciones directivas de ubicación**.

##### <a name="configure-the-location-directive-actions-fasttab"></a>Configurar la ficha desplegable Acciones de directiva de ubicación

1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Nuevo** para crear una línea.
1. En la nueva línea, establezca los siguientes valores. Acepte los valores predeterminados para el resto de campos.

    - **Número de secuencia:** acepte el valor predeterminado.
    - **Nombre:** _Masivo_
    - **Estrategia:** _Ninguna_

1. Acepte los valores predeterminados del resto de campos.
1. Seleccione **Guardar** para que hacer que el botón **Editar consulta** esté disponible.

##### <a name="edit-the-query"></a>Editar la consulta

1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Editar consulta**.
1. En la ficha **Rango**, seleccione **Nuevo** para agregar una línea a la cuadrícula.
1. En la nueva línea, establezca los siguientes valores:

    - **Tabla**: *Ubicaciones*
    - **Tabla derivada:** *Ubicaciones*
    - **Campo**: *ID de zona*
    - **Criterios:** *Masivo* (Seleccione el signo más doble \[**++**\] en el campo para expandir la lista y luego seleccione *Masivo*.)

1. Seleccione **Aceptar**.

## <a name="scenario"></a>Situación

### <a name="set-up-the-scenario"></a>Configuración el escenario

Para este escenario, use los datos de muestra integrados y cree los registros que se describen en esta sección.

#### <a name="use-the-usmf-sample-data"></a>Utilice los datos de muestra de USMF

Para trabajar en este escenario mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/fin-ops/get-started/demo-data.md) estándar. Además, también debe seleccionar la entidad legal **USMF** antes de empezar.

#### <a name="create-demand"></a>Crear demanda

Siga estos pasos para crear la demanda a la que aplicará el slotting.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Seleccione **Nuevo** para crear un pedido de ventas.
1. En el cuadro de diálogo **Crear pedido de ventas**, en el campo **Cuenta de cliente**, seleccione _US-007_.
1. En el campo **Almacén**, seleccione _61_.
1. Seleccione **Aceptar**.
1. Se abre el nuevo pedido de ventas. Incluye una línea vacía en la ficha desplegable **Líneas de pedido de ventas**. En esta línea, establezca los siguientes valores:

    - **Artículo**: _L0101_
    - **Cantidad:** _20_

1. Seleccione **Agregar línea** para agregar una nueva línea y establecer los siguientes valores:

    - **Artículo**: _T0100_
    - **Cantidad:** _8_

1. Seleccione **Guardar**.
1. Seleccione **Nuevo** para crear un segundo pedido de ventas.
1. En el cuadro de diálogo **Crear pedido de ventas**, en el campo **Cuenta de cliente**, seleccione _US-008_.
1. En el campo **Almacén**, seleccione _61_.
1. Se abre el nuevo pedido de ventas. Incluye una línea vacía en la ficha desplegable **Líneas de pedido de ventas**. En esta línea, establezca los siguientes valores:

    - **Artículo**: _T0100_
    - **Cantidad:** _1_

1. Seleccione **Guardar**.

### <a name="walk-through-a-typical-slotting-scenario"></a>Recorrer un escenario típico de slotting

Una vez que todos los elementos de los requisitos previos estén en su lugar, como se describe en la sección anterior, estará listo para probar la característica trabajando en cada ejercicio de esta sección.

#### <a name="generate-demand"></a>Generar demanda

1. Vaya a **Gestión de almacén \> Configuración \> Reabastecimiento \> Plantillas de slotting** y seleccione la plantilla de slotting que creó anteriormente.
1. En el panel de acciones, seleccione **Generar demanda**. Este comando evalúa toda la demanda que hay en el sistema y que coincide con la consulta de plantilla de slotting. La demanda total en todos los pedidos se consolida en una línea por cantidad/unidad de medida. Aparece un mensaje informativo cuando se completa el proceso.

#### <a name="slotting-demand"></a>Demanda de slotting

La *demanda de slotting* muestra los resultados de la generación de demanda, en función de la configuración de la plantilla de slotting.

- En el panel de acciones, seleccione **Demanda de slotting** para ver los resultados del comando **Generar demanda**. Las líneas en la demanda de slotting se pueden editar. Puede eliminar una línea, agregar una nueva línea o editar los detalles de la línea.

> [!NOTE]
> Puede editar la demanda manualmente o puede importarla desde un sistema externo mediante la administración de datos. Cualquier artículo que esté en la demanda de slotting se utilizará en el siguiente paso, independientemente de su origen.

#### <a name="locate-demand"></a>Localizar demanda

Una vez que se ha generado la demanda, debe usar el comando **Localizar demanda** para generar el *plan de slotting*.

- En el panel de acciones, seleccione **Localizar demanda**. Se ejecuta el proceso de slotting. Aparece un mensaje informativo cuando se completa el proceso.

#### <a name="slotting-plan"></a>Asignar plan

El plan de slotting muestra la ubicación a la que se asignó cada artículo/cantidad, si se usó el desbordamiento, si se creó el trabajo de interrupción y la línea de plantilla que se usó. *Las demandas a las que no se pudo crear una posición se resaltan en rojo.*

- En el panel de acciones, seleccione **Plan de slotting** para ver los resultados.

> [!NOTE]
> - Los procesos **Generar demanda**, **Localizar demanda** y **Ejecutar reposición** ahora se ejecutan en un espacio aislado. (Estos procesos están disponibles en el Panel de acciones, en la página **Plantillas de posicionamiento**).
> - Los procesos **Generar demanda**, **Localizar demanda** y **Ejecutar reposición** tienen un bloqueo para garantizar que no se puedan activar al mismo tiempo. De lo contrario, los datos que se utilizan podrían eliminarse.
> - Los procesos **Generar demanda** y **Localizar demanda** muestran una advertencia si la ejecución no generó registros o si a los registros les falta información.
> - Cuando selecciona **Plan de posicionamiento**, la página no tiene los botones **Nuevo**, **Editar** o **Eliminar** en el Panel de acciones, porque el origen de datos no se puede editar.
> - Cuando selecciona **Ejecutar reposición**, el sistema valida la plantilla de ranura seleccionada y procesa.

#### <a name="create-replenishment"></a>Crear reabastecimiento

Una vez creado el plan de slotting, debe crear un *trabajo de reabastecimiento* basado en el plan.

- En el panel de acciones, seleccione **Ejecutar reabastecimiento**. Aparece un mensaje informativo cuando se completa el proceso. Este mensaje indica el número de encabezados que se crearon para el id. de creación de trabajo.

Las directivas de ubicación que se utilizarán se identifican en función del código de directiva que se especifica en cada línea de plantilla.

## <a name="tips"></a>Sugerencias

### <a name="set-up-automatic-slotting"></a>Configurar slotting automático

Una vez que todos los elementos requeridos estén en su lugar, puede configurar el slotting para que se ejecute automáticamente siguiendo estos pasos.

1. Vaya a **Gestión de almacenes \> Reabastecimiento \> Ejecutar slotting**.
1. Especifique los pasos de slotting que se van a ejecutar. Seleccione uno o varias de las siguientes pasos de slotting:

    - Generar demanda
    - Localizar demanda
    - Crear trabajo de reabastecimiento

    > [!NOTE]
    > Los pasos de slotting son progresivos. Si quiere seleccionar *Localizar demanda*, primero debe seleccionar *Generar demanda*.

1. Especifique la plantilla de slotting que va a utilizar.
1. Establezca la periodicidad para que se ejecute automáticamente, si lo desea.

Para los ejercicios del escenario, **no** configure el slotting automático.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]