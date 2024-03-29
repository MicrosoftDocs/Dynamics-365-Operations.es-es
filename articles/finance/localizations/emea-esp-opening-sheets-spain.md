---
title: Entradas especiales y hojas de apertura
description: Las entidades jurídicas de España pueden registrar entradas especiales como entradas de apertura para el período actual, mientras adaptan sus cuentas a los cambios de las reglas de contabilidad.
author: AdamTrukawka
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Spain
ms.author: atrukawk
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 261334
ms.search.form: LedgerOpeningSheet_ES
ms.openlocfilehash: 713dc48b3a80edc586f6a4e3057ad1db552fb9d4
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292300"
---
# <a name="special-entries-and-opening-sheets"></a>Entradas especiales y hojas de apertura

[!include [banner](../includes/banner.md)]

Las entidades jurídicas de España pueden registrar entradas especiales como entradas de apertura para el período actual, mientras adaptan sus cuentas a los cambios de las reglas de contabilidad.

Mediante hojas de apertura, puede indicar lo siguiente:

-   Aumentar el valor de activos fijos financieros específicos.
-   Cambiar el valor de materias primas específicas si el valor ha cambiado significativamente durante el año y cuando el material cumple criterios específicos.

Al cerrar las entradas del ejercicio anterior, puede crear varias líneas configurando el campo **Tipo** como **Apertura**.. De esta forma, puede registrar entradas de apertura especiales para el ejercicio actual. Puede realizar ajustes en la hoja de apertura para el ejercicio fiscal de la página **Hojas de apertura**.

## <a name="create-a-new-opening-sheet"></a>Crear una nueva hoja de apertura
Para crear una nueva **Hoja de apertura**, haga clic en **Nueva** en la página **Hojas de apertura**, y especifique lo siguiente.

|  Campo           |  Descripción |
|--------------------|----------------------------------|
| **Hojas de apertura** | Escriba un código para la hoja de apertura. Puede crear varias hojas de apertura para cada año, pero cada una debe tener un identificador exclusivo en el campo **Hojas de apertura**.                                                                                                                                  |
| **Nombre**           | Nombre para la hoja de apertura.                                                                                                                                                                                                                                                                       |
| **Capa de registro**  | Seleccione la capa de registro para las transacciones.                                                                                                                                                                                                                                                    |
| **Tipo**           | Seleccione **Apertura** para realizar ajustes de todo el ejercicio que se han mantenido por separado de los registros diarios en el último período del año. Si selecciona **Apertura**, debe usar el campo **Período fiscal de apertura** en la ficha **General** para especificar el período de apertura en el que registrar. |
| **Desde … Hasta**      | Especifique el período al que deben aplicarse los ajustes.                                                                                                                                                                                                                                                 |
| **Registrar**           | Especifique la fecha de registro de los ajustes.                                                                                                                                                                                                                                                     |

Tras especificar información general sobre la hoja de apertura, deberá especificar las cuentas principales que se incluirán en la hoja de apertura. Para ello, haga clic en **Cuentas de apertura** &gt; **Cargar saldos** en la página **Hojas de apertura**. Haga clic en **Registrar** para registrar todos los saldos de cuentas contables en la hoja de apertura.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
