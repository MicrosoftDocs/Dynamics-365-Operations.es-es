---
title: "Gestionar actualizaciones de coste estándar"
description: "Las actualizaciones los datos de coste estándar se pueden gestionar con dos métodos diferentes: el método de una versión y el de dos versiones."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 69992
ms.assetid: 468de7af-c7b5-4345-bd5a-ba3aa5a900cc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d1d498b1a843415e106c90330dd661b78bc2865e
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017

---

# <a name="manage-standard-cost-updates"></a>Gestionar actualizaciones de coste estándar

[!include[banner](../includes/banner.md)]


Las actualizaciones los datos de coste estándar se pueden gestionar con dos métodos diferentes: el método de una versión y el de dos versiones. 

El método de una versión usa una única versión de gestión de costes que contiene todos los registros de costes. Estos registros incluyen los costes originales y todas las actualizaciones de costes.
El método de dos versiones emplea una versión que contiene los registros de los costes originales y otra que contiene los registros de todas las actualizaciones de coste. Una ventaja principal del método de dos versiones es que se hace una delineación y un seguimiento claros de las actualizaciones de coste en una versión de gestión de costes independiente, sin afectar a la versión de gestión de costes original. El método de dos versiones se puede usar para identificar varias actualizaciones incrementales con diferentes versiones de gestión de costes que contienen los registros de coste incremental. **Ejemplo** En el ejemplo siguiente se muestra cómo se pueden usar los métodos de una versión y de dos versiones para actualizar los costes estándar en un entorno de fabricación. como las actualizaciones que reflejan los nuevos artículos o correcciones de errores. Supongamos que una versión de gestión de costes representa los costes estándares del año actual. El identificador de la versión es 2016-STD. La versión 2016-STD contiene los costes activos actuales de todos los artículos. Además, contiene todas las categorías de costes relacionadas con el enrutamiento y las fórmulas de cálculo de gastos generales conocidas al principio del año 2016. 2016-STD es la versión de gestión de costes original.
-   **Método de una versión de actualización de datos de costes**: en el método de una versión, la versión de gestión de costes original 2016-STD contiene todos los registros de costes. Las actualizaciones de costes se registran en 2016-STD y se establecen en estado "Pendiente". Los costes pendientes se pueden especificar manualmente para los nuevos artículos comprados, o pueden calcularse para que un artículo fabricado refleje correcciones aplicadas. Cuando se usa el método de una versión, los cálculos de lista de materiales no requieren un origen de datos de reserva, ya que todos los costes activos están incluidos en la versión de gestión de costes. Después de activar los costes pendientes, la versión de gestión de costes original 2016-STD contendrá de nuevo todos los costes actualmente activos.
-   **Método de dos versiones de actualización de datos de costes**: el método de dos versiones requiere una versión de gestión de costes adicional que contenga sólo las actualizaciones de costes. El identificador de esta versión es 2016-STD-CHANGES. Las actualizaciones de costes se registran en 2016-STD-CHANGES y se establecen en estado "Pendiente". Con el método de dos versiones, los cálculos de lista de materiales de costes pendientes para artículos fabricados requieren un origen de datos de reserva. Esto se debe a que la versión de gestión de costes adicional 2016-STD-CHANGES sólo contiene un subconjunto de datos de coste. La reserva se puede expresar como los costes activos o la versión de gestión de costes 2016-STD, ya que ambos identifican el origen de los datos de coste si no se incluye en 2016-STD-CHANGES. Después de activar los costes pendientes, la versión de gestión de costes 2016-STD-CHANGES contendrá los costes actuales activos que reflejan las actualizaciones, mientras que la versión de gestión de costes original 2016-STD no se verá afectada. Si usa el método de dos versiones, es necesario configurar directivas de bloqueos para la versión de gestión de costes original a fin de impedir actualizaciones. También se deben configurar directivas de bloqueos idénticas para la versión de gestión de costes adicional, con la excepción de la fecha de inicio especificada y el uso selectivo de directivas de bloqueos para permitir actualizaciones. La fecha de inicio especificada debería actualizarse con cada lote de cambios para reflejar la fecha de activación programada.

En este ejemplo se usa una versión de gestión de costes adicional para administrar las actualizaciones del año 2016. Es posible usar más de una versión de gestión de costes adicional como, por ejemplo, una versión independiente para cada lote de actualizaciones. Cuando se usa más de una gestión de costes adicional, la reserva se debe expresar como costes activos, ya que los costes activos abarcan varias versiones de gestión de costes.






