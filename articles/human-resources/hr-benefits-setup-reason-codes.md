---
title: Configurar códigos de motivos
description: Dynamics 365 Human Resources usa códigos de motivo para explicar por qué los beneficios de un empleado están cambiando.
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5bcfa60349d6d362504184dd90cc97ea27e8ba43
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689533"
---
# <a name="set-up-reason-codes"></a>Configurar códigos de motivos


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources usa códigos de motivo para explicar por qué los beneficios de un empleado están cambiando.

> [!NOTE]
> A partir de enero de 2021, se migraron los códigos de motivo al espacio de trabajo **Administración de personal** en lugar de al espacio de trabajo **Administración de prestaciones**. Para obtener más información, consulte [Migrar manualmente los códigos de motivo a la Administración de personal](hr-benefits-setup-reason-codes.md#manually-migrate-reason-codes-to-personnel-management).

## <a name="create-reason-codes"></a>Crear códigos de motivo

1. En el espacio de trabajo **Administración de personal** (o el espacio de trabajo **Administración de prestaciones** si aún no se han migrado los códigos de motivo), seleccione **Vínculos** y, a continuación, seleccione **Códigos de motivo**.

2. Seleccione **Nuevo**.

3. Especifique los valores para los siguientes campos:

   | Campo | Descripción |
   | --- | --- |
   | **Código de motivo** | Un nombre único para identificar la razón por la cual un empleado cambiaría una inscripción al plan de beneficios. |
   | **Descripción** | Una descripción del código de motivo. |

4. En **Escenarios aplicables**, establezca **Administración de prestaciones** en **Sí**. (No es aplicable si los códigos de motivo aún no se han migrado al espacio de trabajo **Administración de personal**).

5. Seleccione **Guardar**.

## <a name="manually-migrate-reason-codes-to-personnel-management"></a>Migrar manualmente los códigos de motivo a la Administración de personal

En enero de 2021, se migraron los códigos de motivo al espacio de trabajo **Administración de personal** en lugar de al espacio de trabajo **Administración de prestaciones**. La mayoría de los datos de códigos de motivo se migrarán automáticamente en su entorno. Es posible que algunos datos de códigos de motivo no se migren. Por ejemplo, ahora los códigos de motivo tienen 15 caracteres como máximo, por lo que cualquier código de motivo de más de 15 caracteres no se migrará automáticamente.

Verá un banner en la página **Vínculos** del espacio de trabajo **Administración de prestaciones** que le informará de la migración y de si no se han migrado algunos códigos de motivo.

1. Seleccione **Códigos de motivo** para obtener detalles sobre el estado de la migración.

   [![Códigos de motivos.](./media/hr-benefits-setup-reason-codes-link.png)](./media/hr-benefits-setup-reason-codes-link.png)

2. Seleccione un código de motivo que no haya podido migrar.

   [![Estado de la migración de los códigos de motivo.](./media/hr-benefits-setup-reason-codes-status.png)](./media/hr-benefits-setup-reason-codes-status.png)

3. Seleccione **Migrar código de motivo**.

   [![Migrar código de motivo.](./media/hr-benefits-setup-reason-codes-migrate.png)](./media/hr-benefits-setup-reason-codes-migrate.png)

4. En el panel **Migración de código de motivo de prestación** tiene dos opciones para asignar a un código de motivo de Administración de personal:

   - Para utilizar un código de motivo existente en Administración de personal, elija uno de los cuadros desplegables **Usar código de motivo existente**.
     > [!NOTE]
     > Solo puede utilizar un código de motivo existente en Administración de personal si aún no se ha migrado otro código de motivo de Administración de prestaciones.
   - Para crear un nuevo código de motivo en Administración de personal, introduzca uno nuevo en **Nuevo código de motivo** y, a continuación, escriba una descripción en **Nueva descripción**.

   [![Asignar a un código de motivo de Administración de personal.](./media/hr-benefits-setup-reason-codes-mapping.png)](./media/hr-benefits-setup-reason-codes-mapping.png)

Una vez que se hayan migrado los códigos de motivo a Administración de personal, la opción de usarlos en Administración de prestaciones se establece automáticamente en **Sí**.

[![Usar código de motivo en la Administración de prestaciones.](./media/hr-benefits-setup-reason-codes-use.png)](./media/hr-benefits-setup-reason-codes-use.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
