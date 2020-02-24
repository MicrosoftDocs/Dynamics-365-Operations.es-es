---
title: Maestro de proveedores integrado
description: Este tema describe la integración de datos de proveedor entre aplicaciones de Finance and Operations y Common Data Service.
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
ms.openlocfilehash: 2442a6869daac22a435c1a7504b93ea4b5c14747
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019994"
---
# <a name="integrated-vendor-master"></a>Maestro de proveedores integrado

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

El término *proveedor* hace referencia a una organización proveedora o a un único propietario que forma parte del proceso de cadena de suministro y que suministra mercancías para el negocio. Aunque *proveedor* sea un concepto establecido en las aplicaciones de Finance and Operations, el concepto de proveedor no existe en otras aplicaciones de Dynamics 365. En su lugar, algunos negocios sobrecargan la entidad Cuenta para almacenar la información de clientes y proveedores. Otros usan un concepto personalizado de proveedor. La integración de Common Data Service admite ambos diseños. Por lo tanto, puede habilitar cualquiera de los dos en función de su escenario empresarial.

La integración de datos de proveedor entre aplicaciones de Finance and Operations y otras aplicaciones de Dynamics 365 permite el control múltiple de los datos. Independientemente del origen de los datos de provededor, se encuentra integrado en segundo plano entre aplicaciones e infraestructuras diferentes. 

### <a name="vendor-data-flow"></a>Flujo de datos del proveedor

Si desea usar aplicaciones de Dynamics 365 para el control de proveedores y desea aislar la información de proveedor de la información de cliente, puede utilizar el nuevo diseño de proveedor.

![Flujo de datos del proveedor](media/dual-write-vendor-data-flow.png)

Si desea usar otras aplicaciones Dynamics 365 para el control de proveedores y desea seguir usando la entidad Cuenta para almacenar la información de proveedor puede utilizar el diseño de proveedor ampliado. En este diseño, la información ampliada del proveedor, como el grupo de proveedores y el perfil de registro de proveedor, se almacena en el detalle del proveedor.

![Flujo de datos ampliado del proveedor](media/dual-write-vendor-detail.jpg)

La información de contacto del proveedor se parece a la información de contacto de cliente. En segundo plano, la información de la persona de contacto se almacena y se recupera de las mismas entidades.

## <a name="templates"></a>Plantillas

Los datos del proveedor incluyen toda la información sobre el proveedor, como el grupo de proveedores, las direcciones, la información de contacto, el perfil de pago y el perfil de factura. Una colección de mapas de entidad funciona conjuntamente durante la interacción de los datos del proveedor, como se muestra en la tabla siguiente.

Aplicaciones de Finance and Operations | Otras aplicaciones de Dynamics 365         | Descripción
----------------------------|---------------------------------|------------
Proveedor V2               | Cuenta | Las empresas que utilizan la entidad Cuenta para almacenar la información de proveedor pueden continuar utilizandola de la misma manera. También pueden aprovechar la funcionalidad explícita del proveedor que está por venir debido a la integración de aplicaciones de Finance and Operations.
Proveedor V2               | Msdyn\_vendors | Las empresas que utilizan una solución personalizada para los proveedores pueden aprovecharse del concepto de proveedor del componente estándar que se está introduciendo en Common Data Service debido a la integración de aplicaciones de Finance and Operations. 
Grupos de proveedores | msdyn_vendorgroups | Esta plantilla sincroniza la información del grupo de proveedores.
Método de pago de proveedor | msdyn_vendorpaymentmethods | Esta plantilla sincroniza la información del método de pago del proveedor.
Contactos V2 de CDS             | contactos                        | La plantilla [contactos](customer-mapping.md#cds-contacts-v2-to-contacts) sincroniza toda la información de contacto principal, secundaria, y terciaria, para clientes y proveedores.
Líneas de multivencimientos      | msdyn_paymentschedulelines      | La plantilla [líneas de programación de pago](customer-mapping.md#payment-schedule-lines-to-msdyn_paymentschedulelines) sincroniza los datos de referencia para clientes y proveedores.
Multivencimientos            | msdyn_paymentschedules          | La plantilla [programaciones de pago](customer-mapping.md#payment-schedule-to-msdyn_paymentschedules) sincroniza los datos de referencia de la programación de pago, para clientes y proveedores.
Líneas de días de pago de CDS V2    | msdyn_paymentdaylines           | La plantilla [líneas de día de pago](customer-mapping.md#payment-day-lines-cds-v2-to-msdyn_paymentdaylines) sincroniza los datos de referencia de las líneas de día de pago para clientes y proveedores.
Días de pago de CDS            | msdyn_paymentdays               | La plantilla [días de pago](customer-mapping.md#payment-days-cds-to-msdyn_paymentdays) sincroniza los datos de referencia de los días de pago, para clientes y proveedores.
Condiciones de pago            | msdyn_paymentterms              | La plantilla [términos de pago](customer-mapping.md#terms-of-payment-to-msdyn_paymentterms) sincroniza los datos de referencia de los términos de pago, para clientes y proveedores.
Afijos de nombre                | msdyn_nameaffixes               | La plantilla [afijos de nombre](customer-mapping.md#name-affixes-to-msdyn_nameaffixes) sincroniza los datos de referencia de los afijos de nombre, para clientes y proveedores.

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [Vendors](includes/VendorsV2-msdyn-vendors.md)]

[!include [Vendor groups](includes/VendVendorGroup-msdyn-vendorgroups.md)]

[!include [Vendor payment methods](includes/VendorPaymentMethod-msdyn-vendorpaymentmethods.md)]
