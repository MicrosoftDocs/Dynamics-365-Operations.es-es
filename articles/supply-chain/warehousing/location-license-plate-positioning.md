---
title: Posición de matrícula de entidad de almacén de ubicación
description: El posicionamiento de la ubicación de la matrícula de entidad le permite ver dónde se encuentra una matrícula de entidad en una ubicación de paletas múltiples, como una ubicación que utiliza estanterías de paletas de doble profundidad.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLicensePlate, WHSLocationProfile, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 4dc084e4ef568d97912bfa22657b616fd6e493e03ad95703db66584f03e5381e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739691"
---
# <a name="location-license-plate-positioning"></a>Posición de matrícula de entidad de almacén de ubicación

[!include [banner](../includes/banner.md)]

El posicionamiento de la ubicación de la matrícula de entidad le permite ver dónde se encuentra una matrícula de entidad en una ubicación de paletas múltiples, como una ubicación que utiliza estanterías de paletas de doble profundidad.

La función agrega un número de secuencia a cada matrícula de entidad que se coloca en una ubicación de almacenamiento. Este número de secuencia se usa para pedir las matrículas de entidad en la ubicación de almacenamiento. Por lo tanto, la función admite de manera inteligente escenarios en los que los clientes están utilizando un sistema de estantería por gravedad y deben saber, con fines de selección, qué matrícula de entidad está orientada hacia el frente.

Este tema presenta un escenario que muestra cómo configurar y usar la función.

## <a name="turn-on-the-location-license-plate-positioning-feature"></a>Active la función de posicionamiento de matrícula de ubicación

Antes de que pueda usar el posicionamiento de ubicación de matrícula de entidad, debe activar la función en su sistema. Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:

- **Módulo:** *Gestión de almacén*
- **Nombre de la función:** *Posicionamiento de ubicación de matrícula de entidad*

## <a name="example-scenario"></a>Supuesto de ejemplo

### <a name="make-sample-data-available"></a>Hacer que los datos de muestra estén disponibles

Para resolver este escenario utilizando los valores que se sugieren aquí, debe trabajar en un sistema donde se instalen datos de muestra. Además, también debe seleccionar la entidad legal **USMF** antes de comenzar.

### <a name="set-up-the-feature-for-this-scenario"></a>Configure la función para este escenario

Complete los siguientes procedimientos para configurar la característica de *Posicionamiento de ubicación de matrícula de entidad* para el escenario que se presenta en este tema.

#### <a name="location-profiles"></a>Perfiles de ubicación

La función debe estar activada en el perfil de ubicación para cada ubicación donde se utilizará.

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Perfiles de ubicación**.
1. En la lista de perfiles de ubicación en el panel izquierdo, seleccione **BULK-06**.
1. En la ficha desplegable **General**, la función ha agregado dos nuevas opciones. Establezca los valores siguientes:

    - **Habilitar la posición de la matrícula:** *Sí*

        Cuando esta opción se establece en *Sí*, la posición de la matrícula de entidad se mantendrá para las matrícula de entidad en la ubicación.

    - **Mostrar la posición LP del dispositivo móvil:** *Sí*

        Cuando esta opción se establece en *Sí*, la posición de la matrícula de entidad se mostrará a los usuarios de dispositivos móviles durante el ajuste y el recuento. Puede cambiar la configuración de esta opción solo cuando la función está activada.

1. Seleccione **Guardar**.

#### <a name="location-directives"></a>Directivas de ubicación

1. Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.
1. En el panel izquierdo, asegúrese de que el campo **Tipo de orden de trabajo** se establece en *Pedidos de ventas*.
1. En la lista de directivas de ubicación, seleccione **61 SO Orden de recogida**.
1. En el panel Acciones, seleccione **Editar**.
1. En la ficha desplegable **Líneas**, seleccione la línea que tiene un valor de **Secuencia de números** de *2*.
1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione la línea que tiene un valor **Nombre** de *Elija por menos de palet* (debería ser la única línea) y cambie su valor **Secuencia de números** a *2*.
1. Seleccione **Nuevo** encima de la cuadrícula para agregar una línea para una nueva acción directiva de ubicación.
1. En la nueva línea, establezca los siguientes valores:

    - **Número de secuencia:** *1*
    - **Nombre:** *Elegir posición 1*

1. Mientras la nueva línea aún está seleccionada, seleccione **Editar consulta** sobre la cuadrícula.
1. En el editor de consultas, seleccione la pestaña **Uniones**.
1. Expanda la tabla **Ubicaciones** de unión para mostrar la unión a la tabla **Dimensiones de inventario**.
1. Expanda la tabla **Dimensiones de inventario** de unión para mostrar la unión a la tabla **Inventario disponible**.
1. Seleccione **Dimensiones de inventario** y luego seleccione **Agregar unión de tabla**.
1. En la lista de tablas que aparece, en la columna **Relación**, seleccione **Matrícula (matrícula de entidad)**. Luego seleccione **Seleccionar** para agregar **Matrícula de entidad** a la tabla de unión **Dimensiones de inventario**.
1. Mientras **Matrícula de entidad** todavía está seleccionado, seleccione **Agregar unión de tabla**.
1. En la lista de tablas que aparece, en la columna **Relación**, seleccione **Posicionamiento de ubicación de matrícula (matrícula de entidad)**. Luego seleccione **Seleccionar** para agregar **Posicionamiento de ubicación de matrícula de entidad** a la tabla de unión **Dimensiones de inventario**.

    ![Uniones de tabla.](media/LpTableJoin.png "Uniones de tabla")

1. Seleccione **Aceptar** para confirmar las tablas unidas actualizadas y cerrar el editor de consultas.
1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Editar consulta** para abrir de nuevo el cuadro de diálogo del editor de consultas.
1. En la ficha **Rango**, seleccione **Nuevo** para agregar una línea a la cuadrícula.
1. En la nueva línea, establezca los siguientes valores:

    - **Tabla:** *Posicionamiento de ubicación de matrícula de entidad*
    - **Tabla derivada:** *Posicionamiento de ubicación de matrícula de entidad*
    - **Campo:** *Posición LP*
    - **Criterio:** *1*

    ![Nuevo rango.](media/LpPositionCriteria.png "Nuevo rango")

1. Seleccione **Aceptar** para confirmar sus cambios y cerrar el editor de consultas.

### <a name="set-up-sample-data-for-this-scenario"></a>Configure los datos de muestra para este escenario

Para este escenario, el usuario debe iniciar sesión en la aplicación móvil de almacenamiento mediante el uso de un trabajador configurado para el almacén *61* para realizar trabajo. El usuario también debe completar las transacciones.

Debido a que la función *Posicionamiento de ubicación de matrícula de entidad* agrega un nuevo identificador para las posiciones de matrícula en una ubicación, primero debe crear algunos datos para admitir el escenario.

#### <a name="spot-count-the-first-location"></a>Recuento de la primera ubicación

1. Abra la aplicación móvil de almacenaje e inicie sesión en el almacén *61*.
1. Vaya a **Inventario \> Recuento puntual**.
1. En la página **Recuento puntual**, configure el campo **Ubicación** a *01A01R1S1B*.
1. Seleccione **Aceptar**.

    La página muestra la ubicación que introdujo. También muestra el siguiente mensaje: "¿Ubicación completa, agregar nuevo LP o artículo?"

1. Seleccione **Actualizar** para agregar un recuento en la ubicación.
1. En la página **Recuento de ciclos: agregar nuevo LP o artículo**, seleccione el campo **Artículo** y luego introduzca el valor *A0001*.
1. Seleccione **Aceptar**.
1. En la página **Recuento de ciclos: agregar nuevo LP o artículo**, seleccione el campo **LP** y luego introduzca el valor *LP1001* (o cualquier otro número de matrícula de entidad de su elección).

    La página **Recuento de ciclos: agregar nuevo LP o artículo** muestra **Matrícula de entidad Posición 1**.

1. Seleccione **Aceptar**.

    Ahora debe especificar la cantidad del artículo que se cuenta en la matrícula de entidad.

1. Establezca el campo **Cantidad** a *10*.
1. Seleccione **Aceptar**.

    La página muestra la ubicación que introdujo. También muestra el siguiente mensaje: "¿Ubicación completa, agregar nuevo LP o artículo?"

1. Seleccione **Actualizar** para agregar otro recuento en la ubicación.
1. En la página **Recuento de ciclos: agregar nuevo LP o artículo**, seleccione el campo **Artículo** y luego introduzca el valor *A0002*.
1. Seleccione **Aceptar**.
1. En la página **Recuento de ciclos: agregar nuevo LP o artículo**, seleccione el campo **LP** y luego introduzca el valor *LP1002* (o cualquier otra matrícula de entidad de almacén de su elección, siempre que difiera de la matrícula de entidad de almacén que especificó anteriormente).
1. Cambie la posición de la matrícula de entidad configurando el campo **Posición LP** a *2*.
1. Seleccione **Aceptar**.
1. Especifique la cantidad del artículo que se cuenta en la matrícula de entidad configurando el campo **Cantidad** a *10*.
1. Seleccione **Aceptar**.

    La página muestra la ubicación que introdujo. También muestra el siguiente mensaje: "¿Ubicación completa, agregar nuevo LP o artículo?"

1. Seleccione **Aceptar**.

El trabajo se completó.

#### <a name="spot-count-the-second-location"></a>Recuento de la segunda ubicación

1. En la página **Recuento puntual**, configure el campo **Ubicación** a *01A01R1S2B*.
1. Seleccione **Aceptar**.

    La página muestra la ubicación que introdujo. También muestra el siguiente mensaje: "¿Ubicación completa, agregar nuevo LP o artículo?"

1. Seleccione **Actualizar** para agregar un recuento en la ubicación.
1. En la página **Recuento de ciclos: agregar nuevo LP o artículo**, seleccione el campo **Artículo** y luego introduzca el valor *A0002*.
1. Seleccione **Aceptar**.
1. En la página **Recuento de ciclos: agregar nuevo LP o artículo**, seleccione el campo **LP** y luego introduzca el valor *LP1003* (o cualquier otra matrícula de entidad de almacén de su elección, siempre que difiera de ambas matrículas de entidad de almacén que especificó anteriormente).

    La página **Recuento de ciclos: agregar nuevo LP o artículo** muestra **Matrícula de entidad Posición 1**.

1. Seleccione **Aceptar**.
1. Especifique la cantidad del artículo que se cuenta en la matrícula de entidad configurando el campo **Cantidad** a *10*.
1. Seleccione **Aceptar**.

    La página muestra la ubicación que introdujo. También muestra el siguiente mensaje: "¿Ubicación completa, agregar nuevo LP o artículo?"

1. Seleccione **Aceptar**.

El trabajo se completó.

#### <a name="work-details"></a>Detalles del trabajo

> [!NOTE]
> Los recuentos puntuales desde la aplicación móvil crean trabajo de recuento cíclico en Microsoft Dynamics 365. El trabajo requiere que se acepten los recuentos antes de contabilizarlos en el inventario.

1. Inicie sesión en Dynamics 365 Supply Chain Management.
1. Vaya a **Gestión de almacenes \> Trabajo \> Detalles de trabajo**.
1. En la pestaña **Visión general**, busque las líneas que tienen los siguientes valores:

    - **Tipo de orden de trabajo:** *Recuento cíclico*
    - **Almacén**: *61*
    - **Situación del trabajo:** *Revisión pendiente*

    Se deberían haber creado dos identificadores de trabajo para estas líneas. Se deben aceptar los recuentos de ambos identificadores de trabajo.

1. En la cuadrícula, seleccione la primera identificación de trabajo para el tipo de orden de trabajo *Recuento cíclico*.
1. En el panel de acciones, en la pestaña **Trabajo**, en el grupo **Trabajo**, seleccione **Recuento cíclico**.

    Se muestran dos líneas, una para cada artículo y matrícula de entidad. Los valores en los campos **Cantidad contada**, **Ubicación**, **Matrícula de entidad** y **Artículo** deben coincidir con las entradas de recuento que creó en el dispositivo móvil. Si alguno de estos campos no está visible, seleccione **Dimensiones de la pantalla** en el Panel de acciones para agregarlos a la cuadrícula.

1. Seleccione ambas líneas.
1. En el panel de acciones, seleccione **Aceptar recuento**.
1. Recibirá un mensaje de "Publicación - Diario". Seleccione **Detalles del mensaje** para ver el número de diario publicado.
1. Cierre los detalles del mensaje.
1. Actualice la página **Trabajo**.

    La primera identificación de trabajo se ha cerrado y ya no se muestra.

    > [!TIP]
    > Para ver el trabajo cerrado, seleccione la casilla de verificación **Mostrar cerrado** sobre la cuadrícula.

    Ahora aceptará el trabajo para la matrícula de entidad en la ubicación *01A01R1S2B*.

1. En la pestaña **Vista general**, seleccione la segunda identificación de trabajo para el tipo de orden de trabajo *Recuento cíclico*.
1. En el panel de acciones, en la pestaña **Trabajo**, en el grupo **Trabajo**, seleccione **Recuento cíclico**.

    Se muestra una línea para el artículo y la matrícula. Los valores en los campos **Cantidad contada**, **Ubicación**, **Matrícula de entidad** y **Artículo** deben coincidir con las entradas de recuento que creó en el dispositivo móvil.

1. Seleccione la línea.
1. En el panel de acciones, seleccione **Aceptar recuento**.
1. Recibirá un mensaje de "Publicación - Diario". Seleccione **Detalles del mensaje** para ver el número de diario publicado.
1. Cierre los detalles del mensaje.
1. Actualice la página **Trabajo**.

    La segunda identificación de trabajo se ha cerrado y ya no se muestra.

    > [!TIP]
    > Para ver el trabajo cerrado, seleccione la casilla de verificación **Mostrar cerrado** sobre la cuadrícula.

#### <a name="on-hand-by-location"></a>Inventario disponible por ubicación

1. Vaya a **Gestión de almacén \> Consultas e informes \> Inventario disponible por ubicación**.
1. Establezca los valores siguientes:

    - **Sitio**: *6*
    - **Almacén**: *61*
    - **Actualizar entre ubicaciones:** *Sí*

1. Tenga en cuenta que la ubicación *01A01R1S1B* tiene dos matrículas de entidad:

    - **A0001**, donde el campo **Posición LP** se establece en *1*
    - **A0002**, donde el campo **Posición LP** se establece en *2*

1. Tenga en cuenta que la ubicación *01A01R1S2B* tiene una matrícula de entidad:

    - **A0002**, donde el campo **Posición LP** se establece en *1*

### <a name="sales-order-scenario"></a>Escenario de pedidos de ventas

Ahora que la función *Posicionamiento de ubicación de matrícula de entidad* se ha configurado y se ha organizado el inventario, debe crear un pedido de ventas para generar el trabajo de selección que indicará al trabajador del almacén que elija el artículo *A0002* desde la ubicación del inventario donde se encuentra la identificación del pallet *1*.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - **Cuenta de cliente:** *US-004*
    - **Almacén**: *61*

1. Seleccione **Aceptar**.
1. Se agrega una nueva línea a cuadrícula en la ficha desplegable **Líneas de pedido de ventas**. En esta nueva línea, establezca los siguientes valores:

    - **Código de artículo:** *A0002*
    - **Cantidad:** *1*

1. En el menú **Inventario** sobre la cuadrícula, seleccione **Reserva**.
1. En la página **Reserva**, en el Panel de acciones, seleccione **Reservar lote** para reservar inventario para la línea de pedido.
1. Cierre la página **Reserva**.
1. En el panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**.

    Recibirá un mensaje informativo que indican el trabajo, la identificación de oleada y el identificador de envío que se crean para el pedido.

1. En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Almacén**, sobre la cuadrícula, seleccione **Detalles del trabajo**.
1. Aparecerá la página **Trabajo** y muestra el trabajo que se creó para la línea de ventas. Anote el identificador de trabajo que se muestra.

### <a name="sales-picking-scenario"></a>Escenario de selección de ventas

1. Abra la aplicación móvil e inicie sesión en el almacén *61*.
1. Vaya a **Saliente \> Selección de ventas**.
1. En la página **Escanear una identificación de trabajo / identificación de matrícula de entidad**, seleccione el campo **Identificación** y luego introduzca la identificación de trabajo desde la línea de ventas.
1. Tenga en cuenta que el trabajo de selección lo dirige a elegir el artículo *A0002* desde la ubicación *01A01R1S2B*. Recibe esta instrucción porque el artículo *A0002* está en una matrícula de entidad que está en la posición *1* en esa ubicación.

    ![Ubicación de la posición 1.](media/LocationLicensePlatePositioning.png "Ubicación de la posición 1")

1. Introduzca la identificación de la matrícula de entidad que creó para la ubicación y luego siga las indicaciones para elegir el pedido de ventas.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]