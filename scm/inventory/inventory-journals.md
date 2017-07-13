---
title: Diarios de inventario
description: "Este artículo describe cómo puede usar diarios de inventario para registrar diversos tipos de transacciones de inventario físico."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalBOM, InventJournalCount, InventJournalCountTag, InventJournalLossProfit, InventJournalMovement, InventJournalTransfer, WMSJournalTable
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 51631
ms.assetid: 3fedeaaf-502f-483c-93d2-ab266828189e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: fa629b4b8f7fcbd15ee89bc66cbc0bd7ca45215c
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# Diarios de inventario
<a id="inventory-journals" class="xliff"></a>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


Este artículo describe cómo puede usar diarios de inventario para registrar diversos tipos de transacciones de inventario físico. 

Los diarios de inventario en Microsoft Dynamics 365 for Finance and Operations se usan para registrar transacciones de inventario físico de distintos tipos, como el registro de emisiones y recepciones, los movimientos de inventario, la creación de listas de materiales (BOM) y la conciliación del inventario físico. Todos estos diarios de inventario se usan en forma similar, pero se dividen en diferentes tipos.

## Tipos de diarios de inventario
<a id="types-of-inventory-journals" class="xliff"></a>
Los siguientes tipos de diarios de inventario están disponibles:

-   Movimiento
-   Ajuste de inventario
-   Transferir
-   L. MAT
-   Recepción de artículos
-   Entrada desde producción.
-   Recuento
-   Recuento de etiquetas

### Movimiento
<a id="movement" class="xliff"></a>

Cuando usa un diario de movimientos de inventario, puede agregar coste a un artículo cuando agrega el inventario, pero debe asignar manualmente el coste adicional en una cuenta de contabilidad general en particular si especifica una cuenta de contrapartida de la contabilidad general cuando se crea el diario. Este tipo de diario de inventario es útil si desea cargar un artículo a un departamento diferente o si desea quitar artículos del inventario para fines de gasto.

### Ajuste de inventario
<a id="inventory-adjustment" class="xliff"></a>

Cuando usa un diario de ajuste de inventario, puede agregar coste a un artículo al agregar el inventario. El coste adicional se registra automáticamente en una cuenta de contabilidad general específica, en función de la configuración del perfil de contabilización del grupo de artículos. Use este tipo de diario de inventario para actualizar pérdidas y ganancias a las cantidades de inventario cuando el artículo debe conservar la cuenta de contrapartida de contabilidad general predeterminada. Al registrar un diario de ajuste de inventario, se registra una recepción o emisión del inventario, se modifican los valores del inventario y se crean transacciones contables.

### Transferir
<a id="transfer" class="xliff"></a>

Puede usar los diarios de la transferencia a los artículos de la transferencia entre las ubicaciones de existencias, los lotes o las variantes de producto sin asociar las consecuencias de coste. Por ejemplo, puede transferir los artículos de un almacén a otro dentro de la misma empresa. Cuando usa un diario de transferencias, debe especificar las dimensiones de inventario “de” y “a” (por ejemplo, para el sitio y el almacén). El inventario disponible para las dimensiones de inventario definidas se cambia según corresponda. Las transferencias de inventario reflejan el movimiento instantáneo de material. No se realiza el seguimiento de inventario en tránsito. Si el inventario en tránsito debe ser seguido, debe usar un pedido de transferencia en su lugar. Cuando se registra un diario de transferencias, se crean dos transacciones de inventario para cada línea de diario:

-   Una emisión de inventario en la ubicación “de”
-   Una recepción de inventario en la ubicación “a”

### L. MAT
<a id="bom" class="xliff"></a>

Al notificar una L. MAT. como terminados, puede crear un diario de L. MAT. Mediante un diario de L. MAT., puede registrar la L. MAT. directamente. Este registro genera una recepción de inventario del producto, junto con una L. MAT. asociada y una emisión de inventario de los productos que se incluyen en la L. MAT. Este tipo de diario de inventario es útil en las situaciones de producción simples o de grandes cantidades en las que no se necesitan rutas.

### Recepción de artículos
<a id="item-arrival" class="xliff"></a>

Puede usar el diario de recepción de artículos para registrar la recepción de artículos (por ejemplo, pedidos de compra). Un diario de recepción de artículos se puede crear como parte de la gestión de llegada de la página **Visión general de llegadas**, o bien crear manualmente una entrada del diario de la página **Recepción de artículos**. Si se habilita el nombre del diario de recepción de artículos para comprobar las ubicaciones de recogida, Finance and Operations busca una ubicación para los artículos recibidos y, si hay sitio, genera destinos de ubicación para los artículos entrantes.

### Entrada desde producción.
<a id="production-input" class="xliff"></a>

Los diarios de entrada de producción funcionan como los diarios de recepción de artículos pero se usan para los pedidos de producción.

### Recuento
<a id="counting" class="xliff"></a>

Los diarios de recuento le permiten corregir el inventario disponible actual que se registra para los artículos o grupos de artículos, y después registrar la cuenta física real, de manera que pueda realizar los ajustes necesarios para conciliar las diferencias. Puede asociar las directivas de recuento con los grupos de recuento para ayudar a agrupar los artículos que tienen diferentes características para poder incluir los artículos en un diario de recuento. Por ejemplo, puede configurar los grupos de recuento para contar artículos que tienen una frecuencia concreta o para contar artículos cuando las existencias se encuentren en un nivel determinado. Para obtener información sobre cómo definir los grupos de recuento, vea [Definición de procesos de recuento de inventario (guía de tareas)](http://ax.help.dynamics.com/en/wiki/define-inventory-counting-processes/).

### Recuento de etiquetas
<a id="tag-counting" class="xliff"></a>

Los diarios de recuento de etiquetas se usan para asignar una etiqueta numerada a un lote de recuento. La etiqueta debe contener un número de etiqueta, un número de artículo y una cantidad de artículo. Para ayudar a garantizar que una etiqueta se usa solo una vez y que todas las etiquetas se usarán, cada número de artículo debe tener el sistema único de etiquetas que tiene su propia secuencia numérica. Tres valores de estado se pueden definir para cada etiqueta:

-   **Usado**: el número de artículo se cuenta para esta etiqueta.
-   **Anulado**: el número de artículo se anula para esta etiqueta.
-   **Falta**: el número de artículo falta para esta etiqueta.

Cuando se registra un diario de recuento de etiquetas, se crea un diario de recuento nuevo basado en las líneas del diario de recuento de etiquetas. Para obtener más información acerca del recuento de etiquetas, vea [Recuento de etiquetas de inventario](inventory-tag-counting.md).

## Trabajo con diarios
<a id="working-with-journals" class="xliff"></a>
Sólo se puede tener acceso a una línea de diario un usuario por vez. Si varios usuarios deben tener acceso a los diarios al mismo tiempo para crear líneas de diario, esos usuarios deben seleccionar los diarios que no se usan actualmente para evitar que la información se sobrescriba. En las situaciones en las que varios departamentos usan el mismo tipo de diario, resulta útil crear varios nombres de diario (por ejemplo, uno por departamento). También puede servir de ayuda dividir los diarios para que cada rutina de registro se especifique en su propio diario de inventario único. Para las rutinas de registro asociadas a las transacciones de inventario, cree un diario para los ajustes periódicos del inventario y otro para el recuento de inventario.

## Registro de líneas de diario
<a id="posting-journal-lines" class="xliff"></a>
Puede registrar las líneas de diario que crea en cualquier momento hasta que haya bloqueado un artículo de transacciones adicionales. Los datos que introduzca en un diario permanecen en ese diario incluso si cierra el diario sin registrar las líneas.




