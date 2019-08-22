---
title: Procesar diario de asignaciones contables
description: Use la página Solicitud de asignación de proceso para crear un diario de asignaciones que se pueda revisar y aprobar antes de registrarlo en la contabilidad general o se pueda registrar directamente en la contabilidad general.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 087bd4f203e8762447e823b19076b79296a390d6
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846376"
---
# <a name="process-ledger-allocation-journal"></a>Procesar diario de asignaciones contables

[!include [task guide banner](../../includes/task-guide-banner.md)]

Use la página Solicitud de asignación de proceso para crear un diario de asignaciones que se pueda revisar y aprobar antes de registrarlo en la contabilidad general o se pueda registrar directamente en la contabilidad general. Antes de crear un diario de asignaciones, debe haber al menos una regla de asignación de diario activa. Esta tarea usa la empresa de demostración USMF.

1. Vaya a Contabilidad general > Asignaciones > Solicitud de asignación de proceso.
2. En el campo Regla, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, busque y seleccione el registro deseado.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
5. En el campo de fecha inicial, escriba una fecha.
    * La fecha inicial es muy importante cuando el libro mayor es el origen de datos para la regla. Esta fecha controla los saldos contables que se incluirán para asignación.     En el campo Origen cero, seleccione Detener. Esto detendrá el proceso de asignación y mostrará un mensaje que indique que se seleccionó el importe de origen cero.  
6. En el campo Opciones de propuesta, seleccione "Sólo propuesta".
    * Seleccione Propuesta solo para revisar y aprobar opcionalmente el resultado en los Diarios de asignaciones antes de registrar la asignación en la Contabilidad general.  
7. En el campo Fecha de registro de contabilidad general, escriba una fecha.
8. Haga clic en Aceptar
9. Vaya a Contabilidad general > Asignaciones > Diarios de asignaciones.
10. Haga clic en Líneas.
11. Haga clic en Registrar.
12. Haga clic en Registrar.

