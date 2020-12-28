---
title: Selección de clúster dirigida por el sistema
description: Este tema proporciona una descripción general de la selección de clúster dirigida por el sistema en Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkCluster, WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 0838405bcb5ee0d8e582093fbbd69553228cb2b6
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437244"
---
# <a name="system-directed-cluster-picking"></a>Selección de clúster dirigida por el sistema

[!include [banner](../includes/banner.md)]

La selección de clúster es un proceso de selección de piezas que le permite elegir artículos para múltiples pedidos al mismo tiempo agrupándolos en clústeres de selección. Después tendrá que visitar el lugar de selección una sola vez. Por lo general, esta funcionalidad se usa para seleccionar pedidos pequeños o cantidades que son menores que la de cajas.

Cuando se configura la selección de clúster dirigida por el sistema, puede seleccionar los encabezados de trabajo de selección de clúster en función de un clúster generado por el sistema. El sistema selecciona en clúster los pedidos hasta el número de posiciones especificado en el perfil del clúster. Por lo tanto, puede seleccionar varios pedidos a la vez sin tener que crear manualmente un clúster.

La selección de clúster dirigida por el sistema ofrece una alternativa a la creación manual de clúster, donde se utiliza un perfil de clúster para crear un clúster. Hay que definir varias líneas relacionadas con la configuración en el perfil del clúster antes de usarlo:

- **Numero de posiciones** corresponde al número de pedidos que se colocarán en un clúster. Por lo tanto, corresponde al número de bolsas.
- **Dividir clúster** determina cuándo se debe dividir el clúster.
- **Generar id. de clúster** controla si el sistema generará el id. del clúster o si lo especificará el usuario.
- **Tipo de comprobación del orden** determina si se requiere la comprobación de posición.

Se utiliza un nuevo elemento de menú de dispositivo móvil para la selección de clúster dirigida por el sistema. El **Id. de perfil del clúster** debe especificarse para la opción seleccionada **Dirigido por**. Además, las consultas de secuencias de trabajo dirigidas por el sistema pueden agrupar pedidos en función de criterios específicos de la empresa. Esto le permite optimizar todavía más la asignación de órdenes de trabajo especificando criterios de ordenación personalizados usando las consultas de secuencia de trabajos dirigidas por el sistema.

Cuando se habilita la selección de clúster dirigida por el sistema, a los trabajadores del almacén se les presenta un clúster donde las órdenes de selección se han asignado previamente a las posiciones de clúster. Por lo tanto, los trabajadores pueden comenzar a seleccionar un artículo para múltiples órdenes de trabajo visitando una sola vez la ubicación de selección. El proceso de selección para la selección de clúster dirigida por el sistema es el mismo que el proceso para la selección de clúster dirigida por el usuario.

## <a name="enable-the-system-directed-cluster-picking-feature"></a>Habilitar la característica de selección de clúster dirigida por el sistema

Antes de poder usar esta característica, debe estar habilitada en su sistema. Los administradores pueden usar la página [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y habilitarla si es necesario. Aquí, la característica aparece como:

- **Módulo**: gestión de almacén
- **Nombre de característica**: elección de clúster dirigida por el sistema

Esta característica también requiere habilitar una característica dependiente. La característica dependiente es:

- **Módulo**: gestión de almacén
- **Nombre de la característica**: secuencia de trabajo dirigida al sistema de secuenciación de trabajo

## <a name="set-up-system-directed-cluster-picking"></a>Configurar la selección de clúster dirigida por el sistema

### <a name="create-cluster-profiles"></a>Crear perfiles de clúster

Los perfiles de clúster controlan cómo el sistema crea cada clúster. Si se requieren diferentes clústeres, se debe crear un perfil de grupo diferente para cada elemento del menú de dispositivo móvil.

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Perfiles de clúster**.
2. Seleccione **Nuevo**.
3. En el campo **Id. de perfil de clúster**, escriba **Posición 2**.
4. En el campo **Nombre**, especifique **Posición 2**.
5. En la ficha desplegable **General**, especifique la información siguiente:

    - **Generar ID de clúster**: seleccione **Sí**. Esta opción determina si el sistema crea automáticamente el id. del clúster o si el usuario lo creará al comienzo de la selección. 
    - **Activar posiciones**: seleccione **Sí**. Esta opción determina si los nombres de las posiciones se generan automáticamente en función de la configuración del nombre de la posición. Si esta opción está establecida en **No** se usará el id. de matrícula para la posición.
    - **Número de posiciones**: seleccione **2**. Este campo determina el número máximo de posiciones que puede tener el clúster (es decir, el número máximo de cajas, bolsas, etc.).
    - **Nombre de la posición**: seleccione **Numérico** para designar a las posiciones usando números consecutivos. Si selecciona **Alfabético**, se asignarán nombres a las posiciones por orden alfabético.
    - **Dividir clúster en**: seleccione **Colocar**. Este campo determina cuándo se divide el clúster. 
    - **Tipo de comprobación del orden**: seleccione **Escaneo de posición**. Este campo determina si se comprueba el paso de colocación en posición.
        
6. En la ficha desplegable **Ordenación de clústeres**, puede definir criterios de ordenación creando una nueva línea e introduciendo la siguiente información:

    - **Secuencia numérica**: seleccione **1**. Este campo determina la secuencia que ordena el sistema. Se introduce un valor automáticamente, pero puede cambiarlo si es necesario.
    - **Nombre de campo**: introduzca **WMSLocationId**. Este campo determina el campo que la línea usa para los criterios de ordenación.
    - **Ordenación**: seleccione **Ascendente**. Este campo define si la ordenación se realiza en orden ascendente o descendente.

### <a name="create-a-mobile-device-menu-item"></a>Crear un elemento de menú del dispositivo móvil

Para crear un nuevo elemento del menú de dispositivo móvil para la selección de clúster dirigida por el sistema y vincular el id. de perfil del clúster al elemento del menú de dispositivo móvil, siga estos pasos.

1. Vaya a **Gestión de almacenes > Configurar > Dispositivo móvil > Elementos de menú del dispositivo móvil**.
1. Seleccione **Nuevo**.
1. En la sección de encabezado, especifique la información siguiente:
    - **Nombre del elemento del menú**: clúster SD
    - **Título**: clúster SD
    - **Modo**: trabajo
    - **Usar trabajo existente**: sí

1. En la ficha desplegable **General**, especifique la información siguiente:
    - **Dirigido por**: elección de clústeres dirigida por el sistema
    - **Generar matrícula**: sí
    - **Id. de perfil de clúster**: posición 2

1. En la ficha rápida **Clases de trabajo**, configure la clase de trabajo válida para este elemento de menú del dispositivo móvil configurando los siguientes campos:
    - **Id. de la clase de trabajo**: ventas
    - **Tipo de orden de trabajo**: pedidos de venta

1. En el panel Acciones **Elementos de menú del dispositivo móvil**, seleccione **Consultas de secuencia de trabajo dirigidas por el sistema** y siga estos pasos para especificar una nueva consulta de secuencia de trabajo dirigida por el sistema:
    - Seleccione **Nuevo** en el panel Acciones.
    - **Número de secuencia**: 1
    - **Descripción**: prioridad de trabajo, id. de trabajo

1. En el panel Acciones, seleccione **Editar consulta**
1. Seleccione la pestaña **Ordenar**
1. Seleccione **Añadir** para agregar una nueva línea y luego introduzca lo siguiente:
    - **Tabla**: trabajo
    - **Tabla derivada**: trabajo
    - **Campo**: prioridad de trabajo
    - **Dirección de búsqueda**: ascendente
1. Seleccione **Añadir** para agregar una segunda línea y luego introduzca lo siguiente:
    - **Tabla**: trabajo
    - **Tabla derivada**: trabajo
    - **Campo**: id. de trabajo
    - **Dirección de búsqueda**: ascendente

1. Ahora el sistema ordenará los id. de trabajo en el clúster, primero por prioridad de trabajo y luego por id. de trabajo.

### <a name="set-up-a-mobile-device-menu"></a>Configurar un menú de dispositivo móvil

1. Vaya a **Gestión de almacenes > Configurar > Dispositivo móvil > Menú del dispositivo móvil**.
1. Agregue el elemento de menú **Clúster SD** que acaba de crear a un menú de dispositivo móvil.
1. Seleccione el menú **Saliente**.
1. En el panel Acciones, seleccione **Editar**.
1. Desplácese hasta encontrar **Clúster SD**.
1. Seleccione **Clúster SD**, y se habilitará la flecha que apunta a la **Estructura del menú**.
1. Seleccione el botón de **flecha** para mover el elemento de menú **Clúster SD** a la estructura de menú **Saliente**.
1. Seleccione **Clúster SD** desde la lista **Estructura del menú** y luego seleccione las flechas **ARRIBA** o **ABAJO** para mover el elemento del menú a la posición deseada del menú del dispositivo móvil.

## <a name="scenario"></a>Situación

### <a name="create-picking-work"></a>Crear trabajo de selección

Antes de poder configurar la selección de clúster dirigida por el sistema, debe crear un trabajo de salida válido. El perfil de clúster que creó anteriormente especifica dos posiciones de clúster. Por lo tanto, debe crear al menos dos identificadores de trabajo. En este escenario, creará dos pedidos de ventas, reservará inventario, despachará los pedidos de ventas al almacén y luego procesará manualmente la oleda.

1. Vaya a **Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas**.
1. Seleccione **Nuevo** en el panel Acciones para crear el primer pedido de ventas.
    - Se abrirá el menú **Crear pedido de ventas**, introduzca la siguiente información:
        - En la ficha desplegable **Cliente**, introduzca **Cuenta de cliente** - **US-004**.
        - En la ficha desplegable **General**, introduzca **Almacén** - **62**.
        - Seleccione **Aceptar** para cerrar el menú y crear el pedido de venta.
    - En la ficha desplegable **Líneas de pedido de venta**, seleccione **Añadir línea** si no se agrega automáticamente una nueva línea e introduzca lo siguiente:
        - **Número de artículo**: A0001
        - **Cantidad**: 1
        - Seleccione **Agregar línea** para agregar una segunda línea.
        - **Número de artículo**: A0002
        - **Cantidad**: 3
    - Reserve inventario para las dos líneas que acaba de crear.
        - Seleccione **Línea 1**.
        - En el panel Acciones **Líneas de pedido de venta**, seleccione **Inventario** y luego seleccione **Reserva** en la lista.
        - En el formulario **Reserva**, seleccione **Reservar lote interno** para reservar el inventario.
        - Cierre el formulario **Reserva** cuando se complete la reserva.
        - Repita estos pasos para reservar inventario para **Línea 2**.
1. Seleccione **Nuevo** en el panel Acciones para crear el segundo pedido de ventas
    - Se abrirá el menú **Crear pedido de ventas**, introduzca la siguiente información:
        - En la ficha desplegable **Cliente**, introduzca **Cuenta de cliente** - **US-005**.
        - En la ficha desplegable **General**, introduzca **Almacén** - **62**.
        - Seleccione **Aceptar** para cerrar el menú y crear el pedido de venta
    - En la ficha desplegable **Líneas de pedido de venta**, seleccione **Añadir línea** si no se agrega automáticamente una nueva línea e introduzca la siguiente información:
        - **Número de artículo**: A0001
        - **Cantidad**: 4
        - Seleccione **Agregar línea** para agregar una segunda línea.
        - **Número de artículo**: A0002
        - **Cantidad**: 2
    - Reserve inventario para las dos líneas que acaba de crear.
        - Seleccione **Línea 1**.
        - En el panel Acciones **Líneas de pedido de venta**, seleccione **Inventario** y luego seleccione **Reserva** en la lista.
        - En el formulario **Reserva**, seleccione **Reservar lote interno** para reservar el inventario.
        - Cierre el formulario **Reserva** cuando se complete la reserva.
        - Repita estos pasos para reservar inventario para **Línea 2**.
    - Cierre el pedido de ventas y vuelva a la página de la lista **Todos los pedidos de venta**.
1. Encuentre los dos pedidos de ventas que acaba de crear (es posible que deba actualizar la página). En la tabla, seleccione ambas órdenes de venta utilizando la marca de verificación de la sección.
    - En el panel Acciones **Todos los pedidos de ventas**, seleccione la pestaña **Almacén**.
    - En el grupo **Acciones**, seleccione **Despachar al almacén** para despachar ambos pedidos de ventas al almacén.
1. Cuando se completa el proceso de despacho al almacén, se mostrará un mensaje informativo.
    - Se crearán envíos para cada pedido de ventas.
    - Se creará una oleada y ambos envíos se asignarán a la oleada. Anote el **Id. de oleada**.
1. Vaya a **Gestión de almacenes > Oleadas de salida > Oleadas de envío > Todas las oleadas**.
    - En la lista **Todas las oleadas**, busque y seleccione el **Id. de oleada** que creó en el paso anterior.
    - En el panel Acciones, seleccione la pestaña **Oleada**.
    - En el grupo **Oleada**, seleccione **Proceso** para procesar la oleada y cree **Trabajo**.
    - Se generarán mensajes informativos cuando se haya completado el procesamiento, indicando que se ha creado trabajo y se ha publicado la oleada.
1. **Opcional**: vaya a **Gestión de almacenes > Trabajo> Detalles del trabajo** para ver el trabajo creado. Se crean dos identificadores de trabajo diferentes. Cada id. de trabajo tiene dos líneas de selección.

### <a name="run-the-mobile-device-flow"></a>Ejecutar el flujo del dispositivo móvil

1. Inicie sesión en el dispositivo móvil para un usuario en el almacén **62**.
1. En el **Menú principal**, seleccione **Saliente**.
1. En el menú **Saliente**, seleccione el elemento de menú **Clúster SD** para iniciar la selección.
    - Se crea un clúster y se le adjuntan los dos id. que creó anteriormente. Si creó más de dos identificadores de trabajo, solo se agregarán los dos primeros al clúster. Tenga en cuenta que los identificadores de trabajo se agregan al clúster en orden ascendente, como especificó en la configuración de la consulta.

    > [!NOTE]
    > El nuevo clúster se crea automáticamente solo si se creó previamente una cantidad suficiente de identificadores de trabajo adicionales. De lo contrario, se muestra el siguiente mensaje: "No se encuentra trabajo suficiente para el clúster".

    - Después de seleccionar el menú, aparece la primera pantalla de selección. El sistema agrega todas las líneas de selección coincidentes de los dos identificadores de trabajo y le indica que visite la ubicación de selección una vez para poder satisfacer ambos pedidos mediante una sola selección. Este proceso se realiza de la misma manera que el proceso de selección de clúster dirigida por el usuario.

1. Confirme la primera ubicación de selección y el artículo seleccionando **Aceptar**.
    - La cantidad de la selección será el total del artículo que se muestra en los pedidos de ventas en el clúster.
1. introduzca el nombre de la posición (numérico o alfabético) para confirmar que la cantidad de artículos elegida para la posición se colocó en la posición correcta.
1. Repita este proceso hasta que todas las cantidades de artículos se hayan seleccionado y colocado en la posición correcta.
1. El último paso en el dispositivo móvil es **Colocar** el clúster en la ubicación final. Seleccione **Aceptar**
    - Cuando se confirma esta operación de colocación, el clúster se cierra y se divide según el valor que establecido en el campo **Dividir clúster en** del perfil del clúster. Los identificadores de trabajo también se cierran.
1. Se muestra un mensaje de "Clúster completo" en el dispositivo móvil.
