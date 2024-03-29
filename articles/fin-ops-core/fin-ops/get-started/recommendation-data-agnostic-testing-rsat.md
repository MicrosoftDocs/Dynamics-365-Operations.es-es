---
title: Prueba independiente de datos mediante Regression Suite Automation Tool
description: En este artículo se describe las recomendaciones para la prueba independiente de datos mediante Regression Suite Automation Tool.
author: FrankDahl
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2019-09-11
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.custom: 21761
ms.openlocfilehash: f4322cb76d1d83c02ec9d4dcb997a1cd4730d090
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269603"
---
# <a name="data-agnostic-testing-using-the-regression-suite-automation-tool"></a>Prueba independiente de datos mediante Regression Suite Automation Tool

[!include [banner](../includes/banner.md)]

Aunque la validación funcional de una aplicación de ERP no puede ser completamente independiente de los datos, hay fases y enfoques varios para pruebas. Estas fases de prueba incluyen:  

- Marco SysTest
- Marco de trabajo ATL
- Regression Suite Automation Tool (RSAT)

[![Pirámide de la clasificación de prueba.](./media/rsat-data-agnostic-testing-01.PNG)](./media/rsat-data-agnostic-testing-01.PNG)

## <a name="overview"></a>Información general
-   **Marco de SysTest** El marco de SysTest es fiable para escribir pruebas de unidad. Dado que las pruebas de unidad prueban generalmente un método o función, siempre deberían ser independientes de los datos y depender solo de los datos introducidos proporcionados como parte de la prueba.
-   **Marco de ATL** – Microsoft tiene un marco de ATL que es una abstracción en el marco de SysTest y hace que la prueba funcional de escritura sea mucho más sencilla y fiable. Este marco se debe usar para escribir pruebas de componentes o pruebas de integración sencillas.
-   **RSAT** – El RSAT se usa para las pruebas de integración y las de ciclo de negocio. Las pruebas de ciclo de negocio, también denominadas las pruebas de la validación de la regresión, dependen de datos existentes. Sin embargo, estas pruebas se pueden convertir en independientes de datos si considera factores adicionales. 

    - o Donde las pruebas de unidad y de componente son de bajo y nivel y pueden ser completamente independientes de datos (no dependientes del conjunto de datos actual) las pruebas de ciclo de negocio o validación de regresión dependen de algunos datos existentes. Estos datos incluyen la configuración, las opciones de configuración (parámetros) y datos maestros (cliente, proveedores, artículos, etc.), pero nunca los datos de transacción. Asegúrese de que durante las pruebas, si cualquiera de estos cambia que vuelvan a invertirse como parte de la prueba final.
    - Seleccione los datos maestros basados en determinados criterios en lugar de seleccionar un registro concreto. Por ejemplo, si desea seleccionar un artículo de acuerdo con sus valores de dimensión y disponibilidad de existencias, filtre la lista de productos con estos valores, seleccione el primer artículo, y copie el número que se utilizará para las pruebas futuras. Si es una línea de datos maestros sencilla como cliente, proveedor o artículo, puede crearse como parte de la automatización y usarse en las pruebas futuras con el encadenamiento. 
    - o Introduzca los identificadores únicos, como números de factura mediante una secuencia numérica o usando funciones Microsoft Excel como =TEXT(NOW(),"yyyymmddhhmm"). Esta función proporcionará un número único cada minuto, lo que le permite seguir cuándo tuvo lugar la acción. Esto se puede usar para las variables como números de recibo de producto y números de factura de proveedor. Estas pruebas continúan trabajando en la misma base de datos una y otra vez, sin requerir ninguna restauración.
    - Establezca el **Modo de edición** del entorno siempre en **Lectura** o **Edición** como el primer caso de prueba porque la opción predeterminada es **Automático**. Las opciones **Automático** usan la configuración anterior y pueden producir pruebas poco fiables. 
 
    [![Página opciones, pestaña Rendimiento.](./media/rsat-data-agnostic-testing-02.PNG)](./media/rsat-data-agnostic-testing-02.PNG)
 
    - Solo valide después de filtrar según una transacción en particular en lugar de una validación genérica. Por ejemplo, para el número de registros, filtre según el número de transacción o la fecha de transacción de modo que la validación excluya el resto de transacciones. 
    - Si está comprobando un saldo o una comprobación presupuestaria del cliente, guarde el valor primero y después agregue el valor de transacción para validar el resultado esperado en lugar de validar un valor esperado fijo. 
 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
