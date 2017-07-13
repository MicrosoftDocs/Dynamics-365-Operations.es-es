---
title: "Informes financieros de saldo de comprobación"
description: "En este artículo se describen los informes predeterminados para los saldos de comprobación. También se describen los componentes asociados a estos informes y cómo puede modificar los informes para que se adapten a sus requisitos empresariales."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 86e8e91f2af474999d89bb63ac9e2afad7843c8a
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# Informes financieros de saldo de comprobación
<a id="trial-balance-financial-reports" class="xliff"></a>

[!include[banner](../includes/banner.md)]


En este artículo se describen los informes predeterminados para los saldos de comprobación. También se describen los componentes asociados a estos informes y cómo puede modificar los informes para que se adapten a sus requisitos empresariales. 

Informes de saldo de comprobación predeterminados
<a id="default-trial-balance-reports" class="xliff"></a>
-----------------------------

Tres informes de saldo de comprobación están disponibles en informes financieros en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.

| Informe predeterminado                                 | Qué hace                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Saldo de comprobación detallado - predeterminado               | Ofrece información de saldo para todas las cuentas e incluye saldos de débito y de crédito, y el neto de estos, junto con la fecha de transacción, el asiento y la descripción del diario.                  |
| Resumen de saldo de comprobación – predeterminado                | Ofrece información de saldo para todas las cuentas e incluye saldos de apertura y de cierre, y saldos de débito y crédito, junto con su diferencia neta.                                        |
| Resumen de saldo de comprobación año por año – predeterminado | Ofrece información de saldo para todas las cuentas e incluye saldos de apertura y cierre, y saldos de débito y crédito, junto con su diferencia neta para el año actual y el anterior. |

## Bloques de creación
<a id="building-blocks" class="xliff"></a>
Los informes financieros del saldo de comprobación usan los siguientes bloques de creación.

| Informe predeterminado                                 | Definición de filas          | Definición de columnas                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| Saldo de comprobación detallado - predeterminado               | Saldo de comprobación - predeterminado | Saldo de comprobación detallado - predeterminado               |
| Resumen de saldo de comprobación – predeterminado                | Saldo de comprobación - predeterminado | Resumen de saldo de comprobación - predeterminado                |
| Resumen de saldo de comprobación año por año – predeterminado | Saldo de comprobación - predeterminado | Resumen de saldo de comprobación año por año - predeterminado |

### Definición de filas
<a id="row-definition" class="xliff"></a>

La definición de filas, Saldo de comprobación – Predeterminado, contiene una sola fila que extrae todas las cuentas principales. Por tanto, cualquier persona puede generar el informe sin tener que realizar ninguna modificación. Cuando ve el informe, explora la fila única para ver los detalles acerca de cada cuenta. Puede modificar la definición de filas para que incluya más detalle. Para modificar la definición de filas Saldo de comprobación - predeterminado para que incluya filas para todas las cuentas, siga estos pasos.

1.  Haga clic en **Editar** y, a continuación, en **Insertar filas de dimensiones**. El comando **Insertar filas de dimensiones** le permite elegir las dimensiones que desea tener en la definición de filas. Para esta definición de filas, va a usar **Cuenta principal**.
2.  Asegúrese de que **Cuenta principal** contiene todos los ampersands (&) y haga clic en **Aceptar**.

La definición de filas contiene ahora todas las cuentas principales para la entidad jurídica predeterminada.

### Definición de columnas
<a id="column-definition" class="xliff"></a>

Cada informe de saldo de comprobación usa otra definición de columna. Estas definiciones de columnas contienen diversos tipos de columnas para proporcionar distintos niveles de detalle y datos financieros.

-   **Tipos de columnas de Saldo de comprobación detallados – predeterminado:**
    -   **DESC** : la descripción de la definición de filas.
    -   **ACCT**: códigos de cuenta
    -   **ATTR (3)** atributos:
        -   Fecha de la transacción
        -   Comprobante
        -   Descripción del diario
    -   **FD**: los datos financieros que contienen solo débitos
    -   **FD**: los datos financieros que contienen solo créditos
    -   **CALC**: la diferencia neta
-   **Tipos de columnas de Resumen de saldo de comprobación - predeterminado:**
    -   **ACCT**: códigos de cuenta
    -   **DESC** : la descripción de la definición de filas.
    -   **ATTR**: un atributo:
        -   Comprobante
    -   **FD**: los datos financieros de saldo inicial
    -   **FD**: los datos financieros que contienen solo débitos
    -   **FD**: los datos financieros que contienen solo créditos
    -   **CALC**: la diferencia neta
    -   **CALC**: el saldo de cierre
-   **Resumen de saldo de comprobación año por año - predeterminado:**
    -   **ACCT**: códigos de cuenta
    -   **DESC** : la descripción de la definición de filas.
    -   **ATTR**: un atributo
        -   Comprobante
    -   **FD**: datos financieros de saldo inicial para el año actual
    -   **FD**: los datos financieros que solo contienen débitos para el año actual
    -   **FD**: los datos financieros que solo contienen créditos para el año actual
    -   **CALC**: la diferencia neta
    -   **CALC**: el saldo de cierre
    -   **FD**: los datos financieros que solo contienen débitos para el año pasado
    -   **FD**: los datos financieros que solo contienen créditos para el año pasado

 

Consulte también
<a id="see-also" class="xliff"></a>
--------

[Informes financieros](financial-reporting-getting-started.md)

[Ver informes financieros](view-financial-reports.md)

[Blog de informes financieros de Dynamics](http://blogs.msdn.com/b/dynamics_financial_reporting/)




