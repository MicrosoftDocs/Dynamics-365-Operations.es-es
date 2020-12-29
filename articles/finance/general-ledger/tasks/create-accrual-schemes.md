---
title: Crear esquemas de acumulación
description: Este tema explica cómo crear un esquema de acumulación.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAccrualTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a83870c4cec4de2e51e90ff1889d4beff6c23f95
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447682"
---
# <a name="create-accrual-schemes"></a>Crear esquemas de acumulación

[!include [banner](../../includes/banner.md)]

Este tema explica cómo crear un esquema de acumulación. Esta tarea usa la empresa de demostración USMF.

1. Vaya a **Panel de exploración > Módulos > Contabilidad general > Configuración del diario > Esquemas de acumulación**.
2. Seleccione **Nuevo**.
3. En el campo **Identificación acumulada**, escriba un valor.
4. En el campo **Descripción del plan de provisión**, escriba un valor.
5. En el campo **Débito**, especifique los valores deseados. La cuenta principal definida reemplazará la cuenta principal de débito en la línea de asiento de diario y también se usará para la inversión del aplazamiento en función de las transacciones de acumulaciones contables.  
6. En el campo **Crédito**, especifique los valores deseados. La cuenta principal definida reemplazará la cuenta principal de crédito en la línea de asiento de diario y también se usará para la inversión del aplazamiento en función de las transacciones de acumulaciones contables.  
7. En el campo **Asiento**, seleccione cómo desea que se determine el asiento cuando se registran las transacciones.
8. En el campo **Descripción**, escriba un valor para describir las transacciones que se registrarán.
9. En el campo **Frecuencia de períodos**, seleccione la frecuencia con la que se deben producir las transacciones.
10. En el campo **Número de repeticiones por período**, especifique un número.
11. En el campo **Registrar transacciones**, seleccione cuándo se deben registrar las transacciones, por ejemplo, **Mensual**.

