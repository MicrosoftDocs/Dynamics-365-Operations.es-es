---
title: "Informes financieros de saldo de comprobación"
description: "Este artículo describe los informes predeterminados para el saldo de comprobación. También se explica los bloques de creación que están asociados a estos informes y cómo puede modificar los informes para que se adapte a sus requisitos empresariales."
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
ms.custom: 12314
ms.assetid: 3b77d6f3-fd07-41a7-9ddb-1b22d1ae33fc
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 750e2975eb75511afd75b6be0c8dfe90c8a9c89c
ms.lasthandoff: 03/31/2017


---

# <a name="trial-balance-financial-reports"></a>Informes financieros de saldo de comprobación

Este artículo describe los informes predeterminados para el saldo de comprobación. También se explica los bloques de creación que están asociados a estos informes y cómo puede modificar los informes para que se adapte a sus requisitos empresariales. 

<a name="default-trial-balance-reports"></a>Informes de saldo de comprobación predeterminados
-----------------------------

Hay tres informes de saldo de comprobación disponibles en Informes financieros en Microsoft Dynamics 'AX 7'.

| Informe predeterminado                                 | Qué hace                                                                                                                                                                                        |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Saldo de comprobación detallado - predeterminado               | Ofrece información de saldo para todas las cuentas e incluye saldos de débito y de crédito, y el neto de estos, junto con la fecha de transacción, el asiento y la descripción del diario.                  |
| Resumen de saldo de comprobación – predeterminado                | Ofrece información de saldo para todas las cuentas e incluye saldos de apertura y de cierre, y saldos de débito y crédito, junto con su diferencia neta.                                        |
| Resumen de saldo de comprobación año por año – predeterminado | Ofrece información de saldo para todas las cuentas e incluye saldos de apertura y cierre, y saldos de débito y crédito, junto con su diferencia neta para el año actual y el anterior. |

## <a name="building-blocks"></a>Bloques de creación
Los informes financieros del saldo de comprobación usan los siguientes bloques de creación.

| Informe predeterminado                                 | Definición de filas          | Definición de columnas                              |
|------------------------------------------------|-------------------------|------------------------------------------------|
| Saldo de comprobación detallado - predeterminado               | Saldo de comprobación - predeterminado | Saldo de comprobación detallado - predeterminado               |
| Resumen de saldo de comprobación – predeterminado                | Saldo de comprobación - predeterminado | Resumen de saldo de comprobación - predeterminado                |
| Resumen de saldo de comprobación año por año – predeterminado | Saldo de comprobación - predeterminado | Resumen de saldo de comprobación año por año - predeterminado |

### <a name="row-definition"></a>Definición de filas

La definición de filas, saldo de comprobación – establezca como valor predeterminado, contiene una sola fila que extraiga en todas las cuentas principales. Por tanto, cualquier persona puede generar el informe sin tener que realizar ninguna modificación. Cuando ve el informe, explora la fila única para ver los detalles acerca de cada cuenta. Puede modificar la definición de filas para que incluya más detalle. Para modificar la definición de filas Saldo de comprobación - predeterminado para que incluya filas para todas las cuentas, siga estos pasos.

1.  Haga clic en **Editar** y, a continuación, en **Insertar filas de dimensiones**. El comando **Insertar filas de dimensiones** le permite elegir las dimensiones que desea tener en la definición de filas. Para esta definición de filas, va a usar **Cuenta principal**.
2.  Asegúrese de que **Cuenta principal** contiene todos los ampersands (&) y haga clic en **Aceptar**.

La definición de filas contiene ahora todas las cuentas principales para la entidad jurídica predeterminada.

### <a name="column-definition"></a>Definición de columnas

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

 

<a name="see-also"></a>Consulte también
--------

[Financial reporting](financial-reporting-getting-started.md)

[View financial reports](view-financial-reports.md)

[] Blog de los informes financieros de Dynamics (http://blogs.msdn.com/b/dynamics_financial_reporting/)


