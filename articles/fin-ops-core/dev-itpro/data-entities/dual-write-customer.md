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
ms.openlocfilehash: 09d985e5c6816ec0c718aaf418f4e85fb828f1c6
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769692"
---
# <a name="integrated-customer-master"></a>Maestro de clientes integrado

[!include [banner](../includes/banner.md)]

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

Aplicaciones de Finance and Operations | Otras aplicaciones de Dynamics 365         | Descripción
----------------------------|---------------------------------|------------
Contactos V2 de CDS             | contactos                        | Esta plantilla sincroniza toda la información de contacto principal, secundaria, y terciaria, para clientes y proveedores.
Grupos de clientes             | msdyn_customergroups            | Esta plantilla sincroniza la información del grupo de clientes.
Método de pago de cliente     | msdyn_customerpaymentmethods    | Esta plantilla sincroniza la información del método de pago del cliente.
Clientes V3                | cuentas                        | Esta plantilla sincroniza la información de maestro de cliente para los clientes comerciales y organizativos.
Clientes V3                | contactos                        | Esta plantilla sincroniza los datos maestros de cliente para los consumidores y los usuarios finales.
Tarjeta de fidelización                | msdyn_loyaltycards              | Esta plantilla sincroniza la información de la tarjeta de fidelización del cliente.
Afijos de nombre                | msdyn_nameaffixes               | Esta plantilla sincroniza los datos de referencia de los afijos de nombre, para clientes y proveedores.
Líneas de días de pago de CDS V2    | msdyn_paymentdaylines           | Esta plantilla sincroniza los datos de referencia de las líneas de días de pago, para clientes y proveedores.
Días de pago de CDS            | msdyn_paymentdays               | Esta plantilla sincroniza los datos de referencia de los días de pago, para clientes y proveedores.
Líneas de multivencimientos      | msdyn_paymentschedulelines      | Sincroniza los datos de referencia de las líneas de programación de pago, para clientes y proveedores.
Multivencimientos            | msdyn_paymentschedules          | Esta plantilla sincroniza los datos de referencia de la programación de pago, para clientes y proveedores.
Condiciones de pago            | msdyn_paymentterms              | Esta plantilla sincroniza los datos de referencia de las los términos de pago (términos de pago), para clientes y proveedores.

[!include [banner](../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](dual-write/CDSContactsV2-contacts.md)]

[!include [mapping customer group](dual-write/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](dual-write/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](dual-write/CustomersV3-accounts.md)]

[!include [mapping customer contacts](dual-write/CustomersV3-contacts.md)]

[!include [mapping loyalty card](dual-write/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping name affixes](dual-write/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](dual-write/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](dual-write/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](dual-write/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](dual-write/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](dual-write/TermsofPayment-msdyn-paymentterms.md)]
