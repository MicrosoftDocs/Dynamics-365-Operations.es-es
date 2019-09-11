---
title: Procesar diario de asignaciones contables
description: En este tema se explica cómo procesar una solicitud de asignación en Dynamics 365 for Finance and Operations.
author: aprilolson
manager: AnnBe
ms.date: 07/26/2019
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
ms.openlocfilehash: 0798d9f1c09e827bf64635cf67102f77244948c5
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867448"
---
# <a name="process-ledger-allocation-journal"></a>Procesar diario de asignaciones contables

[!include [task guide banner](../../includes/task-guide-banner.md)]

En este tema se explica cómo procesar una solicitud de asignación en Dynamics 365 for Finance and Operations. Use la página Solicitud de asignación de proceso para crear un diario de asignaciones que se pueda revisar y aprobar antes de registrarlo en la contabilidad general o se pueda registrar directamente en la contabilidad general. Antes de crear un diario de asignaciones, debe haber al menos una regla de asignación de diario activa. Esta tarea usa la empresa de demostración USMF.

1. En el panel de navegación, vaya a **Módulos > Contabilidad general > Asignaciones > Solicitud de asignación de proceso**.
2. En el campo **Regla**, seleccione el registro deseado en el menú desplegable.
3. En el campo **A partir de la fecha**, escriba una fecha.

    - El campo **A partir de la fecha** es muy importante cuando el libro mayor es el origen de datos para la regla. Esta fecha controla los saldos contables que se incluirán para asignación.  
    - En el campo **Origen cero**, seleccione **Detener**. Esto detendrá el proceso de asignación y mostrará un mensaje que indique que se seleccionó el importe de origen cero.  

4. En el campo **Opciones de propuesta**, seleccione **Sólo propuesta**. Seleccione **Propuesta solo** para revisar y aprobar opcionalmente el resultado en los Diarios de asignaciones antes de registrar la asignación en la Contabilidad general.  
5. En el campo Fecha de registro de contabilidad general, escriba una fecha.
6. Seleccione **Aceptar**.
7. En el panel de navegación, vaya a **Módulos > Contabilidad general > Asignaciones > Diarios de asignaciones**.
8. Seleccionar **Líneas**.
9. Seleccione **Registrar**.
10. Seleccione **Registrar**.

