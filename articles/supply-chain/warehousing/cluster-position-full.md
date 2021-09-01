---
title: Posición completa del clúster
description: Este tema proporciona información acerca de la característica Posición completa de clústeres. Esta característica ofrece una alternativa a la aplicación más estricta de las reglas de las pausas laborales cuando se utiliza el picking en clúster, ya que permite un mayor margen de error en las restricciones volumétricas de los contenedores o bolsas.
author: Mirzaab
ms.date: 08/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 2da0421bdb1496d51c807e51a26a980238886a42dfec167dac95611cc3df97bd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730043"
---
# <a name="cluster-position-full"></a>Posición completa del clúster

[!include [banner](../includes/banner.md)]

La característica *Posición completa del clúster* ofrece una alternativa a la aplicación más estricta de las reglas de las pausas laborales cuando se utiliza el picking en clúster, ya que permite un mayor margen de error en las restricciones volumétricas de los contenedores o bolsas. En un escenario común, no todos los elementos de una orden de trabajo caben en un contenedor seleccionado. Los trabajadores del almacén que realizan picking en clúster tienen pocas opciones en este escenario: deben cambiar a un tamaño de contenedor más grande o trabajar con su supervisor para encontrar una solución diferente.

Esta característica introduce la capacidad de ejecutar el botón **Completo** en una de las unidades de trabajo en un clúster. En versiones anteriores, esta opción solo estaba disponible para el picking de pedidos normal, no para el picking en clúster. Sin embargo, esta característica difiere del botón estándar **Completo** en el que cancela el trabajo restante. No sugiere que el usuario agregue otro contenedor al mismo clúster y no crea automáticamente un nuevo trabajo.

## <a name="turn-on-the-cluster-position-full-feature"></a>Activar la característica Posición completa del clúster

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de la característica**: *Posición completa del clúster*

## <a name="setup"></a>Configurar

Esta sección proporciona pautas y un ejemplo que muestra cómo configurar y usar la característica *Posición completa del clúster*.

### <a name="make-sample-data-available"></a>Hacer que los datos de muestra estén disponibles

Para trabajar en el [escenario de ejemplo](#example-scenario) mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar. Además, también debe seleccionar la entidad legal **USMF** antes de empezar.

También puede usar este escenario de ejemplo como guía para trabajar con esta en un sistema de producción. Sin embargo, en ese caso, debe sustituir sus propios valores para los valores de configuración que se describen aquí.

### <a name="cluster-profiles"></a>Perfiles de clúster

Debe especificar si los identificadores de clúster se generan automáticamente, cuántas posiciones se utilizan, cuándo se rompen los clústeres y cómo se secuencia y verifica el trabajo de picking.

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Perfiles de clúster**.
1. En el panel de lista, seleccione el registro **Crear clúster**.
1. En la ficha desplegable **General**, compruebe los valores siguientes:

    - **Generar Id. de clúster**: seleccione *Sí*.
    - **Activar posiciones**: *Sí*
    - **Número de posiciones**: *2*
    - **Nombre de la posición**: *Numérico*
    - **Dividir clúster en**: *Colocar*
    - **Tipo de comprobación del orden**: *Escaneo de posición*

1. En la ficha desplegable **Clasificación de clústeres**. La cuadrícula debe estar en blanco (es decir, no debe contener líneas).

### <a name="work-templates"></a>Plantillas de trabajo

Debe definir cómo crear el trabajo de picking para el picking en clúster.

1. Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.
1. En la parte superior de la página, establezca el campo **Tipo de orden de trabajo** en *Pedidos de venta*.
1. Asegúrese de que se enumeren las siguientes plantillas de trabajo de los datos de demostración. Si no están disponibles, no podrá completar el escenario.

    - 61 SO Etapa
    - 61 SO Picking en clúster

### <a name="location-directives"></a>Directivas de ubicación

Debe especificar dónde se recogen los artículos y dónde se colocan.

1. Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.
1. En el encabezado de lista, establezca el campo **Tipo de orden de trabajo** en *Pedidos de venta*.
1. Asegúrese de que se enumeren las siguientes directivas de pedido de venta de los datos de demostración. Si no están disponibles, no podrá completar el escenario.

    - 61 Picking en clúster
    - 61 SO Orden de picking

### <a name="mobile-device-menu-items"></a>Elementos de menú del dispositivo móvil

Debe configurar un elemento de menú del dispositivo móvil para usar el trabajo existente realizado mediante picking en clúster. En el elemento del menú del dispositivo móvil para el picking en clúster, el parámetro **Permitir la división del trabajo** debe estar activado y la clase de trabajo *SO picking* debe agregarse la clase de trabajo.

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. En el panel de lista, seleccione el registro **Crear picking en clúster**.
1. Seleccione **Editar** en el Panel de acciones.
1. En la ficha desplegable **General**, establezca los valores siguientes:

    - **Dirigido por**: *Picking de clústeres*
    - **Generar matrícula de entidad de almacén:** *Sí*
    - **Permitir división del trabajo**: *Sí*
    - **Id. de perfil de clúster**: *Crear clúster*

    Acepte los valores predeterminados para el resto de campos.

1. En la ficha desplegable **Clases de trabajo**, agregue las siguientes dos líneas, según sea necesario:

    - Línea 1 (generalmente presente en los datos de demostración):

        - **Id. de la clase de trabajo**: *Ventas* 
        - **Tipo de orden de trabajo**: *Pedidos de venta*

    - Línea 2 (probablemente no está presente en los datos de demostración):

        - **Identificador de la clase de trabajo**: *SO picking*
        - **Tipo de orden de trabajo**: *Pedidos de venta*

1. Vaya a **Configuración de confirmación de trabajo** en el Panel de acciones.
1. Seleccione **Editar**.
1. Especifique uno de los valores siguientes en la línea en la cuadrícula:
    - **Tipo de trabajo** - *Picking*
    - **Confirmación del producto** - *Seleccionar la casilla de verificación*

1. Seleccione **Guardar** en el Panel de acciones y cierre la página.

## <a name="create-picking-work"></a>Crear trabajo de selección

Antes de que pueda iniciar el picking en clúster, debe crear algún trabajo de salida. El perfil de clúster que creó anteriormente especifica dos posiciones de clúster. Por lo tanto, se deben crear al menos dos identificadores de trabajo para el picking de pedidos de venta. Para este escenario, las transacciones ocurrirán en el almacén *61*, y usarán los elementos *L0101* y *T0100*. Los datos de demostración deben tener suficiente inventario disponible de estos artículos. Asegúrese de tener suficiente inventario para completar las transacciones.

### <a name="create-sales-order-1"></a>Crear pedido de ventas 1

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Seleccione **Nuevo** para crear un pedido de ventas 1.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - **Cuenta de cliente:** *US-010*
    - **Almacén**: *61*

1. Seleccione **Aceptar**.
1. Se abre el nuevo pedido de ventas. En la ficha desplegable **Líneas de pedido de venta**, agregue una línea que tenga los siguientes valores:

    - **Código de artículo:** *T0100*
    - **Cantidad:** *5*

1. En la ficha desplegable **Detalles de línea**, en la pestaña **Entrega**, establezca el campo **Fecha de entrega confirmada** en la fecha de hoy.
1. En la ficha desplegable **Líneas de pedido de venta**, agregue una segunda línea que tenga los siguientes valores:

    - **Código de artículo:** *L0101*
    - **Cantidad:** *20*

1. En la ficha desplegable **Detalles de línea**, en la pestaña **Entrega**, establezca el campo **Fecha de entrega confirmada** en la fecha de hoy.
1. Para cada línea que acaba de agregar, siga estos pasos para reservar el inventario:

    1. Seleccione la línea que desea reservar.
    2. En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario \> Reserva**.
    3. En la página **Reserva**, en el Panel de acciones, seleccione **Reservar lote** para reservar inventario.
    4. Cierre la página **Reserva**.

1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.

    Cuando se complete la emisión, recibirá mensajes informativos que muestran la oleada y los identificadores de carga que se crearon.

### <a name="create-sales-order-2"></a>Crear pedido de ventas 2

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Seleccione **Nuevo** para crear un pedido de ventas 2.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - **Cuenta de cliente:** *US-011*
    - **Almacén**: *61*

1. Seleccione **Aceptar**.
1. Se abre el nuevo pedido de ventas. En la ficha desplegable **Líneas de pedido de venta**, agregue una línea que tenga los siguientes valores:

    - **Código de artículo:** *L0101*
    - **Cantidad:** *20*

1. En la ficha desplegable **Detalles de línea**, en la pestaña **Entrega**, establezca el campo **Fecha de entrega confirmada** en la fecha de hoy.
1. En la ficha desplegable **Líneas de pedido de venta**, agregue una segunda línea que tenga los siguientes valores:

    - **Código de artículo:** *T0100*
    - **Cantidad:** *2*

1. En la ficha desplegable **Detalles de línea**, en la pestaña **Entrega**, establezca el campo **Fecha de entrega confirmada** en la fecha de hoy.
1. Para cada línea que acaba de agregar, siga estos pasos para reservar el inventario:

    1. Seleccione la línea que desea reservar.
    2. En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario \> Reserva**.
    3. En la página **Reserva**, en el Panel de acciones, seleccione **Reservar lote** para reservar inventario.
    4. Cierre la página **Reserva**.

1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.

    Cuando se complete la emisión, recibirá mensajes informativos que muestran la oleada y los identificadores de carga que se crearon.

### <a name="get-work-ids-and-license-plate-numbers"></a>Obtener identificaciones de trabajo y números de entidad de almacén

Se deberían haber creado dos identificadores de trabajo, cada uno de los cuales tiene dos líneas de picking. Siga estos pasos para encontrar los identificadores de trabajo y las asignaciones de matrículas de entidad de almacén.

1. Vaya a **Gestión de almacenes \> Trabajo \> Detalles de trabajo**.
1. En la cuadrícula **Información general**, busque la columna **Número de pedido** para los dos pedidos de venta que acaba de crear. Para cada pedido de venta, anote el identificador de trabajo correspondiente.
1. Seleccione la fila de cada pedido de ventas para mostrar información relacionada en la cuadrícula **Líneas**. Tome nota de la ubicación desde la que se recogerá cada artículo.
1. Vaya a **Gestión de inventario \> Consultas e informes \> Inventario disponible**.
1. En el panel de acciones, seleccione **Dimensiones** para abrir el cuadro de diálogo **Mostrar dimensión**.
1. Asegúrese de que las casillas de verificación **Matrícula de entidad de almacén**, **Almacén** y **Número de artículo** están seleccionadas y luego seleccione **Aceptar**.
1. En el panel **Filtrar**, configure los siguientes filtros:

    - **Número de artículo** - **es uno de** - *L0101* y *T100*
    - **Almacén** - **empieza con** - *61*

1. Anote los valores de la **Matrícula de entidad de licencia** que se muestran.

## <a name="example-scenario"></a><a name="example-scenario"></a>Supuesto de ejemplo

### <a name="mobile-device-flow-execution--work-confirmation-setup-for-the-product"></a>Ejecución del flujo de dispositivos móviles: configuración de la confirmación de trabajo para el producto

1. Inicie sesión en la aplicación móvil Warehouse Management como un usuario en el almacén *61*.
1. Vaya a **Saliente \> Creación de picking en clúster**.

    La página **TAREA: Asignar trabajo al clúster** aparece.

1. Especifique el identificador de trabajo para el pedido de venta 1 para asignarlo a la posición 1 del grupo.
1. Seleccione **Aceptar** (símbolo de marca de verificación).
1. Especifique el identificador de trabajo para el pedido de venta 2 para asignarlo a la posición 2 del grupo.
1. Seleccione **Aceptar** (símbolo de marca de verificación).

    La página **TAREA: Creación de picking en clúster: picking** aparece y muestra *Elemento L0101 2 PL*.

Debido a que el perfil del clúster estableció el número de posiciones en 2, el sistema lo dirige automáticamente a la primera selección de consolidación: dos palés (PL) del artículo *L0101*.

En cualquier momento durante los siguientes pasos, puede seleccionar la pestaña **Detalles** para ver información adicional sobre la tarea, como la ubicación de picking.

1. Defina el campo **ARTÍCULO** en *L0101*. Esto confirma el número de elemento, que es necesario para este elemento de menú (lo configuró anteriormente seleccionando **Configuración de confirmación de trabajo** desde la página **Elemento de menú del dispositivo móvil** cuando creó este elemento de menú).
1. Ingrese el número de la matrícula de la entidad de almacén que está asociada con el artículo en la ubicación que se está recogiendo. Escogerá dos palés.
1. Selecciona el campo **LP** en *LP\_PICK\_01*.
1. Seleccione **Aceptar** (símbolo de marca de verificación).

    La página **TAREA: Ordenar: Creación de picking en clúster** aparece. Aquí, clasificará los dos palets recogidos en una posición de recogida. Esta posición puede ser una bolsa o un contenedor que se utiliza para separar el inventario recogido por pedido de venta.

1. Vea los detalles que se muestran para el artículo (*L0101*) y la cantidad (*20* por unidad) que se clasificará en la posición 1 (para el pedido de cliente 1).
1. Establezca el campo **POSICIÓN NA** en *1*.
1. Seleccione **Aceptar** (símbolo de marca de verificación).
1. Vea los detalles que se muestran para el artículo (*L0101*) y la cantidad (*20* por unidad) que se clasificará en la posición 2 (para el pedido de cliente 2).
1. Establezca el campo **POSICIÓN NA** en *2*.
1. Seleccione **Aceptar** (símbolo de marca de verificación).

    La página **TAREA: Creación de picking en clúster: picking** aparece y muestra *Elemento T0100 7 por unidad*.

En este escenario, la posición 1 no puede aceptar la cantidad total de artículos que deben seleccionarse para satisfacer el pedido de venta 1. Una posición debe estar marcada como completa. En este escenario, hará una selección parcial del segundo artículo. El segundo artículo se recogerá parcialmente para la posición 1 y se creará un nuevo trabajo para recoger la cantidad restante para cumplir con el pedido.

1. Seleccione el botón Menú (a veces denominado hamburguesa o botón de hamburguesa) y luego seleccione **Posición completa**.
1. Identifique el puesto que está completo y seleccione *1*.
1. Seleccione **Aceptar** (símbolo de marca de verificación).
1. Escriba la cantidad de picking que aún se recoger en la posición 1. El sistema puede determinar qué número de artículo se está recogiendo.
1. Introduzca *2*.
1. Seleccione **Aceptar** (símbolo de marca de verificación).
1. Confirme el número de artículo para completar el picking del artículo restante en la posición 2.
1. Establezca el campo **ARTÍCULO** en *T0100*.
1. Seleccione **Aceptar** (símbolo de marca de verificación).
1. Especifique la matrícula de entidad de almacén de la cual se está recogiendo el artículo configurando el campo **LP** en *LPREPL04*.
1. Seleccione **Aceptar** (símbolo de marca de verificación).
1. Vea los detalles que se muestran para el artículo (*T0100*) y la cantidad (*2* por unidad) que se clasificará en la posición 2 (para el pedido de cliente 2).
1. Establezca el campo **POSICIÓN NA** en *2*.
1. Seleccione **Aceptar** (símbolo de marca de verificación).
1. Vea los detalles que se muestran para el artículo (*T0100*) y la cantidad (*2* por unidad) que se clasificará en la posición 1 (para el pedido de cliente 1).
1. Establezca el campo **POSICIÓN NA** en *1*.
1. Seleccione **Aceptar** (símbolo de marca de verificación).

    La página **TAREA: Ordenar: Creación de picking en clúster: Colocar** aparece.

En este escenario, el picking en clúster se ha completado y se redirige al usuario para que guarde los artículos recogidos de la posición 1 y la posición 2 en la ubicación de almacenamiento provisional *ETAPA01*.

1. Revise la información en la página. Muestra que una cantidad total de *44* se colocará en la ubicación de almacenamiento provisional.
1. Seleccione **Aceptar** (símbolo de marca de verificación).

    Recibe un mensaje "Clúster completado".

Ahora puede usar el elemento de menú **Picking de ventas** para elegir la cantidad restante. A continuación, puede utilizar el elemento de menú **Carga de ventas** para mover los elementos desde la ubicación de almacenamiento provisional al muelle de carga.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]