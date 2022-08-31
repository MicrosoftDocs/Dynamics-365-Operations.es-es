---
title: Reabastecimiento de umbral de zona
description: El reabastecimiento basado en zonas utiliza una estrategia de reabastecimiento mínimo/máximo (mín./máx.), pero evalúa zonas de almacén completas en lugar de solo ubicaciones individuales. Por lo tanto, los directores de almacén pueden aprender más rápido cuándo se requiere un inventario adicional en una zona de picking.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocDirHint, WHSLocDirTable, WHSRequestType
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 44e7dfdbc980c5df6b9426515365611bc0de45c2
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335957"
---
# <a name="zone-threshold-replenishment"></a>Reabastecimiento de umbral de zona

[!include [banner](../includes/banner.md)]

El reabastecimiento basado en zonas utiliza una estrategia de [reabastecimiento](replenishment.md) mínimo/máximo (mín./máx.), pero evalúa zonas de almacén completas en lugar de solo ubicaciones individuales. Por lo tanto, los directores de almacén pueden aprender más rápido cuándo se requiere un inventario adicional en una zona de picking.

La configuración de esta característica se asemeja a la configuración del reabastecimiento basado en ubicaciones. Sin embargo, cuando configura una plantilla para un reabastecimiento mínimo/máximo, también puede especificar si el umbral debe evaluarse por ubicación o por zona. Si configura una evaluación basada en zonas, debe agregar zonas específicas a la consulta de selección de zona.

Al igual que el reabastecimiento mínimo/máximo basado en ubicaciones, el reabastecimiento mínimo/máximo basada en zonas se basa en la configuración de un umbral de inventario mínimo que desencadena la creación de un trabajo de reabastecimiento para los artículos seleccionados. Este trabajo de reabastecimiento aumentará el inventario hasta el umbral máximo especificado para la zona.

> [!NOTE]
> Los procesos de reabastecimiento de zona para variantes de producto no son compatibles con la versión actual.


A diferencia del reabastecimiento mínimo/máximo basado en ubicaciones, el reabastecimiento mínimo/máximo basado en zonas no requiere ubicaciones fijas para evaluar si las ubicaciones deben almacenar un determinado artículo. Por lo tanto, el reabastecimiento basado en zonas le permite utilizar el reabastecimiento mínimo/máximo incluso si no tiene ubicaciones fijas para cada artículo o variante de artículo en el almacén. Cuando una cantidad en la zona cae por debajo del umbral mínimo especificado, se crea un trabajo de reabastecimiento. Las directivas de ubicación determinarán en qué ubicación concreta se debe colocar el inventario.

## <a name="turn-on-the-zone-threshold-replenishment-feature"></a>Activar la característica de reabastecimiento de umbral de zona

Antes de poder usar la característica *Reabastecimiento de umbral de zona*, esta debe estar activada para su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de característica:** *Reabastecimiento de umbral de zona*

## <a name="set-up-zone-based-replenishment"></a><a name="setup"></a>Configurar reabastecimiento basado en zonas

Para configurar un reabastecimiento basada en zonas, debe configurar varias partes del sistema. Esta sección presenta las diversas configuraciones y proporciona valores de datos de demostración que puede introducir si desea trabajar en el escenario al final de este artículo.

### <a name="set-up-directive-codes"></a>Configurar códigos de directivas

Los [códigos de directivas](control-warehouse-location-directives.md) le permiten ser más específico cuando define la plantilla de ubicación que se utiliza en una plantilla de trabajo. Cada código establece un valor común al que puede hacer referencia cuando configura cada tipo de plantilla.

#### <a name="view-and-edit-directive-codes"></a>Ver y editar códigos de directivas

Para ver o editar sus códigos de directivas, vaya a **Gestión de almacenes \> Configuración \> Códigos de directivas**.

#### <a name="prepare-demo-data-directive-codes"></a>Preparar códigos de directivas de datos de demostración

En este ejemplo se muestra cómo preparar un código de directivas. Si tiene previsto trabajar en el escenario al final de este artículo, utilice los valores de datos de demostración que se proporcionan aquí. De lo contrario, utilice sus propios valores.

1. Seleccione la entidad jurídica **USMF** para trabajar con los datos de demostración.
1. Vaya a **Gestión de almacenes \> Configurar \> Códigos de directivas**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.
1. Establezca los siguientes valores en la fila nueva:

    - **Código de directiva:** _Reabastecimiento de zona_
    - **Descripción de la directiva:** _Reabastecimiento de zona_

1. Seleccione **Guardar** para guardar el nuevo código.

### <a name="set-up-replenishment-templates"></a>Configurar plantillas de reabastecimiento

Las [plantillas de reabastecimiento mínimo/máximo](tasks/set-up-min-max-replenishment-process.md) son el mecanismo principal para mantener niveles óptimos en ubicaciones de picking. En estas plantillas, debe configurar las reglas que se utilizarán para reabastecer el inventario en el almacén. El reabastecimiento para la que se pueden usar las plantillas incluye el reabastecimiento basado en zonas.

#### <a name="view-and-edit-replenishment-templates"></a>Ver y editar plantillas de reabastecimiento

Una plantilla de reabastecimiento es un conjunto de reglas que controlan cuándo y cómo se reabastece un ubicación. Seleccione una plantilla para controlar cuándo y cómo se realiza el reabastecimiento. Para ver o editar sus plantillas de reabastecimiento, vaya a **Gestión de almacén \> Configuración \> Reabastecimiento \> Plantillas de reabastecimiento**.

#### <a name="prepare-a-demo-data-replenishment-template"></a>Preparar una plantilla de reabastecimiento de datos de demostración

En este ejemplo se muestra cómo preparar una plantilla de reabastecimiento. Si tiene previsto trabajar en el escenario al final de este artículo, utilice los valores de datos de demostración que se proporcionan aquí. De lo contrario, utilice sus propios valores.

1. Seleccione la entidad jurídica **USMF** para trabajar con los datos de demostración.
1. Vaya a **Administración de almacenes \> Configurar \> Reabastecimiento \> Plantillas de reabastecimiento**.
1. Seleccione **Editar** para poner la página en modo de edición.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula **Visión general**.
1. Establezca los siguientes valores en la fila nueva. Acepte los valores predeterminados para el resto de campos.

    - **Plantilla de reabastecimiento:** _Reabastecimiento mín./máx. de zona_
    - **Descripción:** _Reabastecimiento mín./máx. de zona_
    - **Tipo de reabastecimiento:** _Mínimo o máximo_

1. Seleccione **Guardar**.
1. Mientras la nueva fila sigue seleccionada en la cuadrícula **Visión general**, seleccione **Nuevo** encima de la cuadrícula **Detalles de la plantilla de reabastecimiento** para agregar una fila asociada a la plantilla de reabastecimiento *Reabastecimiento mín./máx. de zona* que acaba de crear.
1. Establezca los siguientes valores en la fila nueva:

    - **Número de secuencia:** Introduzca _1_.
    - **Descripción:** Introduzca _Reabastecimiento de zona de picking_.
    - **Unidad de reabastecimiento:** Seleccione _ea_.
    - **Tipo de solicitud**: deje este campo en blanco.
    - **Código de directiva**: este campo vincula la plantilla de reabastecimiento con una directiva de ubicación. Seleccione el código de la directiva de datos de demostración que creó anteriormente (_Reabastecimiento de zona_).
    - **Plantilla de trabajo**: deje este campo en blanco.
    - **Cantidad mínima:** Este campo establece la cantidad a la que se desencadenará el reabastecimiento. Introduzca _50_.
    - **Cantidad máxima:** Este campo establece la cantidad máxima de un artículo que puede estar presente en una zona. El trabajo de reabastecimiento generado aumentará el inventario a esta cantidad. Introduzca _150_.
    - **Unidad:** Este campo establece la unidad para los valores mínimo y máximo. Seleccione _ea_.
    - **Incremento de la demanda:** Seleccione _Redondear_.
    - **Reabastecer solo ubicaciones fijas vacías:** marque esta casilla.
    - **Reabastecer solo ubicaciones fijas:** desactive esta casilla.
    - **Modo de consulta del producto:** seleccione _Consulta del producto_.
    - **Alcance del umbral de reabastecimiento:** este campo define si la plantilla debe evaluar por zona o por ubicación específica. Seleccione _Zona_.
    - **Almacén:** seleccione _61_.

1. Seleccione **Seleccionar productos** encima de la cuadrícula **Detalles de plantilla de reabastecimiento**.
1. En el cuadro de diálogo **Consulta de producto**, en la pestaña **Intervalo**, seleccione **Agregar** para agregar una fila a la cuadrícula.
1. Establezca los siguientes valores en la fila nueva:

    - **Tabla:** _Artículos_
    - **Tabla derivada:** _Artículos_
    - **Campo:** _Número de artículo_
    - **Criterios**: _A0001_

1. Seleccione **Aceptar** para guardar su consulta y cerrar el cuadro de diálogo.
1. Seleccione **Seleccionar zonas para reabastecer** encima de la cuadrícula **Detalles de plantilla de reabastecimiento**.
1. En el cuadro de diálogo **Consulta de zona**, en la pestaña **Intervalo**, agregue una fila a la cuadrícula.
1. Establezca los siguientes valores en la fila nueva:

    - **Tabla:** _Zona de almacén_
    - **Tabla derivada:** _Zona de almacén_
    - **Campo**: _ID de zona_
    - **Criterios:** _FLOOR_

1. Seleccione **Aceptar** para guardar su consulta y cerrar el cuadro de diálogo.

### <a name="set-up-location-directives"></a>Configurar directivas de ubicación

A diferencia del reabastecimiento mín./máx. basada en ubicaciones, el reabastecimiento mín./máx. basado en zonas requiere que configure las directivas de ubicación de selección y las directivas de ubicación, porque el sistema evalúa toda la zona en lugar de solo la ubicación de selección para el trabajo de salida.

#### <a name="view-and-edit-location-directives"></a>Ver y editar directivas de ubicación

Para ver o editar sus directivas de ubicación, vaya a **Gestión de almacenes \> Configuración \> Directivas de ubicación**.

Para ver ejemplos que muestran cómo usar la configuración para crear las directivas de ubicación de selección y las directivas de ubicación requeridas, consulte la siguiente sección.

#### <a name="prepare-demo-data-location-directives"></a>Preparar directivas de ubicación de datos de demostración

Para preparar datos de demostración para que puedan usarse en el escenario al final de este artículo, debe crear dos directivas de ubicación: una para selección y otra para colocación.

##### <a name="create-a-replenishment-pick-directive"></a>Crear una directiva de selección de reabastecimiento

1. Seleccione la entidad jurídica **USMF** para trabajar con los datos de demostración.
1. Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.
1. En el panel izquierdo, establezca el campo **Tipo de orden de trabajo** en _Reabastecimiento_.
1. En el panel de acciones, seleccione **Nuevo** para crear una nueva directiva.
1. Establezca los valores siguientes:

    - **Número de secuencia:** acepte el valor predeterminado.
    - **Nombre:** introduzca _Selección de zona_.
    - **Tipo de trabajo**: seleccione _Selección_.
    - **Sitio:** seleccione _6_.
    - **Almacén:** seleccione _61_.
    - **Código de directiva:** deje en blanco este campo.
    - **Varios SKU:** establezca esta opción en _No_.

1. Seleccione **Guardar** para crear una directiva que tenga la configuración que ha configurado hasta ahora.
1. En la ficha desplegable **Líneas**, seleccione **Nuevo** para agregar una línea a la cuadrícula.
1. En la nueva línea, establezca los siguientes valores:

    - **Número de secuencia:** Introduzca _1_.
    - **Cantidad inicial**: introduzca _0_.
    - **Cantidad final**: introduzca _10000000_.
    - **Unidad:** deje este campo en blanco.
    - **Cantidad para localizar:** seleccione _Ninguna_.
    - **Restringir por unidad:** desactive esta casilla.
    - **Redondear por arriba a unidad:** desactive esta casilla.
    - **Localizar cantidad de embalaje:** desactive esta casilla.
    - **Permitir división:** seleccione esta casilla.

1. Seleccione **Guardar** para guardar la nueva línea.
1. Mientras su nueva línea aún está seleccionada en la cuadrícula **Líneas**, seleccione **Nuevo** en la ficha desplegable **Acciones de directiva de ubicación** para agregar una fila a la cuadrícula.
1. Establezca los siguientes valores en la fila nueva:

    - **Número de secuencia:** Introduzca _1_.
    - **Nombre:** introduzca _Seleccionar desde grandes cantidades_.
    - **Uso de ubicación fija:** seleccione _Ubicaciones fijas y no fijas_.
    - **Permitir inventario negativo**: desactive esta casilla.
    - **Lote habilitado**: desactive esta casilla.
    - **Estrategia:** seleccione _Ninguna_.

1. Seleccione **Guardar** para guardar la nueva acción.
1. Mientras su nueva acción aún está seleccionada, seleccione **Editar consulta** encima de la cuadrícula **Acciones de directiva de ubicación**.
1. Aparece un cuadro de diálogo de consulta, donde puede seleccionar las ubicaciones desde las que reabastecer. En la pestaña **Intervalo**, seleccione **Nuevo** para agregar una fila a la cuadrícula.
1. Establezca los siguientes valores en la fila nueva:

    - **Tabla**: _Ubicaciones_
    - **Tabla derivada:** _Ubicaciones_
    - **Campo**: _ID de zona_
    - **Criterios**: _BULK_

1. Seleccione **Aceptar** para guardar su consulta y cerrar el cuadro de diálogo.
1. Seleccione **Guardar** para guardar su directiva de ubicación.

##### <a name="create-a-replenishment-put-directive"></a>Crear una directiva de colocación de reabastecimiento

1. En la página **Directivas de ubicación**, en el panel izquierdo, asegúrese de que el campo **Tipo de orden de trabajo** sigue seleccionado en _Reabastecimiento_.
1. En el panel de acciones, seleccione **Nuevo** para crear otra nueva directiva.
1. Establezca los valores siguientes:

    - **Número de secuencia:** acepte el valor predeterminado.
    - **Nombre:** introduzca _Colocación de zona_.
    - **Tipo de orden de trabajo:** seleccione _Colocación_.
    - **Sitio:** seleccione _6_.
    - **Almacén:** seleccione _61_.
    - **Código de directiva:** seleccione _Reabastecimiento de zona_ para vincular esta directiva de ubicación a la plantilla de reabastecimiento que creó anteriormente utilizando el código que creó anteriormente.
    - **Varios SKU:** establezca esta opción en _No_.

1. Seleccione **Guardar** para crear una directiva que tenga la configuración que ha configurado hasta ahora.
1. En la ficha desplegable **Líneas**, seleccione **Nuevo** para agregar una línea a la cuadrícula.
1. En la nueva línea, establezca los siguientes valores:

    - **Número de secuencia:** Introduzca _1_.
    - **Cantidad inicial**: introduzca _0_.
    - **Cantidad final**: introduzca _10000000_.
    - **Unidad:** deje este campo en blanco.
    - **Cantidad para localizar:** seleccione _Ninguna_.
    - **Restringir por unidad:** desactive esta casilla.
    - **Redondear por arriba a unidad:** desactive esta casilla.
    - **Localizar cantidad de embalaje:** desactive esta casilla.
    - **Permitir división:** seleccione esta casilla.

1. Seleccione **Guardar** para guardar la nueva línea.
1. Mientras su nueva línea aún está seleccionada en la cuadrícula **Líneas**, seleccione **Nuevo** en la ficha desplegable **Acciones de directiva de ubicación** para agregar una fila a la cuadrícula.
1. Establezca los siguientes valores en la fila nueva:

    - **Número de secuencia:** Introduzca _1_.
    - **Nombre:** introduzca _Colocación de zona_.
    - **Uso de ubicación fija:** seleccione _Ubicaciones fijas y no fijas_.
    - **Permitir inventario negativo**: desactive esta casilla.
    - **Lote habilitado**: desactive esta casilla.
    - **Estrategia:** seleccione _Consolidar_.

1. Seleccione **Guardar** para guardar la nueva acción.
1. Mientras su nueva acción aún está seleccionada, seleccione **Editar consulta** encima de la cuadrícula **Acciones de directiva de ubicación**.
1. Aparece un cuadro de diálogo de consulta, donde puede seleccionar la zona a la que reabastecer. Esta zona debe ser la misma zona que se especifica en la plantilla de reabastecimiento. En la pestaña **Intervalo**, seleccione **Nuevo** para agregar una fila a la cuadrícula.
1. Establezca los siguientes valores en la fila nueva:

    - **Tabla**: _Ubicaciones_
    - **Tabla derivada:** _Ubicaciones_
    - **Campo**: _ID de zona_
    - **Criterios:** _FLOOR_

1. Seleccione **Aceptar** para guardar su consulta y cerrar el cuadro de diálogo.
1. Seleccione **Guardar** para guardar su directiva de ubicación.

## <a name="scenario"></a>Situación

En esta sección se proporciona un escenario de muestra que expone cómo trabajar con la característica.

### <a name="prepare-the-sample-data-that-is-required-for-the-sample-scenario"></a>Preparar los datos de muestra necesarios para el escenario de muestra

Antes de empezar a trabajar en el escenario, debe activar los datos de muestra y configurar la característica como se describe en esta sección y en las secciones anteriores de este artículo.

#### <a name="use-the-usmf-legal-entity"></a>Usar la entidad jurídica USMF

Para trabajar en el escenario mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/fin-ops/get-started/demo-data.md) estándar. Además, también debe seleccionar la entidad legal **USMF** antes de empezar.

#### <a name="prepare-additional-sample-data"></a>Preparar datos de muestra adicionales

Después de haber seleccionado la entidad jurídica **USMF**, agregue los datos de muestra adicionales que se requieren, como se describe en la sección [Configurar reabastecimiento basado en zonas](#setup) que aparece anteriormente en este artículo.

#### <a name="check-your-on-hand-inventory"></a>Comprobar el inventario disponible

Siga estos pasos para asegurarse de que su sistema incluya suficiente inventario para admitir el escenario de muestra.

1. Asegúrese de que haya inventario disponible para el artículo *A0001* en dos ubicaciones diferentes en la zona de selección (*FLOOR*) que se especifica en la plantilla de reabastecimiento. Sin embargo, el inventario total debe ser inferior a la cantidad mínima requerida (*50*) que se especifica en la plantilla de reabastecimiento. De esta manera, puede simular cómo se realiza el cálculo para toda la zona en lugar de solo para una única ubicación. **Utilice cualquiera de los procesos del almacén para ajustar el inventario según sea necesario.**
1. Asegúrese de que haya suficiente inventario para el artículo *A0001* en una ubicación de almacenaje que se especifica en la directiva de ubicación de selección de zona donde el trabajo de reabastecimiento debe seleccionar los artículos del id. de zona *BULK*. El inventario total debe ser superior a la cantidad máxima requerida (*150*) que se especifica en la plantilla de reabastecimiento.
1. Opcional pero recomendado: siga estos pasos para crear un diario de ajuste de inventario:

    1. Vaya a **Gestión del inventario \> Movimientos de diario \> Artículos \> Ajuste de inventario**.
    1. Seleccione **Nuevo**.
    1. En el cuadro de diálogo **Crear diario de inventario**, en el campo **Almacén**, seleccione *61*.
    1. Seleccione **Aceptar**.
    1. En la ficha desplegable **Líneas de diario**, use el botón **Nuevo** para agregar tres líneas a la cuadrícula y establecer los siguientes valores. Una vez que haya terminado de configurar cada línea, seleccione **Guardar**.

        - **Línea 1:**

            - **Código de artículo:** *A0001*
            - **Sitio**: *6*
            - **Almacén**: *61*
            - **Ubicación:** *02A01R1S1B*
            - **Matrícula:** seleccione una matrícula existente en la lista o cree una nueva matrícula.
            - **Cantidad:** *1000*

        - **Línea 2:**

            - **Código de artículo:** *A0001*
            - **Sitio**: *6*
            - **Almacén**: *61*
            - **Ubicación:** *07A01R2S1B*
            - **Matrícula:** seleccione una matrícula existente en la lista o cree una nueva matrícula.
            - **Cantidad:** *15*

        - **Línea 3:**

            - **Código de artículo:** *A0001*
            - **Sitio**: *6*
            - **Almacén**: *61*
            - **Ubicación:** *07A01R1S1B*
            - **Matrícula:** seleccione una matrícula existente en la lista o cree una nueva matrícula.
            - **Cantidad:** *10*

    1. En el panel de acciones, seleccione **Validar**. Corrija los errores que se encuentren antes de avanzar al siguiente paso.
    1. En el panel de acciones, seleccione **Registrar** para registrar el inventario en el almacén.

### <a name="sample-scenario-run-zone-based-minmax-replenishment"></a>Escenario de muestra: Ejecutar reabastecimiento mín./máx. basado en zonas

Una vez que todos los datos de muestra de requisitos previos estén en su lugar, puede desencadenar el reabastecimiento siguiendo estos pasos.

1. Vaya a **Gestión de almacenes \> Reabastecimiento \> Reabastecimientos**.
1. En el cuadro de diálogo **Reabastecimiento**, en la ficha desplegable **Registros a incluir**, seleccione **Filtrar**.
1. En el cuadro de diálogo **Consulta**, en la pestaña **Intervalo**, edite la fila de la tabla predeterminada de la siguiente manera:

    - **Tabla:** seleccione _Plantillas de reabastecimiento_.
    - **Tabla derivada:** seleccione _Plantillas de reabastecimiento_.
    - **Campo:** seleccione _Plantilla de reabastecimiento_.
    - **Criterios:** seleccione _Reabastecimiento mín./máx. de zonas_. Esta plantilla de reabastecimiento es la plantilla de reabastecimiento que creó mientras preparaba los datos de demostración para este escenario.

1. Seleccione **Aceptar** para guardar la consulta y vuelva al cuadro de diálogo **Reabastecimiento**.
1. Seleccione **Aceptar** para ejecutar la plantilla de reabastecimiento.

El trabajo de reabastecimiento ahora se crea para seleccionar el inventario desde la zona *BULK* y reabastecerlo en la zona *FLOOR*.

## <a name="notes-and-tips"></a>Notas y consejos

Aquí se muestran algunas notas y consejos para trabajar con la característica:

- Para configurar el trabajo de reabastecimiento que va a la zona deseada, puede vincular las líneas de la plantilla de reabastecimiento y las directivas de ubicación de cualquiera de las siguientes maneras:

    - Edite la consulta del encabezado de la directiva de ubicación y filtre las líneas de la plantilla de reabastecimiento seleccionadas.
    - Utilice un código de directiva en la línea de la plantilla de reabastecimiento, y haga que coincida con la directiva de ubicación de colocación.

- Si está utilizando ubicaciones dinámicas, se creará un trabajo de reabastecimiento para la primera ubicación disponible o para una ubicación que ya contiene inventario, si la acción de directiva de ubicación está configurada para usar la estrategia **Consolidar**.
- Si utiliza ubicaciones fijas en lugar de zonas, debe usar el [reabastecimiento mín./máx. estándar](tasks/set-up-min-max-replenishment-process.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]