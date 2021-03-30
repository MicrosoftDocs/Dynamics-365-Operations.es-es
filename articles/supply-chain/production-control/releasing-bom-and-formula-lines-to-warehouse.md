---
title: Liberar las líneas de LM y fórmula al almacén
description: En este tema se describe el proceso para liberar la materia prima para las líneas de LM y las líneas de fórmula al almacén.
author: johanhoffmann
manager: tfehr
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysOperationTemplateForm, ProdParmReleaseToWarehouse, WHSReleaseToWarehouseProdBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 62808c2e488e2c38b7dedfc258d9f2bf3e78c23c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209308"
---
# <a name="release-bom-and-formula-lines-to-the-warehouse"></a>Liberar las líneas de LM y fórmula al almacén

[!include [banner](../includes/banner.md)]

En este tema se describe el proceso para liberar la materia prima para las líneas de lista de materiales (LM) y las líneas de fórmula al almacén. Cuando libera una LM o una línea de fórmula al almacén, primero el sistema determina si los materiales están disponibles ya en la ubicación de entrada de producción de la planta donde el material será consumido para el proceso de producción.

- Si el material está disponible en la ubicación de entrada de producción, se selecciona desde dicha ubicación inmediatamente después de que se de la señal para la liberación del material al almacén.
- Si el material no está disponible en la ubicación de entrada de producción, la liberación de material indica que el material se debe mover de ubicación en el almacén a la ubicación de entrada de producción. El material se mueve a través del trabajo del almacén para selección de la materia prima. Por lo tanto, los procesos del almacén para selección de la materia prima deben estar configurados. Para obtener más información, vea [Visión general sobre el reabastecimiento](../warehousing/replenishment.md) y [Controlar el trabajo de almacén con plantillas de trabajo y directivas de ubicación](../warehousing/control-warehouse-location-directives.md).

## <a name="methods-for-releasing-bom-and-formula-lines"></a>Métodos para liberar LM y las líneas de fórmula

Puede configurar la liberación de LM y líneas de fórmula de modo que aparezca como parte de la liberación de un pedido de producción o pedido de lote. Como alternativa, la liberación se puede controlar por un trabajo por lotes o como interacción manual.

El método que se usa para liberar LM y las líneas de fórmula se controal con el parámetro **Liberar línea de producción**. Puede buscar este parámetro en **Control de producción** \> **Configuración** \> **Parámetros de producción**.

- **Liberar LM y las líneas de fórmula como parte de liberación de la producción o del pedido de lote** En este método, la LM y las líneas de fórmula para una producción o un pedido de lote se liberan como parte del proceso de liberación del pedido. Normalmente, durante la liberación de un peidod o lote producción, los trabajos de producción se liberan a los trabajadores de la planta y se imprimen los documentos de producción. Durante este proceso, el estado del pedido también cambia a **Liberado**.
- **Liberar LM y las líneas de fórmula mediante un trabajo por lotes o como interacción manual** En este método, la LM y las líneas de fórmula se pueden liberar sólo con el trabajo por lotes **Liberación automática de LM y líneas de fórmula** o como interacción manual. Para liberar manualmente la LM y las líneas de fórmula, en la página de lista del pedido de producción o la página de detalles del pedido de producción, en el panel de acciones, seleccione **Liberar a almacén**.

Para ver una demostración rápida de cómo liberar L. MAT. y las líneas de fórmula a la producción mediante un trabajo por lotes, vea este breve vídeo de YouTube: [Liberar por lotes la selección de producción al almacén](https://www.youtube.com/watch?v=8urAJn50dQ8).

## <a name="releasing-the-bom-and-formula-lines-by-using-a-batch-job"></a>Liberar la LM y las líneas de fórmula mediante un trabajo por lotes

El trabajo por lotes **Liberación automática de la LM y líneas de fórmula** pasa por la LM seleccionada y las líneas de fórmula que tengan una cantidad restante para liberar. El trabajo sólo tiene en cuenta pedidos que tengan un estado **Liberado**, **Iniciado**, o **Notificado como terminado**. Si la lista de materiales o una línea de fórmula tiene una cantidad restante que se deba liberar, el trabajo libera hasta la cantidad que se pueda cubrir con la cantidad que ya se haya reservado físicamente y la cantidad que esté físicamente disponible.

### <a name="example-of-a-batch-job-release"></a>Ejemplo de liberación de un trabajo por lotes

| Situación | Cantidad pendiente de liberación | Cantidad físicamente reservada | Cantidad físicamente disponible | Cantidad liberada en el trabajo por lotes |
|----------|-------------------------------|------------------------------|-------------------------------|------------------------------------|
| 1        | 100                           | 20                           | 90                            | 100                                |
| 2        | 100                           | 20                           | 70                            | 90                                 |
| 3        | 100                           | 0                            | 90                            | 90                                 |
| 4        | 100                           | 0                            | 110                           | 100                                |
| 5        | 100                           | 20                           | 0                             | 20                                 |

### <a name="batch-job-setup"></a>Configuración de trabajos por lotes

En la consulta para el trabajo por lotes **Liberación automática de LM y líneas de fórmula** , puede configurar un criterio de filtro para especificar con cuántos días de antelación el trabajo debe buscar las líneas que tengan cantidades sin liberar. En la consulta para el trabajo, en el campo **Fecha de la materia prima** , utilice la función **(LessThanDate ())** como criterio de filtro.

La ilustración siguiente muestra unpedido de producción que tiene dos trabajos, 10 y 20, que cubre el ensamblado y el embalaje para el pedido de producción. Cada trabajo está configurado para consumir una cantidad de material. En este ejemplo, el límite de tiempo de liberación que se indica con la flecha verde por debajo de la escala temporal es igual al número de días que se ha especificado en el criterio **(LessThanDate ())**. Por ejemplo, **(LessThanDate (2))** indica que el trabajo debe buscar sólo cantidades inéditas en un límite de tiempo de dos días.

![Ejemplo de un pedido de producción que tiene dos trabajos por lotes](media/bach-job-setup.PNG)

## <a name="releasing-material-per-operation-number-or-in-proportion-to-the-amount-of-finished-goods"></a>La liberación de material por el número de operación o en proporción al importe de producto terminado

Si se libera el material usando el valor del parámetro **En la liberación del pedido de producción**, al hacer un liberación manual, tiene dos opciones para controlar el lanzamiento materiales:

- Liberación de material por el número de operación.
- Liberación de material en proporción a la cantidad de producto terminado.

### <a name="release-material-per-operation-number"></a>Liberación de material por el número de operación

Para controlar las operaciones a las que liberarse el material debe , use la página **Liberar a almacén**.

- Seleccione **Control de producción** \> **Pedidos de producción** \> **Todos los pedidos de producción**, seleccione un pedido de producción y, a continuación, en la pestaña **Almacén** , seleccione **Liberar a almacén**. A continuación use **Desde nº. Oper.** y campos **Hasta nº. Oper.** para especificar el intervalo de números de operación.

La ilustración siguiente muestra un pedido de producción que tiene dos operaciones, 10 y 20. En este ejemplo, si se limita la liberación a la operación 10, solo el material M9203 será liberado.

![Ejemplo de liberación del material por el número de operación](media/two-operations.PNG)

Para ver una demostración rápida de cómo liberar material en proporción al importe de productos terminados, mire este vídeo corto de YouTube sobre [Mejoras al proceso de liberación de una orden de producción](https://www.youtube.com/watch?v=Rm3ojAz6Zu0)

### <a name="release-material-in-proportion-to-the-amount-of-finished-goods"></a>Liberación de material en proporción a la cantidad de producto terminado

Puede liberar la materia prima para una cantidad parcial de producto terminado o en una unidad específica.

- Para liberar materia prima por una cantidad parcial o producto terminado, seleccione **Control de producción** \> **Pedidos de producción** \> **Todos los pedidos de producción**, seleccione un pedido de producción y, a continuación, en la pestaña **Almacén** , seleccione **Liberar a almacén**. A continuación, introduzca una cantidad en el campo **Cantidad**.

    Por ejemplo, un pedido de producción se crea y se programa para 1.000 piezas (uds.). El supervisor de planta planifica la producción de 100 unidades. para el siguiente turno y desea liberar el material sólo para ese turno. En este caso, el supervisor puede utilizar el campo **Cantidad** para liberar el material para las 100 unidades. que está prevista que el siguiente turno.

- Para liberar materia prima en una unidad específica, seleccione **Control de producción** \> **Pedidos de producción** \> **Todos los pedidos de producción**, seleccione un pedido de producción y, a continuación, en la pestaña **Almacén** , seleccione **Liberar a almacén**. A continuación utilice el campo **Unidad** para seleccionar la unidad de producto terminado para liberar el material.

    Las unidades que están disponibles se definen en el ID de grupo de secuencia de unidades del producto terminado.

    Por ejemplo, un producto terminado tiene la siguiente conversión de unidades entre las libras (lbs.) y pallet (PL): 1 PL = 100 lbs. Para crear un pedido de producción para 10.000 lbs. de producto terminado, puede liberar las materias primas para el número de pallets que pretenda generar. Seleccione **PL** como unidad y, a continuación, seleccione un número correspondiente en el campo **Cantidad**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]