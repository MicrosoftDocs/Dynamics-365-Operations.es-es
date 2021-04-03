---
title: Crear una solicitud de baja de flujo de trabajo
description: Cree un flujo de trabajo de solicitudes de bajas y ausencias para administrar solicitudes de bajas de manera coherente en Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 05/08/2020
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c2c2020c68c4aca3594a2532d32f968ab76f6b7b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463319"
---
# <a name="create-a-leave-request-workflow"></a>Crear una solicitud de baja de flujo de trabajo

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Puede crear un flujo de trabajo en Dynamics 365 Human Resources para administrar solicitudes de bajas y ausencias de manera coherente. Un flujo de trabajo de **permisos y ausencias** le permite:

- Definir tareas
- Determinar quién debe completar las tareas
- Especificar quién puede aprobar o rechazar solicitudes

## <a name="create-a-leave-and-absence-request-workflow"></a>Crear un flujo de trabajo de solicitudes de permisos y ausencias

1. En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.

2. En **Configuración**, seleccione **Flujos de trabajo de recursos humanos**.

3. Seleccione **Nueva** y luego seleccione **Solicitud de bajas y ausencias**. 

4. Cuando el aparezca el cuadro de mensaje **¿Abrir este archivo?**, seleccione **Abrir** e inicie sesión con las credenciales de su empresa.

5. Use el editor de flujo de trabajo para crear un flujo de trabajo para sus solicitudes de licencia. Para obtener más información sobre cómo trabajar con flujos de trabajo, consulte [Visión general de la creación de flujos de trabajo](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/create-workflow?toc=/dynamics365/commerce/toc.json.)

## <a name="leave-and-absence-request-workflow-data-elements"></a>Elementos de datos de flujo de trabajo de solicitudes de bajas y ausencias

Puede usar los siguientes elementos de datos para crear aprobaciones condicionales o automáticas en flujos de trabajo para solicitudes de bajas y ausencias:

- **Importe**
- **Comentar**
- **Compañía**
- **Creado por**
- **Fecha y hora de creación**
- **Fecha de finalización**
- **Tipo de baja**
- **Modificado por**
- **Fecha y hora de modificación**
- **Código de motivo**
- **Id. de solicitud**
- **Fecha de inicio**
- **Estado** 
- **Fecha de envío**
- **Enviado por**
- **Enviado por Recursos Humanos**
- **Enviado por el Administrador**
- **Enviado por delegación**
- **Trabajador**
- **Tipo de trabajador**

Estos ejemplos muestran cómo puede crear diferentes tipos de condiciones de flujo de trabajo utilizando estos elementos de datos:

- Use **Código de razón** en una declaración condicional para enrutar solicitudes de baja por enfermedad con el código de razón **Cirugía** a RRHH para su aprobación, mientras encamina todos los demás códigos de razón al gerente. Para obtener más información sobre las declaraciones condicionales, consulte [Configurar decisiones condicionales en un flujo de trabajo](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-conditional-decision-workflow). 

- Utilizar **Enviado por Recursos humanos** y **Enviado por el gerente** en una acción automática para aprobar automáticamente las solicitudes de baja que estos roles envían en nombre de los empleados. Para obtener más información sobre accciones automáticas, consulte [Configurar procesos de aprobación en un flujo de trabajo](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-approval-process-workflow).

- User **Tipo de baja** en una declaración condicional o acción automática para controlar cómo el flujo de trabajo enruta las solicitudes con ciertos tipos de bajas.

## <a name="see-also"></a>Consulte también

- [Visión general de bajas y ausencias](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]