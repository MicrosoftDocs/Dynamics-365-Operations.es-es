---
title: Solucionar problemas de la gestión de costes
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con gestión de costes.
author: riluan
manager: tfehr
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: e84bb167395c06295b0e8ef8b9fd98aa4bc0cc14
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "4437298"
---
# <a name="troubleshoot-cost-management"></a>Solucionar problemas de la gestión de costes

Este tema describe cómo solucionar problemas que pueden surgir al trabajar con gestión de costes.

## <a name="functional-gaps-between-the-inventory-valueaging-reports-and-their-storage-versions"></a>Brechas funcionales entre el valor de inventario / informes de antigüedad y sus versiones de almacenamiento

Las funciones [Almacenamiento de informes de antigüedad de inventario](inventory-aging-report-storage.md) e [Informe de almacenamiento de valor de inventario](inventory-value-report-storage.md) permiten que Supply Chain Management muestre grandes volúmenes de transacciones de inventario. En cada caso, los resultados del informe se guardan para su exploración y exportación, a diferencia de las versiones sin almacenamiento de estos informes. Sin embargo, algunas funciones que existen en las versiones sin almacenamiento de estos informes no existen en las versiones de almacenamiento. Las siguientes subsecciones resumen las diferencias y proporcionan soluciones.

### <a name="storage-reports-dont-include-subtotals-even-if-they-are-enabled-in-the-report-layout"></a>Los informes de almacenamiento no incluyen subtotales, incluso si están habilitados en el diseño del informe

Los subtotales pueden causar problemas cuando se exporta el resultado, especialmente si los usuarios cambian la secuencia de registro.

Para comprobar los subtotales, puede exportar el resultado a Microsoft Excel. Alternativamente, si desea verificar los subtotales dentro de Supply Chain Management, use [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para habilitar las funciones *Nuevo control de cuadrícula* y *(Vista previa) Agrupación en cuadrículas*, que proporcionan una forma mucho más flexible de ver el subtotal de cualquier grupo por columna. Para obtener más información, consulte [Funcionalidades de cuadrícula](../../fin-ops-core/fin-ops/get-started/grid-capabilities.md).

### <a name="inventory-value-storage-report-doesnt-support-ledger-account-information"></a>El informe de almacenamiento del valor de inventario no admite la información de la cuenta del libro mayor

Puede ejecutar el balance de prueba para obtener el saldo de las cuentas de inventario y compararlo con el informe **Almacenamiento de valor de inventario**.

## <a name="warnings-or-errors-are-shown-when-changing-a-ledger-period-status-without-closing-inventory"></a>Se muestran advertencias o errores cuando se cambia el estado de un período de contabilidad sin cerrar el inventario

Microsoft introdujo las siguientes validaciones para evitar problemas causados por un proceso de fin de período incorrecto en torno al cálculo de costos. Si encuentra alguno de los siguientes mensajes de error, consulte [KB 4561987](https://fix.lcs.dynamics.com/Issue/Details?kb=4561987&bugId=445351&dbType=3&qc=f514f2adcddcddceec43af58c26ae8a9020effdc7cdfe085d9d0deeb8cc7b6a3) para obtener más información sobre cómo resolver estos problemas.

- Está a punto de ejecutar un nuevo cálculo con una fecha %1 (10-02-2019). El último recálculo registrado se ejecutó en un período anterior con una fecha %2 (20-01-2019). No se ha registrado ninguna ejecución de cierre de inventario con fecha %3 (31-01-2019) coincidentese con el final del período. Recuerde ejecutar un cierre de inventario a partir del %3 (31-01-2019) que coincida con el final del período. La valoración de los inventarios, el costo de los bienes vendidos y las variaciones pueden no ser correctos en el libro mayor auxiliar o en el libro mayor general hasta que se haya ejecutado.

- Está a punto de cambiar el estado del período del libro mayor %1 a %2. No se ha registrado ninguna ejecución de cierre de inventario con fecha %3 coincidente con el final del período. Ejecute un cierre de inventario a partir del %3 que coincida con el final del período antes de cambiar el estado. La valoración de los inventarios, el costo de los bienes vendidos y las variaciones pueden no ser correctos en el libro mayor auxiliar o en el libro mayor general hasta que se haya ejecutado. Reportado desde la entidad legal %4. Por ahora, es informativa, pero deberá realizar dicha acción en el futuro.

- La estructura de la cuenta %1 se ha cambiado. Una o más cuentas principales %2 ya no existen. Estas cuentas principales son requeridas por %3 con fecha %4. Agregue estas cuentas principales a la estructura de cuenta %1 antes de que pueda reanudar el trabajo %3. Por ahora, es informativa, pero deberá realizar dicha acción en el futuro.

- Está a punto de ejecutar un cierre de inventario con fecha %1 (31-01-2019). No se ha registrado ningún cálculo de contabilización previa de los costes con fecha %2 (31-01-2019) coincidente con el final del período. Recuerde ejecutar un cálculo de contabilización previa de los costes con fecha %3 (31-01-2019) coincidente con el final del período. La valoración de los inventarios, el costo de los bienes vendidos y las variaciones pueden no ser correctos en el libro mayor auxiliar o en el libro mayor general hasta que se haya ejecutado.

- Está a punto de ejecutar un cálculo de costos retroactivo con fecha %1 (28-02-2019). El último cálculo de contabilización previa de los costes registrado se ejecutó en un período anterior con fecha %2 (31-01-2019). No se ha registrado ninguna ejecución de cierre de inventario con fecha %3 (31-01-2019) coincidente con un final de período.
Recuerde ejecutar un cierre de inventario a partir del %3 (31-01-2019) que coincida con un final de período. La valoración de los inventarios, el costo de los bienes vendidos y las variaciones pueden no ser correctos en el libro mayor auxiliar o en el libro mayor general hasta que se haya ejecutado el cierre de inventario.

## <a name="inventory-aging-report-discrepancies"></a>Discrepancias de informe de vencimiento de inventario

El **Informe de antigüedad de inventario** muestra diferentes valores cuando se ve en diferentes dimensiones de almacenamiento (como sitio o almacén). Para obtener más información sobre la lógica de informes, consulte [Ejemplos y lógica de informes de antigüedad de inventario](inventory-aging-report.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]