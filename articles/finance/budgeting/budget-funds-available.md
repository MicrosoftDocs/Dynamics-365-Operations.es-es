---
title: Fondos presupuestarios disponibles
description: Este tema presenta la característica de fondos presupuestarios disponibles y proporciona información para ayudarle a configurar el control presupuestario para optimizar la administración de los recursos financieros de su organización.
author: RyanCCarlson2
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetControlConfiguration
audience: Application User
ms.reviewer: kfend
ms.custom:
- "60493"
- intro-internal
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2021-11-28
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: 1e7b2bf7ef7bd1bca6db27371f87dfddcdceef89
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8710260"
---
# <a name="budget-funds-available"></a>Fondos presupuestarios disponibles

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tema presenta la característica de fondos presupuestarios disponibles y proporciona información para ayudarle a configurar el control presupuestario para optimizar la administración de los recursos financieros de su organización.

## <a name="enhanced-calculation-feature-for-budget-funds-available"></a>Característica de cálculo mejorada para los fondos presupuestarios disponibles

La característica **Realizar un seguimiento de los montos en el cálculo de los fondos presupuestarios disponibles** le permite realizar un seguimiento de las tablas de control presupuestario subyacentes para los tipos y estados de documentos, según la configuración en la página **Definición de parámetros de control presupuestario**.

Algunas opciones de configuración de control presupuestario deben tener configuraciones específicas para que la característica funcione correctamente. Esas opciones se seleccionan o borran en la pestaña **Fondos presupuestarios disponibles** de la página **Definición de parámetros de control presupuestario**. La siguiente tabla muestra la configuración necesaria para la característica de fondos presupuestarios disponibles.

| Si se selecciona esta opción | Esta opción también debe seleccionarse |
| ------------------------- | -------------------------------- |
| Reservas de presupuesto para pre-reservas de gasto | Reservas presupuestarias para reservas de gasto *y* gastos reales |
| Reservas de presupuesto para reservas de gasto | Gastos reales |
| Reservas presupuestarias para reservas de gasto con documentos del tipo de solicitud de compra | Reservas de presupuesto para pre-reservas de gasto |

Esta característica solo afecta a los documentos nuevos. Se continuará haciendo un seguimiento de los importes de los documentos existentes y se mostrarán en la consulta de estadísticas de control presupuestario hasta que se cambie una configuración de fondos presupuestarios disponibles y se active la nueva configuración de control presupuestario. En ese momento, los datos de seguimiento presupuestario se eliminarán para los documentos que se eliminaron del cálculo de fondos presupuestarios disponibles.

Le recomendamos que deje la opción **Gastos reales no registrados** despejada. Si se selecciona, se realizará un cálculo de control presupuestario que requiere mucho tiempo en documentos no registrados, como facturas de proveedores pendientes.
