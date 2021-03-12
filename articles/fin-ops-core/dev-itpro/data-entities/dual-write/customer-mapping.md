---
title: Maestro de clientes integrado
description: En este tema se describe la integración de datos de cliente entre Finance and Operations y Dataverse.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: b7e9cd27bb918dc3a6088b45803329deb01a864e
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744411"
---
# <a name="integrated-customer-master"></a>Maestro de clientes integrado

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]


Los datos del cliente se pueden dominar en más de una aplicación de Dynamics 365. Por ejemplo, una fila de cliente puede originarse a través de la actividad de ventas en Dynamics 365 Sales (una aplicación basada en modelos en Dynamics 365), o una fila puede originarse a través de la actividad minorista en Dynamics 365 Commerce (una aplicación de Finance and Operations). No importa dónde se originan los datos del cliente, se integran detrás de escena. El maestro de clientes integrado le brinda la flexibilidad de dominar los datos del cliente en cualquier aplicación de Dynamics 365 y brinda una visión integral del cliente a través del conjunto de aplicaciones de Dynamics 365.

## <a name="customer-data-flow"></a>Flujo de datos del cliente

*Cliente* es un concepto bien definido en aplicaciones. Por lo tanto, la integración de los datos del cliente solo implica la armonización del concepto de cliente entre las dos aplicaciones. La ilustración siguiente muestra el flujo de datos del cliente.

![Flujo de datos del cliente](media/dual-write-customer-data-flow.png)

En general, los clientes pueden clasificarse en dos tipos: clientes comerciales/organizativos y consumidores/usuarios finales. Estos dos tipos de clientes se almacenan y controlan de forma diferente en Finance and Operations y en Dataverse.

En Finance and Operations, tanto los clientes comerciales/organizativos como los consumidores/usuarios finales se controlan en una sola tabla que se llama **CustTable** (CustCustomerV3Entity) y se clasifican según el atributo **Type**. (Si **Type** se establece en **Organization**, el cliente es un cliente comercial/organizativo y si **Type** se establece en **Person**, el cliente es consumidor/usuario final). La información de la persona de contacto principal se gestiona a través de la tabla SMMContactPersonEntity.

En Dataverse, los clientes comerciales/organizativos se controlan en la tabla de cuenta y se identifican como clientes cuando el atributo **RelationshipType** se establece en **Customer**. La tabla Contact representa tanto a consumidores/usuarios finales como la persona de contacto. Para proporcionar una clara separación entre un cliente/usuario final y una persona de contacto, la tabla **Contact** tiene un indicador booleano llamado **Sellable**. Si **Sellable** es **True**, el contacto es un consumidor/usuario final y se pueden crear citas y pedidos para dicho contacto. Si **Sellable** es **False**, el contacto es solo una persona de contacto principal de un cliente.

Cuando un contacto no sellable participa en un presupuesto o un proceso de pedido, **Sellable** se establece en **True** para marcar el contacto como sellable. Un contacto que se ha convertido en un contacto sellable permanece como contacto sellable.

## <a name="templates"></a>Plantillas

Los datos del cliente incluyen toda la información sobre el cliente, como el grupo de clientes, las direcciones, la información de contacto, el perfil de pago, el perfil de factura y el estado de fidelidad. Una colección de asignaciones de tabla funciona conjuntamente durante la interacción de los datos del cliente, como se muestra en la tabla siguiente.

Aplicaciones de Finance and Operations | Otras aplicaciones de Dynamics 365         | Descripción
----------------------------|---------------------------------|------------
Contactos V2 de CDS             | contactos                        | Esta plantilla sincroniza toda la información de contacto principal, secundaria, y terciaria, para clientes y proveedores.
Grupos de clientes             | msdyn_customergroups            | Esta plantilla sincroniza la información del grupo de clientes.
Método de pago de cliente     | msdyn_customerpaymentmethods    | Esta plantilla sincroniza la información del método de pago del cliente.
Clientes V3                | cuentas                        | Esta plantilla sincroniza la información de maestro de cliente para los clientes comerciales y organizativos.
Clientes V3                | contactos                        | Esta plantilla sincroniza los datos maestros de cliente para los consumidores y los usuarios finales.
Afijos de nombre                | msdyn_nameaffixes               | Esta plantilla sincroniza los datos de referencia de los afijos de nombre, para clientes y proveedores.
Líneas de días de pago de CDS V2    | msdyn_paymentdaylines           | Esta plantilla sincroniza los datos de referencia de las líneas de días de pago, para clientes y proveedores.
Días de pago de CDS            | msdyn_paymentdays               | Esta plantilla sincroniza los datos de referencia de los días de pago, para clientes y proveedores.
Líneas de multivencimientos      | msdyn_paymentschedulelines      | Sincroniza los datos de referencia de las líneas de programación de pago, para clientes y proveedores.
Multivencimientos            | msdyn_paymentschedules          | Esta plantilla sincroniza los datos de referencia de la programación de pago, para clientes y proveedores.
Condiciones de pago            | msdyn_paymentterms              | Esta plantilla sincroniza los datos de referencia de las los términos de pago (términos de pago), para clientes y proveedores.

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](includes/CDSContactsV2-contacts.md)]

[!include [mapping customer group](includes/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](includes/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](includes/CustomersV3-accounts.md)]

[!include [mapping customer contacts](includes/CustomersV3-contacts.md)]

[!include [mapping name affixes](includes/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](includes/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](includes/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](includes/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](includes/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](includes/TermsofPayment-msdyn-paymentterms.md)]
