---
title: Requisitos netos e información de diagrama de árbol con Optimización de planificación
description: Este tema proporciona información sobre los requisitos netos calculados y la información de diagrama de árbol en Optimización de planificación.
author: t-benebo
ms.date: 7/28/2021
ms.topic: article
ms.search.form: ReqTransOverview
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: edfa6010074a4b04b3200115891723cd45871624
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468871"
---
# <a name="net-requirements-and-pegging-information-with-planning-optimization"></a>Requisitos netos e información de diagrama de árbol con Optimización de planificación

[!include [banner](../../includes/banner.md)]

Cuando ejecuta la planificación maestra en Optimización de planificación, es importante que comprenda su salida, cómo el suministro existente cubre la demanda y por qué se generó un suministro específico. Puede usar la página **Requisitos netos** para comprender mejor los requisitos calculados que produce la planificación maestra.

La página **Requisitos netos** muestra los requisitos netos que Optimización de planificación calculó para el producto. También muestra la configuración de cobertura que se aplicó durante la ejecución de la planificación maestra, un desglose de los totales de requisitos por tipo de transacción e información de diagrama de árbol.

## <a name="open-the-net-requirements-page"></a>Abra la página de requisitos netos

Puede abrir la página **Requisitos netos** de cualquiera de las siguientes formas:

- Vaya a **Gestión de información de productos \> Productos \> Productos despachados**. Seleccione o abra un producto. En el panel Acciones, en la pestaña **Plan** del grupo **Requisito**, seleccione **Requisitos netos**.
- Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**. Abra un pedido de ventas. En la ficha desplegable **Líneas de pedido de ventas**, en la barra de herramientas, seleccione **Producto y suministro \> Requisitos netos**.
- Vaya a **Planificación maestra \> Planificación maestra \> Pedidos planificados**. Seleccione o abra un pedido planificado. En el panel Acciones, en la pestaña **Ver** del grupo **Requisitos**, seleccione **Perfil de requisito**.

## <a name="use-the-net-requirements-page"></a>Usar la página de requisitos netos

La página **Requisitos netos** consta de secciones superior e inferior. El panel de acciones de esta página incluye un botón de **Actualizar**. Cuando se selecciona este botón, aparece un menú de comandos.

### <a name="select-a-master-plan-to-view"></a>Seleccionar un plan maestro para ver

Antes de revisar los requisitos netos del producto, asegúrese de seleccionar el plan maestro relevante en el campo **Plan** de la parte superior de la página.

### <a name="upper-section"></a>Sección superior

La sección superior de la página proporciona las siguientes pestañas:

- **Visión general** - Ver los requisitos del artículo de las dimensiones del producto.
- **Cobertura de artículos** - Ver la configuración de cobertura que se utilizó durante el cálculo de los requisitos.
- **Resumen** - Ver un desglose de los totales de requisitos por tipo de transacción.
- **Período** - Ver los recibos, las emisiones y el inventario disponible proyectado para cada período definido por la plantilla de período. También puede obtener una vista gráfica del inventario disponible proyectado.

### <a name="lower-section"></a>Sección inferior

La sección inferior de la página proporciona las siguientes pestañas:

- **Visión general** - Ver la lista de requisitos de productos que se calcularon durante la ejecución de la planificación maestra, junto con las transacciones de emisión y recepción que corresponden a los requisitos. De forma predeterminada, la lista está ordenada por fecha de requisito. Cuando selecciona un requisito, la ficha desplegable **Diagrama de árbol** de la sección inferior muestra el origen del requisito o las transacciones que cumplen con el requisito.
- **General** - Ver información detallada sobre el requisito seleccionado.
- **Acción** - Ver mensajes de acción para los requisitos.

### <a name="the-action-pane"></a>En Panel de acciones

Los siguientes comandos están disponibles en el Panel de acciones:

- **Actualizar\> Planificación maestra** - Ejecute la planificación maestra directamente desde la página **Requisitos netos**.
- **Actualizar\> Planificación de previsión** - Ejecute la planificación de previsión directamente desde la página **Requisitos netos**. Optimización de planificación aún no admite esta operación.
- **Actualizar\> Programación de continuidad** - Ejecute la programación de continuidad directamente desde la página **Requisitos netos**. Optimización de planificación aún no admite esta operación.

## <a name="example-scenario"></a>Supuesto de ejemplo

Este ejemplo muestra cómo se presenta la información de diagrama de árbol en la página **Requisitos netos**.

### <a name="prerequisites"></a>Requisitos previos

Antes de trabajar con este escenario, prepare los siguientes requisitos previos:

1. Debe trabajar en un sistema donde los datos de muestra estándar estén disponibles y debe configurar la entidad jurídica como *USMF*.
2. Este ejemplo usa el producto *1000*, que forma parte de los datos de muestra de USMF. Asegúrese de que este producto esté disponible y de que esté configurado de la siguiente manera:

    - **Tipo de orden por defecto**: *Pedido de compra*
    - **Inventario disponible:** *10,00*

3. Cree un pedido de ventas para una cantidad de *25,00* del producto *1000*. Utilice las dimensiones de almacenamiento donde se encuentra el inventario disponible.
4. Ejecute la planificación maestra para el plan maestro *DynPlan*.

### <a name="review-the-calculated-requirements"></a>Revisar los requisitos calculados

A continuación, abrirá la página **Requisitos netos** para el producto *1000* para revisar cómo se corresponden los requisitos calculados entre sí.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Seleccione el producto que tiene el **Número de artículo** *1000*.
1. En el panel Acciones, en la pestaña **Plan** del grupo **Requisito**, seleccione **Requisitos netos**.
1. En la página **Requisitos netos**, defina el campo **Plan** como *DynPlan*.
1. En la ficha **Visión general** de la parte inferior de la página, verifique que los siguientes requisitos se enumeran como filas en la cuadrícula.

    | Referencia | Cantidad requerida | Acumulado |
    |---|---|---|
    | Disponible | 10,00 | 10,00 |
    | Pedidos de compra planificados | 15.00 | 25.00 |
    | Pedido de ventas | -25,00 | (En blanco) |

    > [!NOTE]
    > El campo **Cantidad de requisito** representa la cantidad total que el requisito requiere (si el valor es negativo) o suministra (si el valor es positivo). El campo **Acumulado** representa las cantidades totales de recepción y emisión que se acumularon durante el período seleccionado.

1. Seleccione la línea de requisito *Disponible*, y luego, en la ficha desplegable **Diagrama de árbol**, revise los requisitos que cubre este suministro. La siguiente fila debería aparecer allí.

    | Referencia | Cantidad requerida | Cantidad cubierta |
    |---|---|---|
    | Pedido de ventas | -25,00 | -10,00 |

    El inventario disponible existente cubre parcialmente la demanda que proviene del pedido de ventas.

    ![Información de diagrama de árbol para el inventario disponible](media/pegging-on-hand.png "Información de diagrama de árbol para el inventario disponible")

1. Seleccione la línea de requisito *Pedidos de compra planificados*, y luego, en la ficha desplegable **Diagrama de árbol**, revise los requisitos que cubre este suministro. La siguiente fila debería aparecer allí.

    | Referencia | Cantidad requerida | Cantidad cubierta |
    |---|---|---|
    | Pedido de ventas | -25,00 | -15,00 |

    Debido a que el pedido de ventas ya se cubrió parcialmente, el sistema crea un pedido de compra planificado para la cantidad restante no cubierta.

    ![Información de diagrama de árbol para el pedido de compra planificado](media/pegging-planned-purchase-order.png "Información de diagrama de árbol para el pedido de compra planificado")

1. Seleccione la línea de requisito *Pedido de ventas*, y luego, en la ficha desplegable **Diagrama de árbol**, revise los requisitos que cubre esta demanda. Las siguientes filas deberían aparecer allí.

    | Referencia | Cantidad requerida | Cantidad cubierta |
    |---|---|---|
    | Disponible | 10,00 | 10,00 |
    | Pedidos de compra planificados | 15.00 | 15.00 |

    ![Información de diagrama de árbol para el pedido de ventas](media/pegging-planned-purchase-order.png "Información de diagrama de árbol para el pedido de ventas")

> [!NOTE]
> Dado que Optimización de planificación aún no admite algunas funciones, los tipos de requisito *Stock de seguridad* y *Lote caducado* no se incluyen en la página **Requisitos netos**. Para obtener más información, consulte [Análisis de aptitud de optimización de la planificación](planning-optimization-fit-analysis.md).
>
> Si está utilizando el motor de planificación maestra integrado, se admiten los productos controlados por lotes. Para productos controlados por lotes, el inventario disponible vencido se muestra en la página **Requisitos netos**, pero no está vinculado a los requisitos de demanda. Las líneas disponibles caducadas de este tipo se muestran como líneas de requisito de *Lote caducado* en la página **Requisitos netos**.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
