---
title: Maestro de clientes integrado
description: Este artículo describe la integración de datos de cliente entre finanzas y operaciones y Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 1b16eab5c107a3176f0890372d397947698e71de
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111736"
---
# <a name="integrated-customer-master"></a>Maestro de clientes integrado

[!include [banner](../../includes/banner.md)]



Los datos del cliente se pueden dominar en más de una aplicación de Dynamics 365. Por ejemplo, una fila de cliente puede originarse a través de la actividad de ventas en Dynamics 365 Sales (una aplicación de Customer Engagement), o una fila puede originarse a través de la actividad minorista en Dynamics 365 Commerce (una aplicación de Finance and Operations). No importa dónde se originan los datos del cliente, se integran detrás de escena. El maestro de clientes integrado le brinda la flexibilidad de dominar los datos del cliente en cualquier aplicación de Dynamics 365 y brinda una visión integral del cliente a través del conjunto de aplicaciones de Dynamics 365.

## <a name="customer-data-flow"></a>Flujo de datos del cliente

*Cliente* es un concepto bien definido en aplicaciones. Por lo tanto, la integración de los datos del cliente solo implica la armonización del concepto de cliente entre las dos aplicaciones. La ilustración siguiente muestra el flujo de datos del cliente.

![Flujo de datos del cliente.](media/dual-write-customer-data-flow.png)

En general, los clientes pueden clasificarse en dos tipos: clientes comerciales/organizativos y consumidores/usuarios finales. Estos dos tipos de clientes se almacenan y controlan de forma diferente en finanzas y operaciones y Dataverse.

En finanzas y operaciones, tanto los clientes comerciales/organizativos como los consumidores/usuarios finales se controlan en una sola tabla que se llama **CustTable** (CustCustomerV3Entity) y se clasifican según el atributo **Type**. (Si **Type** se establece en **Organization**, el cliente es un cliente comercial/organizativo y si **Type** se establece en **Person**, el cliente es consumidor/usuario final). La información de la persona de contacto principal se gestiona a través de la tabla SMMContactPersonEntity.

En Dataverse, los clientes comerciales/organizativos se controlan en la tabla de cuenta y se identifican como clientes cuando el atributo **RelationshipType** se establece en **Customer**. La tabla Contact representa tanto a consumidores/usuarios finales como la persona de contacto. Para proporcionar una clara separación entre un cliente/usuario final y una persona de contacto, la tabla **Contact** tiene un indicador booleano llamado **Sellable**. Si **Sellable** es **True**, el contacto es un consumidor/usuario final y se pueden crear citas y pedidos para dicho contacto. Si **Sellable** es **False**, el contacto es solo una persona de contacto principal de un cliente.

Cuando un contacto no sellable participa en un presupuesto o un proceso de pedido, **Sellable** se establece en **True** para marcar el contacto como sellable. Un contacto que se ha convertido en un contacto sellable permanece como contacto sellable.

## <a name="templates"></a>Plantillas

Los datos del cliente incluyen toda la información sobre el cliente, como el grupo de clientes, las direcciones, la información de contacto, el perfil de pago, el perfil de factura y el estado de fidelidad. Una colección de asignaciones de tabla funciona conjuntamente durante la interacción de los datos del cliente, como se muestra en la tabla siguiente.

Aplicaciones de finanzas y operaciones | Aplicaciones Customer Engagement         | Descripción
----------------------------|---------------------------------|------------
[Contactos V2 de CDS](mapping-reference.md#115) | contactos | Esta plantilla sincroniza toda la información de contacto principal, secundaria, y terciaria, para clientes y proveedores.
[Grupos de clientes](mapping-reference.md#126) | msdyn_customergroups | Esta plantilla sincroniza la información del grupo de clientes.
[Método de pago de cliente](mapping-reference.md#127) | msdyn_customerpaymentmethods | Esta plantilla sincroniza la información del método de pago del cliente.
[Clientes V3](mapping-reference.md#101) | cuentas | Esta plantilla sincroniza la información de maestro de cliente para los clientes comerciales y organizativos.
[Clientes V3](mapping-reference.md#116) | contactos | Esta plantilla sincroniza los datos maestros de cliente para los consumidores y los usuarios finales.
[Afijos de nombre](mapping-reference.md#155) | msdyn_nameaffixes | Esta plantilla sincroniza los datos de referencia de los afijos de nombre, para clientes y proveedores.
[Líneas de días de pago de CDS V2](mapping-reference.md#157) | msdyn_paymentdaylines | Esta plantilla sincroniza los datos de referencia de las líneas de días de pago, para clientes y proveedores.
[Días de pago de CDS](mapping-reference.md#158) | msdyn_paymentdays | Esta plantilla sincroniza los datos de referencia de los días de pago, para clientes y proveedores.
[Líneas de multivencimientos](mapping-reference.md#159) | msdyn_paymentschedulelines | Sincroniza los datos de referencia de las líneas de programación de pago, para clientes y proveedores.
[Multivencimientos](mapping-reference.md#160) | msdyn_paymentschedules | Esta plantilla sincroniza los datos de referencia de la programación de pago, para clientes y proveedores.
[Condiciones de pago](mapping-reference.md#161) | msdyn_paymentterms | Esta plantilla sincroniza los datos de referencia de las los términos de pago (términos de pago), para clientes y proveedores.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

