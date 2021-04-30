---
title: Asignación automática de gastos
description: La característica de gastos de Microsoft Dynamics 365 Supply Chain Management le ayuda a asignar automáticamente los gastos a los pedidos de compra o los pedidos de ventas.
author: dasani-madipalli
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-10-01
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 4e8d65cc1f946f921523607eff850b29f9ff9bf1
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910170"
---
# <a name="automatic-allocation-of-charges"></a>Asignación automática de gastos

[!include [banner](../includes/banner.md)]

Según el cliente con el que trabaja o el artículo que vende, es posible que desee aplicar gastos adicionales específicos. La característica de *gastos* de Microsoft Dynamics 365 Supply Chain Management le ayuda a asignar automáticamente los gastos a los pedidos de compra o los pedidos de ventas.

Los cargos automáticos, o gastos automáticos, se aplican automáticamente al crear un pedido de ventas o un pedido de compra. Puede definir los gastos automáticos de proveedores, clientes, grupos o artículos específicos. También puede definir gastos automáticos que se apliquen a todos los proveedores, clientes o artículos.

## <a name="set-up-charges-codes"></a>Configurar códigos de gastos

Para asignar gastos, primero debe definir códigos de gastos.

1. Siga uno de estos pasos:

    - Para pedidos de compra: vaya a **Proveedores \> Configuración de gastos \> Código de gastos**.
    - Para pedidos de ventas: vaya a **Clientes \> Configuración de gastos \> Código de gastos**.

1. En el panel de acciones, seleccione **Nuevo** para crear un código de gastos.
1. En el encabezado del nuevo registro, establezca los siguientes campos:

    - **Código de gastos**: escriba un código para los gastos.
    - **Descripción**: escriba una descripción de los gastos.
    - **Grupo de impuestos sobre las ventas de artículos**: seleccione un grupo de impuestos sobre las ventas de artículos, si corresponde.
    - **Prorratear** : establezca esta opción en *Sí* si desea prorratear sus gastos. Esta opción solo está disponible para pedidos de ventas.
    - **Importe máximo**: escriba el importe máximo de cancelación permitido para el código de gastos. Este campo se usa para validar los cargos para facturas de proveedor. Solo está disponible para pedidos de compra.

        > [!NOTE]
        > Para activar la funcionalidad de validación de gastos para pedidos de compra, vaya a **Proveedores \> Configuración \> Parámetros de proveedores**. En la ficha desplegable **Validación de facturas**, en la sección **Validación de factura**, establezca la opción **Habilitar validación de conciliación de facturas** en *Sí*.

1. La ficha desplegable **Registro** incluye las secciones **Débito** y **Crédito**. Configure los siguientes campos, según el libro mayor en el que desee registrar los gastos:

    - **Tipo**: seleccione el tipo de cuenta en la que está registrando (*Libro mayor*, *Cliente* o *Articulo*).
    - **Destino**: seleccione el tipo de registros que desea crear (como *Tarifa de intermediación* o *Liquidación del cliente*).
    - **Cuenta**: seleccione la cuenta para la que se publicará el gasto.

1. En el panel Acciones, seleccione **Guardar**.

## <a name="create-charge-groups"></a>Crear grupos de gastos

Los grupos de gastos asignan automáticamente gastos específicos a un grupo de clientes o proveedores. En las siguientes subsecciones se explica cómo crear y asignar estos grupos de gastos.

### <a name="charge-groups-for-purchase-orders"></a>Grupos de gastos para pedidos de compra

Para crear grupos de gastos para pedidos de compra, siga estos pasos.

1. Vaya a **Proveedores \> Configuración de gastos \> Grupo de gastos del proveedor**.
1. En el panel Acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula y después establezca los siguientes campos.

    - **Grupo de gastos**: escriba el nombre del grupo de gastos.
    - **Descripción**: escriba una descripción del grupo de gastos.

1. En el panel Acciones, seleccione **Guardar**.
1. Vaya a **Proveedores \> Proveedores \> Todos los proveedores** y abra un proveedor existente o cree uno nuevo.
1. En la ficha desplegable **Valores predeterminados del pedido de compra**, en la sección **Pedido de compra**, establezca como valor del campo **Grupo de gastos** el grupo de gastos que acaba de crear.

### <a name="charge-groups-for-sales-orders"></a>Grupos de gastos para pedidos de ventas

Para crear grupos de gastos para pedidos de ventas, siga estos pasos.

1. Vaya a **Clientes \> Configuración de gastos \> Grupos de gastos de cliente**.
1. En el panel Acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula y después establezca los siguientes campos.

    - **Grupo de gastos**: escriba el nombre del grupo de gastos.
    - **Descripción**: escriba una descripción del grupo de gastos.

1. En el panel Acciones, seleccione **Guardar**.
1. Vaya **Clientes \> Clientes \> Todos los clientes** y abra un cliente existente o cree uno nuevo.
1. En la ficha desplegable **Valores predeterminados del pedido de ventas**, en la sección **Pedido de ventas**, establezca como valor del campo **Grupo de gastos** el grupo de gastos que acaba de crear.

## <a name="define-auto-charges"></a>Definir gastos automáticos

Una vez que haya configurado los códigos de gasto, siga estos pasos para definir los gastos automáticos.

1. Siga uno de estos pasos:

    - Para pedidos de compra: vaya a **Adquisición y abastecimiento \> Configuración \> Gastos \> Gastos automáticos**.
    - Para pedidos de ventas: vaya a **Clientes \> Configuración \> Configuración de gastos \> Gastos automáticos**.

1. En el panel de lista, en el campo **Nivel**, seleccione el nivel donde se aplica el gasto automático:

    - *Principal*: los gastos se aplican al encabezado del pedido.
    - *Línea*: los gastos se aplican a las líneas de pedido.

1. Seleccione un gasto automático existente para editarlo o seleccione **Nuevo** para definir un nuevo gastos automático.
1. En la lista **Código de cuenta**, seleccione uno de los siguientes valores para especificar el ámbito de las cuentas que se verán afectadas:

    - *Tabla*: los gastos se asignan a un cliente o proveedor concreto.
    - *Grupo*: los gastos se asignan a un grupo de gastos variados.
    - *Todos*: los gastos se asignan a todos los clientes o proveedores.

1. En el campo **Relación con el cliente** o **Relación con el proveedor**, seleccione un cliente o proveedor específico si ha establecido el campo **Código de cuenta** en *Tabla*. Si ha establecido el campo **Código de cuenta** en *Grupo*, seleccione el grupo de gastos del cliente o proveedor.
1. En el campo **Código de artículo**, seleccione uno de los siguientes valores para especificar el ámbito de los artículos que se verán afectados. Puede seleccionar un código de artículo únicamente al definir gastos automáticos en el nivel de línea.

    - *Tabla*: los gastos se asignan a un artículo concreto.
    - *Grupo*: los gastos se asignan a un grupo de gastos de artículo.
    - *Todos*: los gastos se asignan a todos los artículos.

1. En el campo **Relación de artículo**, seleccione un artículo específico si estableció el valor del campo **Código de artículo** en *Tabla*. Si estableció el campo **Código de artículo** en *Grupo*, seleccione un grupo de gastos de artículo.
1. **Solo para pedidos de venta:** en el campo **Modo de código de entrega**, seleccione uno de los siguientes valores para especificar el ámbito de los modos de entrega que se verán afectados:

    - *Tabla*: los gastos se asignan a un modo de entrega específico.
    - *Grupo*: los gastos se asignan a un grupo de entrega específico.
    - *Todos*: los gastos se asignan a todos los modos de entrega.

1. **Solo para pedidos de ventas**: en el campo **Relación de modo de entrega**, seleccione un modo de entrega específico si estableció el campo **Código de modo de entrega** en *Tabla*. Si estableció el campo **Código de modo de entrega** en *Grupo*, seleccione un grupo de modos de entrega.
1. En la ficha desplegable **Líneas**, defina los gastos y tasas de gastos que se usarán cuando se aplique el gasto automático actual. Puede utilizar la barra de herramientas de esta ficha desplegable para agregar tantas líneas como necesite. Para cada línea, establezca los siguientes campos:

    - **Divisa**: seleccione la divisa que se debe utilizar para calcular el gasto.
    - **Código de gastos**: seleccione el código del gasto.
    - **Categoría**: seleccione uno de los siguientes valores:

        - *Fijo*: el gasto se especifica como un importe fijo en la línea. Los gastos fijos se pueden usar en gastos en el encabezado del pedido y en las líneas de pedido.
        - *UDS*: el gasto se basa en la unidad. Estos gastos pueden utilizarse solo en líneas de pedido. Aparecerán al calcular el total del pedido.
        - *Porcentaje*: el gasto se especifica como un porcentaje en la línea. Los gastos en porcentaje se pueden usar en gastos en el encabezado del pedido y en las líneas de pedido.
        - *Porcentaje de empresas vinculadas*: el gasto se especifica como un porcentaje en la línea para los pedidos de empresas vinculadas. Los gastos de porcentaje de empresas vinculadas pueden utilizarse solo en líneas de pedido.
        - *Externo*: el gasto se calcula mediante un servicio de terceros que esté asociado con uno o más transportistas de envío.

    - **Valor de los gastos**: especifique el valor del gasto según la categoría seleccionada.
    - **Código de divisa de gastos**: especifique una divisa para el gasto si desea utilizar una divisa diferente a la que especificó en el campo **Divisa**. Solo puede usar una divisa diferente si ha establecido el campo **Tipo de débito** o **Tipo de crédito** en *Cuenta contable* o *Artículo* para el código de gastos seleccionado.
    - **Importe inicial**: especifique un importe inicial para aplicar el gasto automático en el campo. En este contexto, el importe hace referencia al total del pedido.
    - **Importe final**: especifique el importe final al que aplicar el gasto automático. En este contexto, el importe hace referencia al total del pedido.
    - **Grupo de impuestos**: especifique un grupo de impuestos.
    - **Sitio** y **Almacén**: especifique un sitio y un almacén si los cargos deben aplicarse solo a un sitio y un almacén específicos.
    - **Conservar**: active esta casilla para conservar las transacciones de gastos tras la facturación, de modo que el gasto se pueda aplicar cada vez que se cree una nueva factura para la cuenta de cliente seleccionada.

1. **Solo para pedidos de ventas:** Si desea calcular los gastos por niveles, consulte [Gastos por niveles en pedidos de ventas](/dynamicsax-2012/appuser-itpro/about-tiered-charges-on-sales-orders) para obtener más información.

## <a name="allocate-charges-from-the-header-to-a-line"></a>Asignar gastos del encabezado a una línea

El siguiente procedimiento muestra cómo asignar gastos de nivel de encabezado a una línea. Antes de comenzar este procedimiento, debe tener un gasto de nivel de encabezado de tipo *cantidad fija* y un pedido donde se aplique ese gasto. Además, el pedido ya debería incluir al menos una línea de pedido.

1. Abra el pedido de compra o el pedido de gasto.
1. En el panel de acciones, siga uno de estos pasos:

    - Para pedidos de compra: en la pestaña **Compra**, en el grupo **Gastos**, seleccione **Asignar gastos**.
    - Para pedidos de ventas: en la pestaña **Venta**, en el grupo **Gastos**, seleccione **Asignar gastos**.

1. En el cuadro de diálogo **Asignar gastos a líneas de pedido**, configure los siguientes campos:

    - **Asignación de gastos**: seleccione uno de los siguientes valores para especificar cómo se deben asignar los gastos:

        - *Importe neto*: asignar gastos de acuerdo con el importe de cada línea en relación con el importe neto total.
        - *Cantidad*: asignar gastos según el número de unidades de cada línea en relación con el número total de unidades.
        - *Por línea*: asignar gastos de forma equitativa entre el número total de líneas.

    - **Asignar gastos a líneas**: seleccione un valor para especificar si los gastos deben asignarse a todas las líneas, solo a las líneas positivas o solo a las líneas negativas.
    - **Asignar todo**: active esta casilla para asignar los gastos a las líneas de pedido aunque el código de gastos tenga un tipo de débito distinto de *Artículo*.
    - **Recibidas**: active esta casilla para asignar gastos únicamente a las líneas de pedido recibidas.
    - **En stock**: active esta casilla de verificación para asignar los gastos únicamente a las líneas de pedido inventariadas.
    - **Mostrar selecciones y borrar líneas específicas**: active esta casilla para excluir líneas específicas de esta asignación. Al activar esta casilla, se abre la cuadrícula **Elija las líneas que desea excluir de la asignación**. La cuadrícula solo incluye las líneas que coinciden con los criterios definidos por las configuraciones **Asignar gastos a líneas** y **En stock**. Por ejemplo, si establece el campo **Asignar gastos a líneas** en *Líneas positivas* y activa la casilla **En stock**, la cuadrícula muestra únicamente las líneas positivas e inventariadas. Además, la cuadrícula filtra automáticamente las líneas para las que ya se ha recibido la cantidad completa. Mientras la cuadrícula está abierta, desactive la casilla **Incluir** para cada línea que deba excluirse de la asignación. 

        > [!IMPORTANT]
        > Al trabajar con la cuadrícula **Elija las líneas que desee excluir de la asignación**, asegúrese de dejar la cuadrícula abierta hasta que seleccione **Asignar**. Si cierra la cuadrícula antes de seleccionar **Asignar**, se perderá su configuración de la cuadrícula. Por lo tanto, los cargos se asignarán en función de los criterios que definió anteriormente.

1. Seleccione **Asignar** para aplicar su configuración y cerrar el cuadro de diálogo de consulta.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]