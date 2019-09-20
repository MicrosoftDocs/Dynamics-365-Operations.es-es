---
title: Seguir los cambios en los datos de contratación
description: La característica de proceso de auditoría le permite seguir cuando los candidatos, las vacantes de trabajo, o las solicitudes de empleo cambian, para informar de ello o por motivos de conformidad.
author: tracykeya
manager: AnnBe
ms.date: 04/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.search.region: Global
ms.author: trkeya
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2019 update
ms.openlocfilehash: 448fceccb507bec5b60b686043a303c1997a9ac0
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742687"
---
# <a name="track-changes-in-recruiting-data"></a>Seguir los cambios en los datos de contratación

Puede realizar el seguimiento de cambios realizados a los candidatos, las vacantes de trabajo, o a las solicitudes de trabajo mediante el procesado de auditorías. Esto resulta útil para informar o motivos de conformidad.

Puede ver los datos seguidos en Power BI usando el conector de OData. Para obtener más información, consulte [Conectar con fuentes OData en Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-connect-odata).

## <a name="track-changes"></a>Seguir cambios
Para configurar el seguimiento de los cambios en los datos de contratación, siga estos pasos:

1. En [PowerApps](https://web.powerapps.com), seleccione el entorno adecuado.

2. Seleccione **Configuración** (el icono de engranaje), **Personalizaciones avanzadas** y a continuación **Recursos** en **Recursos de desarrollador**. 

3. En la página **Recursos de desarrollador**, copie el valor en el campo **Valor de la API Web de instancia** . Por ejemplo, el valor podría parecerse a este: https://yourorgname.api.crm.dynamics.com/api/data/v9.1/.

4. A continuación puede consultar los datos desde una de las entidades siguientes:
  - Historial de apertura de trabajo (msdyn_jobopeninghistories)
  - Historial de la solicitud de trabajo (msdyn_jobapplicationhistories) 
  - Historial del candidato (msdyn_candidatehistories)

## <a name="data-reported"></a>Datos presentados

Los siguientes datos están disponibles con el proceso de auditoría.

| Datos presentados | Descripción |
| --- | --- |
| Modificado por (msdyn_ChangedbyId) | Referencia al usuario |
| Creado el (createdon) |  Fecha y hora UTC en la que ocurrió el cambio |
| Tipo de cambio (msdyn_changetype) | Qué ha cambiado |
| Valores comunes para los candidatos, vacantes de trabajo, <br></br>y solicitudes de empleo | Fecha de creación<br></br>Actualizado |
| Historial de la solicitud de trabajo | Artefacto agregado <br></br>Artefacto eliminado |
| Historial de oferta de trabajo | TODO: registro añadido <br></br>TODO: registro eliminado <br></br>TODO: registro actualizado <br></br>TODO: participante añadido <br></br>TODO: participante eliminado |
| Historial del candidato | Artefacto agregado <br></br>Artefacto eliminado <br></br>Experiencia laboral agregada <br></br>Experiencia laboral eliminada <br></br>Educación agregada <br></br>Educación eliminada <br></br>Aptitud añadida <br></br>Aptitud eliminada <br></br>Etiqueta agregada <br></br>Etiqueta eliminada <br></br>Red social añadida <br></br>Red social eliminada <br></br>Datos personales añadidos <br></br>Datos personales actualizados<br></br> |
| Campos cambiados (msdyn_changedfields) | Los campos cambiados de la lista de objeto de JSON, pueden no almacenar valores en todos los campos.<br></br><br></br>Para los cambios "Creado" y "Actualizado", mostrará los campos en el registro creado o modificado.<br></br><br></br>Para los cambios de tipo "Añadido", listará los campos en el registro secundario.<br></br><br></br>**Ejemplo:**<br></br><br></br>{<br></br>  “msdyn_applyurl”: { “newValue”: "" },<br></br>  “msdyn_description”: { “valueOmitted”: verdadero } <br></br>} |
|Historial de la solicitud de trabajo | Solicitud de trabajo (msdyn_JobapplicatonId)<br></br>Estado (msdyn_status) <br></br>Motivo del estado (msdyn_statusreason) <br></br>Motivo de rechazo (msdyn_rejectionreason) |
| Historial de oferta de trabajo | Oferta de trabajo (msdyn_JobopeningId) <br></br>Estado (msdyn_jobopeningstatus) <br></br>Motivo del estado (msdyn_jobopeningstatusreason) |
| Historial del candidato | Candidato (msdyn_CandidateId) |
