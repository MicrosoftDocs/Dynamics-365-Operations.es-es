---
title: Transacciones de exceso o falta
description: Este tema proporciona información que ayuda a configurar los detalles de las políticas de transacciones excesivas / insuficientes, de modo que el sistema pueda determinar cómo gestionar el procesamiento excesivo y el procesamiento insuficiente de mercancías en el momento de la recepción.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMOverUnderTrans, ITMOverUnderToleranceTable, ITMOverUnderReasonTable, ITMOverUnderToleranceGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: c7e75e39877b36e482dd4aaa5cc7c8f84d57d81b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833746"
---
# <a name="overunder-transactions"></a>Transacciones de exceso o falta

[!include [banner](../../includes/banner.md)]

Cuando se procesan los pedidos de un viaje, el sistema espera que la cantidad de artículo que se recibe en el almacén de destino final para consumo coincida con la cantidad especificada en las líneas de pedido de compra asociadas con el viaje. Sin embargo, debido a que la cantidad exacta en las líneas de la orden de compra no siempre se recibe en el almacén, el módulo **Coste de aterrizaje** define un conjunto de reglas que se utilizan para manejar la recepción excesiva y la recepción insuficiente de bienes. Estas reglas son especialmente importantes porque la orden de compra original se ha facturado y ya no se puede modificar. Al configurar los detalles de las políticas de transacciones excesivas / insuficientes, habilita el sistema para determinar cómo gestionar el procesamiento excesivo y el procesamiento insuficiente de mercancías en el momento de la recepción. También puede administrar manualmente el inventario por encima y por debajo de la página **Transacciones por encima/por debajo**.

## <a name="overunder-tolerances"></a>Tolerancias de exceso o falta

Usted establece tolerancias de entrega excesiva y entrega insuficiente para especificar las cantidades o volúmenes superiores e inferiores que se pueden procesar en un viaje sin causar un error. Si el recibo de la línea de viaje está fuera de estas tolerancias, debe modificarse y resolverse antes de que la línea de viaje pueda cerrarse para su posterior procesamiento.

Para configurar las tolerancias, vaya a **Coste de aterrizaje \> Configuración por encima/por debajo \> Tolerancias por encima/por debajo**. Allí, puede ver, editar, agregar y eliminar registros de tolerancia. En la tabla siguiente se describen los campos disponibles para cada registro.

| Campo | Descripción |
|---|---|
| Código de cuenta | <p>Defina el alcance de los proveedores a los que se aplica la tolerancia seleccionando uno de los siguientes valores:</p><ul><li>**Tabla** - La tolerancia por encima / por debajo se aplica solo al proveedor que se selecciona para la fila.</li><li>**Grupo** - La tolerancia por encima / por debajo se aplica a todos los proveedores del grupo de tolerancia de proveedor que se selecciona para la fila.</li><li>**Todo**: aplica el porcentaje de tolerancia por encima/por debajo a todos los proveedores.</li></ul> |
| Relación de cuentas | Seleccione el proveedor o grupo de proveedores al que se aplica la tolerancia por encima / por debajo, según el valor que seleccionó en el campo **Código de cuenta**. |
| Código de artículo | <p>Defina el alcance de los artículos a los que se aplica la tolerancia seleccionando uno de los siguientes valores:</p><ul><li>**Tabla** - La tolerancia por encima / por debajo se aplica solo al artículo que se selecciona para la fila.</li><li>**Grupo** - La tolerancia por encima / por debajo se aplica a todos los artículos del grupo de tolerancia de artículo que se selecciona para la fila.</li><li>**Todo**: aplica el porcentaje de tolerancia por encima/por debajo a todos los artículos.</li></ul> |
| Relación de artículos | Seleccione el artículo o grupo de artículos al que se aplica la tolerancia por encima / por debajo, según el valor que seleccionó en el campo **Código de artículo**. |
| Tolerancia de importe | Ingrese la tolerancia de cantidad que se debe aplicar a una orden de compra completa. |
| Tolerancia de porcentaje | Ingrese el porcentaje de tolerancia que se debe aplicar a una línea de orden de compra individual. |

## <a name="overunder-reasons"></a>Motivos del exceso o la falta

Cuando una cantidad mayor o menor se asocia con una línea de viaje que se recibe, es posible que deba identificar el motivo de la cantidad mayor o menor. En este caso, puede seleccionar el motivo de la entrega en exceso o la entrega insuficiente en la línea de recepción cuando se reciben las mercancías.

Para configurar los motivos de sobreentrega y entrega insuficiente, vaya a **Coste de aterrizaje \> Configuración por encima / por debajo \> Motivos por encima / por debajo**. Allí, puede ver, editar, agregar y eliminar los motivos de sobreentrega y entrega insuficientes disponibles. En la tabla siguiente se describen los campos disponibles para cada razón.

| Campo | Descripción |
|---|---|
| Motivo del exceso o la falta | Ingrese un nombre único para el motivo de la transacción de recepción excesiva o insuficiente. |
| Descripción | Especificar una descripción del motivo por encima/por debajo. |
| Movimiento | Seleccione el diario de movimiento que está asociado con el motivo por encima / por debajo. Este campo enumera todas las revistas disponibles que un tipo de diario de *Movimiento* está asociado con en la página **Nombres de diarios de inventario** (**Configuración de gestión de inventario \> Nombres de revistas \> Inventario**). |

## <a name="item-overunder-tolerance-groups"></a>Grupos de tolerancia de exceso o falta de artículos

Los elementos que tienen tolerancias similares se pueden agrupar. De esta manera, puede establecer la tolerancia por encima / por debajo de todos los elementos de ese grupo al mismo tiempo.

Para configurar los grupos de tolerancia de artículo por encima/por debajo, vaya a **Coste de aterrizaje \> Configuración por encima / por debajo \> Grupos de tolerancia de artículo por encima / por debajo**. Allí, puede ver, editar, agregar y eliminar registros de grupos de tolerancia por encima/por debajo. En la tabla siguiente se describen los campos disponibles para cada registro.

| Campo | Descripción |
|---|---|
| Grupo de tolerancias de exceso o falta | Escriba un nombre exclusivo para el grupo. Elija un nombre que describa la tolerancia, como *1% Var*. |
| Descripción | Escriba una descripción del grupo. |

## <a name="vendor-overunder-tolerance-groups"></a>Grupos de tolerancia de exceso o falta de proveedores

Puede agrupar a los proveedores que regularmente entregan en exceso o de forma insuficiente. A continuación, puede establecer la tolerancia por encima / por debajo por grupo.

Para configurar los grupos de tolerancia de proveedor por encima/por debajo, vaya a **Coste de aterrizaje \> Configuración por encima / por debajo \> Grupos de tolerancia de proveeodr por encima / por debajo**. Allí, puede ver, editar, agregar y eliminar registros de grupos de tolerancia por encima/por debajo. En la tabla siguiente se describen los campos disponibles para cada registro.

| Campo | Descripción |
|---|---|
| Grupos por encima / por debajo | Escriba un nombre exclusivo para el grupo. Elija un nombre que describa el tipo de proveedores que pertenecen al grupo. |
| Descripción | Escriba una descripción del grupo. |

## <a name="view-and-process-overunder-transactions"></a>Ver y procesar transacciones por encima / por debajo

Las transacciones por encima y por debajo se generan cuando la cantidad de bienes que se almacena no coincide con la cantidad inicializada. La cantidad en el diario de llegadas debe actualizarse solo con la cantidad almacenada.

Cuando se procesa la recepción de líneas de viaje, se pueden establecer tolerancias superiores / inferiores para un proveedor. Luego, los elementos serán revisados y validados. La tolerancia se puede establecer como un porcentaje, una cantidad local o ambos.

Si un artículo que se recibe está dentro de la tolerancia, el sistema generará un diario de movimiento. Este diario se puede especificar en la página de parámetros del viaje. Además, se creará una transacción por encima / por debajo. Por ejemplo, el valor del pedido es $100, el valor del recibo es $99 y estos valores satisfacen las reglas de tolerancia. En este caso, se creará un diario de movimiento negativo para la cantidad sub recibida.

Si un artículo que se recibe está fuera de la tolerancia, el sistema generará una transacción por encima / por debajo de la diferencia en la cantidad.

Para ver y procesar transacciones por encima / por debajo, vaya a **Coste de aterrizaje \> Consultas \> Transacciones por encima / por debajo**. Allí, una transacción de más / menos se asociará con todos los artículos en un viaje que se recibieron en exceso o en menos. Le recomendamos que utilice la página **Transacciones por encima / por debajo** para resolver todas las transacciones por encima/por debajo asociadas con los viajes. También recomendamos que **no** utilice diarios de movimiento o recuento para resolver manualmente las transacciones del almacén con entrega insuficiente. En su lugar, debe utilizar la página **Transacciones por encima / por debajo** para gestionar las cantidades de almacén con entrega insuficiente.

### <a name="upper-overview-tab"></a>Ficha Vista general superior

Para ver sus transacciones por encima / por debajo, seleccione la pestaña **Visión general** en la parte superior de la página **Transacciones por encima / por debajo**. En la tabla siguiente se describen los campos disponibles en la cuadrícula.

| Campo | Descripción |
|---|---|
| Número de transacción de exceso o falta | El nombre único del registro de transacción por encima / por debajo que se creó automáticamente cuando se procesó el diario de llegada. |
| Viaje | El viaje al que se adjuntó la línea de compra. |
| Contenedor de envío | El contenedor al que se adjuntó la línea de compra. |
| Diario de llegadas | El diario de llegada desde el que se generó la línea superior / inferior. |
| Referencia | Una referencia a la orden de compra o la orden de transferencia que está asociada con la transacción por encima / por debajo. |
| Número | La orden de compra a la que se hace referencia en la transacción por encima / por debajo. |
| Cuenta del proveedor | El proveedor con el que está relacionado el superior o inferior. |
| Número de la mercancía en tránsito | El número de mercancías en tránsito, si corresponde. |
| Número de artículo | El número de artículo con el que está relacionado el superior o inferior. |
| Cantidad original | La cantidad original de la línea de la orden de compra que se adjunta al envío. |
| Cantidad recibida | La cantidad que se ha recibido realmente. |
| Diferencia | La diferencia entre la cantidad prevista del diario de llegadas y la cantidad que se registró en el diario de llegadas. Un valor negativo indica una entrega excesiva de bienes. |
| Cantidad restante | La cantidad que queda en la línea del diario de llegadas. |
| Entrega con exceso/incompleta | Un valor que indica si la cantidad recibida es superior o inferior. |
| Estado | El estado de la transacción de por encima/por debajo. Dependiendo de la configuración de la página **[Parámetros de costo aterrizado](landed-cost-parameters.md)**, la sobreentrega puede crear automáticamente un diario de movimiento para la cantidad de sobreentrega y registrar el diario. En este caso, la transacción por encima / por debajo tendrá un estado de *Terminado*. Si se requiere una acción para sacar las mercancías del almacén de entrega insuficiente, el registro tendrá un estado de *En proceso*. |
| Motivo del exceso o la falta | La razón que está asociada con la transacción por encima / por debajo. |
| Otras dimensiones de inventario | Puede mostrar columnas para dimensiones adicionales en la cuadrícula según lo requiera. Estas dimensiones incluyen el número de lote, el estado del inventario y el almacén. En el panel de acciones, seleccione **Inventario \> Dimensiones de la pantalla** para abrir un cuadro de diálogo donde puede seleccionar las dimensiones a incluir. |

### <a name="upper-general-tab"></a>Pestaña General superior

Para ver más información sobre la línea que está actualmente seleccionada en la pestaña superior **Visión general**, seleccione la pestaña **General** en la parte superior de la página **Transacciones por encima / por debajo**. La información de esta pestaña incluye los valores de todas las dimensiones disponibles. Esta información se extrae de la orden de compra de origen.

### <a name="lower-overview-tab"></a>Ficha Vista general inferior

Para ver el tipo de documento para la fila que está seleccionada en la pestaña superior **Visión general**, seleccione la pestaña **Descripción general** en la parte inferior de la página **Transacciones por encima / por debajo**. En la tabla siguiente se describen los campos disponibles.

| Campo | Descripción |
|---|---|
| Nuevo tipo de documento | Este campo se establece en *Diario de movimiento* u *Orden de compra*, dependiendo de la acción que se muestra en la línea de transacción de arriba / abajo seleccionada. |
| Número | Una referencia y un vínculo a la orden de compra o al diario de movimiento asociados con la línea de transacción por encima / por debajo seleccionada. |
| Motivo del exceso o la falta | La razón que está asociada con la línea de transacción por encima / por debajo seleccionada. |
| Cantidad | La cantidad que seleccionó para la orden de compra o diario de movimiento asociados con la línea de transacción por encima / por debajo seleccionada. |

### <a name="lower-general-tab"></a>Pestaña General inferior

Para ver el número de transacción por encima / por debajo, el ID de lote y el número de dimensión que están asociados con la línea de transacción por encima / por debajo seleccionada, seleccione la pestaña **General** en la parte inferior de la página **Transacciones por encima / por debajo**. 

### <a name="process-overunder-transactions"></a>Procesar transacciones por encima / por debajo

El panel de acciones de la página **Transacciones por encima / por debajo** proporciona los siguientes comandos para procesar las transacciones que se seleccionan en la página. Cada comando le permite elegir cómo procesar cada transacción.

- **Crear \> Movimiento** - Crear y contabilizar un diario de movimientos para la transacción seleccionada. Para las transacciones inferiores, se crea y contabiliza automáticamente un diario de movimientos por la diferencia entre la cantidad recibida esperada y real. Seleccione este comando para transacciones excesivas si desea que el proveedor se dé cuenta de la diferencia de costo.
- **Crear \> Orden de compra** - Cree una orden de compra por la diferencia entre la cantidad recibida esperada y real de la transacción seleccionada. Seleccione este comando para transacciones excesivas si su organización materializará la diferencia de costo.
- **Crear \> Transferir a destino** - Este comando se aplica solo a las órdenes de transferencia. Selecciónelo si desea transferir la cantidad superior o inferior al almacén de destino.
- **Crear \> Transferir a origen** - Este comando se aplica solo a las órdenes de transferencia. Selecciónelo si desea transferir la cantidad superior o inferior al almacén de origen.
