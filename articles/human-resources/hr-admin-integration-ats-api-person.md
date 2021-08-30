---
title: Persona
description: Este tema describe la entidad de persona para Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ab3dd62785e6f4d94d5bd6faeed5dbc965a7a0573eaeee1c880062ab69b2dc21
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778829"
---
# <a name="person"></a>Persona

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad de persona para Dynamics 365 Human Resources.

Nombre físico: mshr_dirpersonentity

### <a name="description"></a>Descripción

Esta entidad proporciona la información personal de la persona que es el candidato.

## <a name="json-representation"></a>Representación JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_name": "String",
    "mshr_namealias": "String",
    "mshr_knownas": "String",
    "mshr_languageid": "String",
    "mshr_addressbooks": "String",
    "mshr_anniversaryday": Int,
    "mshr_anniversarymonth": Int,
    "mshr_anniversaryyear": Int,
    "mshr_birthday": Int,
    "mshr_birthmonth": Int,
    "mshr_birthyear": Int,
    "mshr_childrennames": "String",
    "mshr_gender": Int,
    "mshr_hobbies": "String",
    "mshr_initials": "String",
    "mshr_maritalstatus": Int,
    "mshr_phoneticfirstname": "String",
    "mshr_phoneticlastname": "String",
    "mshr_phoneticmiddlename": "String",
    "mshr_personalsuffix": "String",
    "mshr_personaltitle": "String",
    "mshr_professionalsuffix": "String",
    "mshr_professionaltitle": "String",
    "mshr_fullprimaryaddress": "String",
    "mshr_addresscity": "String",
    "mshr_addresscountryregionid": "String",
    "mshr_addresscountryregionisocode": "String",
    "mshr_addresscounty": "String",
    "mshr_addressdistrictname": "String",
    "mshr_addresslatitude": Decimal,
    "mshr_addresslocationid": "000003212",
    "mshr_addresslocationroles": "Home",
    "mshr_addresslongitude": Decimal,
    "mshr_addressstate": "String",
    "mshr_addressstreet": "String",
    "mshr_addressvalidfrom": "Date",
    "mshr_addressvalidto": "Date",
    "mshr_addresszipcode": "String",
    "mshr_addressisprivate": Int,
    "mshr_addressdescription": "String",
    "mshr_primarycontactemail": "String",
    "mshr_primarycontactemaildescription": "String",
    "mshr_primarycontactemailisim": Int,
    "mshr_primarycontactemailpurpose": "String",
    "mshr_primarycontactfax": "String",
    "mshr_primarycontactfaxdescription": "String",
    "mshr_primarycontactfaxextension": "String",
    "mshr_primarycontactfaxpurpose": "String",
    "mshr_primarycontactphone": "String",
    "mshr_primarycontactphonedescription": "String",
    "mshr_primarycontactphoneextension": "String",
    "mshr_primarycontactphoneismobile": Int,
    "mshr_primarycontactphonepurpose": "String",
    "mshr_primarycontacttelex": "String",
    "mshr_primarycontacttelexdescription": "String",
    "mshr_primarycontacttelexpurpose": "String",
    "mshr_primarycontacturl": "String",
    "mshr_primarycontacturldescription": "String",
    "mshr_primarycontacturlpurpose": "String",
    "mshr_primarycontactfacebook": "String",
    "mshr_primarycontactfacebookdescription": "String",
    "mshr_primarycontactfacebookisprivate": Int,
    "mshr_primarycontactfacebookpurpose": "String",
    "mshr_primarycontactlinkedin": "String",
    "mshr_primarycontactlinkedindescription": "String",
    "mshr_primarycontactlinkedinisprivate": Int,
    "mshr_primarycontactlinkedinpurpose": "String",
    "mshr_primarycontacttwitter": "String",
    "mshr_primarycontacttwitterdescription": "String",
    "mshr_primarycontacttwitterisprivate": Int,
    "mshr_primarycontacttwitterpurpose": "String",
    "mshr_partytype": "String",
    "mshr_namesequencedisplayas": "String",
    "mshr_firstname": "String",
    "mshr_lastnameprefix": "String",
    "mshr_lastname": "String",
    "mshr_middlename": "String",
    "mshr_electroniclocationid": "String",
    "mshr_dirpersonentityid": "Guid",
    "mshr_addresstimezone": Int
}
```

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de entidad de persona**<br>mshr_dirpersonentityid<br>*GUID* | Solo lectura<br>Obligatorio<br>Generado por el sistema | Identificador único generado por el sistema para el registro de entidad. |
| **Número de parte**<br>mshr_partynumber<br>*Cadena* | Solo lectura<br>Obligatorio<br>Generado por el sistema | Identificador único de la persona generado por el sistema y legible para el usuario.  |
| **Nombre**<br>mshr_name<br>*Cadena* | Solo lectura<br>Obligatorio | El valor del campo es una concatenación de nombre, segundo nombre, prefijo de apellido y apellido en el orden definido en el campo **Visualizar secuencia de nombres como**. |
| **Alias del nombre**<br>mshr_namealias<br>*Cadena* | Leer/Escribir<br>Opcional | Un alias de nombre que se puede proporcionar para la persona. |
| **Conocido como**<br>mshr_knownas<br>*Cadena* | Leer/Escribir<br>Opcional | Un nombre que se puede usar para la persona si normalmente se conoce por otro nombre. |
| **Id. del idioma**<br>mshr_languageid<br>*Cadena* | Leer/Escribir<br>Opcional | El id. de idioma del idioma principal de la persona, como se define en el formato ISO 639-1. |
| **Libretas de direcciones**<br>mshr_addressbooks<br>*Cadena* | Leer/Escribir<br>Opcional | Libreta de direcciones a la que se puede asignar la persona. Las libretas de direcciones que se han configurado para la organización se enumeran en la entidad mshr_diraddressbooksentity. |
| **Día de aniversario**<br>mshr_anniversaryday<br>*Int* | Leer/Escribir<br>Opcional | El día de la fecha de aniversario de la persona. |
| **Mes de aniversario**<br>mshr_anniversarymonth<br>*Opción mshr_monthsofyear establecida* | Leer/Escribir<br>Opcional | El mes de la fecha de aniversario de la persona. |
| **Año de aniversario**<br>mshr_anniversaryyear<br>*Int* | Leer/Escribir<br>Opcional | El año de la fecha de aniversario de la persona. |
| **Día de nacimiento**<br>mshr_birthday<br>*Int* | Leer/Escribir<br>Opcional | El día de la fecha de nacimiento de la persona. |
| **Mes de nacimiento**<br>mshr_birthmonth<br>*Opción mshr_monthsofyear establecida* | Leer/Escribir<br>Opcional | El mes de la fecha de nacimiento de la persona. |
| **Año de nacimiento**<br>mshr_birthyear<br>*Int* | Leer/Escribir<br>Opcional | El año de la fecha de nacimiento de la persona. |
| **Nombres de niños**<br>mshr_childrennames<br>*Cadena* | Leer/Escribir<br>Opcional | Cadena para los nombres de los hijos de la persona. No se requiere delimitación. |
| **Género**<br>mshr_gender<br>*Opción mshr_hcmpersongender establecida* | Leer/Escribir<br>Opcional | Sexo de la persona. |
| **Aficiones**<br>mshr_hobbies<br>*Cadena* | Leer/Escribir<br>Opcional | Aficiones de la persona. |
| **Iniciales**<br>mshr_initials<br>*Cadena* | Leer/Escribir<br>Opcional | Iniciales del nombre de la persona. |
| **Estado civil**<br>mshr_maritalstatus<br>*Opción mshr_hcmpersonmaritalstatus establecida* | Leer/Escribir<br>Opcional | Estado civil de la persona. |
| **Primer nombre fonético**<br>mshr_phoneticfirstname<br>*Cadena* | Leer/Escribir<br>Opcional | La pronunciación fonética del nombre de la persona. |
| **Apellido fonético**<br>mshr_phoneticlastname<br>*Cadena* | Leer/Escribir<br>Opcional | La pronunciación fonética del apellido de la persona. |
| **Segundo nombre fonético**<br>mshr_phoneticmiddlename<br>*Cadena* | Leer/Escribir<br>Opcional | La pronunciación fonética del apellido de la persona. |
| **Sufijo personal**<br>mshr_personalsuffix<br>*Cadena* | Leer/Escribir<br>Opcional | Sufijo personal de la persona. Valores válidos en la entidad mshr_dirnameaffixentity donde mshr_type es el sufijo (200000001). |
| **Tratamiento personal**<br>mshr_personaltitle<br>*Cadena* | Leer/Escribir<br>Opcional | Tratamiento personal de la persona. Valores válidos en la entidad mshr_dirnameaffixentity, donde mshr_type es el tratamiento (200000000).
| **Sufijo profesional**<br>mshr_professionalsuffix<br>*Cadena* | Leer/Escribir<br>Opcional | Sufijo profesional. |
| **Título profesional**<br>mshr_professionaltitle<br>*Cadena* | Leer/Escribir<br>Opcional | Título profesional. |
| **Dirección principal completa**<br>mshr_fullprimaryaddress<br>*Cadena* | Leer/Escribir<br>Opcional | La dirección principal completa de la persona, una concatenación de los campos de dirección principal. |
| **Ciudad de dirección**<br>mshr_addresscity<br>*Cadena* | Leer/Escribir<br>Opcional | La ciudad de la dirección principal de la persona. Configurado en la entidad mshr_logisticsaddresscityentity. |
| **Región del país de la dirección**<br>mshr_addresscountryregionid<br>*Cadena* | Leer/Escribir<br>Opcional | El país o región de la dirección principal de la persona. Valores válidos de la entidad mshr_logisticsaddresscountryregionentity. |
| **Código ISO de la región del país de la dirección**<br>mshr_addresscountryregionisocode<br>*Cadena* | Leer/Escribir<br>Opcional | El código ISO del país de la dirección principal de la persona. |
| **Condado de la dirección**<br>mshr_addresscounty<br>*Cadena* | Leer/Escribir<br>Opcional | Condado de la dirección principal de la persona. Configurado en la entidad mshr_logisticsaddresscountyentity. |
| **Nombre de distrito de la dirección**<br>mshr_addressdistrictname<br>*Cadena* | Leer/Escribir<br>Opcional | El distrito de la dirección principal de la persona. Configurado en la entidad mshr_logisticsaddressdistrictentity. |
| **Latitud de la dirección**<br>mshr_addresslatitude<br>*Cadena* | Leer/Escribir<br>Opcional | Latitud de la dirección principal de la persona. |
| **Id. de ubicación de dirección**<br>mshr_addresslocationid<br>*Cadena* | Leer/Escribir<br>Opcional | El identificador único de la ubicación de la dirección principal de la persona. Valores válidos de la entidad mshr_logisticspostaladdresslocationcdsentity. |
| **Roles de ubicación de dirección**<br>mshr_addresslocationroles<br>*Cadena* | Leer/Escribir<br>Opcional | El rol de ubicación de la dirección principal de la persona. Configurado en la entidad mshr_logisticslocationrolecdsentity. |
| **Longitud de la dirección**<br>mshr_addresslongitude<br>*Cadena* |  Leer/Escribir<br>Opcional | Longitud de la dirección principal de la persona. |
| **Estado de la dirección**<br>mshr_addressstate<br>*Cadena* | Leer/Escribir<br>Opcional | Estado de la dirección principal de la persona. Configurado en la entidad mshr_logisticsaddressstateentity. |
| **Calle de la dirección**<br>mshr_addressstreet<br>*Cadena* | Leer/Escribir<br>Opcional | La calle de la dirección principal de la persona. |
| **Dirección válida desde**<br>mshr_addressvalidfrom<br>*Fecha* | Leer/Escribir<br>Opcional | La fecha a partir de la cual la dirección principal de la persona es válida. |
| **Dirección válida hasta**<br>mshr_addressvalidto<br>*Fecha* | Leer/Escribir<br>Opcional | La fecha hasta la cual la dirección principal de la persona es válida. |
| **Código postal de la dirección**<br>mshr_addresszipcode<br>*Cadena* | Leer/Escribir<br>Opcional | Código postal de la dirección principal de la persona. Configurado en la entidad mshr_logisticsaddresspostalcodeentity. |
| **La dirección es privada**<br>mshr_addressisprivate<br>*Opción mshr_noyes establecida* | Leer/Escribir<br>Opcional | Determina si la dirección principal de la persona se comparte con otras personas de la organización. |
| **Descripción de la dirección**<br>mshr_addressdescription<br>*Cadena* | Leer/Escribir<br>Opcional | Descripción de la dirección principal de la persona. |
| **Correo electrónico de contacto principal**<br>mshr_primarycontactemail<br>*Cadena* | Leer/Escribir<br>Opcional | La dirección de correo electrónico principal de la persona. |
| **Descripción de correo electrónico de contacto principal**<br>mshr_primarycontactemaildescription<br>*Cadena* | Leer/Escribir<br>Opcional | Una descripción proporcionada para la dirección de correo electrónico principal. |
| **El correo electrónico de contacto principal es IM**<br>mshr_primarycontactemailisim<br>*Opción mshr_noyes establecida* | Leer/Escribir<br>Opcional | Determina si la dirección de correo electrónico principal está disponible para mensajes instantáneos. |
| **Finalidad del correo electrónico de contacto principal**<br>mshr_primarycontactemailpurpose<br>*Cadena* | Leer/Escribir<br>Opcional | Finalidad del correo electrónico principal. Configurado en la entidad mshr_logisticslocationroleentity. |
| **Fax de contacto principal**<br>mshr_primarycontactfax<br>*Cadena* | Leer/Escribir<br>Opcional | Número de fax principal. |
| **Descripción de fax de contacto principal**<br>mshr_primarycontactfaxdescription<br>*Cadena* | Leer/Escribir<br>Opcional | Descripción ofrecida del número de fax principal. |
| **Extensión de fax de contacto principal**<br>mshr_primarycontactfaxextension<br>*Cadena* | Leer/Escribir<br>Opcional | La extensión del número de fax principal. |
| **Finalidad del fax de contacto principal**<br>mshr_primarycontactfaxpurpose<br>*Cadena* | Leer/Escribir<br>Opcional | Finalidad del número de fax principal. Configurado en la entidad mshr_logisticslocationroleentity.
| **Teléfono de contacto principal**<br>mshr_primarycontactphone<br>*Cadena* | Leer/Escribir<br>Opcional | Número de teléfono principal. |
| **Descripción de teléfono de contacto principal**<br>mshr_primarycontactphonedescription<br>*Cadena* | Leer/Escribir<br>Opcional | Descripción ofrecida del número de teléfono principal. |
| **Extensión de teléfono de contacto principal**<br>mshr_primarycontactphoneextension<br>*Cadena* | Leer/Escribir<br>Opcional | La extensión del número de teléfono principal. |
| **El teléfono de contacto principal es móvil**<br>mshr_primarycontactphoneismobile<br>*Opción mshr_noyes establecida* | Leer/Escribir<br>Opcional | Determina si el número de teléfono principal es un teléfono móvil. |
| **Finalidad del teléfono de contacto principal**<br>mshr_primarycontactphonepurpose<br>*Cadena* | Leer/Escribir<br>Opcional | Finalidad del número de teléfono principal. Configurado en la entidad mshr_logisticslocationroleentity. |
| **Telex de contacto principal**<br>mshr_primarycontacttelex<br>*Cadena* | Leer/Escribir<br>Opcional | Número de telex principal. |
| **Descripción de telex de contacto principal**<br>mshr_primarycontacttelexdescription<br>*Cadena* | Leer/Escribir<br>Opcional | Descripción ofrecida para el número de telex principal de la persona. |
| **Finalidad del telex de contacto principal**<br>mshr_primarycontacttelexpurpose<br>*Cadena* | Leer/Escribir<br>Opcional | El propósito del número de télex principal de la persona. Configurado en la entidad mshr_logisticslocationroleentity. |
| **URL de contacto principal**<br>mshr_primarycontacturl<br>*Cadena* | Leer/Escribir<br>Opcional | La URL principal. |
| **Descripción de URL de contacto principal**<br>mshr_primarycontacturldescription<br>*Cadena* | Leer/Escribir<br>Opcional | Descripción facilitada de la URL principal de la persona. |
| **Finalidad de la URL de contacto principal**<br>mshr_primarycontacturldescription<br>*Cadena* | Leer/Escribir<br>Opcional | Finalidad de la URL principal de la persona. Configurado en la entidad mshr_logisticslocationroleentity. |
| **Contacto principal de Facebook**<br>mshr_primarycontactfacebook<br>*Cadena* | Leer/Escribir<br>Opcional | Cuenta principal de Facebook. Identificado por id. de usuario. |
| **Descripción de contacto principal de Facebook**<br>mshr_primarycontactfacebookdescription<br>*Cadena* | Leer/Escribir<br>Opcional | Descripción facilitada de la cuenta principal de Facebook de la persona. |
| **Contacto primario de Facebook privado**<br>mshr_primarycontactfacebookisprivate<br>*Opción mshr_noyes establecida* | Leer/Escribir<br>Opcional | Determina si la cuenta principal de Facebook es visible para otros usuarios. |
| **Finalidad del contacto principal de Facebook**<br>mshr_primarycontactfacebookpurpose<br>*Cadena* | Leer/Escribir<br>Opcional | Finalidad de la cuenta principal de Facebook de la persona. Configurado en la entidad mshr_logisticslocationroleentity. |
| **Contacto principal de LinkedIn**<br>mshr_primarycontactlinkedin<br>*Cadena* | Leer/Escribir<br>Opcional | Cuenta principal de LinkedIn. Identificado por nombre de usuario. |
| **Descripción de contacto principal de LinkedIn**<br>mshr_primarycontactlinkedindescription<br>*Cadena* | Leer/Escribir<br>Opcional | Descripción facilitada de la cuenta principal de LinkedIn de la persona. |
| **Contacto primario de LinkedIn privado**<br>mshr_primarycontactlinkedinisprivate<br>*Opción mshr_noyes establecida* | Leer/Escribir<br>Opcional | Determina si la información de cuenta principal de la persona de LinkedIn se comparte con otros usuarios. |
| **Finalidad del contacto principal de LinkedIn**<br>mshr_primarycontactlinkedinpurpose<br>*Cadena* | Leer/Escribir<br>Opcional | Finalidad de la cuenta principal de LinkedIn de la persona. Configurado en la entidad mshr_logisticslocationroleentity. |
| **Contacto principal de Twitter**<br>mshr_primarycontacttwitter<br>*Cadena* | Leer/Escribir<br>Opcional | La cuenta de Twitter principal de la persona. Identificado por @nombre de usuario. |
| **Descripción del contacto principal de Twitter**<br>mshr_primarycontacttwitterdescription<br>*Cadena* | Leer/Escribir<br>Opcional | Descripción facilitada de la cuenta principal de Twitter de la persona. |
| **Contacto primario de Twitter privado**<br>mshr_primarycontacttwitterisprivate<br>*Opción mshr_noyes establecida* | Leer/Escribir<br>Opcional | Determina si la información de cuenta principal de la persona de Twitter se comparte con otros usuarios. |
| **Finalidad del contacto principal de Twitter**<br>mshr_primarycontacttwitterpurpose<br>*Cadena* | Leer/Escribir<br>Opcional | Finalidad de la cuenta principal de Twitter de la persona. Configurado en la entidad mshr_logisticslocationroleentity. |
| **Tipo de parte**<br>mshr_partytype<br>*Cadena* | Leer/Escribir<br>Opcional | El tipo de parte de la persona. Siempre será **Persona** en los candidatos. |
| **Visualización de secuencia de nombres como**<br>mshr_namesequencedisplayas<br>*Cadena* | Leer/Escribir<br>Opcional | La secuencia en la que se concatenan las propiedades del nombre de la persona desde el valor de la propiedad Nombre (mshr_name). |
| **Nombre**<br>mshr_firstname<br>*Cadena* | Leer/Escribir<br>Obligatorio | Nombre de la persona. |
| **Segundo nombre**<br>mshr_middlename<br>*Cadena* | Leer/Escribir<br>Opcional | Segundo nombre de la persona. |
| **Prefijo de apellido**<br>mshr_lastnameprefix<br>*Cadena* | Leer/Escribir<br>Opcional | El prefijo del apellido de la persona. |
| **Apellidos**<br>mshr_lastname<br>*Cadena* | Leer/Escribir<br>Opcional | Apellidos de la persona. |
| **Id. de ubicación electrónica**<br>mshr_electroniclocationid<br>*Cadena* | Leer/Escribir<br>Opcional | Id. de la ubicación electrónica de la persona. |
| **Zona horaria de la dirección**<br>mshr_addresstimezone<br>*Int* | Leer/Escribir<br>Opcional | Zona horaria de la dirección principal de la persona. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]