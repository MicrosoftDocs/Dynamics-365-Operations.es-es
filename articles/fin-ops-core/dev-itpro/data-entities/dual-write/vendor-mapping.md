---
title: Maestro de proveedores integrado
description: Este tema describe la integración de datos de proveedor entre aplicaciones de Finance and Operations y Dataverse.
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
ms.openlocfilehash: f2fc88ed0c0f4dbec55f8ca251cca3d071760b55
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744524"
---
# <a name="integrated-vendor-master"></a>Maestro de proveedores integrado

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



El termino *proveedor* se refiere a una organización proveedora o un propietario único que suministra bienes o servicios a una empresa. Aunque *proveedor* sea un concepto establecido en las aplicaciones de Microsoft Dynamics 365 Supply Chain Management, el concepto de proveedor no existe en aplicaciones basadas en módelos de Dynamics 365. Sin embargo, puede sobrecargar la tabla **Cuenta/contacto** para almacenar información del proveedor. El maestro de proveedores integrado presenta un concepto de proveedor explícito en aplicaciones basadas en modelos en Dynamics 365. Puede usar el nuevo diseño del proveedor o almacenar los datos del proveedor en la tabla **Cuenta/Contacto**. La doble escritura admite ambos enfoques.

En ambos enfoques, los datos del proveedor se integran entre Dynamics 365 Supply Chain Management, Dynamics 365 Sales, Dynamics 365 Field Service y portales Power Apps. En Supply Chain Management, los datos están disponibles para flujos de trabajo, como solicitudes de pedido y órdenes de compra.

## <a name="vendor-data-flow"></a>Flujo de datos del proveedor

Si no quiere almacenar los datos de proveedor de tienda en la tabla **Cuenta/Contacto** en Dataverse puede usar el nuevo diseño de proveedor.

![Flujo de datos del proveedor](media/dual-write-vendor-data-flow.png)

Si quiere continuar almacenando los datos de proveedor de tienda en la tabla **Cuenta/Contacto** puede usar el diseño de proveedor extendido. Para usar el diseño extendido del proveedor, debe configurar los flujos de trabajo del proveedor en el paquete de solución de doble escritura. Para más información, consulte [Cambiar entre diseños de proveedores](vendor-switch.md).

![Flujo de datos ampliado del proveedor](media/dual-write-vendor-detail.jpg)

> [!TIP]
> Si está usando portales Power Apps para proveedores de autoservicio, la información del proveedor puede fluir directamente a aplicaciones Finance and Operations.

## <a name="templates"></a>Plantillas

Los datos del proveedor incluyen toda la información sobre el proveedor, como el grupo de proveedores, las direcciones, la información de contacto, el perfil de pago y el perfil de factura. Una colección de mapas de tabla funciona conjuntamente durante la interacción de los datos del proveedor, como se muestra en la tabla siguiente.

Aplicaciones de Finance and Operations | Otras aplicaciones de Dynamics 365     | Descripción
----------------------------|-----------------------------|------------
Proveedor V2                   | Cuenta                     | Las empresas que utilizan la tabla Cuenta para almacenar la información de proveedor pueden continuar utilizándola de la misma manera. También pueden aprovechar la funcionalidad explícita del proveedor que está por venir debido a la integración de aplicaciones de Finance and Operations.
Proveedor V2                   | Msdyn\_vendors              | Las empresas que utilizan una solución personalizada para los proveedores pueden aprovecharse del concepto de proveedor del componente estándar que se está introduciendo en Dataverse debido a la integración de aplicaciones de Finance and Operations. 
Grupos de proveedores               | msdyn\_vendorgroups         | Esta plantilla sincroniza la información del grupo de proveedores.
Método de pago de proveedor       | msdyn\_vendorpaymentmethods | Esta plantilla sincroniza la información del método de pago del proveedor.
Contactos V2 de CDS             | contactos                    | La plantilla [contactos](customer-mapping.md#cds-contacts-v2-to-contacts) sincroniza toda la información de contacto principal, secundaria, y terciaria, para clientes y proveedores.
Líneas de multivencimientos      | msdyn\_paymentschedulelines | La plantilla [líneas de programación de pago](customer-mapping.md#payment-schedule-lines-to-msdyn_paymentschedulelines) sincroniza los datos de referencia para clientes y proveedores.
Multivencimientos            | msdyn\_paymentschedules     | La plantilla [programaciones de pago](customer-mapping.md#payment-schedule-to-msdyn_paymentschedules) sincroniza los datos de referencia de la programación de pago, para clientes y proveedores.
Líneas de días de pago de CDS V2    | msdyn\_paymentdaylines      | La plantilla [líneas de día de pago](customer-mapping.md#payment-day-lines-cds-v2-to-msdyn_paymentdaylines) sincroniza los datos de referencia de las líneas de día de pago para clientes y proveedores.
Días de pago de CDS            | msdyn\_paymentdays          | La plantilla [días de pago](customer-mapping.md#payment-days-cds-to-msdyn_paymentdays) sincroniza los datos de referencia de los días de pago, para clientes y proveedores.
Condiciones de pago            | msdyn\_paymentterms         | La plantilla [términos de pago](customer-mapping.md#terms-of-payment-to-msdyn_paymentterms) sincroniza los datos de referencia de los términos de pago, para clientes y proveedores.
Afijos de nombre                | msdyn\_nameaffixes          | La plantilla [afijos de nombre](customer-mapping.md#name-affixes-to-msdyn_nameaffixes) sincroniza los datos de referencia de los afijos de nombre, para clientes y proveedores.

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [Vendors](includes/VendorsV2-msdyn-vendors.md)]

[!include [Vendor groups](includes/VendVendorGroup-msdyn-vendorgroups.md)]

[!include [Vendor payment methods](includes/VendorPaymentMethod-msdyn-vendorpaymentmethods.md)]
