---
title: Informes financieros de balance de situación
description: En este artículo se describen los informes predeterminados para los balances de situación. También se describen los componentes de estos informes.
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: FinanicalReports
audience: Application User
ms.reviewer: roschlom
ms.custom: 12274
ms.assetid: 52f78229-f531-4d16-b337-e2628994acb6
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bcfb8e8fd28224ac9fe9a4919f4252dcd01ce360
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5212406"
---
# <a name="balance-sheet-financial-reports"></a>Informes financieros de balance de situación

[!include [banner](../includes/banner.md)]

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



<a name="additional-resources"></a>Recursos adicionales
--------

[Visión general de informes financieros](financial-reporting-getting-started.md)

[Ver informes financieros](view-financial-reports.md)

[Blog de informes financieros de Dynamics](https://blogs.msdn.com/b/dynamics_financial_reporting/)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]