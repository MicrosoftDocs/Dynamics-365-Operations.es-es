---
title: Slotting de almacén
description: En este tema se proporciona información acerca del slotting de almacén. El slotting de almacén le permite consolidar la demanda por artículo y unidad de medida de los pedidos que tienen un estado de Pedido, Reservado o Liberado. Ayuda a los directores de almacén a planificar de manera inteligente las ubicaciones de picking antes de liberar pedidos al almacén y crear trabajos de picking.
author: mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: f6764f8bc082962af37d4775b6fe53d8704658eb
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597467"
---
# <a name="warehouse-slotting"></a>Slotting de almacén

[!include [banner](../includes/banner.md)]

El slotting de almacén le permite consolidar la demanda por artículo y unidad de medida de los pedidos que tienen un estado de *Pedido*, *Reservado* o *Liberado*. La demanda generada se puede aplicar a las ubicaciones que se utilizarán para el picking, en función de la cantidad, la unidad, las dimensiones físicas, las ubicaciones fijas y más. Una vez que se ha establecido el plan de slotting, se puede crear un trabajo de reabastecimiento para llevar la cantidad adecuada de inventario a cada ubicación.

Esta funcionalidad ayuda a los directores de almacén a planificar de manera inteligente las ubicaciones de picking antes de liberar pedidos al almacén y crear trabajos de picking.

## <a name="turn-on-the-warehouse-slotting-feature"></a>Activar la característica de slotting de almacén

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de característica:** *Característica de slotting de almacén*

## <a name="set-up-warehouse-slotting"></a>Configurar slotting de almacén

Antes de utilizar el slotting de almacén, debe configurar los siguiente elementos en su sistema.

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

A continuación, debe configurar el encabezado de la plantilla, las especificaciones de slotting y las directivas de ubicación, como se explica en las subsecciones siguientes.

#### <a name="set-up-a-slotting-template-header"></a>Configurar un encabezado de plantilla de slotting

1. En el encabezado de la plantilla, establezca los siguientes valores:

    - **Plantilla de slotting:** _61_
    - **Descripción:** _61_
    - **Tipo de demanda:** *Pedido de ventas*

        Actualmente, *Pedido de ventas* es el único tipo de demanda que se admite.

    - **Estrategia de demanda:** _Pedido_

        Los siguientes valores están disponibles en este campo:

        - **Pedido**: la cantidad pedida completa en el pedido de ventas debe considerarse demanda.
        - **Reservado**: solo las cantidades de la línea de pedido de ventas que se reservan (físicas y pedidas) deben considerarse demanda.

    - **Almacén**: _61_
    - **Permitir demanda de oleadas para usar cantidades sin reservar:** _sí_

También puede especificar una consulta para reducir el alcance de la demanda que se evalúa.

#### <a name="set-up-slotting-specifications-for-each-template"></a>Configurar especificaciones de slotting para cada plantilla

Para cada plantilla que cree, siga estos pasos para agregar una línea para cada especificación de slotting.

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

        Este campo define las unidades de medida de demanda que son válidas para la línea. (Para obtener más información, consulte la sección [Configurar niveles de unidad de medida para slotting](#unit-tiers) que se indica previamente en este tema.)

    - **Asignar criterios de posición:** _Considere la cantidad_

        Los siguientes valores están disponibles en este campo:

        - **Asumir vacío**: este sistema debe asumir que todas las ubicaciones en el área de picking están vacías y no debe comprobar esas ubicaciones para el inventario.
        - **Considerar cantidad**: el sistema debe comprobar las ubicaciones en el área de picking para el inventario y no debe omitir las ubicaciones que estén vacías.

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

##### <a name="configure-the-location-directives-fasttab"></a>Configurar la ficha desplegable Directivas de ubicación

1. En la ficha desplegable **Directivas generales**, establezca los valores siguientes. Acepte los valores predeterminados para el resto de campos.

    - **Tipo de trabajo**: _Recoger_
    - **Sitio**: _6_
    - **Almacén**: _61_
    - **Código de directiva:** _Slotting_

1. Seleccione **Guardar** para tener disponible la ficha desplegable **Líneas**.

##### <a name="configure-the-lines-fasttab"></a>Configurar la ficha desplegable Líneas

1. En la ficha desplegable **Líneas**, seleccione **Nuevo** para crear una línea.
1. En la nueva línea, establezca los siguientes valores. Acepte los valores predeterminados para el resto de campos.

    - **Cantidad inicial**: _0_
    - **Cantidad final**: _1000000_

1. Seleccione **Guardar** para tener disponible la ficha desplegable **Acciones directivas de ubicación**.

##### <a name="configure-the-location-directive-actions-fasttab"></a>Configurar la ficha desplegable Acciones de directiva de ubicación

1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Nuevo** para crear una línea.
1. En la nueva línea, establezca los siguientes valores. Acepte los valores predeterminados para el resto de campos.

    - **Nombre:** _Masivo_
    - **Estrategia:** _Ninguna_

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

Para trabajar en este escenario mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar. Además, también debe seleccionar la entidad legal **USMF** antes de empezar.

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

El plan de slotting muestra la ubicación a la que se asignó cada artículo/cantidad, si se usó el desbordamiento, si se creó el trabajo de interrupción y la línea de plantilla que se usó. **Las demandas a las que no se pudo crear una posición se resaltan en rojo.**

- En el panel de acciones, seleccione **Plan de slotting** para ver los resultados.

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
