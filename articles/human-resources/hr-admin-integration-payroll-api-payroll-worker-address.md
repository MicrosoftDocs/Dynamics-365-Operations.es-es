---
title: Dirección del trabajador de la nómina
description: Este tema proporciona detalles y una consulta de ejemplo para la entidad de dirección de trabajador de nóminas en Dynamics 365 Human Resources.
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
ms.openlocfilehash: 898ca7b33e39ec33990fecc4c3a7229620fbfddd5ce8ad14423af38047187e55
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6761983"
---
# <a name="payroll-worker-address"></a>Dirección del trabajador de la nómina

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad de dirección de trabajador de nómina para Dynamics 365 Human Resources.

Nombre físico: mshr_payrollworkeraddressentity.

### <a name="description"></a>Descripción

Esta entidad proporciona la ubicación de residencia de nómina y el lugar de trabajo de nómina para un empleado determinado.

## <a name="properties"></a>Propiedades

| Propiedad</br>**Nombre físico**</br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Ciudad**</br>mshr_city</br>*Cadena* | Solo lectura</br>Obligatorio | Ciudad deifnida para la dirección.   |
| **Número de personal**</br>mshr_personnelnumber</br>*Cadena* | Solo lectura</br>Obligatorio | El número de personal exclusivo del empleado.  |
| **Región del país**</br>mshr_countryregionid</br>*Cadena* | Solo lectura</br>Obligatorio | Región del país para la dirección.  |
| **Válido desde**</br>mshr_postaladdressvalidfrom</br>*Desplazamineto de fecha y hora* | Solo lectura </br>Obligatorio | Fecha a partir de la cual es válida la dirección. |
| **Trabajó en dirección** </br> mshr_isworkedinaddressbr </br>*[Conjunto de opciones mshr_NoYes](hr-admin-integration-payroll-api-no-yes.md)* | Solo lectura</br>Obligatorio | Indica si la dirección es donde trabaja el empleado. |
| **Provincia**</br>mshr_county</br>*Cadena* | Solo lectura</br>Obligatorio | Condado deifnido para la dirección.  |
| **Id. de dirección del trabajador de la nómina**</br>mshr_payrollworkeraddressentityid</br>*GUID* | Obligatorio</br>Generado por el sistema | Valor GUID generado por el sistema para identificar de forma única la dirección.  |
| **Campo primario**</br>mshr_primaryfield</br>*Cadena* | Solo lectura</br>Obligatorio |  |
| **Calle**</br>mshr_street</br>*Cadena* | Solo lectura</br>Obligatorio | Calle deifnida para la dirección. |
| **Válido hasta**</br>mshr_postaladdressvalidto</br>*Desplazamineto de fecha y hora* | Solo lectura </br>Obligatorio | Fecha hasta la cual es válida la dirección.  |
| **Id. de ubicación**</br>mshr_locationidbr>*String* | Solo lectura <br>Obligatorio | El id. para la dirección.  |
| **Código postal**</br>mshr_zipcode<br>*Cadena* | Solo lectura <br>Obligatorio |El número de identificación definido para el empleado.  |
| **Vivió en dirección**</br>mshr_islivedinaddressbr </br> *[Conjunto de opciones mshr_NoYes](hr-admin-integration-payroll-api-no-yes.md)* | Solo lectura</br>Obligatorio | Indica si la dirección es donde vive el empleado. |
| **Estado o provincia**</br>mshr_state</br>*Cadena* | Solo lectura</br>Obligatorio | Estado deifnido para la dirección.  |

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
