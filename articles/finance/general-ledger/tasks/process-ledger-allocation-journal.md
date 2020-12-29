---
title: Procesar diario de asignaciones contables
description: En este tema se explica cómo procesar una solicitud de asignación en Dynamics 365 Finance.
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
ms.openlocfilehash: 33e989d3641ae1eaa28a55398fcf51674ac1ed72
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447630"
---
# <a name="process-ledger-allocation-journal"></a>Procesar diario de asignaciones contables

[!include [banner](../../includes/banner.md)]

En este tema se explica cómo procesar una solicitud de asignación. Use la página Solicitud de asignación de proceso para crear un diario de asignaciones que se pueda revisar y aprobar antes de registrarlo en la contabilidad general o se pueda registrar directamente en la contabilidad general. Antes de crear un diario de asignaciones, debe haber al menos una regla de asignación de diario activa. Esta tarea usa la empresa de demostración USMF.

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

