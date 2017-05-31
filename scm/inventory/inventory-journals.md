---
title: Diarios de inventario
description: "Este artículo describe cómo puede usar diarios de inventario para registrar diversos tipos de transacciones de inventario físico."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalBOM, InventJournalCount, InventJournalCountTag, InventJournalLossProfit, InventJournalMovement, InventJournalTransfer, WMSJournalTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 51631
ms.assetid: 3fedeaaf-502f-483c-93d2-ab266828189e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d947b184fd61af3b997182f0a39a8c13c58d6a5a
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="inventory-journals"></a>Diarios de inventario

[!include[banner](../includes/banner.md)]


Este artículo describe cómo puede usar diarios de inventario para registrar diversos tipos de transacciones de inventario físico. 

Los diarios de inventario en Microsoft Dynamics 365 for Operations se usan para registrar transacciones de inventario físico de distintos tipos, como el registro de emisiones y recepciones, los movimientos de inventario, la creación de listas de materiales (BOM) y la conciliación del inventario físico. Todos estos diarios de inventario se usan en forma similar, pero se dividen en diferentes tipos.

## <a name="types-of-inventory-journals"></a>Tipos de diarios de inventario
Los siguientes tipos de diarios de inventario están disponibles:

-   Movimiento
-   Ajuste de inventario
-   Transferir
-   L. MAT
-   Recepción de artículos
-   Entrada desde producción.
-   Recuento
-   Recuento de etiquetas

### <a name="movement"></a>Movimiento

Cuando usa un diario de movimientos de inventario, puede agregar coste a un artículo cuando agrega el inventario, pero debe asignar manualmente el coste adicional en una cuenta de contabilidad general en particular si especifica una cuenta de contrapartida de la contabilidad general cuando se crea el diario. Este tipo de diario de inventario es útil si desea cargar un artículo a un departamento diferente o si desea quitar artículos del inventario para fines de gasto.

### <a name="inventory-adjustment"></a>Ajuste de inventario

Cuando usa un diario de ajuste de inventario, puede agregar coste a un artículo al agregar el inventario. El coste adicional se registra automáticamente en una cuenta de contabilidad general específica, en función de la configuración del perfil de contabilización del grupo de artículos. Use este tipo de diario de inventario para actualizar pérdidas y ganancias a las cantidades de inventario cuando el artículo debe conservar la cuenta de contrapartida de contabilidad general predeterminada. Al registrar un diario de ajuste de inventario, se registra una recepción o emisión del inventario, se modifican los valores del inventario y se crean transacciones contables.

### <a name="transfer"></a>Transferir

Puede usar los diarios de la transferencia a los artículos de la transferencia entre las ubicaciones de existencias, los lotes o las variantes de producto sin asociar las consecuencias de coste. Por ejemplo, puede transferir los artículos de un almacén a otro dentro de la misma empresa. Cuando usa un diario de transferencias, debe especificar las dimensiones de inventario “de” y “a” (por ejemplo, para el sitio y el almacén). El inventario disponible para las dimensiones de inventario definidas se cambia según corresponda. Las transferencias de inventario reflejan el movimiento instantáneo de material. No se realiza el seguimiento de inventario en tránsito. Si el inventario en tránsito debe ser seguido, debe usar un pedido de transferencia en su lugar. Cuando se registra un diario de transferencias, se crean dos transacciones de inventario para cada línea de diario:

-   Una emisión de inventario en la ubicación “de”
-   Una recepción de inventario en la ubicación “a”

### <a name="bom"></a>L. MAT

Al notificar una L. MAT. como terminados, puede crear un diario de L. MAT. Mediante un diario de L. MAT., puede registrar la L. MAT. directamente. Este registro genera una recepción de inventario del producto, junto con una L. MAT. asociada y una emisión de inventario de los productos que se incluyen en la L. MAT. Este tipo de diario de inventario es útil en las situaciones de producción simples o de grandes cantidades en las que no se necesitan rutas.

### <a name="item-arrival"></a>Recepción de artículos

Puede usar el diario de recepción de artículos para registrar la recepción de artículos (por ejemplo, pedidos de compra). Un diario de recepción de artículos se puede crear como parte de la gestión de llegada de la página **Visión general de llegadas**, o bien crear manualmente una entrada del diario de la página **Recepción de artículos**. Si se habilita el nombre del diario de recepción de artículos para comprobar las ubicaciones de recogida, Dynamics 365 for Operations busca una ubicación para los artículos recibidos y, si hay sitio, genera destinos de ubicación para los artículos entrantes.

### <a name="production-input"></a>Entrada desde producción.

Los diarios de entrada de producción funcionan como los diarios de recepción de artículos pero se usan para los pedidos de producción.

### <a name="counting"></a>Recuento

Los diarios de recuento le permiten corregir el inventario disponible actual que se registra para los artículos o grupos de artículos, y después registrar la cuenta física real, de manera que pueda realizar los ajustes necesarios para conciliar las diferencias. Puede asociar las directivas de recuento con los grupos de recuento para ayudar a agrupar los artículos que tienen diferentes características para poder incluir los artículos en un diario de recuento. Por ejemplo, puede configurar los grupos de recuento para contar artículos que tienen una frecuencia concreta o para contar artículos cuando las existencias se encuentren en un nivel determinado. Para obtener información sobre cómo definir los grupos de recuento, vea [Definición de procesos de recuento de inventario (guía de tareas)](http://ax.help.dynamics.com/en/wiki/define-inventory-counting-processes/).

### <a name="tag-counting"></a>Recuento de etiquetas

Los diarios de recuento de etiquetas se usan para asignar una etiqueta numerada a un lote de recuento. La etiqueta debe contener un número de etiqueta, un número de artículo y una cantidad de artículo. Para ayudar a garantizar que una etiqueta se usa solo una vez y que todas las etiquetas se usarán, cada número de artículo debe tener el sistema único de etiquetas que tiene su propia secuencia numérica. Tres valores de estado se pueden definir para cada etiqueta:

-   **Usado**: el número de artículo se cuenta para esta etiqueta.
-   **Anulado**: el número de artículo se anula para esta etiqueta.
-   **Falta**: el número de artículo falta para esta etiqueta.

Cuando se registra un diario de recuento de etiquetas, se crea un diario de recuento nuevo basado en las líneas del diario de recuento de etiquetas. Para obtener más información acerca del recuento de etiquetas, vea [Recuento de etiquetas de inventario](inventory-tag-counting.md).

## <a name="working-with-journals"></a>Trabajo con diarios
Sólo se puede tener acceso a una línea de diario un usuario por vez. Si varios usuarios deben tener acceso a los diarios al mismo tiempo para crear líneas de diario, esos usuarios deben seleccionar los diarios que no se usan actualmente para evitar que la información se sobrescriba. En las situaciones en las que varios departamentos usan el mismo tipo de diario, resulta útil crear varios nombres de diario (por ejemplo, uno por departamento). También puede servir de ayuda dividir los diarios para que cada rutina de registro se especifique en su propio diario de inventario único. Para las rutinas de registro asociadas a las transacciones de inventario, cree un diario para los ajustes periódicos del inventario y otro para el recuento de inventario.

## <a name="posting-journal-lines"></a>Registro de líneas de diario
Puede registrar las líneas de diario que crea en cualquier momento hasta que haya bloqueado un artículo de transacciones adicionales. Los datos que introduzca en un diario permanecen en ese diario incluso si cierra el diario sin registrar las líneas.




