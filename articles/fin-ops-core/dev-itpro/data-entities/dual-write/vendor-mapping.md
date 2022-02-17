---
title: Maestro de proveedores integrado
description: Este tema describe la integración de datos de proveedor entre aplicaciones de Finance and Operations y Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 7794f33aed7364b76a7d5ffd08a068342887e468
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8063171"
---
# <a name="integrated-vendor-master"></a>Maestro de proveedores integrado

[!include [banner](../../includes/banner.md)]



El termino *proveedor* se refiere a una organización proveedora o un propietario único que suministra bienes o servicios a una empresa. Aunque *proveedor* sea un concepto establecido en las aplicaciones de Microsoft Dynamics 365 Supply Chain Management, el concepto de proveedor no existe en aplicaciones Customer Engagement. Sin embargo, puede sobrecargar la tabla **Cuenta/contacto** para almacenar información del proveedor. El maestro de proveedores integrado presenta un concepto de proveedor explícito en aplicaciones Customer Engagement. Puede usar el nuevo diseño del proveedor o almacenar los datos del proveedor en la tabla **Cuenta/Contacto**. La doble escritura admite ambos enfoques.

En ambos enfoques, los datos del proveedor se integran entre Dynamics 365 Supply Chain Management, Dynamics 365 Sales, Dynamics 365 Field Service y portales Power Apps. En Supply Chain Management, los datos están disponibles para flujos de trabajo, como solicitudes de pedido y órdenes de compra.

## <a name="vendor-data-flow"></a>Flujo de datos del proveedor

Si no quiere almacenar los datos de proveedor de tienda en la tabla **Cuenta/Contacto** en Dataverse puede usar el nuevo diseño de proveedor.

![Flujo de datos del proveedor.](media/dual-write-vendor-data-flow.png)

Si quiere continuar almacenando los datos de proveedor de tienda en la tabla **Cuenta/Contacto** puede usar el diseño de proveedor extendido. Para usar el diseño extendido del proveedor, debe configurar los flujos de trabajo del proveedor en el paquete de solución de doble escritura. Para más información, consulte [Cambiar entre diseños de proveedores](vendor-switch.md).

![Flujo de datos ampliado del proveedor.](media/dual-write-vendor-detail.jpg)

> [!TIP]
> Si está usando portales de Power Apps para proveedores de autoservicio, la información del proveedor puede fluir directamente a aplicaciones Finanzas y operaciones.

## <a name="templates"></a>Plantillas

Los datos del proveedor incluyen toda la información sobre el proveedor, como el grupo de proveedores, las direcciones, la información de contacto, el perfil de pago y el perfil de factura. Una colección de mapas de tabla funciona conjuntamente durante la interacción de los datos del proveedor, como se muestra en la tabla siguiente.

Aplicaciones de Finance and Operations | Aplicaciones Customer Engagement     | Descripción
----------------------------|-----------------------------|------------
[Contactos V2 de CDS](mapping-reference.md#115) | contactos | Esta plantilla sincroniza toda la información de contacto principal, secundaria, y terciaria, para clientes y proveedores.
[Afijos de nombre](mapping-reference.md#155) | msdyn_nameaffixes | Esta plantilla sincroniza los datos de referencia de los afijos de nombre, para clientes y proveedores.
[Líneas de días de pago de CDS V2](mapping-reference.md#157) | msdyn_paymentdaylines | Esta plantilla sincroniza los datos de referencia de las líneas de días de pago, para clientes y proveedores.
[Días de pago de CDS](mapping-reference.md#158) | msdyn_paymentdays | Esta plantilla sincroniza los datos de referencia de los días de pago, para clientes y proveedores.
[Líneas de multivencimientos](mapping-reference.md#159) | msdyn_paymentschedulelines | Sincroniza los datos de referencia de las líneas de programación de pago, para clientes y proveedores.
[Multivencimientos](mapping-reference.md#160) | msdyn_paymentschedules | Esta plantilla sincroniza los datos de referencia de la programación de pago, para clientes y proveedores.
[Condiciones de pago](mapping-reference.md#161) | msdyn_paymentterms | Esta plantilla sincroniza los datos de referencia de las los términos de pago (términos de pago), para clientes y proveedores.
[Proveedores V2](mapping-reference.md#202) | msdyn_vendors | Las empresas que utilizan una solución personalizada para los proveedores pueden aprovecharse del concepto de proveedor del componente estándar que se está introduciendo en Dataverse debido a la integración de aplicaciones de Finance and Operations.
[Grupos de proveedores](mapping-reference.md#200) | msdyn_vendorgroups | Esta plantilla sincroniza la información del grupo de proveedores.
[Método de pago de proveedor](mapping-reference.md#201) | msdyn_vendorpaymentmethods | Esta plantilla sincroniza la información del método de pago del proveedor.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
