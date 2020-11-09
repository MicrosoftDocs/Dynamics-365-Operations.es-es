---
title: Configurar directivas de consolidación de envíos
description: Este tema explica cómo configurar directivas de consolidación de envíos predeterminadas y personalizadas.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, TMSMode, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: adb88bbd29a89a1d18d7fd4781c2541ffb4e721f
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016226"
---
# <a name="configure-shipment-consolidation-policies"></a>Configurar directivas de consolidación de envíos

[!include [banner](../includes/banner.md)]

El proceso de consolidación de envíos que utiliza directivas de consolidación de envíos permite la consolidación automatizada de envíos durante la liberación automática y manual al almacén. Después de activar esta característica, debe configurar sus directivas iniciales. Si no se configuran directivas, cada línea de ventas generará un envío separado que tiene una sola línea de carga.

Los escenarios que se presentan en este tema muestran cómo configurar directivas de consolidación de envío predeterminadas y personalizadas.

## <a name="turn-on-the-shipment-consolidation-policies-feature"></a>Active la característica Directivas de consolidación de envíos

> [!IMPORTANT]
> En el [primer escenario](#scenario-1) que se describe en este tema, primero configurará un almacén para que use la característica de consolidación de envíos anterior. Luego, hará que las directivas de consolidación de envíos estén disponibles. De esta manera, puede experimentar cómo funciona el escenario de actualización. Si planea utilizar un entorno de datos de demostración para pasar por el primer escenario, no active la característica antes de pasar por el escenario.

Antes de poder usar la característica *Directivas de consolidación de envíos* , debe activarla en su sistema. Los administradores pueden usar la configuración de [gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla. En el espacio de trabajo **Administración de características** , la característica aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de la característica:** *Consolidar envío*

## <a name="make-demo-data-available"></a>Hacer que los datos de demostración estén disponibles

Cada escenario de este tema hace referencia a valores y registros que se incluyen en los datos de demostración estándar que se proporcionan para Microsoft Dynamics 365 Supply Chain Management. Si desea utilizar los valores que se proporcionan aquí mientras realiza los ejercicios, asegúrese de trabajar en un entorno donde estén instalados los datos de demostración y configure la entidad jurídica en **USMF** antes de empezar.

## <a name="scenario-1-configure-default-shipment-consolidation-policies"></a><a name="scenario-1"></a>Escenario 1: configurar directivas de consolidación de envíos predeterminadas

Hay dos situaciones en las que debe configurar el número mínimo de directivas predeterminadas después de activar la característica *Directivas de consolidación de envíos*.

- Está actualizando un entorno que ya contiene datos.
- Está configurando un entorno completamente nuevo.

### <a name="upgrade-an-environment-where-warehouses-are-already-configured-for-cross-order-consolidation"></a>Actualice un entorno donde los almacenes ya están configurados para la consolidación de pedidos cruzados

Cuando comienza este procedimiento, la característica *Directivas de consolidación de envíos* debería estar desactivada, para simular un entorno en el que ya se haya utilizado la característica básica de consolidación de orden cruzado. Luego usará la administración de características para activar la característica, de modo que pueda aprender cómo configurar directivas de consolidación de envíos después de la actualización.

Siga estos pasos para configurar directivas de consolidación de envío predeterminadas en un entorno donde los almacenes ya se han configurado para la consolidación de pedidos cruzados.

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Almacenes**.
1. En la lista, busque y abra el registro de almacén deseado (por ejemplo, almacén *24* en los datos de demostración **USMF** ).
1. En el panel Acciones, seleccione **Editar**.
1. En la ficha desplegable **Almacén** , configure la opción **Consolidar el envío en el despacho al almacén** en *Sí*.
1. Repita los pasos 2 a 4 para todos los demás almacenes donde se requiera consolidación.
1. Cierre la página.
1. Utilice [gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para activar la característica *Directivas de consolidación de envíos*. En el espacio de trabajo **Gestión de características** , la característica se llama *Consolidar envío*.
1. Vaya a **Gestion de almacenes \> Configurar \> Despachar al almacén \> Directivas de consolidación de envíos**. Puede que tenga que actualizar su navegador para ver el nuevo elemento de menú **Directivas de consolidación de envíos** después de activar la característica.
1. En el panel Acciones, seleccione **Crear configuración predeterminada** para crear las siguientes directivas:

    - Una directiva **CrossOrder** para el tipo de directiva *Ordenes de venta* (siempre que tenga al menos un almacén configurado para usar la característica de consolidación anterior)
    - Una directiva **Predeterminada** para el tipo de directiva *Ordenes de venta*
    - Una directiva **Predeterminada** para el tipo de directiva *Problema de transferencia*
    - Una directiva **CrossOrder** para el tipo de directiva *Problema de transferencia* (siempre que tenga al menos un almacén configurado para usar la característica de consolidación anterior)

    > [!NOTE]
    > - Ambas directivas **CrossOrder** consideran el mismo conjunto de campos que la lógica anterior, excepto el campo del número de pedido. (Ese campo se utiliza para consolidar líneas en envíos, en función de factores como el almacén, el modo de transporte de entrega y la dirección).
    > - Ambas directivas **Predeterminadas** consideran el mismo conjunto de campos que la lógica anterior, incluido el campo del número de pedido. (Ese campo se utiliza para consolidar líneas en envíos, en función de factores como número de pedido, el almacén, el modo de transporte de entrega y la dirección).

1. Selecciona la directiva **CrossOrder** para el tipo de directiva *Ordenes de venta* y luego, en el panel Acciones, seleccione **Editar consulta**.
1. En el cuadro de diálogo del editor de consultas, observe que se enumeran los almacenes donde la opción **Consolidar el envío en el despacho al almacén** está establecida en *Sí*. Por lo tanto, están incluidos en la consulta.

### <a name="create-default-policies-for-a-new-environment"></a>Crear directivas predeterminadas para un nuevo entorno

Siga estos pasos para configurar directivas de consolidación de envío predeterminadas en un entorno completamente nuevo.

1. Utilice [gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para activar la característica *Directivas de consolidación de envíos* , si todavía no la ha activado. En el espacio de trabajo **Gestión de características** , la característica se llama *Consolidar envío*.
1. Vaya a **Gestion de almacenes \> Configurar \> Despachar al almacén \> Directivas de consolidación de envíos**.
1. En el panel Acciones, seleccione **Crear configuración predeterminada** para crear las siguientes directivas:

    - Una directiva **Predeterminada** para el tipo de directiva *Ordenes de venta*
    - Una directiva **Predeterminada** para el tipo de directiva *Problema de transferencia*

    > [!NOTE]
    > Ambas directivas **Predeterminadas** consideran el mismo conjunto de campos que la lógica anterior, incluido el campo del número de pedido. (Ese campo se utiliza para consolidar líneas en envíos, en función de factores como número de pedido, el almacén, el modo de transporte de entrega y la dirección).

## <a name="scenario-2-configure-custom-shipment-consolidation-policies"></a>Escenario 2: configurar directivas de consolidación de envíos personalizadas

Este escenario muestra cómo configurar directivas de consolidación de envío personalizadas. Las directivas personalizadas pueden admitir requisitos comerciales complejos donde la consolidación de envíos depende de varias condiciones. Para cada directiva de ejemplo que aparece más adelante en este escenario, se incluye una breve descripción del caso de negocio. Estas directivas de ejemplo deben configurarse en una secuencia que garantice una evaluación similar a una pirámide de las consultas. (En otras palabras, las directivas que tienen la mayoría de las condiciones deben ser evaluadas como de mayor prioridad).

### <a name="turn-on-the-feature-and-prepare-master-data-for-this-scenario"></a>Active la característica y prepare los datos maestros para este escenario

Antes de poder realizar los ejercicios en este escenario, debe activar la característica y preparar los datos maestros necesarios para realizar el filtrado, como se describe en las subsecciones siguientes. (Estos requisitos previos también se aplican a los escenarios enumerados en [Escenarios de ejemplo de cómo usar las directivas de consolidación de envíos](#example-scenarios)).

#### <a name="turn-on-the-feature-and-create-the-default-policies"></a>Active la característica y cree las directivas predeterminadas

Utilice la administración de características para activar la característica, si aún no la ha activado, y cree las directivas de consolidación predeterminadas que se describen en el [escenario 1](#scenario-1).

#### <a name="create-two-new-product-filter-codes"></a>Crear dos nuevos códigos de filtro de producto

1. Vaya a **Gestion de almacenes \> Configurar \> Filtros de producto \> Filtros de producto** y agregue dos filtros de producto:

    - Filtro de productos 1:

        - **Código de filtro:** *Inflamable*
        - **Título del filtro:** *Código 4*

    - Filtro de productos 2:

        - **Código de filtro:** *Explosivo*
        - **Título del filtro:** *Código 4*

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Abra el producto con número de artículo *M9200*. (El producto que seleccione debe estar habilitado para procesos de almacén avanzado \[WMS\] y este producto está habilitado previamente para procesos WMS en los datos de demostración **USMF** ).
1. En la ficha desplegable **Almacén** , establezca el campo **Código 4** en *Inflamable*.
1. Cierre la página.
1. Abra el producto con número de artículo *M9201*. (Este producto también está habilitado previamente para procesos WMS en los datos de demostración **USMF** ).
1. En la ficha desplegable **Almacén** , establezca el campo **Código 4** en *Explosivo*.
1. Cierre la página.

#### <a name="create-a-new-transportation-mode-of-delivery"></a>Crear un nuevo modo de transporte de entrega

1. Vaya a **Administración de transporte \> Configuración \> Transportistas \> Modo**.
1. Cree un modo de transporte que se utilizará en consultas de consolidación y asígnele el nombre *Vías aéreas*.
1. Vaya a **Administración de transporte \> Configuración \> Transportistas \> Transportistas de envío**.
1. Cree un transportista con la siguiente configuración:

    - **Transportista de envío:** *Vías aéreas*
    - **Nombre:** *Vías aéreas*
    - **Modo:** *Vías aéreas*

1. En la ficha desplegable **Servicios** del nuevo operador, agregue una fila que tenga la siguiente configuración:

    - **Servicio de transportista:** *Aire*
    - **Método de transporte:** *Aire*

1. En el panel Acciones, seleccione **Guardar**.

    > [!NOTE]
    > Cuando guarde el nuevo transportista, el campo **Modo de entrega** para la nueva fila en la cuadrícula **Servicios** se establece automáticamente en *Airwa-Air*. Cuando usa el modo de entrega *Airwa-Air* para un pedido de ventas, el modo de transporte *Vías aéreas* se utilizará para los envíos relacionados.

#### <a name="create-an-order-pool"></a>Crear un grupo de pedidos

1. Vaya a **Ventas y marketing \> Configuración \> Pedidos de ventas \> Grupos de pedidos**.
1. Cree un grupo de pedidos que se utilizará para la consulta de consolidación. Este grupo de pedidos debe tener la siguiente configuración:

    - **Grupo:** Introduzca un número entero que no haya sido utilizado por ningún otro grupo.
    - **Nombre:** *ShipCons*

1. Vaya a **Ventas y marketing \> Clientes \> Todos los clientes**.
1. Abra el cliente que tiene el número de cuenta *US-003*.
1. En el ficha desplegable **Valores predeterminados de pedidos de ventas** , establezca el campo **Grupo de pedidos de ventas** en el grupo de órdenes que acaba de crear.
1. Cierre la página y luego repita los pasos 4 y 5 para el cliente que tiene el número de cuenta *US-004*.

### <a name="create-example-policy-1"></a>Crear directiva de ejemplo 1

En este ejemplo, creará una directiva *Cliente + Modo* que se puede usar para el siguiente caso de negocio:

- La directiva consultará una cuenta de cliente específica ( *US-001* ) y un modo específico de entrega ( *Airwa-Air* ).
- La consolidación con envíos abiertos está desactivada.
- La consolidación se realiza por id. de pedido. (En otras palabras, habrá envíos separados por pedido, almacén, etc.).

Siga estos pasos para crear la directiva de consolidación de envíos para este caso de negocios.

1. Vaya a **Gestion de almacenes \> Configurar \> Despachar al almacén \> Directivas de consolidación de envíos**.
1. Establezca el campo **Tipo de directiva** en *Ordenes de venta*.
1. En el panel Acciones, seleccione **Nuevo** para crear una directiva que tenga la siguiente configuración:

    - **Nombre de directiva:** *CustomerMode*
    - **Descripción de directiva:** *Cuenta de cliente y modo de entrega*

1. Deje la opción **Consolidar con envíos abiertos** establecida en *No*.
1. En el panel Acciones, seleccione **Guardar**.
1. En la ficha desplegable **Campos de consolidacion** , en la lista **Campos restantes** , seleccione la fila donde el campo **Nombre del campo** está establecido en *Modo de entrega*.
1. Seleccione el botón **Añadir** ![Flecha correcta](media/forward-button.png) para mover el campo a la lista **Campos seleccionados**.
1. En el panel Acciones, seleccione **Editar consulta**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Rango** , en la cuadrícula, busque la fila donde el campo **Campo** está establecido en *Cuenta de cliente* y establezca el campo **Criterio** para esa fila en *US-001*.
1. Seleccione **Añadir** para agregar una fila que tenga la siguiente configuración a la cuadrícula:

    - **Tabla:** *Líneas de pedido*
    - **Tabla derivada:** *Líneas de pedido*
    - **Campo:** *Modo de entrega*
    - **Criterio:** *Airwa-Air*

1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

> [!NOTE]
> Para este caso de negocio, las líneas de pedido para el cliente *US-001* que usan el modo de entrega *Airwa-Air* no se consolidarán en todos los pedidos. Esta directiva está destinada a usarse primero en una secuencia, en los casos en que los envíos para todos los demás modos de entrega se consoliden para este cliente.

### <a name="create-example-policy-2"></a>Crear directiva de ejemplo 2

En este ejemplo, creará una directiva *Mercancías peligrosas* que se puede usar para el siguiente caso de negocio:

- La directiva consultará un código de filtro específico ( *peligroso* ) y un modo específico de entrega ( *Airwa-Air* ).
- La consolidación con envíos abiertos está activada.
- La consolidación se realiza en todos los pedidos. (En otras palabras, habrá envíos separados por cuenta, almacén, etc., pero solo dentro del grupo de artículos que se especifica en la consulta).

Siga estos pasos para crear la directiva de consolidación de envíos para este caso de negocios.

1. Vaya a **Gestion de almacenes \> Configurar \> Despachar al almacén \> Directivas de consolidación de envíos**.
1. Establezca el campo **Tipo de directiva** en *Ordenes de venta*.
1. En el panel Acciones, seleccione **Nuevo** para crear una directiva que tenga la siguiente configuración:

    - **Nombre de directiva:** *Tipo de artículo*
    - **Descripción de directiva:** *Consolidar el mismo tipo de artículo en todos los pedidos*

1. Configure la opción **Consolidar con envíos abiertos** en *Sí*.
1. En el panel Acciones, seleccione **Guardar**.
1. En la ficha desplegable **Campos de consolidacion** , en la lista **Campos restantes** , seleccione la fila donde el campo **Nombre del campo** está establecido en *Modo de entrega*.
1. Seleccione el botón **Añadir** ![Flecha correcta](media/forward-button.png) para mover el campo a la lista **Campos seleccionados**.
1. En el panel Acciones, seleccione **Editar consulta**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Uniones** , expanda y seleccione **Tablas \> Detalles de carga** en el árbol.
1. Seleccione **Agregar unión de tabla**.
1. En la cuadrícula de relaciones que aparece, busque y seleccione la fila donde el campo **Relación** está establecido en *Número de artículo de almacén (número de artículo)* y luego elija **Seleccionar**. 
1. En la pestaña **Rango** , seleccione **Añadir** para agregar una fila que tenga la siguiente configuración a la cuadrícula:

    - **Tabla:** *Número de artículo del almacén*
    - **Tabla derivada:** *Número de artículo del almacén*
    - **Campo:** *Código 4*
    - **Criterio:** *Inflamable*

1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

> [!NOTE]
> Para este caso de negocio, todas las líneas de pedido donde los artículos tienen un código de filtro específico (es decir, el código de filtro donde el campo **Código 4** está establecido en *Inflamable* ) se consolidarán con otros artículos del mismo tipo en todos los pedidos. Si hay un envío abierto para la misma cuenta, almacén y grupo de artículos, se le adjuntarán las nuevas líneas.

### <a name="create-example-policy-3"></a>Crear directiva de ejemplo 3

En este ejemplo, creará una directiva *Requisitos del cliente* que se puede usar para el siguiente caso de negocio:

- La directiva consultará una cuenta de cliente específica.
- La consolidación con envíos abiertos está activada.
- La consolidación se realiza en todos los pedidos, pero se basa en las solicitudes de los clientes. (En otras palabras, los pedidos múltiples se agruparán en envíos, según el mismo número de solicitud del cliente y el mismo almacén).

Siga estos pasos para crear la directiva de consolidación de envíos para este caso de negocios.

1. Vaya a **Gestion de almacenes \> Configurar \> Despachar al almacén \> Directivas de consolidación de envíos**.
1. Establezca el campo **Tipo de directiva** en *Ordenes de venta*.
1. En el panel Acciones, seleccione **Nuevo** para crear una directiva que tenga la siguiente configuración:

    - **Nombre de directiva:** *CustomerOrderNo*
    - **Descripción de directiva:** *Consolidar líneas basadas en el pedido del cliente*

1. Configure la opción **Consolidar con envíos abiertos** en *Sí*.
1. En el panel Acciones, seleccione **Guardar**.
1. En la ficha desplegable **Campos de consolidacion** , en la lista **Campos restantes** , seleccione la fila donde el campo **Nombre de campo** está establecido en *Solicitud de cliente*.
1. Seleccione el botón **Añadir** ![Flecha correcta](media/forward-button.png) para mover el campo a la lista **Campos seleccionados**.
1. En la lista **Campos restantes** , seleccione la fila donde el campo **Nombre del campo** está establecido en *Modo de entrega*.
1. Seleccione el botón **Añadir** ![Flecha correcta](media/forward-button.png) para mover el campo a la lista **Campos seleccionados**.
1. En el panel Acciones, seleccione **Editar consulta**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Rango** , busque la fila donde el campo **Campo** está establecido en *Cuenta de cliente* y establezca el campo **Criterio** para esa fila en *US-001*.
1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

> [!NOTE]
> Para este caso de negocio, todas las líneas de pedido donde los pedidos de ventas tienen el mismo número de solicitud del cliente se consolidarán en un solo envío, independientemente del número de pedido de ventas. (El número de solicitud del cliente se utiliza como número de \[pedido de compra\]) del cliente. Si hay un envío abierto para la misma cuenta, almacén y solicitud del cliente, se le agregarán las nuevas líneas. Esta directiva se puede usar si el cliente envía líneas de pedido adicionales que tienen el mismo número de pedido varias veces durante un día y desea que todas las líneas se agrupen en un solo envío. (En otras palabras, habrá un conocimiento de embarque y un albarán).

### <a name="create-example-policy-4"></a>Crear directiva de ejemplo 4

En este ejemplo, creará una directiva *Clientes que permiten consolidación* que se puede usar para el siguiente caso de negocio:

- La directiva consultará un grupo de pedidos específico para identificar a los clientes que aceptan envíos consolidados.
- La consolidación con envíos abiertos está desactivada.
- La consolidación se realiza en todos los pedidos utilizando los campos seleccionados por defecto en la directiva CrossOrder (para replicar la casilla anterior **Consolidar envío en el despacho al alamacén** ).

- Puede anular la regla en un pedido de ventas seleccionando un grupo de pedidos diferente.

Siga estos pasos para crear la directiva de consolidación de envíos para este caso de negocios.

1. Vaya a **Gestion de almacenes \> Configurar \> Despachar al almacén \> Directivas de consolidación de envíos**.
1. Establezca el campo **Tipo de directiva** en *Ordenes de venta*.
1. En el panel Acciones, seleccione **Nuevo** para crear una directiva que tenga la siguiente configuración:

    - **Nombre de directiva:** *Grupo de pedidos*
    - **Descripción de directiva:** *Consolidar en todos los pedidos según el grupo de pedidos*

1. Deje la opción **Consolidar con envíos abiertos** establecida en *No*.
1. En el panel Acciones, seleccione **Guardar**.
1. En la ficha desplegable **Campos de consolidacion** , en la lista **Campos restantes** , seleccione la fila donde el campo **Nombre del campo** está establecido en *Modo de entrega*.
1. Seleccione el botón **Añadir** ![Flecha correcta](media/forward-button.png) para mover el campo a la lista **Campos seleccionados**.
1. En el panel Acciones, seleccione **Editar consulta**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Rango** , seleccione **Añadir** para agregar una fila que tenga la siguiente configuración a la cuadrícula:

    - **Tabla:** *Pedidos de ventas*
    - **Tabla derivada:** *Pedidos de ventas*
    - **Campo:** *Grupo*
    - **Criterio:** *ShipCons*

1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

> [!NOTE]
> Para este caso de negocio, todas las líneas de pedido donde los pedidos de ventas pertenecen al mismo grupo de pedidos se consolidarán en un solo envío a través de los pedidos de ventas para la misma cuenta, almacén y modo de entrega de transporte. En lugar del grupo de pedidos, puede usar cualquier otro campo para distinguir un grupo de clientes y usar el encabezado del pedido de ventas de forma predeterminada. Puede utilizar este enfoque si el cliente, no el almacén, está impulsando la necesidad de consolidación. (En la lógica de consolidación anterior, el almacén impulsó la necesidad de consolidación).

### <a name="create-example-policy-5"></a>Crear directiva de ejemplo 5

En este ejemplo, creará una directiva *Almacenes que permiten consolidación* que se puede usar para el siguiente caso de negocio:

- La directiva consultará un grupo de pedidos específico para identificar almacenes que pueden consolidar envíos.
- La consolidación con envíos abiertos está desactivada.
- La consolidación se realiza en todos los pedidos utilizando los campos seleccionados por defecto en la directiva CrossOrder (para replicar la casilla anterior **Consolidar envío en el despacho al alamacén** ).

Por lo general, este caso de negocios se puede abordar mediante las directivas predeterminadas que creó en el [escenario 1](#scenario-1). Sin embargo, también puede crear directivas similares manualmente siguiendo estos pasos.

1. Vaya a **Gestion de almacenes \> Configurar \> Despachar al almacén \> Directivas de consolidación de envíos**.
1. Establezca el campo **Tipo de directiva** en *Ordenes de venta*.
1. En el panel Acciones, seleccione **Nuevo** para crear una directiva que tenga la siguiente configuración:

    - **Nombre de directiva:** *Peido cruzado*
    - **Descripción de directiva:** *Consolidación de pedidos cruzados para almacenes específicos*

1. Deje la opción **Consolidar con envíos abiertos** establecida en *No*.
1. En el panel Acciones, seleccione **Guardar**.
1. En la ficha desplegable **Campos de consolidacion** , en el campo **Campos restantes** , seleccione la fila donde el campo **Nombre del campo** está establecido en *Modo de entrega*.
1. Seleccione el botón **Añadir** ![Flecha correcta](media/forward-button.png) para mover el campo a la lista **Campos seleccionados**.
1. En el panel Acciones, seleccione **Editar consulta**.
1. En el cuadro de diálogo del editor de consultas, en la pestaña **Rango** , busque la fila donde el campo **Campo** está establecido en *Almacén* y establezca el campo **Criterio** para esa fila en *61, 63*.
1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

### <a name="set-the-order"></a>Configurar el pedido

Ahora que ha creado todas sus directivas, debe establecer el orden en que se aplicarán. Para utilizar un enfoque tipo pirámide, donde las directivas que tienen la mayoría de las condiciones se evalúan como de mayor prioridad, siga estos pasos.

1. Vaya a **Gestion de almacenes \> Configurar \> Despachar al almacén \> Directivas de consolidación de envíos**.
1. Establezca el campo **Tipo de directiva** en *Ordenes de venta*.
1. Seleccione cada directiva que aparezca en la columna de la izquierda y luego use los botones **Hacer subir** y **Hacer bajar** del panel Acciones para organizar las directivas en el siguiente orden:

    1. CustomerMode
    1. Tipo de artículo
    1. CustomerOrderNo
    1. Grupo de pedidos
    1. Pedido cruzado
    1. Predeterminada

## <a name="example-scenarios-of-how-to-use-shipment-consolidation-policies"></a><a name="example-scenarios"></a> Escenarios de ejemplo de cómo usar las directivas de consolidación de envíos

Los siguientes escenarios ilustran cómo podría utilizar las directivas de consolidación de envíos que creó al leer este tema. Cada escenario le lleva por unproceso de consolidación de envíos que utiliza directivas de consolidación de envíos durante el deespacho automátizado o manual al almacén:

- Escenario 1: [Consolidar los envíos cuando se despachan al almacén mediante Despacho automático de pedidos de ventas](../warehousing/consolidate-shipments-automatic.md)
- Escenario 2: [Consolidar envíos cuando la directiva de consolidación de envíos se anula desde la página Despachar al almacén](../warehousing/consolidate-shipments-release-to-warehouse-override.md)
- Escenario 3: [Consolidar los envíos utilizando Despachar al almacén desde área de trabajo de planificación de la carga](../warehousing/consolidate-shipments-load-planning-workbench.md)
- Escenario 4: [Consolidar los envíos utilizando el área de trabajo de consolidación de envíos](../warehousing/consolidate-shipments-manual-workbench.md)
- Escenario 5: [Consolidar los envíos manualmente utilizando la página Consolidar envíos](../warehousing/consolidate-shipments-manual-form.md)


## <a name="additional-resources"></a>Recursos adicionales

- [Directivas de consolidación de envíos](about-shipment-consolidation-policies.md)
