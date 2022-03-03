---
title: Confirmar y transferir
description: Este tema explica cómo usar la función Confirmar y transferir, que permite a los usuarios enviar cargas fuera del almacén antes de completar todo el trabajo asociado con esas cargas.
author: mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadTemplate,WHSWorkTemplateTable,WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 7b487684980f60112d9af6bea02672f7e919c834
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103598"
---
# <a name="confirm-and-transfer"></a>Confirmar y transferir

[!include [banner](../includes/banner.md)]

La función *Confirmar y transferir* permite a los usuarios enviar cargas fuera del almacén antes de completar todo el trabajo asociado con esas cargas. Cuando se recibe un envío que incluye líneas de carga que no se recogieron por completo, se solicita al usuario confirmador que divida las cantidades restantes en una nueva carga o que cancele las cantidades incompletas.

Los sistemas que están configurados para permitir escenarios de soporte de división de carga donde las cargas planificadas y parcialmente cargadas deben adaptarse debido a circunstancias nuevas o cambiantes.

El cliente incluye lógica que permite que una carga parcialmente cargada se cierre y se confirme como enviada. Todos los envíos y líneas de carga restantes (incluidas las cantidades de línea completas o parciales) se transfieren a una carga y envío recién creados, si se requiere esta reinversión y la configuración lo permite. Los nuevos envíos y cargas se crean automáticamente en función de los criterios iniciales para el envío y la creación de carga y sus atributos principales permanecen sin cambios. También hay una opción para cancelar automáticamente las cantidades restantes si aún no se ha creado una orden de trabajo y el usuario considera que esta cancelación es necesaria.

Esta funcionalidad admite escenarios en los que la carga completa no cabe en un solo camión, o donde parte de la carga debe salir del almacén antes de que el resto de la carga esté lista para el envío. En estos escenarios, los productos restantes se pueden transferir a una nueva carga y, por lo tanto, a un nuevo camión. Debido a que esta característica se puede usar con cargas que de otro modo pretenden requerir un envío de carga completa, proporciona flexibilidad adicional para que los gerentes de transporte puedan resolver escenarios no estándar o imprevistos.

Cuando se divide una carga, la función *Confirmar y transferir* realiza las siguientes acciones:

- Se crean nuevas cargas y envíos según sea necesario. Cada carga o envío tendrá la mayoría de los mismos atributos que la carga o envío original. La excepción es el estado de carga, que se volverá a calcular en función del estado de trabajo.
- Se informa al usuario que se ha creado una nueva carga. El usuario también recibe una notificación sobre el identificador de la nueva carga.
- Las líneas de carga, los encabezados de trabajo y las líneas de trabajo que se dividieron se actualizan con la nueva información de carga y envío.
- Si se divide un envío completo, el envío se mantiene y solo se actualizan las referencias de carga. Si el envío debe dividirse, se crea un nuevo envío.

Cuando se cancelan las cantidades restantes, las cantidades de la línea de carga que no se han recogido y que no tienen trabajo no cancelado asociado con ellas se eliminan de la carga. Si hay algún trabajo en proceso, el usuario solo puede dividir la carga. Las cantidades restantes no se pueden cancelar.

Puede dividir solo cargas que cumplan con los siguientes criterios:

- Una o más líneas de carga han recogido cantidades.
- El estado de carga es menor que el cargado.
- No hay datos de línea de carga. (Estos datos se crean a través de la consolidación de matrículas de entidad en la ubicación de preparación y la función Confirmar y transferir no admite la consolidación de matrículas).
- Actualmente no hay inventario en espera de embalaje en una ubicación de embalaje. (La característica *Confirmar y transferir* no admite el inventario que se ha recogido en la estación de empaquetado, pero que aún no se ha empaquetado, a menos que los contenedores que estén empacados se coloquen en ubicaciones de preparación con el trabajo de carga creado).

> [!NOTE]
> Esta funcionalidad difiere de la funcionalidad de carga de transporte, que debe usarse en almacenes que nunca pueden planificar y crear cargas antes de la recolección, sino que cargan el espacio de transporte disponible después de que se completa la recolección.
>
> Use la función *Confirmar y transferir* en situaciones donde las cargas generalmente se planifican y crean con anticipación, pero donde a veces ocurren excepciones en las que la carga no se ajusta al transporte disponible (como un camión).

## <a name="turn-the-confirm-and-transfer-feature-on-or-off"></a>Activar o desactivar la característica de confirmar y transferir

Para utilizar la funcionalidad descrita en este tema, debe activarse la característica *Confirmar y transferir* en su sistema. A partir de la versión 10.0.25 de Supply Chain Management, esta característica es obligatoria y no se puede desactivar. Si está ejecutando una versión anterior a la 10.0.25, los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Confirmar y transferir* en el espacio de trabamo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="set-up-confirm-and-transfer"></a>Configurar confirmar y transferir

Para usar la característica *Confirmar y transferir*, debe activarla en cada plantilla de carga relevante. Además, dependiendo de sus requisitos, es posible que desee preparar sus plantillas de trabajo para admitir la función. Si desea trabajar en el escenario de ejemplo que se proporciona más adelante en este tema, configure su sistema como se describe en esta sección. (Ese escenario se basa en los datos de demostración **USMF**).

### <a name="prepare-your-load-templates"></a>Prepare sus plantillas de carga

1. Vaya a **Administración de almacenes \> Configuración \> Carga \> Plantillas de carga**.
1. En el Panel de acciones, seleccione **Editar** para poner la página en modo de edición.
1. Seleccione la casilla de verificación **Permitir división de carga durante la confirmación de envío** para cada plantilla existente donde desea activar la función. Alternativamente, seleccione **Nuevo** para crear una nueva plantilla y configurarla según lo requiera. Cada carga que cree utilizando esa plantilla heredará esta funcionalidad. (Si estás trabajando con los datos de demostración **USMF**, active la función para la plantilla de carga **Contenedor de 20'**).

### <a name="prepare-your-work-templates"></a>Prepare sus plantillas de trabajo

Esta configuración no es necesaria en todas las situaciones. El ejemplo que se muestra aquí garantiza que el trabajo se puede interrumpir por envío para admitir el escenario de ejemplo que se proporciona más adelante en este tema. También hay otras formas de lograr este resultado.

1. Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.
1. En la cuadrícula en la parte superior de la página, seleccione una plantilla de trabajo existente donde desee configurar la función *Confirmar y transferir*. (Si estás trabajando con los datos de demostración **USMF**, seleccione la plantilla de trabajo **51 Recoger para preparar**). Alternativamente, cree una nueva plantilla de trabajo.
1. En el panel de acciones, seleccione **Editar consulta** para abrir el cuadro de diálogo **Ventas**.
1. En el cuadro de diálogo **Ventas**, en la pestaña **Clasificación**, seleccione **Agregar** para añadir una fila a la cuadrícula.
1. Establezca los siguientes valores en la fila nueva:

    - **Tabla:** *Transacciones laborales temporales*
    - **Tabla derivada:** *Transacciones laborales temporales*
    - **Campo:** *Identificación del envío*
    - **Dirección de búsqueda:** *Ascendente*

1. Seleccione **Aceptar** para guardar la configuración y cerrar el cuadro de diálogo **Ventas**.
1. Si recibe un mensaje que indica que la agrupación se restablecerá, seleccione **Sí** para continuar.
1. En la cuadrícula en la parte superior de la página **Plantillas de trabajo**, seleccione la plantilla que acaba de editar y luego, en el Panel de acciones, seleccione **Saltos de encabezado de trabajo**.
1. En el Panel de acciones, seleccione **Editar** para poner la página en modo de edición.
1. Establezca los siguientes valores en la cuadrícula:

    - **Nombre de la tabla:** *Transacciones laborales temporales*
    - **Nombre del campo:** *Identificación del envío*
    - **Agrupar por este campo:** seleccione esta casilla de verificación.

1. En el panel Acciones, seleccione **Guardar**.
1. Cierre la página.

## <a name="scenario"></a>Situación

Este escenario muestra un ejemplo en el que el proceso de recolección aún no se ha completado, pero los artículos que se han recogido hasta ahora deben cargarse en un camión y enviarse de todos modos. Por lo tanto, el usuario puede dividir las líneas de carga no seleccionadas en una nueva carga. Todas las relaciones de datos se actualizarán automáticamente.

> [!NOTE]
> Los valores específicos que se describen en este escenario se basan en los datos de demostración **USMF**. Le recomendamos que use estos datos de demostración mientras hace una demostración o aprende a usar la función. Si no estás usando los datos de demostración **USMF**, sustituya sus propios valores según sea necesario.

### <a name="step-1-create-a-load-that-has-multiple-load-lines"></a>Paso 1: cree una carga que tenga varias líneas de carga

Antes de poder usar esta funcionalidad, debe tener una carga que contenga varias líneas de carga. También debe asegurarse de que las ubicaciones de selección tengan suficiente inventario para todos los artículos en los pedidos de ventas que creará. Revise la configuración de la directiva de ubicación (**Gestión de almacenes \> Configuración \> Directivas de ubicación**) y tome nota de las ubicaciones de selección que se utilizan para la selección de pedidos de ventas. Si debe ajustar el inventario, crear movimientos manuales, utilizar la reposición o utilizar cualquier otro flujo, según sea necesario.

Para crear una carga cualificada, primero cree tres pedidos de ventas siguiendo estos pasos.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. En el panel de acciones, seleccione **Nuevo** para abrir el cuadro de diálogo **Crear pedido de ventas**.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores (como mínimo):

    - En la ficha desplegable **Cliente**, configure el campo **Cuenta de cliente** a *US-004* (*Cave Wholesales*).
    - En la ficha desplegable **General**, establezca el campo **Almacén** en *51*.

1. Seleccione **Aceptar** para crear el pedido de ventas y cierre el cuadro de diálogo **Crear pedido de ventas**.
1. Se abre su nuevo pedido de ventas. En la cuadrícula **Líneas de pedido de venta**, agregue una línea que tenga los siguientes valores:

    - **Código de artículo:** *M9200*
    - **Cantidad:** *40*
    - **Unidad**: *u*

1. En el menú **Inventario** sobre la cuadrícula, seleccione **Reserva**.
1. En el panel de acción, seleccione **Reservar lote**, para abrir la página **Reserva**.
1. Reserve el inventario en la línea de ventas y luego cierre la página **Reserva**.
1. Repita los pasos del 1 al 4 para agregar un segundo pedido de ventas para el mismo cliente y almacén.
1. Agregue dos líneas de ventas que tengan los siguientes valores. Después de agregar cada línea, reserve el inventario como se describe en los pasos 6 a 8.

    - **Línea 1**: establezca el campo **Número de artículo** a *M9200*, el campo **Cantidad** a *30* y el campo **Unidad** a *ea*.
    - **Línea 2**: establezca el campo **Número de artículo** a *M9201*, el campo **Cantidad** a *20* y el campo **Unidad** a *ea*.

1. Repita los pasos del 1 al 4 para agregar un tercer pedido de ventas para el mismo cliente y almacén.
1. Agregue dos líneas de ventas que tengan los siguientes valores. Después de agregar cada línea, reserve el inventario como se describe en los pasos 6 a 8.

    - **Línea 1**: establezca el campo **Número de artículo** a *M9201*, el campo **Cantidad** a *20* y el campo **Unidad** a *ea*.
    - **Línea 2**: establezca el campo **Número de artículo** a *M9202*, el campo **Cantidad** a *60* y el campo **Unidad** a *ea*.

#### <a name="load-planning-workbench"></a>Área de trabajo de planificación de la carga

El banco de trabajo de planificación de carga utilizará el identificador de la plantilla de carga para construir los envíos y liberar las líneas de pedido de ventas al almacén.

1. Vaya a **Gestión de almacén \> Cargas \> Área de trabajo de planificación de la carga**.
1. En el campo **Almacén**, seleccione *51*.

    Ahora construirá la carga para el pedido de ventas que acaba de crear.

1. En la pestaña **Líneas de venta**, en la cuadrícula, seleccione las líneas de ventas para los nuevos pedidos de ventas.
1. En el panel de acciones, en la ficha **Suministro y demanda**, en el grupo **Agregar**, seleccione **A una carga nueva**.
1. En el cuadro de diálogo **Cargar plantilla de asignación**, en el campo **Cargar Id. de plantilla** seleccione *Contenedor de 20'*.
1. Seleccione **Aceptar**.
1. En la sección **Cargas** de la página **Área de trabajo de planificación de carga**, en la cuadrícula, busque el ID de carga recién creado para el almacén *51*. Desplácese hacia la derecha hasta que vea la columna **Permitir división de carga durante la confirmación de envío**. La casilla de verificación debe estar seleccionada para su carga.
1. Seleccione la carga.
1. En el menú **Lanzamiento** sobre la cuadrícula, seleccione **Liberar al almacén** para crear trabajo.
1. En el cuadro de diálogo **Liberar carga al almacén**, verifique que la ficha desplegable **Registros para incluir** muestra su identificación de carga.
1. Seleccione **Aceptar**.

    Es posible que reciba un mensaje de "Operación en proceso" mientras el sistema crea los envíos y trabaja.

1. En la sección **Cargas** de la página **Área de trabajo de planificación de carga**, su carga ahora debería tener un estado de carga de *Oleada*. Seleccione la carga, y luego, en el menú **Información relacionada** sobre la cuadrícula, seleccione **Detalles de oleada** para ver los identificadores de envío que se crearon. Cuando haya terminado, cierre la página **Oleadas**.
1. En la sección **Cargas** de la página **Área de trabajo de planificación de carga**, seleccione la carga, y luego, en el menú **Información relacionada** sobre la cuadrícula, seleccione **Detalles del trabajo** para ver el trabajo que se creó para los pedidos de ventas.
1. Anote los identificadores de trabajo que se crearon. Es posible que deba desplazarse hacia la derecha para ver el número de pedido de ventas y el identificador de envío asociados con el identificador de trabajo.

### <a name="step-2-set-up-the-execution-flow-for-mobile-devices"></a>Paso 2: configure el flujo de ejecución para dispositivos móviles

Las tareas del dispositivo móvil requerirán la entrada de información por parte del usuario, como la identificación del trabajo o la identificación de la matrícula de entidad. En los campos, esta información generalmente se proporciona a los usuarios del almacén en forma de códigos de barras que se encuentran en la documentación, el embalaje o el estante. Para completar los pasos del dispositivo móvil para escenarios, asegúrese de haber identificado las identificaciones de trabajo para las transacciones y las identificaciones de matrícula de entidad para el artículo y la ubicación en las transacciones.

1. Inicie sesión en el dispositivo móvil utilizando un identificador de usuario y contraseña para el almacén *51*.
1. Seleccione **Saliente**.
1. Seleccione **Selección de ventas**.
1. Tiene la opción de introducir la identificación del trabajo o la identificación de la matrícula de entidad. Introduzca la identificación de trabajo para el primer pedido de ventas y luego seleccione **Introducir**.
1. En el **Ubi** campo, ingrese la ubicación que se muestra para confirmar la ubicación de recogida. Luego seleccione **Introducir**.
1. En el campo **LP** introduzca el identificador de la matrícula de entidad. La identificación de la matrícula debe coincidir con el artículo, el almacén y la ubicación del artículo que se selecciona de la ubicación seleccionada. Cuando haya terminado, seleccione **Introducir**.
1. En el campo **Articulo**, introduzca el número de artículo para confirmar el artículo que se está seleccionando y luego seleccione **Entrar**.
1. En el campo **Ctd**, introduzca la cantidad del artículo para que se está recogiendo y después seleccione **Introducir**.
1. En el campo **LP objetivo** introduzca un identificador de la matrícula de entidad objetivo. Las matrículas de entidad de destino están definidas por el usuario. Asegúrese de introducir una identificación de matrícula que recordará. Recomendamos que use la fecha actual más una secuencia de dos dígitos (AAMMDD\#\#) como el formato, como *19112301*. Cuando haya terminado, seleccione **Introducir**.
1. Revise la información que se muestra. Esta información es la información *Recoger* que ahora se convertirá en los datos *Colocar* para la transacción de colocación. Cuando haya terminado, seleccione **Introducir**.

    - Recibe un mensaje **Trabajo completado**.

1. Repita los pasos del 4 al 10 para el identificador de trabajo del segundo pedido de ventas.

El siguiente paso es cargar las dos matrículas de entidad recogidas en el camión.

1. Inicie sesión en el dispositivo móvil utilizando un identificador de usuario y contraseña para el almacén *51*.
1. Seleccione **Saliente**.
1. Seleccione **Cargando ventas**.
1. Introduzca la identificación de matrícula de entidad de destino definida por el usuario que creó para la primera identificación de trabajo en el procedimiento anterior. Luego seleccione **Introducir** poner la matrícula de entidad de destino en la ubicación **MONTAJE**.
1. Introduzca nuevamente la identificación de la matrícula de entidad de destino y luego seleccione **Introducir** para poner la matrícula en la ubicación **BAHÍA**.
1. Repita los pasos 4 a 5 para la identificación de la matrícula de entidad de destino que creó para la segunda identificación de trabajo.

Las dos identificaciones de trabajo ahora estarán cerradas (cargadas).

### <a name="step-3-confirm-the-outbound-shipment"></a>Paso 3: confirme el envío saliente

En este paso, confirmará los dos pedidos de ventas y el trabajo que se ha completado para que la carga envíe los artículos seleccionados de la carga y cree una nueva carga para los artículos no seleccionados. La confirmación del envío de salida debe hacerse en la página **Detalles de carga**.

1. Vaya a **Gestión de almacén \> Cargas \> Área de trabajo de planificación de la carga**.
1. En la sección **Cargas**, en la cuadrícula, seleccione la fila para la identificación de carga que creó.
1. Seleccione el enlace de identificación de carga para abrir la página **Detalles de carga**.
1. En la página **Detalles de carga**, en el Panel de acciones, en la pestaña **Enviar y recibir**, en el grupo **Confirmar**, seleccione **Envío saliente** para iniciar la confirmación.
1. En el cuadro de diálogo **Confirmar envío**, en el campo **Método de división de carga durante la confirmación del envío**, seleccione *Dividir cantidad a nueva carga*.
1. Seleccione **Aceptar**.

    Es posible que reciba un mensaje de "Operación en proceso".

    Recibirá mensajes informativos que indican que se ha confirmado el envío de su carga y que se ha creado una nueva carga a partir de la cantidad dividida.

Actualice la página **Área de trabajo de planificación de carga** para ver la carga recién creada.

También puede confirmar que las relaciones de transacción se han actualizado de las siguientes maneras:

- El envío restante (sin procesar) y las líneas de envío se actualizan con la nueva identificación de carga.
- El pedido de cliente está vinculado a la nueva identificación de carga.
- La carga original no incluye las líneas de carga restantes.
- El trabajo restante se ha actualizado con la nueva identificación de carga.
- La oleada sigue siendo la misma.
- El estado de la nueva carga se actualiza correctamente. (Si el estado del trabajo es _En proceso_, el estado de carga también debe ser _En proceso_.)

## <a name="notes-and-tips"></a>Notas y consejos

- También puedes activar el parámetro **Permitir división de carga durante la confirmación de envío** después de que la carga se haya creado con el parámetro **Plantilla de carga** desactivado pero antes de que comience el proceso de carga. Vaya a la carga deseada y luego, en la vista de encabezado, active el parámetro.
- La opción **Dividir cantidad a nueva carga** también funciona cuando algunos de los encabezados de trabajo restantes tienen un estado de *En proceso*. Por lo tanto, aún puede usar la funcionalidad incluso si los trabajadores ya están ejecutando las órdenes de recogida.
- Si selecciona **Cancelar cantidad no cumplida** mientras queda trabajo que tiene un estado de *Abierto* o *En progreso*, recibirá el siguiente mensaje de error: "No se puede cancelar la cantidad restante para la carga. Existe trabajo para la carga".
- Si selecciona **Cancelar cantidad no cumplida** cuando no queda trabajo pero hay líneas de carga inéditas en la carga, recibirá el siguiente mensaje de error: "No se pudo confirmar el envío para la carga porque la cantidad del artículo excede el porcentaje que se define por debajo de la entrega". Para evitar el error, puede configurar el porcentaje **Bajo entrega** en la línea de carga inédita al 100 %. Las líneas no lanzadas no se moverán a una nueva carga, pero la carga actual se confirmará con una entrega insuficiente. En este caso, no podrá volver a lanzar el pedido original. Por lo tanto, tendrá que gestionarlo de alguna otra forma.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]