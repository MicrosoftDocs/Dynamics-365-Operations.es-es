---
title: Crear esquemas de acumulación
description: Esta guía de tareas describe los pasos de la creación de un esquema de acumulación.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ce96ccfb0dc3e4a723af967147dae93772c5b44f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1553140"
---
# <a name="create-accrual-schemes"></a>Crear esquemas de acumulación

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta guía de tareas describe los pasos de la creación de un esquema de acumulación. Esta tarea usa la empresa de demostración USMF.

1. Vaya a Contabilidad general > Configuración de diario > Esquemas de acumulación.
2. Haga clic en Nuevo.
3. En el campo Identificación acumulada, escriba un valor.
4. En el campo Descripción del plan de provisión, escriba un valor.
5. En el campo Débito, especifique los valores deseados.
    * La cuenta principal definida reemplazará la cuenta principal de débito en la línea de asiento de diario y también se usará para la inversión del aplazamiento en función de las transacciones de acumulaciones contables.  
6. En el campo Crédito, especifique los valores deseados.
    * La cuenta principal definida reemplazará la cuenta principal de crédito en la línea de asiento de diario y también se usará para la inversión del aplazamiento en función de las transacciones de acumulaciones contables.  
7. En el campo Asiento, seleccione cómo desea que se determine el asiento cuando se registran las transacciones.
8. En el campo Descripción, escriba un valor para describir las transacciones que se registrarán.
9. En el campo Frecuencia de períodos, seleccione la frecuencia con la que se deben producir las transacciones.
10. En el campo Número de repeticiones por período, especifique un número.
11. En el campo Registrar transacciones, seleccione cuándo se deben registrar las transacciones, por ejemplo, Mensual.

