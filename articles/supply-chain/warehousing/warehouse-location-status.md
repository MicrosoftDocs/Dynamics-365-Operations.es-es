---
title: Estado de ubicación de almacén
description: En este tema se ofrece una visión general de la característica Estado de ubicación de almacén.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile,WHSLocation
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 31216c24f54f22ec928eb143d4a913aabcd50cf8
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016019"
---
# <a name="warehouse-location-status"></a>Estado de ubicación de almacén

[!include [banner](../includes/banner.md)]

Microsoft Dynamics 365 Supply Chain Management incluye varios campos de ubicación que le brindan flexibilidad cuando trabaja y mantiene ubicaciones. Puede incluir estados de ubicación en la consulta de directiva de ubicación para ofrecer un mejor control del flujo del almacén.

Los siguientes cuatro campos en la página **Ubicaciones** realizan un seguimiento de la información sobre el estado actual de una ubicación. Estos campos permiten a los directores de almacén obtener una visión general del estado de las ubicaciones del almacén. También permiten generar informes y filtros avanzados.

- **Número de artículo** : el artículo que se encuentra actualmente en la ubicación. Si la ubicación contiene varios artículos, este campo está en blanco.
- **Fecha y hora de la última actividad** : la marca de tiempo de la última transacción de almacén que se realizó en la ubicación.
- **Fecha de vencimiento** : la fecha en la que se llevó al almacén el inventario en la ubicación. Este valor se calcula en función de la fecha de vencimiento de la matrícula. Resulta preciso para ubicaciones que tienen seguimiento de matrícula, pero puede que no lo sea para ubicaciones que no lo tienen.
- **Estado de ubicación** : el estado de la ubicación. Hay cuatro valores posibles:

    - **Indeterminado** : el perfil de ubicación no puede realizar un seguimiento del estado. Por lo tanto, el estado actual es desconocido.
    - **Vacío** : actualmente no hay inventario en la ubicación.
    - **Selección** : se ha realizado transacciones de salida en la ubicación desde que estuvo vacía por última vez.
    - **Almacenamiento** : se ha realizado transacciones de entrada en la ubicación desde que estuvo vacía por última vez.

## <a name="turn-on-the-warehouse-location-status-feature"></a>Activar la característica Estado de ubicación de almacén

Antes de poder usar la característica *Estado de ubicación de almacén* , esta debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario. En el espacio de trabajo **Administración de funciones** , la función aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de la característica:** *Estado de ubicación de almacén*

## <a name="set-up-warehouse-location-status"></a>Configurar el estado de ubicación del almacén

### <a name="prepare-the-sample-data-that-is-required-for-the-example-scenario"></a>Preparar los datos de muestra necesarios para el escenario de ejemplo

Antes de empezar a trabajar en el escenario, debe activar los datos de muestra y configurar la característica como se describe en esta sección. Para completar el escenario de ejemplo, debe usar la aplicación de almacén o el emulador basado en navegador. Los pasos que se proporcionan aquí usan la aplicación de almacén. Los pasos para el emulador basado en navegador son similares.

#### <a name="use-the-usmf-legal-entity"></a>Usar la entidad jurídica USMF

Para trabajar en el escenario de ejemplo mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar. Además, también debe seleccionar la entidad legal **USMF** antes de empezar.

#### <a name="set-up-location-profiles"></a>Configurar perfiles de ubicación

El escenario de ejemplo requiere que prepare dos perfiles de ubicación.

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Perfiles de ubicación**.
1. Seleccione **Editar** para poner la página en modo de edición.
1. Seleccione el perfil **BULK-06**.
1. En la ficha desplegable **General** , establezca los valores siguientes:

    - **Habilitar artículo en la ubicación** : establezca esta opción en _Sí_.
    - **Habilitar la fecha y hora de la actividad de ubicación:** establezca esta opción en _Sí_.
    - **Habilitar estado de la ubicación** : establezca esta opción en _Sí_.

    Estas opciones controlan si los campos de referencia en la ubicación están activos.

1. Repita los pasos del 3 al 4 para el perfil **PICK-06**.

> [!NOTE]
> Cuando los parámetros del perfil de ubicación ( **Habilitar elemento en la ubicación** , **Habilitar la actividad de la ubicación** , **Habilitar estado de la ubicación** ) están establecidos en *Sí* , el sistema actualiza inmediatamente las ubicaciones relevantes ejecutando el trabajo *control de coherencia del estado de la ubicación del almacén*.

### <a name="scenario"></a>Situación

1. Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**.
1. Seleccione **Nuevo**.
1. En el cuadro de diálogo **Crear orden de compra** , en la ficha desplegable **Proveedor** , en el campo **Cuenta de proveedor** , seleccione *104*.
1. En la ficha desplegable **General** , en el campo **Almacén** , seleccione el almacén *61*.
1. Seleccione **Aceptar**.
1. Se abre su nuevo pedido de compra (PC). Incluye una línea vacía en la cuadrícula **Líneas de pedido de compra**. En esta línea, establezca los siguientes valores:

    - **Código de artículo:** _A0002_
    - **Cantidad:** _5_

1. En el panel de acciones, en la pestaña **Compra** , en el grupo **Acciones** , seleccione **Confirmar** para confirmar la orden de compra.
1. En el dispositivo móvil, vaya a **Entrada \> Recibir compra**.
1. Seleccione el campo **PONUM** , introduzca el número de PC y confirme.
1. Seleccione el campo **ITEM** , introduzca *A0002* como el número de artículo y confirme.
1. En la página **Cantidad** , introduzca *5* como la cantidad y confirme.

    Puede introducir la cantidad en una de las siguientes formas:

    - Seleccione el signo más ( **+** ) o el signo menos ( **–** ) para sumar o restar un valor numérico.
    - Seleccione el campo en blanco entre el signo más ( **+** ) y el signo menos ( **–** ) para abrir el teclado numérico.

1. Confirme su selección de número de artículo *A0002* y una cantidad de *5*. Aparece el mensaje "Trabajo completado" en la parte inferior de la página.
1. Seleccione el botón Menú (a veces se denomina como la hamburguesa o el botón de hamburguesa) en la esquina superior derecha y luego seleccione **Cancelar** para salir de **Recibir compra** y volver al menú **Entrada**.
1. En la página del pedido de compra, seleccione **Detalles del trabajo** encima de la cuadrícula **Líneas de pedido de compra**.
1. En la pestaña **General** , observe los valores **Id. de trabajo** e **Id. de matrícula de entidad objetivo** que se crearon.
1. En la sección **Líneas** , observe los valores **Ubicación** para los tipos de trabajo *Picking* y *Colocación*.
1. En el dispositivo móvil, vaya a **Entrada \> Ubicación compra**.
1. Seleccione el campo **Id.** , introduzca el id. de trabajo y confirme.
1. Confirme una vez más para completar la entrada *Picking*.
1. Seleccione el botón Menú en la esquina superior derecha y, a continuación, seleccione **Listo** para completar el trabajo de *Picking*.
1. Anote la ubicación y confirme. Aparece el mensaje "Trabajo completado" en la parte inferior de la página.
1. Seleccione el botón Menú en la esquina superior derecha y, a continuación, seleccione **Cancelar** para salir de **Ubicación de compra** y volver al menú **Entrada**.
1. Seleccione **Volver** para volver al menú principal.
1. En Dynamics 365 Supply Chain Management, vaya a **Gestión de almacenes \> Configurar \> Almacén \> Ubicaciones**.
1. Filtre por **Ubicación** e introduzca la ubicación del trabajo de pedido de compra. Debería ver los siguientes resultados:

    - La columna **Estado de ubicación** muestra un valor de *Almacenamiento* porque la última transacción en esta ubicación fue una colocación.
    - La columna **Número de artículo** muestra un valor de *A0002* porque ese artículo se recibió y se colocó en la ubicación.
    - La columna **Fecha y hora de la última actividad** muestra la marca de tiempo de la fecha y hora en que se completó el trabajo en la ubicación.

1. En el dispositivo móvil, vaya a **Calidad \> Movimiento**.
1. Seleccione el campo **LOC/LP** e introduzca la ubicación que anotó en los pasos anteriores.
1. Confirme la información que se muestra. Anote la matrícula de entidad de almacén que se genera.
1. En la pantalla **Para información** , seleccione el campo **LOC/LP** e introduzca *06A07R2S1B* como la ubicación a la que mover el elemento.
1. En la pantalla **Para información** , confirme el valor **LP** (el id. de la matrícula de entidad de almacén de destino), que se genera automáticamente. Aparece el mensaje "Trabajo completado" en la parte inferior de la página.
1. Seleccione el botón Menú en la esquina superior derecha y, a continuación, seleccione **Cancelar** para salir de **Movimiento** y volver al menú **Gestión de calidad**.
1. Seleccione **Volver** para volver al menú principal.
1. En Dynamics 365 Supply Chain Management, vaya a **Gestión de almacenes \> Configurar \> Almacén \> Ubicaciones**.
1. Actualice la página **Ubicaciones** y vuelva a ver la ubicación original de almacenamiento. Tenga en cuenta que el campo **Estado de la ubicación** ahora se ha establecido en *Vacío* y la columna **Número de artículo** está en blanco.
1. Vea el registro de ubicación *06A07R2S1B* y tenga en cuenta que el valor **Estado** ha cambiado a *Almacenamiento* , y que los campos **Número de artículo** y **Fecha y hora de la última actividad** se han actualizado.
1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Seleccione **Nuevo**.
1. En el cuadro de diálogo **Crear pedido de ventas** , en el campo **Cuenta de cliente** , seleccione *US-002*.
1. En el campo **Almacén** , seleccione *61*.
1. Seleccione **Aceptar**.
1. Se abre su nuevo pedido de ventas. Incluye una línea vacía en la cuadrícula **Líneas de pedido de ventas**. En esta línea, establezca los siguientes valores:

    - **Código de artículo:** _A0002_
    - **Cantidad:** _1_

1. En la ficha desplegable **Líneas de pedido de ventas** , en el menú **Inventario** , seleccione **Reserva**.
1. En la página **Reserva** , seleccione **Reservar lote** para reservar la línea de pedido. A continuación, seleccione el botón **Cerrar** ( **X** ) de la esquina superior derecha para cerrar la página.
1. En el panel de acciones, en la pestaña **Almacén** , en el grupo **Acciones** , seleccione **Liberar al almacén**.
1. En la sección **Líneas de pedido de ventas** , en el menú **Almacén** , seleccione **Detalles del trabajo**.
1. Copie el valor **Id. de trabajo** que creó.
1. En el dispositivo móvil, vaya a **Salida \> Picking de ventas**.
1. Seleccione el campo **Id.** , introduzca el id. de trabajo que copió anteriormente y confirme.
1. En la página **Pedidos de venta: Picking** , el campo **LOC** sugiere la ubicación de picking como la ubicación de almacenamiento que se creó anteriormente. Tome nota de la ubicación.
1. Seleccione el campo **LOC** , introduzca la ubicación y confirme.
1. Seleccione el campo **LP** , introduzca la matrícula de entidad de almacén que anotó durante la actividad de Movimiento y confirme.
1. Seleccione el campo **Artículo** , introduzca *A0002* como el número de artículo y confirme.
1. En la página **Cantidad** , introduzca *1* como la cantidad y confirme.

    Puede introducir la cantidad en una de las siguientes formas:

    - Seleccione el signo más ( **+** ) o el signo menos ( **–** ) para sumar o restar un valor numérico.
    - Seleccione el campo en blanco entre el signo más ( **+** ) y el signo menos ( **–** ) para abrir el teclado numérico.

1. Selecciona el campo **LP OBJETIVO** , introduzca un id. de matrícula de entidad de destino definida por el usuario y confirme.
1. Confirme una vez más para completar el trabajo de picking. Aparece el mensaje "Trabajo completado" en la parte inferior de la página.
1. Seleccione el botón Menú en la esquina superior derecha y, a continuación, seleccione **Cancelar** para completar la actividad de picking y vuelva al menú **Salida**.
1. En Dynamics 365 Supply Chain Management, vaya a **Gestión de almacenes \> Configurar \> Almacén \> Ubicaciones**.
1. Filtre por **Ubicación** e introduzca la ubicación de picking del trabajo de pedido de ventas.
1. Tenga en cuenta que el campo **Estado de ubicación** para la ubicación desde la que se seleccionó el trabajo de pedido de ventas ahora está establecido en *Picking* y que el campo **Fecha y hora de la última actividad** se ha sido actualizado.

> [!NOTE]
> Los campos de ubicación se actualizan solo mediante transacciones de almacén. Si mueve el inventario utilizando un diario u otros procesos que no sean de WHS, los campos no se actualizarán.
