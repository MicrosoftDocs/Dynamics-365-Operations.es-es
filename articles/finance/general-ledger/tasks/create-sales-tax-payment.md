---
title: Crear un pago de impuestos
description: El procedimiento de la tarea de liquidar y registrar impuestos liquida los saldos de impuestos de las cuentas de impuestos y los anota como contrapartida en la cuenta de liquidación de impuestos para un período determinado.
author: twheeloc
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5066689fb85dd176da1ca1561614e443cb87d816
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832763"
---
# <a name="create-a-sales-tax-payment"></a>Crear un pago de impuestos

[!include [banner](../../includes/banner.md)]

El procedimiento de la tarea de liquidar y registrar impuestos liquida los saldos de impuestos de las cuentas de impuestos, y los anota como contrapartida en la cuenta de liquidación de impuestos para un período determinado.

1. Vaya a **Impuestos > Declaraciones > Impuestos > Liquidar y registrar impuestos**.
2. En el campo **Período de liquidación**, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. En el campo **Fecha inicial**, escriba una fecha.
    * Si no selecciona la opción **Incluir correcciones** en la página **Parámetros de contabilidad general**, la liquidación se puede procesar para diferentes versiones. El original es la primera liquidación para un intervalo de períodos y se puede procesar solo una vez para un intervalo de períodos. Las últimas correcciones liquidarán las transacciones de impuestos que se hayan registrado después de crear la versión original.   
5. En el campo **Fecha de transacción**, especifique una fecha.
6. Haga clic en **Aceptar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]