---
title: Directivas de unidad de medida y de existencias
description: "Este artículo describe cómo se usan las unidades predeterminadas, las secuencias de unidad y las conversiones de unidades en los procesos de almacén."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResProductDetails, EcoResProductDetailsExtended, EcoResStorageDimensionGroup, InventItemOrderSetup, UnitOfMeasureConversion, WHSRFMenuItem, WHSUOMSeqGroupTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 29611
ms.assetid: 4b5ca875-9a06-416d-9ac0-cc3ab8f7338e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 82cf9147c050ec661bb2518b2af4e832f8cc480f
ms.lasthandoff: 03/31/2017


---

# <a name="unit-of-measure-and-stocking-policies"></a>Directivas de unidad de medida y de existencias

[!include[banner](../includes/banner.md)]


Este artículo describe cómo se usan las unidades predeterminadas, las secuencias de unidad y las conversiones de unidades en los procesos de almacén.

Los grupos de secuencia de unidades definen la secuencia de unidades que se puede usar en las operaciones de almacén. Se crean en la página **Grupos de secuencias de unidades**. La secuencia muestra la relación de las distintas unidades. Por ejemplo, almacena pallets que contienen cajas que, a su vez, contienen piezas individuales de artículos. En este caso, deberá proporcionar las tres unidades diferentes y el orden lógico de las capas. Los grupos de secuencias de unidades le permiten definir directivas para la agrupación de las matrículas y las unidades predeterminadas que se deben usar para los distintos procesos de almacén. Este artículo se aplica a la solución de almacenamiento avanzada que está disponible en Gestión de almacenes y la solución de almacenamiento más básica que está disponible en Gestión del inventario.

## <a name="unit-sequence-groups-for-released-products"></a>Grupos de secuencias de unidades para productos emitidos
Si desea usar los productos emitidos en los procesos de trabajo de almacén, se les debe asignar un grupo de secuencias de unidades. Si valida un producto que está asociado a un grupo de dimensiones de almacenamiento y la opción **Usar procesos de gestión de almacenes** para el grupo de dimensiones de almacenamiento se establece en **Sí**, recibirá un mensaje de error si no se ha definido una identificación del grupo de secuencias de unidades para el producto. Si el grupo de secuencias de unidades que se usa contiene varias líneas (y por tanto varias unidades), debe configurar una conversión de unidades entre las unidades. Esta configuración se completa en la página **Conversiones de unidades**. La unidad más pequeña de un grupo de secuencias que se asocia a un artículo emitido debe coincidir con la unidad de inventario definida para el producto correspondiente. La unidad de inventario es la unidad que se usará para los cálculos de base del inventario disponible. También puede configurar las conversiones de unidad de medida para las variantes de productos maestros mediante la opción **Habilitar las conversiones de unidad de medida**.

## <a name="license-plate-grouping"></a>Agrupar por matrícula de entidad de almacén
Puede especificar si los recibos de menos o más de una unidad específica se deben agrupar en una matrícula de entidad de almacén o dividirse en una matrícula de entidad de almacén para cada unidad. Para configurar este comportamiento, use la opción **Agrupar por matrícula de entidad de almacén** en la ficha **Detalles de línea** de la página **Grupos de secuencias de unidades**. Si desea usar la agrupación por matrícula de entidad de almacén cuando procesa el trabajo con un dispositivo móvil, debe seleccionar la opción **Agrupación por matrícula de entidad de almacén** en el elemento de menú **Dispositivo móvil**. Por ejemplo, está usando un dispositivo móvil para registrar un artículo asociado a un grupo de secuencias de unidades que tiene dos líneas. La primera línea es para las piezas y la opción **Agrupar por matrícula de entidad de almacén** se ha establecido en **Sí**. La segunda línea es para la unidad de pallet y la opción **Agrupar por matrícula de entidad de almacén** se ha establecido en **No**. En este caso, el sistema puede dirigir automáticamente la división y la creación de matrículas de entidad de almacén por cada 100 unidades.

## <a name="units-for-cycle-counting"></a>Unidades para el recuento cíclico
Para definir las unidades que se deben usar como parte de los procesos de recuento cíclico, seleccione la opción **Usar unidad para el recuento cíclico** en la página **Grupos de secuencias de unidades**. Puede seleccionar un máximo de cuatro unidades en el grupo de secuencias. Si selecciona más de cuatro unidades, las unidades adicionales no se mostrarán en el dispositivo móvil.

## <a name="default-units-for-mobile-device-receiving-processes"></a>Unidades predeterminadas para procesos de recepción de dispositivos móviles
Para definir las unidades predeterminadas que se deben usar para los procesos de recepción en los dispositivos móviles, active las opciones **Unidad predeterminada para compra y transferencia** y **Unidad de producción predeterminada** de la página **Grupos de secuencias de unidades**. Por ejemplo, puede especificar que, de forma predeterminada, el sistema debe usar cantidades de pallet cuando el inventario disponible del pedido de compra se recibe mediante un dispositivo móvil, pero la unidad de mantenimiento de existencias debe ser Piezas. Para obtener la conversión para el número de piezas que cada pallet contiene, debe definir una conversión de unidades, como 100 UDS = 1 PL.

## <a name="default-order-settings"></a>Configuración predeterminada de pedido
Como parte de la creación de productos emitidos, debe seleccionar las unidades predeterminadas para las compras, las ventas y el inventario para procesar los diferentes pedidos. Puede establecer las unidades y las cantidades predeterminadas para varios documentos de origen con las páginas **Configuración predeterminada de pedido** y **Configuración de pedido específica del sitio** . Puede obtener acceso a estas páginas desde la página **Productos emitidos**.




