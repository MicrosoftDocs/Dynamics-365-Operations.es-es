---
title: Informe financiero de informe de ingresos
description: "En este artículo se describen los informes predeterminados para las declaraciones de ingresos. También se describen los componentes asociados con este informe."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 1773a36ab58f1b24c544c08dc1c48039513e28d9
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="income-statement-financial-report"></a>Informe financiero de informe de ingresos

[!include[banner](../includes/banner.md)]


En este artículo se describen los informes predeterminados para las declaraciones de ingresos. También se describen los componentes asociados con este informe. 

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

[Informes financieros](financial-reporting-getting-started.md)

[Ver informes financieros](view-financial-reports.md)

[Blog de informes financieros de Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)



