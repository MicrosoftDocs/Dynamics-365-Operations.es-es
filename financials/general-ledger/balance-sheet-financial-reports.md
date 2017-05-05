---
title: "Informes financieros de balance de situación"
description: "En este artículo se describen los informes predeterminados para los balances de situación. También se describen los componentes de estos informes."
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
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 664d32c2bfecb50e24fd48a66ab5b34cef6c09a3
ms.lasthandoff: 03/31/2017


---

# <a name="balance-sheet-financial-reports"></a>Informes financieros de balance de situación

[!include[banner](../includes/banner.md)]


En este artículo se describen los informes predeterminados para los balances de situación. También se describen los componentes de estos informes. 

<a name="default-balance-sheet-reports"></a>Informes de balance de situación predeterminados
-----------------------------

Hay dos informes de balance de situación predeterminados. En un informe, se apilan las secciones. En el otro, las secciones se encuentran en paralelo.

| Informe predeterminado                       | Qué hace                                                                                                                           |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|
| Balance de situación - predeterminado              | Ofrece una visión de la posición financiera de la organización para el año.                                                                 |
| Balance de situación en paralelo – predeterminado | Ofrece una visión de la posición financiera de la organización para el año. Los activos y el pasivo y los recursos propios de los accionistas se encuentran en paralelo. |

## <a name="building-blocks"></a>Bloques de creación
Los informes financieros del balance de situación usan los siguientes bloques de creación.

| Informe predeterminado                       | Definición de filas                       | Definición de columnas             |
|--------------------------------------|--------------------------------------|-------------------------------|
| Balance de situación - predeterminado              | Balance de situación - predeterminado              | Anual y desviación - predeterminado    |
| Balance de situación en paralelo – predeterminado | Balance de situación en paralelo – predeterminado | Columna de año hasta la fecha - predeterminado |

### <a name="row-definition"></a>Definición de filas

Las definiciones de filas para ambos informes de balance de situación contienen secciones para cada parte de un balance de situación tradicional. El informe en paralelo incluye un salto de la columna, de modo que el pasivo y los recursos propios del propietario aparezcan junto a los activos. La dimensión Categoría de cuenta principal se usa para crear ambas definiciones de filas. Por tanto, cualquier persona puede generar los informes sin tener que realizar ninguna modificación.

### <a name="column-definition"></a>Definición de columnas

Las definiciones de columnas contienen diversos tipos de columnas para proporcionar distintos niveles de detalle y datos financieros.

-   **Anual y desviación - tipos de columna predeterminadas:**
    -   **DESC** : la descripción de la definición de filas.
    -   **FD**: datos financieros de año hasta la fecha para el año actual
    -   **FD**: datos financieros de año hasta la fecha para el año pasado
    -   **CALC**: la desviación de restar el último año del actual

<!-- -->

-   **Columna de año hasta la fecha - predeterminado:**
    -   **DESC** : la descripción de la definición de filas.
    -   **FD**: datos financieros de año hasta la fecha para el año actual

 

<a name="see-also"></a>Consulte también
--------

[Informes financieros](financial-reporting-getting-started.md)

[Ver informes financieros](view-financial-reports.md)

[Blog de informes financieros de Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)




