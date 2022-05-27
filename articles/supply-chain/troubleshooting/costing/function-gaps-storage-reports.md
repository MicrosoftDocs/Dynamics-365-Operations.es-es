---
title: Brechas funcionales entre el valor de inventario / informes de antigüedad y sus versiones de almacenamiento
description: Brechas funcionales entre el valor de inventario / informes de antigüedad y sus versiones de almacenamiento
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f74389648034bf036ce48ac84b3421a8a340f105
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686664"
---
# <a name="functional-gaps-between-inventory-valueaging-reports-and-their-storage-versions"></a>Brechas funcionales entre el valor de inventario / informes de antigüedad y sus versiones de almacenamiento

Las funciones [Almacenamiento de informes de antigüedad de inventario](/dynamics365/supply-chain/cost-management/inventory-aging-report-storage) e [Informe de almacenamiento de valor de inventario](/dynamics365/supply-chain/cost-management/inventory-value-report-storage) permiten que Supply Chain Management muestre grandes volúmenes de transacciones de inventario. En cada caso, los resultados del informe se guardan para su exploración y exportación, a diferencia de las versiones sin almacenamiento de estos informes. Sin embargo, algunas funciones que existen en las versiones sin almacenamiento de estos informes no existen en las versiones de almacenamiento. Las siguientes subsecciones resumen las diferencias y proporcionan soluciones.

## <a name="storage-reports-dont-include-subtotals-even-if-they-are-enabled-in-the-report-layout"></a>Los informes de almacenamiento no incluyen subtotales, incluso si están habilitados en el diseño del informe

Los subtotales pueden causar problemas cuando se exporta el resultado, especialmente si los usuarios cambian la secuencia de registro.

Para comprobar los subtotales, puede exportar el resultado a Microsoft Excel. Alternativamente, si desea verificar los subtotales dentro de Supply Chain Management, use [Gestión de funciones](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) para habilitar las funciones *Nuevo control de cuadrícula* y *Agrupación en cuadrículas*, que proporcionan una forma mucho más flexible de ver el subtotal de cualquier grupo por columna. Para obtener más información, consulte [Funcionalidades de cuadrícula](/dynamics365/fin-ops-core/fin-ops/get-started/grid-capabilities).

## <a name="inventory-value-storage-report-doesnt-support-ledger-account-information"></a>El informe de almacenamiento del valor de inventario no admite la información de la cuenta del libro mayor

Puede ejecutar el balance de prueba para obtener el saldo de las cuentas de inventario y compararlo con el informe **Almacenamiento de valor de inventario**.
