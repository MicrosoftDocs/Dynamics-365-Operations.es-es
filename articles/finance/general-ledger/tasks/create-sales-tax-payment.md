---
title: Crear un pago de impuestos
description: El trabajo de liquidar y registrar impuestos liquida los saldos de impuestos de las cuentas de impuestos y los anota como contrapartida en la cuenta de liquidación de impuestos para un período determinado.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e41217d26239cf704709d1d48666c382e1e2e824
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985717"
---
# <a name="create-a-sales-tax-payment"></a>Crear un pago de impuestos

[!include [banner](../../includes/banner.md)]

El trabajo de liquidar y registrar impuestos liquida los saldos de impuestos de las cuentas de impuestos y los anota como contrapartida en la cuenta de liquidación de impuestos para un período determinado.

1. Vaya a Impuestos > Declaraciones > Impuestos > Liquidar y registrar impuestos.
2. En el campo Período de liquidación, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
4. En el campo Fecha inicial, escriba una fecha.
    * Si la opción de incluir correcciones no está seleccionada en la página de parámetros de contabilidad general, la liquidación se puede procesar para diferentes versiones. El original es la primera liquidación para un intervalo de períodos y puede procesarse solo una vez para un intervalo de períodos. Las últimas correcciones liquidarán las transacciones de impuestos que se hayan registrado después de crear la versión original.   
5. En el campo Fecha de transacción, especifique una fecha.
6. Haga clic en Aceptar

