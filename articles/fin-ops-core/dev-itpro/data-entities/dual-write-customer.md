---
title: Maestro de clientes integrado
description: Este tema describe la integración de datos de cliente entre Finance and Operations y Common Data Service.
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
ms.openlocfilehash: 6c8c94eb8ff04d489eb24b7e0f4642aef20a3b18
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182057"
---
## <a name="integrated-customer-master"></a>Maestro de clientes integrado

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Es habitual que los registros de cliente se controlen en más de una aplicación. Por ejemplo, la actividad de ventas puede aportar registros de clientes comerciales a través de una aplicación de Sales y el e-commerce o la venta minorista puede aportar registros de cliente mediante una aplicación de Finance and Operations. Independientemente del origen del registro de cliente, se encuentra integrado en segundo plano entre aplicaciones e infraestructuras diferentes. El control de cliente integrado ayuda a gestionar escenarios de múltiples maestros y proporciona una vista completa del cliente al conjunto de aplicaciones de Dynamics 365.

## <a name="customer-data-flow"></a>Flujo de datos del cliente

*Cliente* es un concepto bien definido en aplicaciones. Por lo tanto, la integración de los datos del cliente solo implica la armonización del concepto de cliente entre las dos aplicaciones. La ilustración siguiente muestra el flujo de datos del cliente.

![Flujo de datos del cliente](media/dual-write-customer-data-flow.png)

En general, los clientes pueden clasificarse en dos tipos: clientes comerciales/organizativos y consumidores/usuarios finales. Estos dos tipos de clientes se almacenan y controlan de forma diferente en Finance and Operations y Common Data Service.

En Finance and Operations, tanto clientes comerciales/organizativos como consumidores/usuarios finales se controlan en una sola tabla que se llama **CustTable** (CustomerCustomerV3Entity) y se clasifican en función del atributo **Type** . (Si **Type** se establece en **Organization**, el cliente es un cliente comercial/organizativo y si **Type** se establece en **Person**, el cliente es consumidor/usuario final). La información de la persona de contacto principal se gestiona a través de la entidad SMMContactPersonEntity.

En Common Data Service, los clientes comerciales/organizativos se controlan en la entidad de cuenta y se identifican como clientes cuando el atributo **RelationshipType** se establece en **Customer**. La entidad Contact representa tanto a consumidores/usuarios finales como la persona de contacto. Para proporcionar una clara separación entre un cliente/usuario final y una persona de contacto, la entidad **Contact** tiene un indicador booleano llamado **Sellable**. Si **Sellable** es **True**, el contacto es un consumidor/usuario final y se pueden crear citas y pedidos para dicho contacto. Si **Sellable** es **False**, el contacto es solo una persona de contacto principal de un cliente.

Cuando un contacto no sellable participa en un presupuesto o un proceso de pedido, **Sellable** se establece en **True** para marcar el contacto como sellable. Un contacto que se ha convertido en un contacto sellable permanece como contacto sellable.

## <a name="templates"></a>Plantillas

Los datos del cliente incluyen toda la información sobre el cliente, como el grupo de clientes, las direcciones, la información de contacto, el perfil de pago, el perfil de factura y el estado de fidelidad. Una colección de mapas de entidad funciona conjuntamente durante la interacción de los datos del cliente, como se muestra en la tabla siguiente.

Aplicaciones de Finance and Operations    | Otras aplicaciones de Dynamics 365
--------------------------|---------------------------------
Cliente V3               | Cuenta
Cliente V3               | Contacto
Contactos V2 de CDS           | Contacto
Grupos de clientes           | Msdyn\_customergroups
Método de pago de cliente   | Msdyn\_customerpaymentmethods
Tarjeta de fidelización              | Msdyn\_loyaltycards
Programa de pagos          | Msdyn\_paymentschedules
Programa de pagos          | Msdyn\_paymentschedulelines
Día de pago de CDS           | Msdyn\_paymentdays
Líneas de días de pago de CDS     | Msdyn\_paymentdaylines
Condiciones de pago          | Msdyn\_paymentterms
Afijos de nombre              | Msdyn\_nameaffixes

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="customer-v3-to-account"></a>Cliente V3 a cuenta

Esta plantilla sincroniza la información de maestro de cliente para los clientes comerciales y organizativos entre aplicaciones de Finance and Operations y Common Data Service.

<!-- ![](media/dual-write-account-1.png) -->

<!-- ![](media/dual-write-account-2.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
CUSTOMERACCOUNT | = | accountnumber
INVOICEADDRESSCITY | = | address2\_city
INVOICEADDRESSCOUNTRYREGIONISOCODE | = | address2\_country
INVOICEADDRESSCOUNTY | = | address2\_county
INVOICEADDRESSLATITUDE | \> | address2\_latitude
INVOICEADDRESSLONGITUDE | \> | address2\_longitude
INVOICEADDRESSSTATE | = | address2\_stateorprovince
INVOICEADDRESSSTREET | = | address2\_line1
INVOICEADDRESSZIPCODE | = | address2\_postalcode
CREDITLIMIT | = | creditlimit
DELIVERYADDRESSCITY | = | address1\_city
DELIVERYADDRESSCOUNTRYREGIONISOCODE | = | address1\_country
DELIVERYADDRESSCOUNTY | = | address1\_county
DELIVERYADDRESSLATITUDE | \> | address1\_latitude
DELIVERYADDRESSLONGITUDE | \> | address1\_longitude
DELIVERYADDRESSZIPCODE | = | address1\_postalcode
ORGANIZATIONNAME | = | name
ORGANIZATIONNUMBEROFEMPLOYEES | = | numberofemployees
PRIMARYCONTACTEMAIL | = | emailaddress1
PRIMARYCONTACTFAX | = | fax
PRIMARYCONTACTPHONE | = | telephone1
PRIMARYCONTACTTWITTER | = | primarytwitterid
PRIMARYCONTACTURL | = | websiteurl
SALESCURRENCYCODE | = | transactioncurrencyid.isocurrencycode
SALESMEMO | = | descripción
CREDITLIMITISMANDATORY | \>\< | msdyn\_creditlimitismandatory
CREDITRATING | = | msdyn\_creditrating
CUSTOMERGROUPID | = | msdyn\_customergroupid.msdyn\_groupid
IDENTIFICATIONNUMBER | = | msdyn\_identificationnumber
INVOICEACCOUNT | = | msdyn\_billingaccount.accountnumber
INVOICEADDRESS | \>\< | msdyn\_invoiceaddress
ISONETIMECUSTOMER | \>\< | msdyn\_onetimecustomer
ONHOLDSTATUS | \>\< | msdyn\_onholdstatus
PARTYCOUNTRY | = | msdyn\_partycountry
PARTYSTATE | = | msdyn\_partystateprovince
PAYMENTDAY | = | msdyn\_paymentday.msdyn\_name
PAYMENTMETHOD | = | msdyn\_customerpaymentmethod.msdyn\_name
PAYMENTSCHEDULE | = | msdyn\_paymentschedule.msdyn\_name
PAYMENTTERMS | = | msdyn\_paymentterm.msdyn\_name
PAYMENTTERMSBASEDAYS | = | msdyn\_paymenttermsbasedays
PRIMARYCONTACTFACEBOOK | = | msdyn\_primaryfacebookid
PRIMARYCONTACTFAXEXTENSION | = | msdyn\_faxextension
PRIMARYCONTACTLINKEDIN | = | msdyn\_primarylinkedinid
TAXEXEMPTNUMBER | = | msdyn\_taxexemptnumber
VENDORACCOUNT | = | msdyn\_vendor.msdyn\_vendoraccountnumber
PRIMARYCONTACTEMAILDESCRIPTION | = | msdyn\_emailaddress1description
PRIMARYCONTACTFACEBOOKDESCRIPTION | = | msdyn\_primaryfacebookdescription
PRIMARYCONTACTFAXDESCRIPTION | = | msdyn\_faxdescription
PRIMARYCONTACTLINKEDINDESCRIPTION | = | msdyn\_primarylinkedindescrption
PRIMARYCONTACTPHONEDESCRIPTION | = | msdyn\_telephone1description
PRIMARYCONTACTPHONEEXTENSION | = | msdyn\_telephone1extension
PRIMARYCONTACTTWITTERDESCRIPTION | = | msdyn\_primarytwitteriddescription
PRIMARYCONTACTURLDESCRIPTION | = | msdyn\_websiteurldescription
LANGUAGEID | \<\< | ninguno
DELIVERYADDRESSSTREET | = | address1\_line1
DELIVERYADDRESSSTATE | = | address1\_stateorprovince
ninguno | \>\> | address1\_addresstypecode
ninguno | \>\> | customertypecode
PARTYTYPE | \<\< | ninguno
PARTYNUMBER | = | msdyn\_partynumber

## <a name="customer-v3-to-contact"></a>Cliente V3 a contacto

Esta plantilla sincroniza los datos maestros del cliente para los consumidores y usuarios finales entre Finance and Operations y otras aplicaciones de Dynamics 365.

<!-- ![](media/dual-write-contact-1.png) -->
<!-- ![](media/dual-write-contact-2.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
ninguno | \>\> | msdyn\_sellable
PARTYTYPE | \<\< | ninguno
PARTYNUMBER | = | msdyn\_partynumber
CUSTOMERACCOUNT | = | msdyn\_contactpersonid
CUSTOMERGROUPID | = | msdyn\_customergroupid.msdyn\_groupid
PERSONFIRSTNAME | = | firstname
PERSONLASTNAME | = | lastname
PERSONMIDDLENAME | = | middlename
PERSONPROFESSIONALTITLE | = | jobtitle
PERSONGENDER | \>\< | gendercode
PERSONMARITALSTATUS | \>\< | familystatuscode
LANGUAGEID | \<\< | ninguno
ADDRESSCITY | = | address1\_city
ADDRESSCOUNTRYREGIONISOCODE | = | address1\_country
ADDRESSCOUNTY | = | address1\_county
ADDRESSLATITUDE | \> | address1\_latitude
ADDRESSLONGITUDE | \> | address1\_longitude
ADDRESSLOCATIONROLES | \<\< | ninguno
ADDRESSSTATE | = | address1\_stateorprovince
ADDRESSSTREET | = | address1\_line1
ADDRESSZIPCODE | = | address1\_postalcode
ADDRESSPOSTBOX | = | address1\_postofficebox
ninguno | \>\> | address1\_addresstypecode
INVOICEADDRESSCITY | = | address2\_city
INVOICEADDRESSCOUNTRYREGIONISOCODE | = | address2\_country
INVOICEADDRESSCOUNTY | = | address2\_county
INVOICEADDRESSLATITUDE | \> | address2\_latitude
INVOICEADDRESSLONGITUDE | \> | address2\_longitude
INVOICEADDRESSSTATE | = | address2\_stateorprovince
INVOICEADDRESSSTREET | = | address2\_line1
INVOICEADDRESSZIPCODE | = | address2\_postalcode
ninguno | \>\> | address2\_addresstypecode
DELIVERYADDRESSCITY | = | address3\_city
DELIVERYADDRESSCOUNTRYREGIONISOCODE | = | address3\_country
DELIVERYADDRESSCOUNTY | = | address3\_county
DELIVERYADDRESSLATITUDE | \> | address3\_latitude
DELIVERYADDRESSLONGITUDE | \>\> | address3\_longitude
DELIVERYADDRESSSTATE | = | address3\_stateorprovince
DELIVERYADDRESSSTREET | = | address3\_line1
DELIVERYADDRESSZIPCODE | = | address3\_postalcode
ninguno | \>\> | address3\_addresstypecode
PRIMARYCONTACTEMAIL | = | emailaddress1
PRIMARYCONTACTEMAILDESCRIPTION | = | msdyn\_emailaddress1description
PRIMARYCONTACTFAX | = | fax
PRIMARYCONTACTFAXDESCRIPTION | = | msdyn\_faxdescription
PRIMARYCONTACTFAXEXTENSION | = | msdyn\_faxextension
IDENTIFICATIONNUMBER | = | msdyn\_identificationnumber
PARTYCOUNTRY | = | msdyn\_partycountry
PARTYSTATE | = | msdyn\_partystateprovince
PRIMARYCONTACTFACEBOOK | = | msdyn\_primaryfacebookid
PRIMARYCONTACTFACEBOOKDESCRIPTION | = | msdyn\_primaryfacebookdescription
PRIMARYCONTACTLINKEDIN | = | msdyn\_primaryinkedinid
PRIMARYCONTACTLINKEDINDESCRIPTION | = | msdyn\_primarylinkedindescrption
PRIMARYCONTACTPHONE | = | telephone1
PRIMARYCONTACTPHONEDESCRIPTION | = | msdyn\_telephone1description
PRIMARYCONTACTPHONEEXTENSION | = | msdyn\_telephone1extension
PRIMARYCONTACTTWITTER | = | msdyn\_primarytwitterid
PRIMARYCONTACTTWITTERDESCRIPTION | = | msdyn\_primarytwitteriddescription
PRIMARYCONTACTURL | = | websiteurl
PRIMARYCONTACTURLDESCRIPTION | = | msdyn\_websiteurldescription
SALESCURRENCYCODE | = | transactioncurrencyid.isocurrencycode
SALESMEMO | = | descripción

## <a name="contacts"></a>Contactos

Esta plantilla sincroniza toda la información de contacto princpal, secundaria y terciaria para clientes y proveedores entre Finance and Operations y otras aplicaciones de Dynamics 365.

<!-- ![](media/dual-write-contacts.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
CONTACTPERSONPARTYNUMBER | = | msdyn\_partynumber
ASSOCIATEDCONTACTTYPE | \<\< | ninguno
FIRSTNAME | = | firstname
MIDDLENAME | = | middlename
LASTNAME | = | lastname
ASSOCIATEDCONTACTNUMBER | = | msdyn\_vendorcontactid.msdyn\_vendoraccountnumber
PRIMARYADDRESSCITY | = | address1\_city
PRIMARYADDRESSCOUNTRYREGIONID | = | address1\_country
PRIMARYADDRESSCOUNTYID | = | address1\_county
PRIMARYFAXNUMBER | = | fax
PRIMARYADDRESSSTATEID | = | address1\_stateorprovince
PRIMARYADDRESSSTREET | = | address1\_line1
PRIMARYADDRESSZIPCODE | = | address1\_postalcode
PRIMARYPHONENUMBER | = | telephone1
PRIMARYEMAILADDRESS | = | emailaddress1
EMPLOYMENTDEPARTMENT | = | departamento
NOTES | = | descripción
GENDER | \>\< | gendercode
GOVERNMENTIDENTIFICATIONNUMBER | = | governmentid
PRIMARYURL | = | websiteurl
MARITALSTATUS | \>\< | familystatuscode
ISRECEIVINGDIRECTMAIL | \>\< | donotemail
EMPLOYMENTPROFESSION | = | jobtitle
SPOUSENAME | = | spousesname
ninguno | \>\> | msdyn\_contactforvendor
ninguno | \>\> | msdyn\_contactpersonid

## <a name="customer-groups"></a>Grupos de clientes

Esta plantilla sincroniza la información de grupo de clientes entre Finance and Operations y otras aplicaciones de Dynamics 365.

<!-- ![](media/dual-write-customer-groups.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
CUSTOMERGROUPID | = | msdyn\_groupid
DESCRIPCIÓN | = | msdyn\_description
ISSALESTAXINCLUDEDINPRICE | \>\< | msdyn\_issalestaxincludedinprice
PAYMENTTERMID | = | msdyn\_paymenttermid.msdyn\_name
CLEARINGPERIODPAYMENTTERMNAME | = | msdyn\_clearingperiodpaymenttermname.msdyn\_name

## <a name="customer-payment-methods"></a>Métodos de pago de cliente

Esta plantilla sincroniza la información de método de pago del cliente entre Finance and Operations y otras aplicaciones de Dynamics 365.

<!-- ![](media/dual-write-customer-payment-methods.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
NOMBRE | = | msdyn\_name
ACCOUNTTYPE | \>\< | msdyn\_accounttype
DISCOUNTGRACEPERIODDAYS | = | msdyn\_discountgraceperioddays
BRIDGINGPOSTINGENABLED | \>\< | msdyn\_bridgingpostingenabled
ISSEPA | \>\< | msdyn\_issepa
LASTFILENUMBER | = | msdyn\_lastfilenumber
LASTFILENUMBERTODAY | = | msdyn\_lastfilenumbertoday
DESCRIPCIÓN | = | msdyn\_description
PAYMENTTYPE | \>\< | msdyn\_paymenttype
CREATEANDDRAWBILLOFEXCHANGEDURINGINVOICEPOSTING | \>\< | msdyn\_invoiceupdate
PAYMENTSTATUS | \>\< | msdyn\_paymentstatus
SUMBYPERIOD | \>\< | msdyn\_sumbyperiod
ENABLEPOSTDATEDCHECKCLEARINGPOSTING | \>\< | msdyn\_enablepostdatescheckclearingposting
BILLOFEXCHANGEDRAFTTYPE | \>\< | msdyn\_billofexchangedrafttype
DIRECTDEBIT | \>\< | msdyn\_directdebit

## <a name="loyalty-cards"></a>Tarjetas de fidelización

Esta plantilla sincroniza la información de la tarjeta de fidelización del cliente entre Finance and Operations y otras aplicaciones de Dynamics 365.

<!-- ![](media/dual-write-loyalty-cards.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
CARDNUMBER | = | msdyn\_cardnumber
CARDTENDERTYPE | \>\< | msdyn\_cardtendertype
PARTYNUMBER | = | msdyn\_partynumber
REPLACEMENTCARDNUMBER | \> | msdyn\_replacementcardnumber
OMOPERATINGUNITNUMBER | = | msdyn\_operatingunitnumber
LOYALTYENROLLMENTDATE | = | msdyn\_enrollmentdate

## <a name="payment-schedules"></a>Multivencimientos

Esta plantilla sincroniza los datos de referencia de multivencimientos para clientes y proveedores entre Finance and Operations y otras aplicaciones de Dynamics 365.

<!-- ![](media/dual-write-payment-schedules.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
NOMBRE | = | msdyn\_name
DESCRIPCIÓN | = | msdyn\_description
ALLOCATIONMETHOD | \>\< | msdyn\_allocationmethod
PAYMENTFREQUENCYUNITS | \>\< | msdyn\_paymentfrequencyunit
PAYMENTFREQUENCY | = | msdyn\_paymentfrequency
NUMBEROFPAYMENTS | = | msdyn\_numberofpayments
FIXEDPAYMENTAMOUNT | = | msdyn\_fixedpaymentamount
MINIMUMPAYMENTAMOUNT | = | msdyn\_minimumpaymentamount
SALESTAXALLOCATIONMETHOD | \>\< | msdyn\_salestaxallocationmethod
NOTES | = | msdyn\_note

## <a name="payment-schedule-lines"></a>Líneas de multivencimientos

Sincroniza los datos de referencia de las líneas multivencimientos para clientes y proveedores entre Finance and Operations y otras aplicaciones de Dynamics 365.

<!-- ![](media/dual-write-payment-schedule-lines.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
PAYMENTSCHEDULENAME | = | msdyn\_paymentschedule.msdyn\_name
PAYMENTSCHEDULENAME | \> | msdyn\_name
LINENUMBER | = | msdyn\_linenumber
PERIODSAFTERDUEDATE | = | msdyn\_periodsafterduedate
PERCENTORAMOUNT | \>\< | msdyn\_percentoramount
PERCENTORAMOUNTVALUE | = | msdyn\_percentoramountvalue

## <a name="payment-days"></a>Días de pago

Esta plantilla sincroniza los datos de referencia de los días de pago para clientes y proveedores entre Finance and Operations y otras aplicaciones de Dynamics 365.

<!-- ![](media/dual-write-payment-days.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
NOMBRE | = | msdyn\_name
DESCRIPCIÓN | = | msdyn\_description

## <a name="payment-day-lines"></a>Líneas de días de pago

Esta plantilla sincroniza los datos de referencia de las líneas de días de pago para clientes y proveedores entre Finance and Operations y otras aplicaciones de Dynamics 365.

<!-- ![](media/dual-write-payment-day-lines.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
CDSINTEGRATIONKEY | = | msdyn\_paymentdaylineid
FREQUENCY | \>\< | msdyn\_frequency
DAYOFWEEK | \>\< | msdyn\_dayofweek
DAYOFMONTH | = | msdyn\_dayofmonth
NOMBRE | = | msdyn\_paymentday.msdyn\_name

## <a name="payment-terms"></a>Condiciones de pago

Esta plantilla sincroniza los datos de referencia de las condiciones de pago (términos de pago) para clientes y proveedores entre Finance and Operations y aplicaciones de Dynamics 365.

<!-- ![](media/dual-write-payment-terms.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
DESCRIPCIÓN | = | msdyn\_description
NOMBRE | = | msdyn\_name
NUMBEROFMONTHS | = | msdyn\_numberofmonth
CUTOFFDAYOFMONTH | = | msdyn\_cutoffdayofmonth
ISCASHPAYMENT | \>\< | msdyn\_iscashpayment
NUMBEROFDAYS | = | msdyn\_days
ISCERTIFIEDCOMPANYCHECK | \>\< | msdyn\_iscertifiedcompanycheck
ISDEFAULTPAYMENTTERM | \>\< | msdyn\_isdefaultpaymentterm
CREDITCARDPAYMENTTYPE | \>\< | msdyn\_creditcardpaymenttype
CREDITCARDCREDITCHECKTYPE | \>\< | msdyn\_creditcardcreditchecktype
PAYMENTDAYNAME | = | msdyn\_paymentdayname.msdyn\_name
PAYMENTMETHODTYPE | \>\< | msdyn\_paymentmethodtype
PAYMENTSCHEDULENAME | = | msdyn\_paymentschedulename.msdyn\_name

## <a name="name-affixes"></a>Afijos de nombre

Esta plantilla sincroniza los datos de referencia de los afijos de nombre para clientes y proveedores entre Finance and Operations y otras aplicaciones de Dynamics 365.

<!-- ![](media/dual-write-name-affixes.png) -->

Campo de origen | Tipo de asignación | Campo de destino
---|---|---
AFFIX | = | msdyn\_affix
TIPO | \>\< | msdyn\_affixtype
DESCRIPCIÓN | = | msdyn\_description
