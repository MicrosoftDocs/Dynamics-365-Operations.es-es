---
title: Cálculos de L. MAT
description: La acumulación de costes y los cálculos del precio de venta se conocen como cálculos de lista de materiales (L. MAT) y se inician desde la página Cálculos. Este tema proporciona información sobre los cálculos de L.MAT.
author: AndersGirke
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcTable, CostingVersion, InventItemPrice, ProdSetupCostEstimation
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 273763
ms.assetid: c6fa3348-eafa-4847-9132-e65c5f55cbf4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: a718a2e825630ccfaa54ff9dece1d3d19d59018c
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3983949"
---
# <a name="bom-calculations"></a>Cálculos de L. MAT

[!include [banner](../includes/banner.md)]

La acumulación de costes y los cálculos del precio de venta se conocen como cálculos de lista de materiales (L. MAT) y se inician desde la página Cálculos. Este tema proporciona información sobre los cálculos de L.MAT.

La acumulación de costes y los cálculos del precio de venta se conocen como cálculos de lista de materiales (L. MAT) y se inician desde la página **Cálculos**. La página **Cálculos** se usa para realizar las siguientes tareas:

-   Calcular el coste de un artículo fabricado y generar un registro de coste de artículo asociado dentro de una versión de gestión de costes.
-   Calcular el precio de venta de un artículo fabricado y generar un registro de precio de venta de artículo asociado en una versión de gestión de costes.

La forma en que se utiliza la página **Cálculos** varía ligeramente, en función de cómo se inician los cálculos de L. MAT La forma de usar la página **Cálculos** también dependerá de si el cálculo de L. MAT. tiene una versión de gestión de costes estándar o planificados, y de las diversas directivas definidas en la versión de gestión de costes que se utilice en los cálculos de L. MAT. **Nota:** Una variación de la página **Cálculos** se utiliza en el contexto de un pedido de ventas, presupuesto de ventas o artículo de línea de pedido de servicio. Estos cálculos se conocen como cálculos de L. MAT específicos para pedidos. Un cálculo de L. MAT específico para pedido no genera un registro de coste de artículo dentro de una versión de gestión de costes. En su lugar, genera un registro de cálculo que aparece en la página **Detalles de cálculo de la L. MAT**. El registro de cálculo incluye un coste calculado y un precio de ventas calculado. La página **Cálculos** puede abrirse para un único artículo fabricado o para una versión de gestión de costes:

-   Para calcular los costes de un único artículo fabricado, inicie los cálculos de la L. MAT desde la página **Precio de artículo**. La página **Cálculos** hereda el identificador de artículo. La versión de gestión de costes, la versión de L. MAT, la versión de ruta, la cantidad de cálculo, la fecha de cálculo y el sitio deben ser especificados.
    -   De forma predeterminada, la versión de la L. MAT y la versión de ruta se establecen en las versiones activas del artículo, ubicación, fecha y cantidad de cálculo. Sin embargo, puede reemplazar los valores predeterminados con versiones aprobadas.
    -   De forma predeterminada, la cantidad de cálculo se establece en la cantidad de pedido estándar del artículo. Sin embargo, puede anular el valor predeterminado.
    -   La fecha del cálculo o el sitio pueden estar determinados por la versión de gestión de costes, o se pueden establecer valores especificados por el usuario cuando la fecha o el sitio no están determinados por la versión de gestión de costes. Una fecha de cálculo futuro determina cómo se usan los registros de costes pendientes. Los cálculos de L. MAT. usarán un registro de costes pendientes que tenga la fecha de inicio anterior más próxima a la fecha de cálculo o que tenga la misma fecha de cálculo.
-   Para calcular los costes de todos los artículos fabricados o los artículos seleccionados, o para actualizar los artículos en función de su ubicación, inicie los cálculos de la L. MAT en la página **Configuración de la versión de gestión de costes** o la página **Mantenimiento de la versión de gestión de costes**. La página **Cálculos** hereda la versión de gestión de costes.
    -   Para los cálculos, se asume que se utilizará la versión de L. MAT. y la versión de ruta activas de un artículo fabricado (y el sitio, la fecha y la cantidad relacionadas), salvo que un componente fabricado tenga una sublista de materiales o una subruta asociadas.
    -   Para los cálculos, se supone que la cantidad de pedido estándar se usa para los artículos fabricados. La cantidad de pedido estándar proporciona la base de cálculo de las cantidades de componentes determinando las versiones de L. MAT y de ruta relevantes (cuando usa L. MAT y rutas sensibles a la cantidad) y para amortizar costes constantes. Sin embargo, cuando un componente fabricado tiene un tipo de línea de L. MAT de **Producción** o **Proveedor**, o cuando usa un modo de expansión de "hacer para pedir" para los cálculos de L. MAT, esta suposición no se aplica, ya que las cantidades reflejan la cantidad de cálculo especificada.
    -   La fecha del cálculo o el sitio pueden estar determinados por la versión de gestión de costes, o se pueden establecer valores especificados por el usuario cuando la fecha o el sitio no están determinados por la versión de gestión de costes.

Las demás variantes en los cálculos de L. MAT reflejan el tipo y las restricciones de la versión de gestión de costes:

-   Los cálculos de L. MAT que usan costes estándar deben estar restringidos por directivas de versión de gestión de costes ya que dichas restricciones ayudan a garantizar que se usen principios de gestión de costes estándar. Los principios de gestión de costes requieren la aplicación de restricciones sobre el uso de los costes estándar de los artículos comprados, un modo de expansión de un único nivel y la inclusión de gastos varios en los costes unitarios.
-   Los cálculos de L. MAT que usan costes planificados no tienen que seguir principios estándar de gestión de costes. Estos cálculos de L. MAT pueden usar modos diferentes de expansión, orígenes alternativos de datos de coste para artículos comprados y una aplicación opcional de restricciones dentro de la versión de gestión de costes.

### <a name="bom-calculations-that-use-standard-costs"></a>Cálculos de L. MAT. que usan costes estándar

Las directivas de la versión de gestión de costes (para costes estándar) pueden exigir la aplicación de cinco directivas de cálculo de L. MAT. La opción **Restricción de registro** de la versión de gestión de costes exige una de estas directivas, en la que deben incluirse los gastos varios en el precio unitario. Los gastos varios para artículos comprados pueden especificarse manualmente, mientras que los gastos varios para artículos fabricados reflejan la amortización calculada de los costes constantes. La opción **Restricción de cálculo** de la versión de gestión de costes exige el cumplimiento de las otras cuatro directivas relativas a los cálculos de L. MAT:

-   El origen de las contribuciones del coste de los artículos comprados debe estar basado en costes estándar. Es decir, en los cálculos de L. MAT. deben utilizarse los registros de costes de los artículos en la versión de gestión de costes especificada o en la versión de reserva que incluye los costes estándar.
-   Para ayudar a garantizar la exactitud y coherencia de los cálculos de los costes estándar, el modo de expansión debe ser de nivel único.
-   Para ayudar a garantizar resultados coherentes cuando se calcula el precio de venta de los artículos, la configuración de ganancias es un requisito necesario. Se puede usar la configuración de ganancias y se pueden generar los registros de precio de ventas de los artículos solo si la versión de generación de costes permite contenido de precios de ventas.
-   Debe especificar un principio de reserva que puede establecerse en **Ninguno**, **Activo** (en el caso de registros de coste activo) o **Versión de gestión de costes** (en el caso de una versión de gestión de costes especificada).

### <a name="bom-calculations-that-use-planned-costs"></a>Cálculos de L. MAT. que usan costes planificados

Las directivas de la versión de gestión de costes (para costes planificados) pueden exigir opcionalmente la aplicación de cinco directivas de cálculo de L. MAT. Como alternativa, las directivas pueden proporcionar solo valores predeterminados. La opción **Restricción de registro** de la versión de gestión de costes determina si deberá cumplirse la directiva de cálculo de la L. MAT sobre gastos varios, o si esta actuará como valor predeterminado. Los gastos varios se pueden incluir opcionalmente en el precio unitario. La opción **Restricción de cálculo** de la versión de gestión de costes determina si deberán cumplirse las otras cuatro directivas aplicadas a los cálculos de L. MAT., o bien podrán utilizarse valores predeterminados:

-   El origen de las contribuciones de coste para un artículo comprado pueden ser los registros de costes de artículos dentro de una versión de gestión de costes. De manera alternativa, el origen se puede definir según el grupo de cálculo de L. MAT asignado al artículo. Por ejemplo, el grupo de cálculo de L. MAT. puede definir los acuerdos comerciales de precio de compra como origen de los datos de contribución de costes.
-   El modo de expansión puede ser de un solo nivel, de varios niveles, de fabricación sobre pedido o bien basarse en el artículo de línea de L. MAT. El modo de expansión para el tipo de línea de L. MAT. replica la lógica de cálculo de coste para las estimaciones de pedidos de producción.
-   La configuración de ganancias puede ser un requisito necesario o puede ser un valor predeterminado. Se puede usar la configuración de ganancias y se pueden generar los registros de precio de ventas de los artículos solo si la versión de generación de costes permite contenido de precios de ventas.
-   El principio de reserva puede ser un requisito necesario o puede ser un valor predeterminado. El principio de reserva puede establecerse en **Ninguno**, **Activo** (en el caso de registros de coste activo) o **Versión de gestión de costes** (en el caso de una versión de gestión de costes especificada).

Los cálculos de L. MAT. generan mensajes de advertencia y otros tipos de mensajes. Hay varias directivas de cálculo de L. MAT que determinan los tipos de mensajes. Las condiciones de aviso se definen en el grupo de cálculo de L. MAT que se asigna a los artículos. Sin embargo, puede reemplazar estas condiciones de aviso al iniciar un cálculo de L. MAT. Cuando se usa el principio de reserva, suele ser útil mostrar la reserva como un mensaje de información. Al intentar actualizar los costes calculados para artículos a los que les faltan registros de coste, también es útil que el mensaje de información identifique los mensajes que no se actualizaron.

## <a name="bom-calculations-that-use-the-fallback-principle"></a>Cálculos de L. MAT que utilizan el principio de reserva
En las situaciones que se presentan a continuación se muestran dos usos del principio de reserva:

-   **Método de dos versiones sobre las actualizaciones de costes estándar**: la versión de gestión de costes puede incluir los cambios incrementales en los costes estándar, como los registros de costes pendientes que representan nuevos artículos o cambios en los costes. En esta situación, el principio de reserva permite identificar el uso de los costes estándar activos que se incluyen en otras versiones de gestión de costes.
-   **Simulación del impacto de los cambios en los costes planificados**: la versión de gestión de costes puede incluir los cambios incrementales en los costes planificados a efectos de simulación. Esta versión de gestión de costes incluirá los registros de costes pendientes que representan los cambios simulados en los costes de artículos, las categorías de costes y las fórmulas de cálculo de costes indirectos. En esta situación, el principio de reserva permite identificar el uso de los costes estándar activos que se incluyen en otras versiones de gestión de costes.

## <a name="bom-calculation-of-a-suggested-sales-price"></a>Cálculo de L. MAT de un precio de venta sugerido
Cuando se usa un método de marcado según coste, el precio de venta del artículo que se calcula refleja el conjunto de porcentajes de establecimiento de ganancias que se especifica en el cálculo de L. MAT y los costes asociados a sus artículos componente, operaciones de enrutamiento y gastos generales aplicables. El marcado refleja los porcentajes de establecimiento de ganancias asignados a los grupos de costes y los grupos de costes asignados a los artículos, las categorías de coste de las operaciones de enrutamiento y las fórmulas de cálculo de coste indirecto para los gastos generales de fabricación. Los conjuntos de porcentajes de márgenes tienen las siguientes etiquetas: **Estándar**, **Ganancias 1**, **Ganancias 2** y **Ganancias 3**. En el conjunto Ganancias 1, por ejemplo, se puede definir un porcentaje de margen del 50 % para un grupo de costes asignado a material comprado y un porcentaje de margen del 80 % para un grupo de costes asignado a categorías de coste para las operaciones de enrutamiento. El contexto del cálculo de la L. MAT determina el modo en que se tratan los resultados del precio de venta calculado:

-   **Cálculo de la L. MAT para un artículo y versión de costes específica**: el cálculo de la L. MAT genera un registro de precio de venta pendiente en la versión de gestión de costes. Este registro de precio de venta ofrece el punto de partida para ver los detalles de cálculo (por ejemplo, en la página **Calcular coste del artículo**). El registro de precio de venta actúa principalmente como información de referencia y no se usa como base para un precio de ventas en los pedidos de ventas.
-   **Cálculo de L. MAT específico**: se usa una variación de la página **Cálculo de L. MAT** en el contexto de un pedido de venta, presupuesto de ventas o un artículo de línea de pedido de servicio. Un cálculo de L. MAT específico de pedido no genera un registro dentro de una versión de gestión de costes. En su lugar, genera un registro de cálculo que aparece en la página **Resultados del cálculo de la L. MAT**. Este registro de cálculo ofrece el punto de partida para ver los detalles de cálculo (por ejemplo, en la página **Calcular coste del artículo**). La información acerca de un registro de cálculo seleccionado puede transferirse al artículo de línea de origen. Por ejemplo, el precio de ventas calculado se puede transferir a un artículo de línea de pedido de ventas.

## <a name="order-specific-bom-calculations"></a>Cálculos de L. MAT específicos para pedidos
Un cálculo de la lista de materiales (L. MAT.) específico para pedidos representa una variación de un cálculo de L. MAT. para un artículo fabricado. El cálculo de L. MAT. específico del pedido se realiza en el contexto de un pedido de ventas, presupuesto de ventas o artículo de línea de pedido de servicio. Un cálculo MAT específico de pedido genera un registro de cálculo que aparece en la página **Resultados del cálculo de L. MAT** . El registro de cálculo incluye un peso calculado, un coste calculado que se basa en los registros de costes activos, así como en un precio de ventas calculado. El registro de cálculo que cada cálculo de L. MAT específico para pedidos genera en la página **Resultados del cálculo de L. MAT**, que se identifica de forma exclusiva por un número de cálculo. Los resultados de un registro de cálculo se pueden transferir, si lo desea, al artículo de línea de origen. Un cálculo de L. MAT. específico para pedidos se diferencia de dos formas de un cálculo de L. MAT. para un artículo fabricado:

-   Un cálculo de L. MAT específico para pedido no genera un registro de coste de artículo dentro de una versión de gestión de costes. Por lo tanto, las directivas de cálculo de L. MAT no se aplican cuando se crea un registro de costes de artículos, o cuando se sobrescribe un registro de coste.
-   Un cálculo de L. MAT. específico de pedido siempre usa los registros de coste activo para los componentes, las categorías de coste y las fórmulas de cálculo de costes indirectos.





