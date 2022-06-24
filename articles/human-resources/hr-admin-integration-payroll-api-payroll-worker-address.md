---
title: Dirección del trabajador de la nómina
description: Este artículo proporciona detalles y una consulta de ejemplo para la entidad de dirección de trabajador de nóminas en Dynamics 365 Human Resources.
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
ms.openlocfilehash: 683994b24113b8c2017f1bb3c1055e7e0f0eb75e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901129"
---
# <a name="payroll-worker-address"></a>Dirección del trabajador de la nómina


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo describe la entidad de dirección de trabajador de nómina para Dynamics 365 Human Resources.

Nombre físico: mshr_payrollworkeraddressentity.

### <a name="description"></a>Descripción

Esta entidad proporciona la ubicación de residencia de nómina y el lugar de trabajo de nómina para un empleado determinado.

## <a name="properties"></a>Propiedades

| Propiedad</br>**Nombre físico**</br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Número de personal**</br>mshr_personnelnumber</br>*Cadena* | Solo lectura | El número de personal exclusivo del empleado. |
| **Id. de ubicación**</br>mshr_locationidbr>*String* | Solo lectura | El id. para la dirección. |
| **Vivió en dirección**</br>mshr_islivedinaddressbr </br> *[Conjunto de opciones mshr_NoYes](hr-admin-integration-payroll-api-no-yes.md)* | Solo lectura | Un valor que indica si la dirección es donde vive el empleado. |
| **Trabajó en dirección** </br> mshr_isworkedinaddressbr </br>*[Conjunto de opciones mshr_NoYes](hr-admin-integration-payroll-api-no-yes.md)* | Solo lectura | Un valor que indica si la dirección es donde trabaja el empleado. |
| **Región del país**</br>mshr_countryregionid</br>*Cadena* | Solo lectura</br>Obligatorio | El país o región definidos para la dirección. |
| **Código postal**</br>mshr_zipcode<br>*Cadena* | Solo lectura | El número de identificación definido para el empleado. |
| **Calle**</br>mshr_street</br>*Cadena* | Solo lectura | Calle definida para la dirección. |
| **Ciudad**</br>mshr_city</br>*Cadena* | Solo lectura | Ciudad definida para la dirección. |
| **Estado o provincia**</br>mshr_state</br>*Cadena* | Solo lectura | El estado o provincia definidos para la dirección. |
| **Provincia**</br>mshr_county</br>*Cadena* | Solo lectura | Condado definido para la dirección. |
| **Válido desde**</br>mshr_postaladdressvalidfrom</br>*Desplazamineto de fecha y hora* | Solo lectura | Fecha a partir de la cual es válida la dirección. |
| **Válido hasta**</br>mshr_postaladdressvalidto</br>*Desplazamineto de fecha y hora* | Solo lectura | Fecha hasta la cual es válida la dirección. |
| **Campo primario**</br>mshr_primaryfield</br>*Cadena* | Solo lectura | El campo primario. |
| **Id. de dirección del trabajador de la nómina**</br>mshr_payrollworkeraddressentityid</br>*GUID* | Generado por el sistema | Un valor de identificador único global (GUID) generado por el sistema para identificar de forma exclusiva la dirección. |

## <a name="relations"></a>Relaciones

| Valor de la propiedad | Entidad relacionada | Propiedad de navegación | Tipo de recopilación |
| --- | --- | --- | --- |
| _mshr_fk_worker_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Worker_id | mshr_FK_PayrollEmployeeEntity_Address |

## <a name="example-query"></a>Consulta de ejemplo

**Solicitud**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**Respuesta**

```json
{
    "mshr_personnelnumber": "000041",
    "mshr_locationid": "000000538",
    "mshr_islivedinaddress": 200000001,
    "mshr_isworkedinaddress": 200000000,
    "mshr_countryregionid": "USA",
    "mshr_zipcode": "99025",
    "mshr_street": "6543 Cypress Ave",
    "mshr_city": "Tacoma",
    "mshr_state": "WA",
    "mshr_county": "KING",
    "mshr_postaladdressvalidfrom": "2012-09-20T20:14:27Z",
    "mshr_postaladdressvalidto": "2154-12-31T23:59:59Z",
    "mshr_primaryfield": "000041 | 000000538 | 9/20/2012 08:14:27 pm",
    "_mshr_fk_worker_id_value": "00000d3c-0000-0000-d5ff-004105000000",
    "mshr_payrollworkeraddressentityid": "000006f0-0000-0000-f90f-014105000000"

}
```

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
