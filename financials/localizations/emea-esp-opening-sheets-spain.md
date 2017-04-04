---
title: Entradas especiales y hojas de apertura
description: "Las entidades jurídicas en España pueden registrar entradas especiales como entradas de apertura para el período actual, mientras que el adaptarse cuentas a los cambios de las reglas de contabilidad."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261334
ms.assetid: ee065203-20dc-4bbb-bc56-bb01d28a6576
ms.search.region: Spain
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: aeeda64ce560d0508d1bf5f2f626d576201f0d73
ms.lasthandoff: 03/31/2017


---

# <a name="special-entries-and-opening-sheets"></a>Entradas especiales y hojas de apertura

Las entidades jurídicas en España pueden registrar entradas especiales como entradas de apertura para el período actual, mientras que el adaptarse cuentas a los cambios de las reglas de contabilidad.

Mediante las hojas de apertura, puede indicar lo siguiente:

-   Aumentar el valor de activos fijos financieros específicos.
-   Cambie el valor de materias primas específicas si el valor ha cambiado significativamente durante el año y cuando el material cumple criterios específicos.

Al cerrar las entradas del ejercicio anterior, puede crear varias líneas configurando ** tipo ** el campo ** ** apertura. Esto permite que las entradas de apertura especiales para el ejercicio actual se registren. Puede realizar ajustes de la apertura cubren para el ejercicio de ** las hojas de apertura ** la página.

## <a name="create-a-new-opening-sheet"></a>Cree una nueva hoja de apertura
Para crear un nuevo ** hoja de apertura, ** clic ** nuevo ** ** en hojas de apertura ** la página, y especificar lo siguiente.

|                    |                                                                                                                                                                                                                                                                                                   |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Field**          | **Description**                                                                                                                                                                                                                                                                                   |
| **Opening sheets** | Permite especificar un código para la hoja de apertura. Puede crear varias hojas de apertura para cada año, pero cada una debe tener un identificador exclusivo en ** las hojas de apertura ** el campo.                                                                                                                                  |
| **Name**           | Nombre de la hoja de apertura.                                                                                                                                                                                                                                                                       |
| **Posting layer**  | Seleccione la capa de registro para las transacciones.                                                                                                                                                                                                                                                    |
| **Type**           | Seleccione ** ** apertura para realizar ajustes de todo el ejercicio que se han mantenido por separado de los registros diarios en el último período del año. Si selecciona ** apertura **, debe usar ** período fiscal que se abre ** los puestos en ** general ** la ficha para especificar el período de apertura en el que registrar. |
| ** Desde… a **      | Especifique el período al que deben aplicarse los ajustes.                                                                                                                                                                                                                                                 |
| **Post**           | Especifique la fecha de registro de los ajustes.                                                                                                                                                                                                                                                     |

Tras especificar información general sobre la hoja de apertura, deberá especificar las cuentas principales para incluir en la hoja de apertura. Para ello, haga clic en ** las cuentas de apertura ** &gt; ** los saldos de flete ** ** en las hojas de apertura ** la página. Para registrar todos los saldos de la cuenta contable en la apertura, haga clic en ** Registrar **.


