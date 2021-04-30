---
title: Trabajo de puesto de nómina
description: Este tema proporciona detalles y una consulta de ejemplo para la entidad de trabajo de puesto de nóminas en Dynamics 365 Human Resources.
author: jcart
manager: tfehr
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 72f3109f5bea36a390b04b7165fc3831d777b640
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5882072"
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

