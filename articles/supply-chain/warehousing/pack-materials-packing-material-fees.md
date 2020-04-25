---
title: Materiales y cuotas de embalaje
description: Este tema proporciona información sobre las tarifas de material de embalaje que se pagan a las empresas de reciclaje a intervalos específicos.
author: MarkusFogelberg
manager: tfehr
ms.date: 02/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventPackagingGroup, InventPackagingMaterialCode, InventPackagingMaterialFee, InventPackagingMaterialTrans, InventPackagingMaterialTransPurch, InventPackagingUnit
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2194
ms.assetid: 040b65dc-43c9-4256-b69f-b2d6e736fbe9
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2020-02-19
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1061f336701461df7a2cf78661788e4c6100c84d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215709"
---
# <a name="packing-materials-and-fees"></a>Materiales y cuotas de embalaje

[!include [banner](../includes/banner.md)]

Las cuotas de material de embalaje se pagan en intervalos específicos a una empresa de reciclaje. Se debe pagar un importe por unidad de peso para cada material del que consta una unidad de embalaje. Aunque las cuotas de material de embalaje se calculan y se notifican, pero no se registra ninguna transacción contable ya que las cuentas no se contemplan como impuestos que se deban pagar a una autoridad.

Las cuotas y pesos de material de embalaje se calculan para las líneas de pedido de compra y de ventas.

Puede definir una o más unidades de embalaje para un artículo, un grupo de artículos (grupo de embalaje) o para todos los artículos. Una unidad de embalaje consta de materiales de embalaje y sus pesos, además del número de artículos que se incluyen en la unidad de embalaje. Se asigna un código de material de embalaje a cada tipo de material de embalaje definido. De acuerdo con el código de material de embalaje, puede especificar un precio de un período concreto. La cuota de material de embalaje se calcula en función de esta información.

> [!NOTE]
> Aunque la empresa no pague las cuentas de material de embalaje, podrá utilizar las funciones para calcular las estadísticas para los pesos de material de embalaje.

## <a name="set-up-packing-material-allocation"></a><a name="allocations"></a>Configurar la asignación de material de embalaje

Antes de poder calcular los pesos del material de embalaje, las tarifas de material de embalaje, o ambos, debe activar el cálculo y definir qué materiales y tarifas se aplican a qué artículos.

1. Vaya a **Gestión del inventario \> Configuración \> Parámetros de la gestión de inventario y almacenes**.
1. En la pestaña **General**, en la sección **Material de embalaje**, establezca la opción **Calcular tarifas de material de embalaje** a **Sí**.
1. Vaya a **Gestión del inventario \> Configurar \> Material de embalaje \> Grupos de embalaje** y cree todos los grupos de embalaje que use. Todos los artículos en un grupo de embalaje utilizarán la misma asignación de material de embalaje. Si no usa grupos de embalaje, puede omitir este paso.

    > [!TIP]
    > Una vez que haya creado sus grupos de embalaje, puede asignar un grupo a cada producto según lo requiera. Vaya a **Gestión de la información del producto \> Productos \> Productos emitidos**, seleccione un producto y después, en la ficha desplegable **Administrar inventario**, en el campo **Grupo de embalaje**, seleccione el grupo de embalaje apropiado.

1. Vaya a **Gestión del inventario \> Configuración \> Material de embalaje \> Códigos de material de embalaje**, defina cada tipo de material de embalaje que utilice y especifique la unidad en la que se consume el material de embalaje cuando prepara los envíos.
1. Vaya a **Gestión del inventario \> Configuración \> Material de embalaje \> Tarifas de material de embalaje** y establezca una tarifa por cada tipo de material de embalaje que acaba de definir. Las tarifas se calculan en función del precio por unidad que se consume.
1. Para asignar materiales de embalaje a los artículos, vaya a **Gestión del inventario \> Configuración \> Material de embalaje \> Asignación de material de embalaje**, y cree asignaciones. Puede crear tantas asignaciones como necesite. Puede asignar materiales de embalaje para artículos individuales, grupos de artículos (grupos de embalaje) o todos los artículos, según cuán detalladas deben ser sus asignaciones.

    Para cada asignación que cree, siga estos pasos.

    1. En la ficha rápida **General**, establezca los siguientes campos:

        - **Código del artículo** - Seleccione el alcance de la asignación:

            - **Tabla** - Crear una asignación para un solo artículo específico.
            - **Grupo** - Cree una asignación para todos los artículos que pertenecen a un grupo de embalaje que se define en la página **Grupos de embalaje**.
            - **Todos** - Crea una asignación para todos los artículos.

            > [!NOTE]
            > Por lo general, debe realizar todas sus asignaciones al mismo nivel (**Tabla**, **Grupo** o **Todos**). Si utiliza más de un nivel, se utilizará la asignación coincidente más específica para cada elemento. (El nivel **Tabla** tiene prioridad sobre el nivel **Grupo**, y ambos niveles tienen prioridad sobre el nivel **Todos**.)

        - **Relación de artículo** - Si está asignando un solo artículo, seleccione el artículo. Si está asignando un grupo de artículos, seleccione el grupo de embalaje. Si está asignando todos los artículos, deje este campo en blanco.
        - **Configuración**, **Tamaño**, **Color**y **Estilo** - Introduzca los valores para estas dimensiones según lo requiera, para definir aún más el elemento que está asignando.
        - **Unidad de embalaje** - Seleccione la unidad en la que se embala el artículo cuando se utiliza el material de embalaje. Esta unidad puede diferir de la unidad en la que se compra y almacena el artículo.
        - **Factor de unidad de embalaje** - Introduzca el factor de conversión que se utiliza para convertir de la unidad de inventario a la unidad de embalaje. (La conversión usa la fórmula *Unidades de embalaje* = *Unidades de artículos* × *Factor de unidad de embalaje*).

    1. En la ficha desplegable **Material de embalaje**, agregue una línea para cada pieza de material de embalaje que se requiere para la asignación actual. En cada línea, especifique el tipo de material (como se define en la página **Códigos de material de embalaje**) y la cantidad que se consume por cada unidad enviada del artículo actual.

## <a name="packing-units-on-sales-order-lines"></a>Unidades de embalaje en las líneas de pedido de ventas

Después de que hayas [activado el cálculo de las tarifas de material de embalaje y configuró sus asignaciones](#allocations), el sistema verifica que se especifiquen unidades de embalaje para cada artículo que se agrega a un pedido de ventas. Luego calcula las tarifas que se requieren. Cuando se agrega un artículo a un pedido de ventas, se produce uno de los siguientes pasos:

- **Si una asignación de embalaje se aplica al artículo**: el sistema actualiza el pedido de ventas con la unidad de embalaje especificada y la cantidad de unidad de embalaje. (La cantidad de unidad de embalaje se calcula usando la fórmula *Cantidad de unidad de embalaje* = *Cantidad pedida* ÷ *Número de artículos en la unidad de embalaje seleccionada*).
- **Si ninguna asignación de embalaje se aplica al artículo**: puede especificar de manera manual una unidad de embalaje y una cantidad de artículos de embalaje en la línea de pedido de ventas.

También es posible cambiar la unidad de embalaje y la cantidad de unidades de embalaje al registrar la línea de pedido de ventas. Esta capacidad es relevante si la línea de pedido de ventas sólo se entrega o factura parcialmente.

El sistema crea las transacciones de material de embalaje al facturar pedidos de ventas. Las transacciones de material de embalaje contienen los pesos del material de embalaje para la línea de ventas. Puede modificar las transacciones después de facturarlas. Entonces podrá crear transacciones nuevas.

## <a name="packing-units-on-purchase-order-lines"></a>Unidades de embalaje en las líneas de pedido de compra

El sistema no crea transacciones de material de embalaje para las líneas de pedido de compra. En su lugar, usted debe crear transacciones para las líneas del pedido de compra facturado en la página **Transacciones de material de embalaje**.

## <a name="set-up-license-numbers-for-customers-that-are-charged-packing-material-fees"></a>Configure números de licencia para clientes a los que se les cobran tarifas por material de embalaje

Si los pedidos de ventas para un cliente específico deben incluir cargos por los materiales de embalaje que se utilizan para cada pedido, siga estos pasos.

1. Vaya a **Clientes \> Clientes \> Todos los clientes**.
1. Seleccione el cliente al que se le debe cobrar por los materiales de embalaje.
1. En la ficha desplegable **Factura y entrega**, establezca los siguientes campos:

    - En la sección **Impuestos**, en el campo **Número de licencia de derecho de embalaje**, introduzca el número de licencia de la compañía.
    - En la sección **Tarifa de material de embalaje**, en el campo **Número de licencia**, introduzca el número de licencia de la compañía.

Ahora, cuando crea y factura un pedido de ventas que incluye uno o más artículos que usan materiales de embalaje, la factura mostrará las tarifas de material de embalaje.

Para los clientes que no deben pagar las tarifas de material de embalaje, siga estos mismos pasos, pero borre los números de licencia de los campos **Número de licencia de derecho de embalaje** y **Número de licencia**. Las facturas para los clientes que no pagan tarifas de material de embalaje muestran el peso de los materiales de embalaje, pero no las tarifas.

Para generar un informe que muestre todas las tarifas de material de embalaje que su empresa deberá por un período específico, vaya a **Gestión del inventario \> Consultas e informes \> Informes de material de embalaje \> Cálculo de la tarifa del material de embalaje**, especifique un rango de fechas y luego seleccione **Aceptar**.

## <a name="print-packing-material-weights-on-invoices"></a>Imprimir los pesos del material de embalaje en las facturas

Puede imprimir los pesos del material de embalaje en una factura e indicar quién paga las tarifas relacionadas. Los pesos se resumen por código de embalaje.

1. Vaya a **Clientes \> Configuración \> Parámetros de clientes**.
1. En la pestaña **Actualizaciones**, en la ficha desplegable **Factura**, establezca la opción **Imprimir peso de material de embalaje** a **Sí**.
