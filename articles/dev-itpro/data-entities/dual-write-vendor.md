---
title: Maestro de proveedores integrado
description: Este tema describe la integración de datos de proveedor entre Finance and Operations y Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 45808bc35aba04df6fcaf6b1cbfcc2461b0b65cb
ms.sourcegitcommit: 02c223b44ac7196df675afac61c6783f467d1983
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2019
ms.locfileid: "1789240"
---
## <a name="integrated-vendor-master"></a>Maestro de proveedores integrado

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

El término *proveedor* hace referencia a una organización proveedora o a un único propietario que forma parte del proceso de cadena de suministro y que suministra mercancías para el negocio. Aunque *proveedor* sea un concepto establecido en Microsoft Dynamics 365 for Finance and Operations, el concepto de proveedor no existe en Dynamics 365 para Customer Engagement. En su lugar, algunos negocios sobrecargan la entidad Cuenta para almacenar la información de clientes y proveedores. Otros usan un concepto personalizado de proveedor. La integración de Common Data Service admite ambos diseños. Por lo tanto, puede habilitar cualquiera de los dos en función de su escenario empresarial.

La integración de datos de proveedor entre Finance and Operations y Customer Engagement permite el control múltiple de los datos. Independientemente del origen de los datos de provededor, se encuentra integrado en segundo plano entre aplicaciones e infraestructuras diferentes. 

### <a name="vendor-data-flow"></a>Flujo de datos del proveedor

Si desea usar Customer Engagement para el control de proveedores y desea aislar la información de proveedor de la información de cliente, puede utilizar el nuevo diseño de proveedor.

![Flujo de datos del proveedor](media/dual-write-vendor-data-flow.png)

Si desea usar Customer Engagement para el control de proveedores y desea seguir usando la entidad Cuenta para almacenar la información de proveedor puede utilizar el diseño de proveedor ampliado. En este diseño, la información ampliada del proveedor, como el grupo de proveedores y el perfil de registro de proveedor, se almacena en el detalle del proveedor.

![Flujo de datos ampliado del proveedor](media/dual-write-vendor-detail.jpg)

La información de contacto del proveedor se parece a la información de contacto de cliente. En segundo plano, la información de la persona de contacto se almacena y se recupera de las mismas entidades.

## <a name="templates"></a>Plantillas

Los datos del proveedor incluyen toda la información sobre el proveedor, como el grupo de proveedores, las direcciones, la información de contacto, el perfil de pago y el perfil de factura. Una colección de mapas de entidad funciona conjuntamente durante la interacción de los datos del proveedor, como se muestra en la tabla siguiente.

Finance and Operations  | Aplicación Customer Engagement
------------------------|---------------------------------
Proveedor V2               | Cuenta
Proveedor V2               | Msdyn\_vendors
Contactos V2 de CDS         | Contacto
Grupos de proveedores           | Msdyn\_vendorgroups
Método de pago de proveedor   | Msdyn\_vendorpaymentmethods
Multivencimiento        | Msdyn\_paymentschedules
Multivencimiento        | Msdyn\_paymentschedulelines
Día de pago de CDS         | Msdyn\_paymentdays
Líneas de días de pago de CDS   | Msdyn\_paymentdaylines
Condiciones de pago        | Msdyn\_paymentterms
Afijos de nombre            | Msdyn\_nameaffixes

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="vendor-v2-and-account"></a>Proveedor V2 y cuenta 

Las empresas que utilizan la entidad Cuenta para almacenar la información de proveedor pueden continuar utilizandola de la misma manera. También pueden aprovechar la funcionalidad explícita del proveedor que está por venir debido a la integración de Finance and Operations.

## <a name="vendor-v2-and-msdyn_vendors"></a>Proveedor V2 y Msdyn\_vendors

Las empresas que utilizan una solución personalizada para los proveedores pueden aprovecharse del concepto de proveedor del componente estándar que se está introduciendo en Common Data Service debido a la integración de Finance and Operations. 

<!-- ![vendor mappings](media/dual-write-vendors-1.png) -->

<!-- ![vendor mappings](media/dual-write-vendors-2.png) -->

<!-- ![vendor mappings](media/dual-write-vendors-3.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
VENDORACCOUNTNUMBER | = | msdyn\_vendoraccountnumber
VENDORGROUPID | = | msdyn\_vendorgroupid.msdyn\_vendorgroup
VENDORORGANIZATIONNAME | = | msdyn\_name
VENDORPARTYTYPE | \>\< | msdyn\_isperson
PERSONFIRSTNAME | = | msdyn\_firstname
PERSONLASTNAME | = | msdyn\_lastname
CREDITLIMIT | = | msdyn\_vendorcreditlimit
ISFOREIGNENTITY | \>\< | msdyn\_isforeignentity
ISONETIMEVENDOR | \>\< | msdyn\_isonetimevendor
ADDRESSBUILDINGCOMPLIMENT | = | msdyn\_addressbuildingcompliment
PERSONCHILDRENNAMES | = | msdyn\_childrennames
ADDRESSCITY | = | msdyn\_addresscity
ADDRESSCOUNTRYREGIONID | = | msdyn\_addresscountryregionid
ADDRESSCOUNTRYREGIONISOCODE | = | msdyn\_addresscountryregionisocode
ADDRESSCOUNTYID | = | msdyn\_addresscountyid
CREDITRATING | = | msdyn\_creditrating
ADDRESSDESCRIPTION | = | msdyn\_addressdescription
ADDRESSDISTRICTNAME | = | msdyn\_addressdistrictname
DUNSNUMBER | = | msdyn\_dunsnumber
ETHNICORIGINID | = | msdyn\_ethnicorigin
FORMATTEDPRIMARYADDRESS | = | msdyn\_formattedprimaryaddress
PERSONHOBBIES | = | msdyn\_hobbies
PERSONINITIALS | = | msdyn\_initials
LANGUAGEID | = | msdyn\_languageid
PERSONLASTNAMEPREFIX | = | msdyn\_lastnameprefix
PERSONMIDDLENAME | = | msdyn\_middlename
ORGANIZATIONNUMBER | = | msdyn\_organizationnumber
OURACCOUNTNUMBER | = | msdyn\_ourvendoraccountnumber
PAYMENTID | = | msdyn\_paymentid
PERSONPHONETICFIRSTNAME | = | msdyn\_phoneticfirstname
PERSONPHONETICMIDDLENAME | = | msdyn\_phoneticmiddlename
PERSONPHONETICLASTNAME | = | msdyn\_phoneticlastname
ORGANIZATIONPHONETICNAME | = | msdyn\_organizationphoneticname
ADDRESSPOSTBOX | = | msdyn\_addresspostbox
PRIMARYURL | = | msdyn\_primarycontacturl
PRIMARYEMAILADDRESS | = | msdyn\_primaryemailaddress
PRIMARYEMAILADDRESSDESCRIPTION | = | msdyn\_primaryemailaddressdescription
PRIMARYFACEBOOK | = | msdyn\_primaryfacebook
PRIMARYFACEBOOKDESCRIPTION | = | msdyn\_primaryfacebookdescription
PRIMARYFAXNUMBER | = | msdyn\_primaryfaxnumber
PRIMARYFAXNUMBERDESCRIPTION | = | msdyn\_primaryfaxnumberdescription
PRIMARYFAXNUMBEREXTENSION | = | msdyn\_primaryfaxnumberextension
PRIMARYLINKEDIN | = | msdyn\_primarylinkedin
PRIMARYLINKEDINDESCRIPTION | = | msdyn\_primarylinkedindescription
PRIMARYPHONENUMBER | = | msdyn\_pimaryphonenumber
PRIMARYPHONENUMBERDESCRIPTION | = | msdyn\_primaryphonenumberdescription
PRIMARYPHONENUMBEREXTENSION | = | msdyn\_primaryphonenumberextension
PRIMARYTELEX | = | msdyn\_primarytelex
PRIMARYTELEXDESCRIPTION | = | msdyn\_primarytelexdescription
PRIMARYTWITTER | = | msdyn\_primarytwitter
PRIMARYTWITTERDESCRIPTION | = | msdyn\_primarytwitterdescription
PRIMARYURLDESCRIPTION | = | msdyn\_primaryurldescription
PERSONPROFESSIONALSUFFIX | = | msdyn\_professionalsuffix
PERSONPROFESSIONALTITLE | = | msdyn\_professionatitle
ADDRESSSTATEID | = | msdyn\_addressstateid
ADDRESSSTREET | = | msdyn\_addressstreet
ADDRESSSTREETNUMBER | = | msdyn\_addressstreetnumber
VENDORKNOWNASNAME | = | msdyn\_vendorknownasname
ADDRESSZIPCODE | = | msdyn\_addresszipcode
DEFAULTPAYMENTDAYNAME | = | msdyn\_defaultpaymentdayname.msdyn\_name
DEFAULTPAYMENTSCHEDULENAME | = | msdyn\_paymentschedule.msdyn\_name
DEFAULTPAYMENTTERMSNAME | = | msdyn\_paymentterms.msdyn\_name
HASONLYTAKENBIDS | \>\< | msdyn\_hasonlytakenbids
ISMINORITYOWNED | \>\< | msdyn\_isminorityowned
ISVENDORLOCALLYOWNED | \>\< | msdyn\_isvendorlocallyowned
ISSERVICEVETERANOWNED | \>\< | msdyn\_isserviceveteranowned
ISOWNERDISABLED | \>\< | msdyn\_ownerisdisabled
ISWOMANOWNER | \>\< | msdyn\_womanowner
PERSONANNIVERSARYDAY | = | msdyn\_personanniversaryday
PERSONANNIVERSARYYEAR | = | msdyn\_anniversaryyear
PERSONBIRTHDAY | = | msdyn\_birthday
PERSONBIRTHYEAR | = | msdyn\_birthyear
ORGANIZATIONEMPLOYEEAMOUNT | = | msdyn\_numberofemployees
VENDORHOLDRELEASEDATE | = | msdyn\_vendoronholdreleasedate
VENDORPARTYNUMBER | = | msdyn\_vendorpartynumber
ADDRESSLOCATIONID | = | msdyn\_addresslocationid
PERSONANNIVERSARYMONTH | = | msdyn\_vendorpersonanniversarymonth
PERSONBIRTHMONTH | = | msdyn\_vendorpersonbirthmonth
PERSONMARITALSTATUS | \>\< | msdyn\_maritalstatus
ADDRESSLATITUDE | \>\> | msdyn\_addresslatitude
ADDRESSLONGITUDE | \>\> | msdyn\_addresslongitude
ONHOLDSTATUS | \>\< | msdyn\_onholdstatus
CURRENCYCODE | = | msdyn\_currencycode.isocurrencycode
ISVENDORLOCATEDINHUBZONE | \>\< | msdyn\_isvendorlocatedinhubzone
DEFAULTVENDORPAYMENTMETHODNAME | = | msdyn\_vendorpaymentmethod.msdyn\_name
INVOICEVENDORACCOUNTNUMBER | = | msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber
PERSONGENDER | \>\< | msdyn\_gender
AREPRICESINCLUDINGSALESTAX | \>\< | msdyn\_priceincludessalestax
SALESTAXGROUPCODE | = | msdyn\_taxgroup.msdyn\_name
VENDORPRICETOLERANCEGROUPID | = | msdyn\_pricetolerancegroup.msdyn\_groupid

## <a name="contacts"></a>Contactos

Esta plantilla sincroniza toda la información de contacto princpal, secundaria y terciaria para clientes y proveedores entre Finance and Operations y Customer Engagement. Para obtener detalles sobre la asignación de entidad, consulte [Maestro de clientes integrado](dual-write-customer.md#contacts).

## <a name="vendor-groups"></a>Grupos de proveedores

Esta plantilla sincroniza la información de grupo de proveedores entre Finance and Operations y Customer Engagement.

<!-- ![vendor groups mappings](media/dual-write-vendor-groups.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
DEFAULTPAYMENTTERMNAME | = | msdyn\_paymentterms.msdyn\_name
DESCRIPCIÓN | = | msdyn\_description
VENDORGROUPID | = | msdyn\_vendorgroup
CLEARINGPERIODPAYMENTTERMNAME | = | msdyn\_clearingperiodpaymentpermname.msdyn\_name

### <a name="vendor-payment-method"></a>Método de pago de proveedor

Esta plantilla sincroniza la información de método de pago de proveedor entre Finance and Operations y Customer Engagement.

<!-- ![vendor payment method mappings](media/dual-write-vendor-payment-method.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
NOMBRE | = | msdyn\_name
DESCRIPCIÓN | = | msdyn\_description
SUMBYPERIOD | \>\< | msdyn\_sumbyperiod
DISCOUNTGRACEPERIODDAYS | = | msdyn\_discountgraceperioddays
PAYMENTSTATUS | \>\< | msdyn\_paymentstatus
ALLOWPAYMENTCOPIES | \>\< | msdyn\_allowpaymentcopies
PAYMENTTYPE | \>\< | msdyn\_paymenttype
LASTFILENUMBER | = | msdyn\_lastfilenumber
LASTFILENUMBERTODAY | = | msdyn\_lastfilenumbertoday
ACCOUNTTYPE | \>\< | msdyn\_accounttype
BRIDGINGPOSTINGENABLED | \>\< | msdyn\_bridgingposting
ENABLEPOSTDATEDCHECKCLEARINGPOSTING | \>\< | msdyn\_postdatedcheckclearingposting
PROMISSORYNOTEDRAFTTYPE | \>\< | msdyn\_promissorynotedrafttype
DIRECTDEBIT | \>\< | msdyn\_directdebit

