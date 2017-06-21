---
title: "Creación de un presupuesto desde cuentas de transacción y cuentas totales"
description: "Este artículo proporciona una visión general del proceso para crear presupuestos basados en cuentas totales. También explica cómo activar el control presupuestario para las cuentas totales, si se requiere control presupuestario."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BudgetControlConfiguration, BudgetPlanGenerate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13051
ms.assetid: fb1bb2d3-445c-402f-a9a3-aa6503eed78e
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 89ddb0f246eb1d874ff0f2b5305f30355905c45e
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="create-a-budget-from-transaction-accounts-and-total-accounts"></a>Creación de un presupuesto desde cuentas de transacción y cuentas totales

[!include[banner](../includes/banner.md)]


Este artículo proporciona una visión general del proceso para crear presupuestos basados en cuentas totales. También explica cómo activar el control presupuestario para las cuentas totales, si se requiere control presupuestario.

Los documentos de asiento de plan y registro presupuestario permiten presupuestar en las cuentas principales que tienen un tipo de cuenta principal **Total**. Los datos reales solo se pueden registrar en cuentas de transacciones principales. 

Para el proceso periódico **Generar plan presupuestario a partir de contabilidad general**, en la ficha **Origen** puede especificar el tipo de cuenta principal **Total** como criterio. En este caso, cada cuenta principal total se incluirá en el plan presupuestario de destino, y el importe será el importe total del intervalo de cuentas principales seleccionadas. 

Puede activar el control presupuestario para las cuentas principales del tipo **Total**. Esta función se puede usar con grupos presupuestarios. Para cada cuenta principal total, el presupuesto que se debe controlar para un grupo presupuestario debe crearse en la página **Configuración de control presupuestario**. Los criterios especificados deben incluir la cuenta principal total y el intervalo de cuentas. Para acelerar el proceso de creación de grupos presupuestarios, puede aprovecharse la entidad de datos de los grupos de control presupuestario. 

Cuando se utiliza un presupuesto en los informes, como por ejemplo en un informe financiero, el importe presupuestario de la cuenta total consta de los siguientes importes:

-   Los presupuestos creados a partir de cada cuenta contable de transacción en el intervalo de la cuenta total.
-   El importe presupuestario especificado directamente en la cuenta total.

Así pues, puede crear presupuestos independientes para las cuentas de transacción más significativas en el intervalo de la cuenta total y agregar el importe presupuestario disponible a la cuenta total.




