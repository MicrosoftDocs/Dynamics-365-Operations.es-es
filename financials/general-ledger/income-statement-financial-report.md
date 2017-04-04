---
title: Informe financiero de informe de ingresos
description: "Este artículo describe el informe predeterminado para las cuentas de resultados. También se explica los bloques de creación que están asociados a este informe."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 12294
ms.assetid: 30820be0-d943-4f8b-8c25-6414ec393b3d
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 8dd289c1943afb55373ba682afcc3cd107cb67a7
ms.lasthandoff: 03/31/2017


---

# <a name="income-statement-financial-report"></a>Informe financiero de informe de ingresos

Este artículo describe el informe predeterminado para las cuentas de resultados. También se explica los bloques de creación que están asociados a este informe. 

<a name="default-income-statement-report"></a>Informe de ingresos predeterminado
-------------------------------

| Informe predeterminado             | Qué hace                                                                                              |
|----------------------------|-----------------------------------------------------------------------------------------------------------|
| Informe de ingresos – predeterminado | Ofrece una vista de la rentabilidad de la organización para el período actual y también para el ejercicio hasta la fecha. |

## <a name="building-blocks"></a>Bloques de creación
El informe financiero del informe de ingresos usa los siguientes bloques de creación.

| Informe predeterminado             | Definición de filas                     | Definición de columnas          |
|----------------------------|------------------------------------|----------------------------|
| Informe de ingresos - predeterminado | Resumen de informe de ingresos - predeterminado | Periódico y anual - predeterminado |

### <a name="row-definition"></a>Definición de filas

La definición de filas, Resumen de informe de ingresos - predeterminado, contiene una sección para cada parte de un extracto tradicional de ingresos. La dimensión Categoría de cuenta principal se usa para crear esta definición de filas. Por tanto, cualquier persona puede generar el informe sin tener que realizar ninguna modificación.

### <a name="column-definition"></a>Definición de columnas

Las definiciones de columnas contienen diversos tipos de columnas para proporcionar distintos niveles de detalle y datos financieros.

-   **Periódico y anual - tipos de columna predeterminadas:**
    -   **DESC** : la descripción de la definición de filas.
    -   **FD**: datos financieros para el período actual
    -   **FD**: datos financieros para el año hasta la fecha

 

<a name="see-also"></a>Consulte también
--------

[Financial reporting](financial-reporting-getting-started.md)

[View financial reports](view-financial-reports.md)

[] Blog financiero de Reportign de Dynamics (http://blogs.msdn.com/b/dynamics_financial_reporting/)


