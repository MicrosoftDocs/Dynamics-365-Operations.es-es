---
title: Flujo de trabajo de gastos
description: "En este tema se explica cómo puede usar el sistema de flujo de trabajo en Microsoft Dynamics 365 for Finance and Operations para configurar un proceso de revisión de los informes de gastos en Gestión de gastos."
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 6ee607f723659a5b6ecd655ba4fdfca35a4c582d
ms.contentlocale: es-es
ms.lasthandoff: 03/26/2018

---

# <a name="expense-workflow"></a>Flujo de trabajo de gastos

[!INCLUDE [banner](../includes/banner.md)]

Puede usar el sistema de flujo de trabajo en Microsoft Dynamics 365 for Finance and Operations para configurar un proceso de revisión de los informes de gastos en Gestión de gastos. Puede configurar un flujo de trabajo que use los siguientes criterios para determinar quién aprueba los informes de gastos:

- El empleado que notifica la jerarquía y los límites de aprobación predeterminados
- Aprobación de varios niveles que admite aprobadores provisionales y un aprobador final
- Las dimensiones financieras y la responsabilidad del proyecto
- La asignación a usuarios o grupos de usuarios específicos

Las aprobaciones de flujo de trabajo se pueden crear para los informes de gastos, las solicitudes de viaje, los anticipos y la recuperación del impuesto sobre el valor añadido (IVA).

**Ejemplo**

El siguiente proceso muestra un ejemplo del flujo de trabajo de gestión de gastos para un informe de gastos.

1. Un empleado crea y guarda un informe de gastos.
2. El empleado envía el informe de gastos para su aprobación. Se identifica al aprobador según las reglas definidas cuando se configuró el flujo de trabajo.
3. El aprobador recibe una notificación de que el informe de gastos está listo para su aprobación. El aprobador revisa el informe de gastos y comprueba que las siguientes condiciones se cumplan:

    - Que los gastos no infrinjan ninguna directiva de gastos. Si un gasto infringe una directiva, el aprobador comprueba que se incluye una justificación comercial válida en el informe de gastos.
    - Se vinculan recibos electrónicos al informe de gastos.

4. El aprobador aprueba el informe de gastos.
5. El informe de gastos se asigna a un coordinador de proveedores para que proceda a su registro.
6. Deberá realizar uno de los siguientes pasos, en función de si el registro automático está configurado:

    - Si se configura el registro automático, el informe de gastos se procesa para el pago y el estado del informe de gastos se actualiza.
    - Si el registro automático no se configura, el coordinador de proveedores comprueba que se han enviado todos los recibos originales, y que los recibos corresponden a los gastos incluidos en el informe de gastos. Todos los códigos de impuestos especificados en el informe de gastos también se deben comprobar como correctos.

Una vez comprobados estos requisitos, se registra el informe de gastos.

Después de que se registre el informe de gastos, se autoriza el pago para el informe de gastos y se reembolsa al empleado.

