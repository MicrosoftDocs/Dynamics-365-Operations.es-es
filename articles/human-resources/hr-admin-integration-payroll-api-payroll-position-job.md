---
title: Trabajo de puesto de nómina
description: Este tema proporciona detalles y una consulta de ejemplo para la entidad de trabajo de puesto de nóminas en Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 62b9caf94f1c9aa8bb5758e62565fe57dfdd245a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055037"
---
# <a name="payroll-position-job"></a>Trabajo de puesto de nómina

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema proporciona detalles y una consulta de ejemplo para la entidad de relación de trabajo de puesto de nóminas en Dynamics 365 Human Resources.

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de trabajo**<br>mshr_jobid<br>*Cadena* | Solo lectura<br>Obligatorio |El id. de trabajo. |
| **Válido desde**<br>mshr_validto<br>*Desplazamineto de fecha y hora* | Solo lectura <br>Obligatorio | Fecha desde la que es válida el puesto y la relación laboral. |
| **Válido hasta**<br>mshr_validto<br>*Desplazamineto de fecha y hora* | Solo lectura <br>Obligatorio | Fecha hasta la que es válido el puesto y la relación laboral.  |
| **Id. de puesto**<br>mshr_positionid<br>*Cadena* | Solo lectura<br>Obligatorio | El id. del puesto. |
| **Campo primario**<br>mshr_primaryfield<br>*Cadena* | Obligatorio<br>Generado por el sistema |  |
| **Valor de id. de trabajo de puesto**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_PayrollPositionJobEntity de la mshr_payrollpositionjobentity |Id. del trabajo asociado al puesto.|
| **Valor de id. de plan de compensación fijo**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_FixedCompPlan_id de mshr_payrollfixedcompensationplanentity  | Id. del plan de compensación fijo asociado al puesto. |
| **Id. de entidad de trabajo de puesto de nómina**<br>mshr_payrollpositionjobentityid<br>*Guid* | Obligatorio<br>Generado por el sistema. | Valor GUID generado por el sistema para identificar de forma única el trabajo.  |

