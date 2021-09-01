---
title: Selección en exceso de pedidos de ventas y pedidos de transferencia
description: Este tema explica cómo habilitar la selección en exceso de pedidos de ventas y pedidos de transferencia.
author: GalynaFedorova
ms.date: 07/06/2021
ms.topic: article
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-06
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 3c6f9d386f79754edce38e4e2cf4c9bfefbce69bdb252e8754f39d909827fa02
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722160"
---
# <a name="over-picking-for-sales-orders-and-transfer-orders"></a>Selección en exceso de pedidos de ventas y pedidos de transferencia

[!include [banner](../includes/banner.md)]

Este tema presenta un escenario que muestra cómo permitir que un trabajador específico o todos los trabajadores realicen una selección en exceso. El proceso de selección en exceso permite una selección en exceso controlada durante el trabajo de selección.

La selección en exceso del almacén es un concepto simple. El sistema permite a los trabajadores recoger más artículos de los especificados para un pedido. Sin embargo, todavía considera el límite de sobreentrega que se establece en el nivel de línea para la orden de transferencia o la orden de venta. Si se excede ese límite, la aplicación Warehouse Management notifica a los trabajadores que están excediendo el límite de sobreentrega.

La función de selección en exceso ayuda a minimizar el mantenimiento y también ayuda a que su configuración siga siendo flexible. Puede definir uno o más elementos del menú del dispositivo móvil y habilitar la selección en exceso solo para algunos de ellos. También puede evitar que los trabajadores seleccionen en exceso pedidos de venta o transferencia sin tener que cambiar los elementos del menú. En su lugar, puede desactivar una o ambas capacidades en las configuraciones de trabajador relevantes.

La función de selección en exceso puede ayudar a los trabajadores a ahorrar tiempo y esfuerzo cuando recogen y envían artículos. Por ejemplo, la función permite a los trabajadores realizar estas tareas:

- Compense las pérdidas durante la recogida o el envío.
- Evite tener que desembalar algún material de embalaje durante el proceso de recogida.
- Compensar los daños del artículo durante el transporte.
- Enviar una variación de cantidad o unidad de medida.
- Minimizar la rotura de cantidades en las placas de matrícula.
- Evitar el desperdicio de material y la escasez de materiales costosos.
- Medir la cantidad recogida después de la recogida (por ejemplo, mediante el pesaje de camiones).

> [!IMPORTANT]
> La función de selección en exceso se aplica solo a la selección y procesamiento de pedidos de venta y pedidos de transferencia. El reabastecimiento no admite la selección en exceso. Cuando se ejecuta el trabajo de reabastecimiento, el sistema no permitirá que los usuarios realicen una selección en exceso.

El escenario de este tema muestra cómo configurar y usar la función de selección en exceso.

## <a name="scenario-prerequisite-make-demo-data-available"></a>Requisito previo del escenario: hacer que los datos de demostración estén disponibles

El escenario de este tema hace referencia a valores y registros que se incluyen en los datos de demostración estándar que se proporcionan para Microsoft Dynamics 365 Supply Chain Management. Si desea utilizar los valores que se proporcionan aquí mientras realiza los ejercicios, asegúrese de trabajar en un entorno donde estén instalados los datos de demostración y configure la entidad jurídica en *USMF* antes de empezar.

## <a name="scenario-setup"></a>Configuración de escenario

Antes de trabajar en el escenario de ejemplo, debe habilitar la selección en exceso tanto para el trabajador relevante como para el elemento de menú relevante.

### <a name="set-up-a-worker-to-allow-for-over-picking"></a>Configurar un trabajador para permitir la selección en exceso

A continuación, se muestra el procedimiento general para configurar un trabajador para habilitar la selección en exceso de pedidos de venta y pedidos de transferencia por separado. Esta configuración controla qué trabajador puede realizar la selección en exceso y si ese trabajador puede realizar la selección en exceso tanto para los pedidos de transferencia como para los pedidos de venta.

1. Vaya a **Gestión de almacenes \> Configuración \> Empleado**.
1. En el panel de lista, seleccione **Julia Funderburk**.
1. En la ficha desplegable **Usuarios**, seleccione la fila que tiene los siguientes valores. Si ninguna fila existente tiene estos valores, créala.

    - **Id. de usuario:** *24*
    - **Nombre de usuario:** *WH 24*
    - **Almacén predeterminado:** *24*
    - **Nombre del menú:** *Principal*

1. En la ficha desplegable **Trabajo**, establezca los siguientes valores para el usuario *24* si aún no están configurados:

    - **Permitir selección en exceso de ventas:** *Sí*
    - **Permitir selección en exceso de pedido de transferencia:** *Sí*

### <a name="set-up-a-mobile-device-menu-item-to-allow-for-over-picking"></a>Configurar un elemento de menú del dispositivo móvil para permitir la selección en exceso

Este es el procedimiento general para configurar un elemento de menú de un dispositivo móvil para habilitar la selección en exceso. Dependiendo de sus requisitos comerciales para el nivel de permiso del trabajador que usará el menú del dispositivo móvil, algunos parámetros pueden estar activados o desactivados.

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. En el panel de lista, seleccione el registro que se llama *Selección de ventas*. Si ningún registro existente tiene este nombre, créelo. Confirme o establezca los siguientes valores para el registro:

    - **Nombre del elemento del menú:** *Selección de ventas*
    - **Título:** *Selección de ventas*
    - **Modo:** *Trabajo*
    - **Usar trabajo existente:** *Sí*
    - **Dirigido por:** *Dirigido por el usuario*
    - **Anular matrícula de entidad de almacén de destino:** *Sí*
    - **Anular la matrícula durante la colocación:** *Sí*
    - **Mantener trabajo bloqueado por el usuario:** *Sí*
    - **Permitir selección en exceso:** *Sí*

> [!IMPORTANT]
> Una vez que se habilitan los parámetros relevantes tanto para el trabajador como para el elemento de menú del dispositivo móvil, la selección en exceso se puede procesar solo a través del dispositivo móvil.

## <a name="example-scenario"></a>Supuesto de ejemplo

Una vez que se cumplan los requisitos previos, la configuración del trabajador y la configuración del elemento del menú, estará listo para trabajar con la función.

### <a name="create-a-sales-order-that-allows-for-overdelivery"></a>Cree un pedido de ventas que permita la entrega en exceso

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Seleccione **Nuevo** para crear un nuevo pedido de ventas.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - **Cuenta de cliente:** *US-001*
    - **Almacén**: *24*

1. Seleccione **Aceptar**.
1. Se abre el nuevo pedido de ventas. En la ficha desplegable **Líneas de pedido de venta**, agregue una línea que tenga los siguientes valores:

    - **Código de artículo:** *A0001*
    - **Cantidad:** *10*

1. Sobre la ficha desplegable **Detalles de línea**, en la pestaña **Entrega**, configure el campo **Entrega en exceso** a *10*.
1. En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario \> Reserva**.
1. En la página **Reserva**, en el Panel de acciones, seleccione **Reservar lote** para reservar inventario.
1. Cierre la página **Reserva**.
1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.

Cuando se complete la emisión, recibirá mensajes informativos que muestran la oleada y los identificadores de carga que se crearon.

### <a name="get-the-work-id-and-license-plate-number-for-the-new-order"></a>Obtenga la identificación de trabajo y la matrícula de entidad de almacén para el nuevo pedido

Cuando liberó el pedido de ventas al almacén, el sistema debería haber creado un nuevo ID de trabajo que tenga una línea de selección. Siga estos pasos para encontrar los identificadores de trabajo y las asignaciones de matrículas de entidad de almacén.

1. Vaya a **Gestión de almacenes \> Trabajo \> Detalles de trabajo**.
1. En la cuadrícula **Información general**, busque la columna **Número de pedido** para el pedido de venta que acaba de crear. Para cada pedido de venta, anote el identificador de trabajo correspondiente.
1. Seleccione la fila del nuevo pedido de ventas para mostrar información relacionada en la cuadrícula **Líneas**. Tome nota de la ubicación desde la que se recogerá cada artículo.
1. Vaya a **Gestión de inventario \> Consultas e informes \> Inventario disponible**.
1. En el panel Acciones, seleccione **Dimensiones**.
1. En el cuadro de diálogo **Visualización de dimensiones**, asegúrese de que las casillas de verificación **Matrícula de entidad de almacén**, **Almacén** y **Número de artículo** están seleccionadas y luego seleccione **Aceptar**.
1. En el panel **Filtrar**, configure los siguientes filtros:

    - **Número de artículo** - **es uno de** – *A0001*
    - **Almacén** - **empieza con** - *24*

1. Seleccionar **Aplicar**.
1. Anote los valores de la **Matrícula de entidad de licencia** que se muestran.

### <a name="over-pick-the-order-by-using-the-warehouse-management-mobile-app"></a>Selección en exceso del pedido mediante la aplicación móvil Warehouse Management

1. Inicie sesión en la aplicación móvil Warehouse Management como un usuario en el almacén *24*.
1. Vaya a **Salida \> Selección de ventas**.
1. En el campo **Escanear la identificación del trabajo o la matrícula**, introduzca el ID de trabajo que se creó para el pedido de ventas.
1. Seleccione **Aceptar** (símbolo de marca de verificación).
1. Seleccione **Selección en exceso**.
1. Establezca el campo **Cantidad de recogida** en *14*.
1. Seleccione **Aceptar** (símbolo de marca de verificación).

    En la página **Selección en exceso** recibirá el siguiente mensaje: "La entrega en exceso de la línea es del 40,00 por ciento, pero la entrega en exceso permitida es solo del 10,00 por ciento". Este mensaje indica que la cantidad recogida que introdujo excede el límite de entrega en exceso. El límite de entrega en exceso para la línea de pedido de ventas es del 10 por ciento. Por lo tanto, para una cantidad específica de 10, puede realizar una selección en exceso solo de 1, para una cantidad total de 11.

1. Establezca el campo **Cantidad de recogida** en *11*.
1. Seleccione **Aceptar** (símbolo de marca de verificación).
1. En el campo **Matrícula**, introduzca la matrícula que anotó en la sección anterior.
1. En el campo **Matrícula de entidad de destino** introduzca una matrícula de entidad objetivo. Observe que aparecen la ubicación de recogida (*FLOOR-001*), articulo (*A0001*) y cantidad (*11 piezas*).
1. Seleccione **Aceptar** (símbolo de marca de verificación).
1. Revise la información en la página **Órdenes de venta: Colocar**. El campo **Ubicación** debe indicar que los elementos seleccionados van a la ubicación *BAYDOOR*.
1. Seleccione **Aceptar** (símbolo de marca de verificación).

En la página **Escanear una identificación de trabajo / identificación de matrícula de entidad**, recibirá un mensaje de "Trabajo completado". Este mensaje indica que se ha completado el ID de trabajo del pedido de ventas y que la cantidad seleccionada en exceso no excede el límite de entrega en exceso del 10 por ciento.
