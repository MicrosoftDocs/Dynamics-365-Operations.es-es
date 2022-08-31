---
title: Planificación de carga avanzada durante una oleada
description: Este artículo proporciona información sobre la construcción avanzada de carga de oleadas, que asigna automáticamente envíos a oleadas existentes durante la ejecución de oleadas. Por lo tanto, puede crear cargas significativas que representen camiones sin tener que usar el banco de trabajo de planificación de carga.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPostMethod,WHSWaveTemplateTable,WHSLoadMixGroup,WHSLoadBuildTemplate, WHSWaveTableListPage, TMSLoadBuildTemplateApply, TMSLoadBuildTemplates, TMSLoadBuildTemplateCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: c9d41645531fa4318289f32a564c34f0f92681df
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335867"
---
# <a name="advanced-load-building-during-wave"></a>Creación avanzada de carga durante una oleada

[!include [banner](../includes/banner.md)]

La construcción avanzada de carga de oleadas asigna automáticamente envíos a oleadas existentes durante la ejecución de oleadas. Por lo tanto, puede crear cargas significativas que representen camiones sin tener que usar el banco de trabajo de planificación de carga. Esta función es útil para las empresas que desean utilizar el concepto de cargas para rastrear y planificar el envío de mercancías en un camión / remolque, pero que no desean crear manualmente esas cargas todos los días.

Durante el procesamiento de oleadas, el sistema generalmente crea una nueva carga para cada envío al que no se asigna ninguna carga. Sin embargo, cuando se activa la construcción avanzada de carga de oleadas, el sistema asigna cada envío no asignado a una carga existente (si existe una carga adecuada), y las nuevas cargas se crean solo cuando son necesarias. La construcción avanzada de carga de oleadas crea automáticamente las nuevas cargas, según los criterios que usted defina.

Antes de utilizar la función debe configurar el sistema de la siguiente forma:

- Crear *plantillas de oleada* que incluyen el nuevo método **buildLoads**. Este método hace que la construcción avanzada de carga de oleadas esté disponible para las oleadas que usan esas plantillas.
- Configurar *cargar plantillas de compilación*, cada una de los cuales está vinculado a una plantilla y método de oleada específicos. Las plantillas de construcción de carga controlan a qué carga (existente o nueva) se agregan las líneas de carga que se están agitando. Puede combinar o separar envíos, en función de criterios como la plantilla de carga, el equipo y otros valores de campo en la línea de carga.
- Defina *cargar grupos mixtos* para controlar qué elementos deben y no deben combinarse en una sola carga. También debe especificar si la restricción debe generar una advertencia o un error, y si se debe evaluar la restricción volumétrica de la plantilla de carga.

## <a name="turn-on-advanced-wave-load-building-in-your-system"></a>Active la construcción avanzada de carga de oleadas en su sistema

Antes de que pueda usar la construcción avanzada de carga de oleada, debe activar dos funciones para su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de estas funciones y activarlas si es necesario. En el espacio de trabajo **Administración de funciones**, las funciones aparecen de la siguiente forma:

- Característica de creación de carga de oleada:

    - **Módulo:** *Gestión de almacén*
    - **Nombre de la característica:** *Característica de construcción de carga de oleada*

- Código de paso de oleada de toda la organización:

    - **Módulo:** *Gestión de almacén*
    - **Nombre de la característica:** *Código de paso de oleada de toda la organización*

### <a name="make-sample-data-available"></a>Hacer que los datos de muestra estén disponibles

Para trabajar en esta demostración mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/fin-ops/get-started/demo-data.md) estándar. Además, también debe seleccionar la entidad legal **USMF** antes de empezar.

También puede usar esta demostración como guía para usar esta función cuando trabaje en un sistema de producción. Sin embargo, en ese caso, debe sustituir sus propios valores y puede que le falten algunos tipos de registros necesarios que proporcionan los datos de demostración estándar.

### <a name="make-sure-that-the-scenario-setup-includes-enough-available-inventory"></a>Asegúrese de que la configuración del escenario incluye suficiente inventario disponible

Si estás trabajando con los datos de demostración **USMF**, primero debe asegurarse de que su sistema esté configurado para que haya suficiente inventario en cada ubicación relevante. Para esta demostración, la expectativa es que el siguiente inventario esté disponible en el almacén *62*:

- **Artículo A0001:** 10 unidades
- **Artículo A0002:** 10 unidades
- **Artículo M9200:** 10 ea

El artículo **M9200** debe agregarse al almacén. Complete los procedimientos en las siguientes subsecciones para agregar el inventario del artículo.

#### <a name="create-a-new-license-plate-id"></a>Crear una nueva identificación de matrícula de entidad

1. Vaya a **Gestión de almacenes** \> **Configurar** \> **Almacén** \> **Matrículas de entidad**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En la nueva fila, en el campo **Matrícula de identidad**, introduzca *LP6203*.
1. Seleccione **Guardar**.

#### <a name="create-a-standard-cost-for-item-m9200-in-site-6"></a>Cree un coste estándar para el artículo M9200 en el sitio 6

1. Vaya a **Gestión de información de productos** \> **Productos** \> **Productos emitidos**.
1. Buscar en **M9200**.
1. Seleccione la fila para el artículo y luego, en el Panel de acciones, en la pestaña **Administrar costes**, en el grupo **Configurar**, seleccione **Precio del articulo**.
1. En la página **Precio del articulo**, seleccione la pestaña **Precios pendientes**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En la nueva línea, establezca los siguientes valores:

    - **Tipo de coste**: *coste planeado*
    - **Tipo de precio:** *coste*
    - **Versión:** *10*
    - **Sitio**: *6*
    - **Precio:** *1,60*

1. En el panel Acciones, seleccione **Guardar**.
1. En el Panel de acciones, seleccione **Activar precios pendientes**.
1. Seleccione la pestaña **Precios activos** para verificar que el nuevo precio de coste para el sitio *6* ha sido añadido.

#### <a name="create-inventory-in-warehouse-62"></a>Crear inventario en el almacén 62

1. Vaya a **Gestión del inventario** \> **Movimientos de diario** \> **Artículos** \> **Ajuste de inventario**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Crear diario de inventario**, en la ficha desplegable **Visión general**, en el campo **Almacén**, introduzca *62*. Acepte los valores predeterminados en el resto de campos.
1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.
1. Se abrirá la página **Ajuste de inventario**. En la ficha desplegable **Líneas de diario**, seleccione **Nueva** para agregar una línea.
1. En la nueva línea, establezca los siguientes valores. Acepte los valores predeterminados en el resto de campos.

    - **Código de artículo:** *M9200*
    - **Ubicación:** *almacenaje-003*
    - **Cantidad:** cambie el valor a *10*.

1. En el panel Acciones, seleccione **Guardar**.
1. En el Panel de acciones, seleccione **Validar** para verificar si hay errores.
1. En el cuadro de diálogo **Comprobar diario**, seleccione **Aceptar** para comenzar la comprobación. Recibirá un mensaje cuando se complete la verificación.
1. En el Panel de acciones, seleccione **Enviar** para confirmar el ajuste de inventario.
1. En el cuadro de diálogo **Diario de publicación**, seleccione **Aceptar** para comenzar la publicación. Recibirá un mensaje cuando se complete la publicación.

## <a name="set-up-advanced-wave-load-building"></a>Configuración de creación avanzada de carga de oleada

### <a name="regenerate-wave-process-methods"></a>Regenerar métodos de proceso de oleada

Es posible que tenga que regenerar sus métodos de proceso de oleada para hacer que el método de construcción de carga (**buildLoads**) esté disponible.

1. Vaya a **Gestión de almacenes** \> **Configurar** \> **Oleadas** \> **Métodos de procesar oleadas**.
2. Verifique que **buildLoards** está en la lista. Si no está presente, seleccione **Regenerar métodos** en el Panel de acciones para agregarlo.

### <a name="set-up-wave-templates"></a>Configurar plantillas de oleada

Para aprovechar la construcción avanzada de carga de oleadas, debe incluir el método **buildLoads** en cada [plantilla de oleada](tasks/configure-wave-processing.md) relevante.

1. Vaya a **Gestión de almacenes** \> **Configurar** \> **Oleadas** \> **Plantillas de oleada**.
1. Seleccionar una plantilla de oleada.

    Si está trabajando con los datos de demostración **USMF**, seleccione la plantilla **62 Envío predeterminado**.

1. En el Panel de acciones, seleccione **Editar** para poner la página en modo de edición.
1. En la ficha desplegable **Métodos**, en la cuadrícula **Métodos restantes**, seleccione el método **buildLoads**.
1. Seleccione el botón flecha derecha para mover el método **buildLoads** a la cuadrícula **Métodos seleccionados**.
1. Para asignar un valor de **Código de paso de oleada** para el método **buildLoads**, primero debe crear un código en la página **Códigos de paso de oleada**. Puede usar cualquier valor que desee, pero asegúrese de anotarlo, porque lo necesitará más adelante. Siga estos pasos para crear un código **WSC2112**:

    1. En la fila para el método **buildLoads**, haga clic derecho en la flecha hacia abajo en el campo **Código de paso de oleada** y luego seleccione **Ver detalles**.
    1. En la página **Códigos de paso de oleada**, en el Panel de acciones, seleccione **Nuevo**.
    1. En el campo **Código de paso de oleada** campo, introduzca *WSC2112*.
    1. En el campo **Descripción de paso de oleada** campo, introduzca *WSC2112*.
    1. En el campo **Tipo de paso de onda**, seleccione *Planificación de carga*.

1. Seleccione **Guardar** y cierre la página.
1. En la fila para el método **buildLoads**, en el **Código de paso de oleada**, seleccione el código que acaba de crear (**WSC2112**).
1. En el panel Acciones, seleccione **Guardar**.

> [!NOTE]
> Los códigos del paso de oleada son códigos que los usuarios pueden configurar y usar para vincular instancias específicas de los métodos de la oleada a las plantillas correspondientes. Las plantillas incluyen las plantillas para reabastecimiento, la puesta en contenedores, la impresión de etiquetas, el edificio de carga y la ordenación.
>
> Cuando los códigos del paso de oleada no se usan, los usuarios deben introducir texto para referenciar una plantilla específica del método de la instancia de oleada. El texto libre suele tener errores, por lo que los usuarios deben asegurarse de que el texto de paso de oleada que añaden para un método específico de paso de oleada en una plantilla de oleada coincide exactamente con el texto de paso de oleada en la plantilla objetivo.
>
> Los códigos del paso de oleada para un tipo de etapa específico de la oleada se configuran en una página independiente. Para cada instancia de un método del paso de oleada en una plantilla de oleada que precisa un código del paso de oleada, el código del paso de oleada se debe seleccionar en una lista desplegable. La selección de una lista desplegable reemplaza la entrada de texto en la factura de servicios y ayuda a reducir el riesgo y el impacto de los errores humanos. Los códigos de configuración se usan para vincular un método de paso de oleada en una plantilla de oleada a una plantilla objetivo para el método.

### <a name="set-up-load-mix-groups"></a>Configurar grupos de carga mixta

Los grupos de carga mixta establecen reglas para los tipos de elementos que se pueden combinar en una sola carga. Puede configurar tantos grupos de carga mixta como necesite. Sin embargo, para usar la construcción avanzada de carga de oleadas, debe tener al menos uno. Siga estos pasos para crear un grupo de carga mixta.

1. Vaya a **Administración de almacenes** \> **Configurar** \> **Carga** \> **Grupos de carga mixta**.
1. En el Panel de acciones, haga clic en **Nuevo** para crear un grupo de carga.
1. En el campo **Identificación de grupo de carga mixta**, escriba un nombre para el nuevo grupo.

    Si estás trabajando con los datos de demostración **USMF**, establezca los siguientes valores:

    - **Identificación de grupo de carga mixta:** *TV*
    - **Descripción:** *TV*

1. En el Panel de acciones, seleccione **Guardar** para hacer que la ficha desplegable **Criterios de grupo de carga mixta** esté disponible.
1. En la ficha desplegable **Criterios de grupo mixto de carga**, seleccione **Nuevo** para agregar una fila a la cuadrícula.
1. En la nueva fila, establezca los valores deseados en cada campo. Estos valores determinan los grupos de elementos que se consideran para la carga mixta.

    Si está trabajando con los datos de demostración **USMF**, seleccione *TV y vídeo* en el campo **Grupo de artículos**.

1. En el Panel de acciones, seleccione **Guardar** para hacer que la ficha desplegable **Límites de grupo de carga mixta** esté disponible.
1. En la ficha desplegable **Límites de grupo mixto de carga**, seleccione **Nuevo** para agregar una fila a la cuadrícula.
1. En la nueva fila, establezca los valores deseados en cada campo.

    Si estás trabajando con los datos de demostración **USMF**, establezca los siguientes valores:

    - **Grupo de artículos:** *Audio de automóvil*
    - **Acción de planificación de carga:** *Restringir* (este valor evitará los elementos que pertenecen al grupo de artículos **Audio de automóvil** estén en la misma carga que los elementos que pertenecen al grupo de artículos **TV y vídeo**).

1. Continúe trabajando con las reglas hasta que haya agregado todos los criterios y restricciones que necesita para el grupo de carga mixta.

Si está trabajando con los datos de demostración **USMF**, ya ha terminado esta configuración.

### <a name="set-up-load-build-templates"></a>Configurar plantillas planificación de carga

Puede configurar tantos plantillas de planificación de carga. Sin embargo, para usar la construcción avanzada de carga de oleadas, debe tener al menos uno. Siga estos pasos para crear una plantilla de planificación de carga.

1. Vaya a **Administración de almacenes** \> **Configurar** \> **Carga** \> **Plantillas de planificación de carga de oleada**.
1. En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.
1. Establezca los siguientes valores en la fila nueva.

    | Campo | Descripción | Valor en los datos de demostración de USMF |
    |---|---|---|
    | Número de secuencia | El orden en que se evaluará la plantilla. | *1* |
    | Nombre de plantilla de planificación de la carga | Introduzca el identificador único de la plantilla de planificación de la carga. Debe introducir el nombre de la plantilla que creó o actualizó anteriormente en esta configuración. | *62 Envío predeterminado* |
    | Código de paso de oleada | Introduzca el código de paso de oleada a usar para vincular la plantilla a un método de oleada. Debe introducir el código que seleccionó para el método **buildLoads** cuando configuró la plantilla de oleada anteriormente en esta configuración. | *WSC2112* |
    | Id. de plantilla de carga | Seleccione la plantilla de carga que se usará al crear cargas nuevas y contra la que se emparejará al asignar las cargas existentes. La plantilla de carga define el peso y el volumen máximos permitidos para toda la carga. | *Stnd Plantilla de carga* |
    | Equipos | El equipamiento contra el que emparejar al asignar las cargas existentes y a introducir en las nuevas cargas que se crean. | Deje este campo en blanco. |
    | Id. de grupos mixtos de carga | Seleccione el grupo mixto de carga a usar si el artículo está permitido en la carga. El grupo mixto establece las reglas para las clases de artículos que se pueden combinar en una sola carga. Debe seleccionar uno de los grupos mixtos que creó anteriormente en esta configuración. | *TV* |
    | Usar cargas abiertas | Seleccione si se deben agregar cargas abiertas existentes. Las siguientes opciones están disponibles:<ul><li>**Ninguna** - No agregue cargas abiertas a ninguna carga existente.</li><li>**Cualquiera** - Agregue cargas abiertas a cualquier carga existente que sea válida para la línea.</li><li>**Asignada** - Agregue cargas abiertas a la carga que se asigna a la oleada.</li></ul> | *Alguna* |
    | Crear cargas | Especifique si se deben crear nuevas cargas si ninguna carga existente coincide con los criterios. | Seleccionado (= *Sí*) |
    | Permitir división de línea de envío | Especifique si una línea de carga única puede dividirse en varias cargas si la línea completa supera la capacidad máxima de la plantilla de carga. | Desactivado (= *No*) |
    | Validar métricas de volumen | Especificar si la planificación de carga debería comprobar el peso y volumen a medida que se añade cada línea de carga, para garantizar que los límites volumétricos de la plantilla de carga se respetan. | Desactivado (= *No*) |

1. En el Panel de acciones, seleccione **Guardar** para hacer que la opción **Editar consulta** esté disponible.
1. En el panel de acciones, seleccione **Editar consulta** para abrir un cuadro de diálogo para editar la consulta.
1. En el cuadro de diálogo, en la pestaña **Clasificación**, seleccione **Agregar** para añadir una fila a la cuadrícula.
1. En la nueva fila, defina las reglas de ordenación que desea usar. Por ejemplo, establezca los siguientes valores para ordenar los resultados de búsqueda en orden ascendente por número de orden:

    - **Tabla:** *Detalles de carga*
    - **Tabla derivada:** *Detalles de carga*
    - **Campo:** *Número de pedido*
    - **Dirección de búsqueda:** *Ascendente*

1. Seleccione **Aceptar** para guardar sus cambios y cerrar el cuadro de diálogo.
1. En la ficha desplegable **Interrumpir por**, establezca reglas para controlar cómo se dividen sus cargas. Por lo general, puede dividir en campos personalizados que se han extendido a la línea de carga, como **Ruta**, **Tour** o **Ejecución**. Por ejemplo, para crear una carga por número de pedido, seleccione la casilla de verificación **Dividir por** para la fila que tiene los siguientes valores:

    - **Nombre de la tabla de referencia:** *Detalles de carga*
    - **Nombre del campo de referencia:** *Número de pedido*

## <a name="scenario"></a>Situación

Este escenario muestra cómo la configuración que se describió anteriormente en este artículo afecta las operaciones de almacén mientras se procesa un pedido de ventas. Este escenario usa los datos de demostración **USMF** junto con otros valores de demostración que se proporcionan en esas instrucciones de configuración.

### <a name="create-sales-orders"></a>Crear pedidos de ventas

1. Vaya a **Ventas y marketing** \> **Pedidos de ventas** \> **Todos los pedidos de ventas**.
1. En el panel de acciones, seleccione **Nuevo** para abrir el cuadro de diálogo **Crear pedido de ventas**.
1. En el cuadro de diálogo, establezca los valores siguientes:

    - En la ficha desplegable **Cliente**, configure el campo **Cuenta de cliente** a *US-007*.
    - En la ficha desplegable **General**, establezca el campo **Almacén** en *62*.

1. Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.
1. Se abre su nuevo pedido de ventas. Debe incluir una nueva línea vacía en la cuadrícula en la ficha desplegable **Líneas de pedido de venta**. En esta nueva línea, establezca el campo **Número de artículo** a *A0001* y el campo **Cantidad** a *1*.
1. En el menú **Inventario** sobre la cuadrícula, seleccione **Reserva**.
1. En la página **Reserva**, en el Panel de acciones, seleccione **Reservar lote**.
1. Selecciona el botón **Cerrar** botón (**X**) en la esquina superior derecha de la página para volver al pedido de ventas.
1. En el panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**. El sistema crea un envío y lo agrega a una nueva carga, porque ninguna carga existente contiene líneas de carga que tengan este número de pedido.

    Recibirá mensajes informativos que indican el trabajo, la oleada y el envío que se crean para este pedido.

1. Para confirmar la carga, el envío y los detalles del trabajo en la línea de ventas, seleccione la línea y luego, en el menú **Almacén** encima de la cuadrícula, seleccione **Detalles de carga**, **Detalles del envío** o **Detalles del trabajo**.
1. En el pedido de ventas que acaba de crear, en la ficha desplegable **Líneas de pedido de venta**, seleccione **Agregar línea** para añadir otra línea.
1. En la nueva línea, establezca el campo **Número de artículo** a *A0002* y el campo **Cantidad** a *1*.
1. Repita las líneas 6 a 9 para reservar la línea y liberarla en el almacén. El sistema crea un envío **nuevo** para la línea que agregó. Sin embargo, debido a que está utilizando la construcción avanzada de carga de oleada, el sistema agrega ese envío y la línea de carga a la oleada existente. Si no estuviera usando la construcción avanzada de carga de oleada, el sistema crearía una nueva carga para el envío.
1. En el pedido de ventas que acaba de crear, en la ficha desplegable **Líneas de pedido de venta**, seleccione **Agregar línea** para añadir otra línea.
1. En la nueva línea, establezca el campo **Número de artículo** a *M9200* y el campo **Cantidad** a *1*.
1. Repita las líneas 6 a 9 para reservar la línea y liberarla en el almacén. Como antes, el sistema crea un envío **nuevo** para la línea que agregó. Sin embargo, porque el artículo es del grupo de artículos **Audio de automóvil**, **no pasa las restricciones que configuró para el grupo mixto de carga**. Por lo tanto, es **agregado a una nueva carga**. Si no hubiera especificado un grupo mixto de carga en la plantilla de construcción de carga, este envío se habría agregado a la primera carga.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]