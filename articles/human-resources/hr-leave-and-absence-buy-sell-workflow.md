---
title: Crear un flujo de trabajo de solicitudes de compras y ventas de permisos y ausencias
description: Cree un flujo de trabajo de solicitudes de compras y ventas de permisos y ausencias para comprar y vende solicitudes de bajas de manera coherente en Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d490e0c36ea0e854c5d7afc5b3bf75f6b65e542c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420471"
---
# <a name="create-a-buy-and-sell-leave-request-workflow"></a>Crear un flujo de trabajo de solicitudes de compras y ventas de permisos y ausencias

Puede crear un flujo de trabajo en Dynamics 365 Human Resources para administrar las solicitudes de compras y ventas de bajas de forma coherente. Un flujo de trabajo de **Comprar y vender permisos y ausencias** le permite:

- Definir tareas
- Determinar quién debe completar las tareas
- Especificar quién puede aprobar o rechazar solicitudes

## <a name="create-a-buy-and-sell-leave-request-workflow"></a>Crear un flujo de trabajo de solicitudes de compras y ventas de permisos y ausencias

1. En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.

2. En **Configuración**, seleccione **Flujos de trabajo de recursos humanos**.

3. Seleccione **Nueva** y luego seleccione **Solicitud de compra y venta de bajas y ausencias**. 

4. Cuando el aparezca el cuadro de mensaje **¿Abrir este archivo?**, seleccione **Abrir** e inicie sesión con las credenciales de su empresa.

5. Use el editor de flujo de trabajo para crear un flujo de trabajo para sus solicitudes de licencia. Para obtener más información sobre cómo trabajar con flujos de trabajo, consulte [Visión general de la creación de flujos de trabajo](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)

## <a name="leave-and-absence-request-workflow-data-elements"></a>Elementos de datos de flujo de trabajo de solicitudes de bajas y ausencias

Puede usar los siguientes elementos de datos para crear aprobaciones condicionales o automáticas en flujos de trabajo para solicitudes de compras y ventas de permisos y ausencias:

- **Importe**
- **Directiva de compra y venta de bajas**
- **Compañía**
- **Creado por**
- **Fecha y hora de creación**
- **Fecha final**
- **Tipo de baja**
- **Modificado por**
- **Fecha y hora de modificación**
- **Id. de solicitud**
- **Fecha inicial**
- **Estado** 
- **Fecha de envío**
- **Enviado por**
- **Enviado por Recursos Humanos**
- **Enviado por el Administrador**
- **Enviado por delegación**
- **Trabajador**

## <a name="workflow-examples"></a>Ejemplos de flujos de trabajo

Estos ejemplos muestran cómo puede crear diferentes tipos de condiciones de flujo de trabajo utilizando estos elementos de datos:

- Utilice **Enviado por Recursos humanos** y **Enviado por el gerente** en una acción automática para aprobar automáticamente las solicitudes de compra y venta de bajas que estos roles envían en nombre de los empleados. Para obtener más información sobre accciones automáticas, consulte [Configurar procesos de aprobación en un flujo de trabajo](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).

- User **Tipo de baja** en una declaración condicional o acción automática para controlar cómo el flujo de trabajo enruta las solicitudes con ciertos tipos de bajas.

## <a name="see-also"></a>Consulte también

[Visión general de bajas y ausencias](hr-leave-and-absence-overview.md)<br>
[Gestionar directivas de compra y venta de bajas](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]