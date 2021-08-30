---
title: Empleado con nómina
description: Este tema proporciona detalles y una consulta de ejemplo para la entidad Empleado de nóminas en Dynamics 365 Human Resources.
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
ms.openlocfilehash: 20e74e97f98d0bc0fd454d54cbf969d4f1b46c7c98b2949b0ed8cfe671312dd2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768200"
---
# <a name="payroll-employee"></a>Empleado con nómina

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad empleado de nómina para Dynamics 365 Human Resources.

Nombre físico: mshr_payrollemployeeentity.

### <a name="description"></a>Descripción

Esta entidad proporciona información sobre el empleado. Debes configurar los [parámetros de integración de nómina](hr-admin-integration-payroll-api-parameters.md) antes de usar esta entidad.

>[!IMPORTANT] 
>**FirstName**, **MiddleName**, **LastName**, **NameValidFrom** y **NameValidTo** ya no están disponibles en esta entidad. Esto garantiza que solo haya una fuente de datos con fecha de vigencia que respalde esta entidad.
>Estos campos estarán disponibles en el **DirPersonNameHistoricalEntity**, que se publicó en la Platform update 43. Hay una relación OData de **PayrollEmployeeEntity** para **DirPersonNameHistoricalEntity** en el campo **Persona**. 

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Número de personal**<br>mshr_personnelnumber<br>*Cadena* | Solo lectura | El número de personal exclusivo del empleado. |
| **Campo primario**<br>mshr_primaryfield<br>*Cadena* | Solo lectura<br>Generado por el sistema |  |
| **Id. de entidad jurídica**<br>mshr_legalentityID<br>*Cadena* | Solo lectura | Especifica la entidad jurídica (empresa). |
| **Género**<br>mshr_gender<br>[Opción mshr_hcmpersongender establecida](hr-admin-integration-payroll-api-gender.md) | Solo lectura | El sexo del empleado. |
| **ID de entidad de empleado de nómina**<br>mshr_payrollemployeeentityid<br>*GUID* | Obligatorio<br>Generado por el sistema | Valor GUID generado por el sistema para identificar de forma única el empleado. |
| **Fecha inicial del empleo**<br>mshr_employmentstartdate<br>*Desplazamineto de fecha y hora* | Solo lectura | La fecha de inicio del empleo del empleado. |
| **Id. de tipo de identificación**<br>mshr_identificationtypeid<br>*Cadena* |Solo lectura | El tipo de identificación definido para el empleado. |
| **Fecha final del empleo**<br>mshr_employmentenddate<br>*Desplazamineto de fecha y hora* | Solo lectura |La fecha de finalización del empleo del empleado.  |
| **Id. de área de datos**<br>mshr_dataareaid_id<br>*GUID* | Solo lectura <br>Generado por el sistema | Valor GUID generado por el sistema que identifica a la entidad jurídica (empresa). |
| **Válido hasta**<br>mshr_namevalidto<br>*Desplazamineto de fecha y hora* |  Solo lectura | Fecha de finalización de la validez de la información del empleado. |
| **Fecha de nacimiento**<br>mshr_birthdate<br>*Desplazamineto de fecha y hora* | Solo lectura | La fecha de nacimiento del empleado. |
| **El número de identificación para**<br>mshr_identificationnumber<br>*Cadena* | Solo lectura |El número de identificación definido para el empleado.  |

## <a name="example-query-for-payroll-employee"></a>Consulta de ejemplo para empleado de nómina

**Solicitud**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollemployeeentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_identificationtypeid eq @idtype and mshr_namevalidfrom le @asofdate and mshr_namevalidto ge @asofdate&@personnelnumber='000041'&@idtype='SSN'&@asofdate=2021-04-01
```

**Respuesta**

```json
{
    "mshr_legalentityid": "USMF",
    "mshr_personnelnumber": "000041",
    "mshr_employmentstartdate": "2011-04-05T07:00:00Z",
    "mshr_employmentenddate": "2154-12-31T23:59:59Z",
    "mshr_birthdate": "1987-09-12T00:00:00Z",
    "mshr_gender": 200000002,
    "mshr_identificationtypeid": "SSN",
    "mshr_identificationnumber": "888-99-9342",
    "mshr_dataareaid": "USMF",
    "mshr_primaryfield": "000041 | USMF | 4/5/2011 07:00:00 am",
    "_mshr_fk_worker_id_value": "000000ad-0000-0000-d5ff-004105000000",
    "_mshr_fk_employment_id_value": "00000d0d-0000-0000-0600-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
    "mshr_payrollemployeeentityid": "00000d3c-0000-0000-d5ff-004105000000",
    "_mshr_dataareaid_id_value": null
}
```
## <a name="see-also"></a>Consulte también

[Introducción a la API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
