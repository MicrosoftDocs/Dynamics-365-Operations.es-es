---
title: Empleado con nómina
description: Este tema proporciona detalles y una consulta de ejemplo para la entidad Empleado de nóminas en Dynamics 365 Human Resources.
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
ms.openlocfilehash: d3977b758f65875a36749a49459c2a81459a7b69
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5882074"
---
# <a name="payroll-employee"></a>Empleado con nómina

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema proporciona detalles y una consulta de ejemplo para la entidad Empleado de nóminas en Dynamics 365 Human Resources.

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Número de personal**<br>mshr_personnelnumber<br>*Cadena* | Solo lectura<br>Obligatorio | El número de personal exclusivo del empleado. |
| **Campo primario**<br>mshr_primaryfield<br>*Cadena* | Obligatorio<br>Generado por el sistema |  |
| **Apellidos**<br>mshr_lastname<br>*Cadena* | Solo lectura<br>Obligatorio | Apellido del empleado. |
| **Id. de entidad jurídica**<br>mshr_legalentityID<br>*Cadena* | Solo lectura<br>Obligatorio | Especifica la entidad jurídica (empresa). |
| **Válido desde**<br>mshr_namevalidfrom<br>*Desplazamineto de fecha y hora* | Solo lectura <br>Obligatorio | Fecha de inicio de la validez de la información del empleado.  |
| **Género**<br>mshr_gender<br>*Int32* | Solo lectura<br>Obligatorio | El sexo del empleado. |
| **ID de entidad de empleado de nómina**<br>mshr_payrollemployeeentityid<br>*GUID* | Obligatorio<br>Generado por el sistema | Valor GUID generado por el sistema para identificar de forma única el empleado. |
| **Fecha inicial del empleo**<br>mshr_employmentstartdate<br>*Desplazamineto de fecha y hora* | Solo lectura<br>Obligatorio | La fecha de inicio del empleo del empleado. |
| **Id. de tipo de identificación**<br>mshr_identificationtypeid<br>*Cadena* |Solo lectura<br>Obligatorio | El tipo de identificación definido para el empleado. |
| **Fecha final del empleo**<br>mshr_employmentenddate<br>*Desplazamineto de fecha y hora* | Solo lectura<br>Obligatorio |La fecha de finalización del empleo del empleado.  |
| **Id. de área de datos**<br>mshr_dataareaid_id<br>*GUID* | Obligatorio <br>Generado por el sistema | Valor GUID generado por el sistema que identifica a la entidad jurídica (empresa). |
| **Válido hasta**<br>mshr_namevalidto<br>*Desplazamineto de fecha y hora* |  Solo lectura<br>Obligatorio | Fecha de finalización de la validez de la información del empleado. |
| **Fecha de nacimiento**<br>mshr_birthdate<br>*Desplazamineto de fecha y hora* | Solo lectura <br>Obligatorio | La fecha de nacimiento del empleado. |
| **El número de identificación para**<br>mshr_identificationnumber<br>*Cadena* | Solo lectura <br>Obligatorio |El número de identificación definido para el empleado.  |
| **Nombre**<br>mshr_firstname<br>*Cadena* | Solo lectura<br>Obligatorio | Nombre del empleado. |
| **Segundo nombre**<br>mshr_middlename<br>*Cadena* | Solo lectura<br>Obligatorio |Segundo nombre del empleado.  |

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
            "mshr_firstname": "Cassie",
            "mshr_middlename": "Lassie",
            "mshr_lastname": "Hicks",
            "mshr_namevalidfrom": "2021-03-12T20:34:25Z",
            "mshr_namevalidto": "2154-12-31T23:59:59Z",
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
