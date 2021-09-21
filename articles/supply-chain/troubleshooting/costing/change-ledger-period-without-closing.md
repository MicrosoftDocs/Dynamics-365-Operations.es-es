---
title: Advertencias o errores cuando se cambia el estado de un período de contabilidad sin cerrar el inventario
description: Advertencias o errores cuando se cambia el estado de un período de contabilidad sin cerrar el inventario
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 05851753e29da75f014d2cc77e2b8df259620eee
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477510"
---
# <a name="warnings-or-errors-on-changing-ledger-period-status-without-closing-inventory"></a>Advertencias o errores cuando se cambia el estado de un período de contabilidad sin cerrar el inventario

Microsoft introdujo las siguientes validaciones para evitar problemas causados por un proceso de fin de período incorrecto en torno al cálculo de costos. Si encuentra alguno de los siguientes mensajes de error, consulte [KB 4561987](https://fix.lcs.dynamics.com/Issue/Details?kb=4561987&bugId=445351&dbType=3&qc=f514f2adcddcddceec43af58c26ae8a9020effdc7cdfe085d9d0deeb8cc7b6a3) para obtener más información sobre cómo resolver estos problemas.

- Está a punto de ejecutar un nuevo cálculo con una fecha %1 (10-02-2019). El último recálculo registrado se ejecutó en un período anterior con una fecha %2 (20-01-2019). No se ha registrado ninguna ejecución de cierre de inventario con fecha %3 (31-01-2019) coincidentese con el final del período. Recuerde ejecutar un cierre de inventario a partir del %3 (31-01-2019) que coincida con el final del período. La valoración de los inventarios, el coste de los bienes vendidos, y las variaciones pueden no ser correctos en el libro mayor auxiliar o en el libro mayor general hasta que se haya ejecutado.

- Está a punto de cambiar el estado del período del libro mayor %1 a %2. No se ha registrado ninguna ejecución de cierre de inventario con fecha %3 coincidente con el final del período. Ejecute un cierre de inventario a partir del %3 que coincida con el final del período antes de cambiar el estado. La valoración de los inventarios, el coste de los bienes vendidos, y las variaciones pueden no ser correctos en el libro mayor auxiliar o en el libro mayor general hasta que se haya ejecutado. Reportado desde la entidad legal %4. Por ahora, es informativa, pero deberá realizar dicha acción en el futuro.

- La estructura de la cuenta %1 se ha cambiado. Una o más cuentas principales %2 ya no existen. Estas cuentas principales son requeridas por %3 con fecha %4. Agregue estas cuentas principales a la estructura de cuenta %1 antes de que pueda reanudar el trabajo %3. Por ahora, es informativa, pero deberá realizar dicha acción en el futuro.

- Está a punto de ejecutar un cierre de inventario con fecha %1 (31-01-2019). No se ha registrado ningún cálculo de contabilización previa de los costes con fecha %2 (31-01-2019) coincidente con el final del período. Recuerde ejecutar un cálculo de contabilización previa de los costes con fecha %3 (31-01-2019) coincidente con el final del período. La valoración de los inventarios, el coste de los bienes vendidos, y las variaciones pueden no ser correctos en el libro mayor auxiliar o en el libro mayor general hasta que se haya ejecutado.

- Está a punto de ejecutar un cálculo de costos retroactivo con fecha %1 (28-02-2019). El último cálculo de contabilización previa de los costes registrado se ejecutó en un período anterior con fecha %2 (31-01-2019). No se ha registrado ninguna ejecución de cierre de inventario con fecha %3 (31-01-2019) coincidente con un final de período.

Recuerde ejecutar un cierre de inventario a partir del %3 (31-01-2019) que coincida con un final de período. La valoración de los inventarios, el costo de los bienes vendidos y las variaciones pueden no ser correctos en el libro mayor auxiliar o en el libro mayor general hasta que se haya ejecutado el cierre de inventario.