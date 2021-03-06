---
title: Prueba independiente de datos mediante Regression Suite Automation Tool
description: En este tema se describe las recomendaciones para la prueba independiente de datos mediante Regression Suite Automation Tool.
author: kfend
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: 21761
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2019-09-11
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.openlocfilehash: 120a88790b7cdb6a8cfcf97cbafeced4685384f2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744672"
---
# <a name="data-agnostic-testing-using-the-regression-suite-automation-tool"></a>Prueba independiente de datos mediante Regression Suite Automation Tool

[!include [banner](../includes/banner.md)]

Aunque la validación funcional de una aplicación de ERP no puede ser completamente independiente de los datos, hay fases y enfoques varios para pruebas. Estas fases de prueba incluyen:  

- Marco SysTest
- Marco de trabajo ATL
- Regression Suite Automation Tool (RSAT)

[![Pirámide de la clasificación de prueba](./media/rsat-data-agnostic-testing-01.PNG)](./media/rsat-data-agnostic-testing-01.PNG)

## <a name="overview"></a>Visión general
-   **Marco de SysTest** El marco de SysTest es fiable para escribir pruebas de unidad. Dado que las pruebas de unidad prueban generalmente un método o función, siempre deberían ser independientes de los datos y depender solo de los datos introducidos proporcionados como parte de la prueba.
-   **Marco de ATL** – Microsoft tiene un marco de ATL que es una abstracción en el marco de SysTest y hace que la prueba funcional de escritura sea mucho más sencilla y fiable. Este marco se debe usar para escribir pruebas de componentes o pruebas de integración sencillas.
-   **RSAT** – El RSAT se usa para las pruebas de integración y las de ciclo de negocio. Las pruebas de ciclo de negocio, también denominadas las pruebas de la validación de la regresión, dependen de datos existentes. Sin embargo, estas pruebas se pueden convertir en independientes de datos si considera factores adicionales. 

    - o Donde las pruebas de unidad y de componente son de bajo y nivel y pueden ser completamente independientes de datos (no dependientes del conjunto de datos actual) las pruebas de ciclo de negocio o validación de regresión dependen de algunos datos existentes. Estos datos incluyen la configuración, las opciones de configuración (parámetros) y datos maestros (cliente, proveedores, artículos, etc.), pero nunca los datos de transacción. Asegúrese de que durante las pruebas, si cualquiera de estos cambia que vuelvan a invertirse como parte de la prueba final.
    - Seleccione los datos maestros basados en determinados criterios en lugar de seleccionar un registro concreto. Por ejemplo, si desea seleccionar un artículo de acuerdo con sus valores de dimensión y disponibilidad de existencias, filtre la lista de productos con estos valores, seleccione el primer artículo, y copie el número que se utilizará para las pruebas futuras. Si es una línea de datos maestros sencilla como cliente, proveedor o artículo, puede crearse como parte de la automatización y usarse en las pruebas futuras con el encadenamiento. 
    - o Introduzca los identificadores únicos, como números de factura mediante una secuencia numérica o usando funciones Microsoft Excel como =TEXT(NOW(),"yyyymmddhhmm"). Esta función proporcionará un número único cada minuto, lo que le permite seguir cuándo tuvo lugar la acción. Esto se puede usar para las variables como números de recibo de producto y números de factura de proveedor. Estas pruebas continúan trabajando en la misma base de datos una y otra vez, sin requerir ninguna restauración.
    - Establezca el **Modo de edición** del entorno siempre en **Lectura** o **Edición** como el primer caso de prueba porque la opción predeterminada es **Automático**. Las opciones **Automático** usan la configuración anterior y pueden producir pruebas poco fiables. 
 
    [![Página opciones, pestaña Rendimiento](./media/rsat-data-agnostic-testing-02.PNG)](./media/rsat-data-agnostic-testing-02.PNG)
 
    - Solo valide después de filtrar según una transacción en particular en lugar de una validación genérica. Por ejemplo, para el número de registros, filtre según el número de transacción o la fecha de transacción de modo que la validación excluya el resto de transacciones. 
    - Si está comprobando un saldo o una comprobación presupuestaria del cliente, guarde el valor primero y después agregue el valor de transacción para validar el resultado esperado en lugar de validar un valor esperado fijo. 
 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]