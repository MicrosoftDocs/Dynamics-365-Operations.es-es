---
title: Gestionar actualizaciones de coste estándar
description: 'Las actualizaciones los datos de coste estándar se pueden gestionar con dos métodos diferentes: el método de una versión o el de dos versiones.'
author: AndersGirke
manager: tfehr
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 69992
ms.assetid: 468de7af-c7b5-4345-bd5a-ba3aa5a900cc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 166d12d707deabc59f7613a5016851b30fcc42d8
ms.sourcegitcommit: 41baf654a2553cfe5c715feb9cc03e48cfc12598
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2021
ms.locfileid: "5024679"
---
# <a name="manage-standard-cost-updates"></a>Gestionar actualizaciones de coste estándar

[!include [banner](../includes/banner.md)]

Las actualizaciones los datos de coste estándar se pueden gestionar con dos métodos diferentes: el método de una versión o el de dos versiones.

El método de una versión usa una única versión de gestión de costes que contiene todos los registros de costes. Estos registros incluyen los costes originales y todas las actualizaciones de costes.

El método de dos versiones emplea una versión que contiene los registros de los costes originales y otra que contiene los registros de todas las actualizaciones de coste. Una ventaja principal del método de dos versiones es que se hace una delineación y un seguimiento claros de las actualizaciones de coste en una versión de gestión de costes independiente, sin afectar a la versión de gestión de costes original. El método de dos versiones se puede usar para identificar varias actualizaciones incrementales con diferentes versiones de gestión de costes que contienen los registros de coste incremental.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo se pueden usar los métodos de una versión y de dos versiones para actualizar los costes estándar en un entorno de fabricación, como las actualizaciones que reflejan los nuevos artículos o correcciones de errores. Supongamos que una versión de gestión de costes representa los costes estándares del año actual. El identificador de la versión es 2020-STD. La versión 2020-STD contiene los costes activos actuales de todos los artículos. Además, contiene todas las categorías de costes relacionadas con el enrutamiento y las fórmulas de cálculo de gastos generales conocidas al principio del año 2020. 2020-STD es la versión de gestión de costes original.

- **Método de una versión de actualización de datos de costes**: en el método de una versión, la versión de gestión de costes original 2020-STD contiene todos los registros de costes. Las actualizaciones de costes se registran en 2020-STD y se establecen en estado Pendiente. Los costes pendientes se pueden especificar manualmente para nuevos artículos comprados, o puede calcularse para un artículo fabricado para reflejar correcciones. Cuando se usa el método de una versión, los cálculos de L. MAT no requieren un origen de datos de reserva, ya que todos los costes activos se incluyen en la versión de gestión de costes. Después de activar los costes pendientes, la versión de gestión de costes original 2020-STD contendrá de nuevo todos los costes actualmente activos.
- **Método de dos versiones de actualización de datos de costes**: el método de dos versiones requiere una versión de gestión de costes adicional que contenga sólo las actualizaciones de costes. El identificador de esta versión es 2020-STD-CHANGES. Las actualizaciones de coste se registran en 2020-STD-CHANGES y su estado se define como Pendiente. Con el enfoque de dos versiones, los cálculos de L. MAT de costes pendientes para artículos fabricados requieren un origen de datos de reserva. Esto se debe a que la versión de gestión de costes adicional 2020-STD-CHANGES sólo contiene un subconjunto de datos de coste. La reserva se puede expresar como los costes activos o la versión de gestión de costes 2020-STD, ya que ambos identifican el origen de los datos de coste si no se incluye en 2020-STD-CHANGES. Después de activar los costes pendientes, la versión de gestión de costes 2020-STD-CHANGES contendrá los costes actuales activos que reflejan las actualizaciones, mientras que la versión de gestión de costes original 2020-STD no se verá afectada. Si usa el método de dos versiones, es necesario configurar directivas de bloqueos para la versión de gestión de costes original a fin de impedir actualizaciones. También se deben configurar directivas de bloqueos idénticas para la versión de gestión de costes adicional, con la excepción de la fecha de inicio especificada y el uso selectivo de directivas de bloqueos para permitir actualizaciones. La fecha de inicio especificada debería actualizarse con cada lote de cambios para reflejar la fecha de activación programada.

En este ejemplo se usa una versión de gestión de costes adicional para administrar las actualizaciones del año 2020. Es posible usar más de una versión de gestión de costes adicional como, por ejemplo, una versión independiente para cada lote de actualizaciones. Cuando se usa más de una gestión de costes adicional, la reserva se debe expresar como costes activos, ya que los costes activos abarcan varias versiones de gestión de costes.

## <a name="financial-dimensions-for-the-standard-cost-revaluation"></a>Dimensiones financieras de la revalorización de costes estándar.

La activación de un nuevo precio estándar normalmente revalorizará el valor de inventario disponible mediante transacciones de revalorización de costos estándar. Por lo general, las dimensiones financieras del artículo se contabilizan en las transacciones. Sin embargo, si desea controlar si se registran las dimensiones financieras y cómo, utilice la [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para activar la función llamada *Opciones de dimensiones financieras predeterminadas para la revalorización del costo estándar de inventario*. Después de habilitar esta función, vaya a **Gestión de costes > Configuración de políticas de contabilidad de inventario > Parámetros** y configure la nueva lista desplegable de **Origen de la dimensión financiera** a uno de los siguientes valores:

- **Ninguno**: no hay dimensiones financieras registradas en las transacciones de revalorización. Si su estructura contable incluye una dimensión financiera, el proceso de revalorización se seguirá ejecutando, pero creará entradas de contabilidad sin ninguna dimensión financiera. En este caso, los usuarios recibirán primero un mensaje de advertencia, para que puedan cancelar la revalorización si es necesario.
- **Tabla**: las dimensiones financieras del artículo se contabilizan en las transacciones de revalorización. Esta es la configuración predeterminada y es consistente con el comportamiento del sistema original sin activar la función *Opciones de dimensiones financieras predeterminadas para la revalorización del costo estándar de inventario*.
- **Registro**: las dimensiones financieras de la transacción que se está revalorizando se registran en las transacciones de revalorización. De forma predeterminada, las dimensiones financieras de la cuenta de inventario de la transacción original se utilizarán tanto para la cuenta de inventario como para la cuenta de revalorización.
