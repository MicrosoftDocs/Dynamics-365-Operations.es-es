---
title: Historial de nombre de la persona
description: Este artículo proporciona detalles y una consulta de ejemplo para la entidad historial de nombres de la persona en Dynamics 365 Human Resources.
author: twheeloc
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e34b0d7bebd1c4037347161087ff3a4485a58878
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875782"
---
# <a name="person-name-history"></a>Historial de nombre de la persona


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo describe la entidad historial de nombres de la persona en Dynamics 365 Human Resources.

Nombre físico: mshr_dirpersonnamehistoricalentity.

### <a name="description"></a>Descripción

Esta entidad proporciona información sobre el historial de nombres de una persona determinada.

> [!IMPORTANT] 
> Los campos **FirstName**, **MiddleName**, **LastName**, **NameValidFrom** y **NameValidTo** ya no están disponibles en la entidad de nómina de empleado. Se han retirado para garantizar que solo haya una fuente de datos como origen de datos de esta entidad.

## <a name="properties"></a>Propiedades

| Propiedad</br>**Nombre físico**</br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Nombre**</br>mshr_firstname</br>*Cadena* | Solo lectura | El nombre. |
| **Prefijo de apellido**</br>mshr_lastnameprefix</br>*String*) | Solo lectura | El prefijo de apellido. |
| **Apellidos**</br>mshr_lastname</br>*String*) | Solo lectura | Apellidos. |
| **Segundo nombre**</br>mshr_middlename</br>*String*) | Solo lectura | El segundo nombre. |
| **Válido hasta**</br>mshr_validto</br>*String*) | Solo lectura | Fecha en la que el nombre es válido. |
| **Número de parte**</br>mshr_partynumber</br>*Cadena* | Solo lectura | Identificador único de la persona generado por el sistema y legible para el usuario. |
| **Campo primario**</br>mshr_primaryfield</br>*Cadena* | Solo lectura | El identificador único del registro. |
| **Identificador de entidad del Historial de nombre de la persona**</br>mshr_dirpersonnamehistoricalentityid</br>*GUID* | Generado por el sistema | Un valor de identificador único global (GUID) generado por el sistema para identificar de forma exclusiva el registro. |

## <a name="relations"></a>Relaciones

| Valor de la propiedad | Entidad relacionada | Propiedad de navegación | Tipo de recopilación |
| --- | --- | --- | --- |
| No aplicable | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | No aplicable | mshr_FK_PayrollEmployeeEntity_Name |

## <a name="example-query-for-payroll-employee"></a>Consulta de ejemplo para empleado de nómina

**Solicitud**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_dirpersonnamehistoricalentities?$filter=mshr_partynumber eq 'HR000001606'
```

**Respuesta**

```json
{
    "mshr_firstname": "Agustina",
    "mshr_lastnameprefix": "",
    "mshr_lastname": "Fierro",
    "mshr_middlename": "middle",
    "mshr_validto": "2021-09-10T21:23:53Z",
    "mshr_partynumber": "HR000001606",
    "mshr_primaryfield": "HR000001606 | ",
    "mshr_dirpersonnamehistoricalentityid": "00000832-0000-0000-c12b-014105000000",
    "mshr_validfrom": null
},
{
    "mshr_firstname": "Agustina",
    "mshr_lastnameprefix": "",
    "mshr_lastname": "Fierro",
    "mshr_middlename": "",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_partynumber": "HR000001606",
    "mshr_primaryfield": "HR000001606 | 9/10/2021 09:23:54 pm",
    "mshr_dirpersonnamehistoricalentityid": "00000832-0000-0000-d20b-000010000000",
    "mshr_validfrom": "2021-09-10T21:23:54Z"
}
```

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
