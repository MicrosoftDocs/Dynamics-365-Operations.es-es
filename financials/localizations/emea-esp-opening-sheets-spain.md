---
title: Entradas especiales y hojas de apertura
description: "Las entidades jurídicas de España pueden registrar entradas especiales como entradas de apertura para el período actual, mientras adaptan sus cuentas a los cambios de las reglas de contabilidad."
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 0a65bf228e69603b91d308aaf026c226bcae4a77
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="special-entries-and-opening-sheets"></a>Entradas especiales y hojas de apertura

[!include[banner](../includes/banner.md)]


Las entidades jurídicas de España pueden registrar entradas especiales como entradas de apertura para el período actual, mientras adaptan sus cuentas a los cambios de las reglas de contabilidad.

Mediante hojas de apertura, puede indicar lo siguiente:

-   Aumentar el valor de activos fijos financieros específicos.
-   Cambiar el valor de materias primas específicas si el valor ha cambiado significativamente durante el año y cuando el material cumple criterios específicos.

Al cerrar las entradas del ejercicio anterior, puede crear varias líneas configurando el campo **Tipo** como **Apertura**.. De esta forma, puede registrar entradas de apertura especiales para el ejercicio actual. Puede realizar ajustes en la hoja de apertura para el ejercicio fiscal de la página **Hojas de apertura**.

## <a name="create-a-new-opening-sheet"></a>Crear una nueva hoja de apertura
Para crear una nueva **Hoja de apertura**, haga clic en **Nueva** en la página **Hojas de apertura**, y especifique lo siguiente.

|                    |                                                                                                                                                                                                                                                                                                   |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Campo**          | **Descripción**                                                                                                                                                                                                                                                                                   |
| **Hojas de apertura** | Escriba un código para la hoja de apertura. Puede crear varias hojas de apertura para cada año, pero cada una debe tener un identificador exclusivo en el campo **Hojas de apertura**.                                                                                                                                  |
| **Nombre**           | Nombre para la hoja de apertura.                                                                                                                                                                                                                                                                       |
| **Capa de registro**  | Seleccione la capa de registro para las transacciones.                                                                                                                                                                                                                                                    |
| **Tipo**           | Seleccione **Apertura** para realizar ajustes de todo el ejercicio que se han mantenido por separado de los registros diarios en el último período del año. Si selecciona **Apertura**, debe usar el campo **Período fiscal de apertura** en la ficha **General** para especificar el período de apertura en el que registrar. |
| **Desde … Hasta**      | Especifique el período al que deben aplicarse los ajustes.                                                                                                                                                                                                                                                 |
| **Registrar**           | Especifique la fecha de registro de los ajustes.                                                                                                                                                                                                                                                     |

Tras especificar información general sobre la hoja de apertura, deberá especificar las cuentas principales que se incluirán en la hoja de apertura. Para ello, haga clic en **Cuentas de apertura** &gt; **Cargar saldos** en la página **Hojas de apertura**. Haga clic en **Registrar** para registrar todos los saldos de cuentas contables en la hoja de apertura.




