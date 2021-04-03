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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: dceaca64132857d796a16c2450a372ba05712cf5
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262462"
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

- Está a punto de ejecutar un nuevo cálculo con una fecha %1 (10-02-2019). El último recálculo registrado se ejecutó en un período anterior con una fecha %2 (20-01-2019). No se ha registrado ninguna ejecución de cierre de inventario con fecha %3 (31-01-2019) coincidentese con el final del período. Recuerde ejecutar un cierre de inventario a partir del %3 (31-01-2019) que coincida con el final del período. La valoración de los inventarios, el coste de los bienes vendidos, y las variaciones pueden no ser correctos en el libro mayor auxiliar o en el libro mayor general hasta que se haya ejecutado.

- Está a punto de cambiar el estado del período del libro mayor %1 a %2. No se ha registrado ninguna ejecución de cierre de inventario con fecha %3 coincidente con el final del período. Ejecute un cierre de inventario a partir del %3 que coincida con el final del período antes de cambiar el estado. La valoración de los inventarios, el coste de los bienes vendidos, y las variaciones pueden no ser correctos en el libro mayor auxiliar o en el libro mayor general hasta que se haya ejecutado. Reportado desde la entidad legal %4. Por ahora, es informativa, pero deberá realizar dicha acción en el futuro.

- La estructura de la cuenta %1 se ha cambiado. Una o más cuentas principales %2 ya no existen. Estas cuentas principales son requeridas por %3 con fecha %4. Agregue estas cuentas principales a la estructura de cuenta %1 antes de que pueda reanudar el trabajo %3. Por ahora, es informativa, pero deberá realizar dicha acción en el futuro.

- Está a punto de ejecutar un cierre de inventario con fecha %1 (31-01-2019). No se ha registrado ningún cálculo de contabilización previa de los costes con fecha %2 (31-01-2019) coincidente con el final del período. Recuerde ejecutar un cálculo de contabilización previa de los costes con fecha %3 (31-01-2019) coincidente con el final del período. La valoración de los inventarios, el coste de los bienes vendidos, y las variaciones pueden no ser correctos en el libro mayor auxiliar o en el libro mayor general hasta que se haya ejecutado.

- Está a punto de ejecutar un cálculo de costos retroactivo con fecha %1 (28-02-2019). El último cálculo de contabilización previa de los costes registrado se ejecutó en un período anterior con fecha %2 (31-01-2019). No se ha registrado ninguna ejecución de cierre de inventario con fecha %3 (31-01-2019) coincidente con un final de período.
Recuerde ejecutar un cierre de inventario a partir del %3 (31-01-2019) que coincida con un final de período. La valoración de los inventarios, el costo de los bienes vendidos y las variaciones pueden no ser correctos en el libro mayor auxiliar o en el libro mayor general hasta que se haya ejecutado el cierre de inventario.

## <a name="inventory-aging-report-discrepancies"></a>Discrepancias de informe de vencimiento de inventario

El **Informe de antigüedad de inventario** muestra diferentes valores cuando se ve en diferentes dimensiones de almacenamiento (como sitio o almacén). Para obtener más información sobre la lógica de informes, consulte [Ejemplos y lógica de informes de antigüedad de inventario](inventory-aging-report.md).

## <a name="an-update-conflict-occurs-when-the-inventory-valuation-method-is-either-standard-cost-or-moving-average"></a>Se produce un conflicto de actualización cuando el método de valoración de inventario es Coste estándar o Media móvil

Cuando registra documentos como diarios de inventario, facturas de pedidos de compra o facturas de pedidos de venta en paralelo para mejorar la escalabilidad y el rendimiento, es posible que reciba un mensaje de error sobre un conflicto de actualización y que algunos de los documentos no se registren. Este problema puede producirse cuando el método de valoración de inventario es *Coste estándar* o *Media móvil*. Ambos métodos son métodos de gestión de costes perpetuos. Es decir, el coste final se determina en el momento de la publicación.

Si está usando el método *Media móvil*, el mensaje de error se parece a este ejemplo:

> No se espera el valor de inventario xx.xx después del cálculo de gasto proporcional

Si está usando el método *Coste estándar*, el mensaje de error se parece a este ejemplo:

> El coste estándar no coincide con el valor del inventario financiero después de la actualización. Valor = xx.xx, Cant. = yy.yy, Coste estándar = zz.zz

Hasta que Microsoft publique una solución para solucionar el problema, considere usar las siguientes soluciones para ayudar a evitar o reducir estos errores:

- Vuelva a publicar los documentos fallidos.
- Cree documentos que tengan menos líneas.
- Evite valores decimales en el coste estándar. Intente definir el coste estándar para que el campo **Cantidad de precio** esté configurado en *1*. Si debe especificar un valor de **Cantidad de precio** que sea mayor que *1*, trate de minimizar el número de decimales en el coste estándar unitario. (Idealmente, debería haber menos de dos cifras decimales). Por ejemplo, evite definir configuraciones de coste estándar como **Precio** = *10* y **Cantidad de precio** = *3*, porque producirán un coste estándar unitario de 3,333333 (donde el valor decimal se repite).
- En la mayoría de los documentos, evite tener varias líneas que contengan la misma combinación de dimensiones de inventario financiero y de producto.
- Reduzca el grado de paralelización. (En este caso, su sistema puede volverse más rápido, porque se producen menos conflictos de actualización y reintentos).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]