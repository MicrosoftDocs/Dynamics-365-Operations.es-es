---
title: Crear jerarquías de modelado de organización para organizaciones B2B
description: Este tema describe cómo crear jerarquías de modelado organizativo para organizaciones de empresa a empresa (B2B).
author: josaw1
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 487af939f92ece8bc3e543b3beeffa239baa1863
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799838"
---
# <a name="create-org-modeling-hierarchies-for-b2b-organizations"></a>Crear jerarquías de modelado de organización para organizaciones B2B

[!include [banner](../../includes/banner.md)]

Este tema describe cómo crear jerarquías de modelado organizativo para organizaciones de empresa a empresa (B2B) en Microsoft Dynamics 365 Commerce.

En la sede central de Commerce, las organizaciones que son socios comerciales están representadas por clientes y entidades jerárquicas de clientes. La organización socio comercial y sus usuarios se representan como clientes, y las jerarquías de clientes se utilizan para asociar esos clientes entre sí.

Cuando un socio comercial solicita unirse a un sitio de comercio electrónico B2B, se realizan las siguientes acciones:

- Además, se crean dos nuevos registros de clientes en el sistema: un registro de cliente **De tipo organización** para la organización del socio comercial y un registro de cliente **De tipo persona** para el solicitante (es decir, el usuario socio comercial que envió la solicitud).
- Se crea un nuevo registro de jerarquía de clientes en **Cliente \> Jerarquía de clientes**. Este registro tiene las siguientes propiedades de encabezado:

    - **Id. de jerarquía de clientes**: identificador único para la jerarquía de clientes. Este id. usa la secuencia numérica que se define en los parámetros compartidos de Commerce en la sede central de Commerce.
    - **Nombre**: el nombre de la organización socio comercial, como se especifica en la solicitud de incorporación.
    - **Objetivo**: esta propiedad se establece en el valor predefinido **Organización de B2B**.
    - **Organización**: id. de cliente del socio comercial.

Estos son los detalles del registro de jerarquía de clientes:

- El registro de cliente del solicitante está asociado con la jerarquía de clientes.
- El rol de administrador está asociado con el solicitante.

Cuando el administrador agrega más usuarios a la organización de socios comerciales en un sitio B2B, se crea un nuevo registro de cliente para cada usuario en la sede central de Commerce. Este registro de cliente también se agrega al registro de jerarquía de clientes relevante para el socio comercial y tiene el rol de "usuario".

> [!NOTE]
> En la mayoría de los casos, los valores de propiedad correspondientes de todos los registros de clientes de una jerarquía deben coincidir. Por ejemplo, como todos los usuarios socios comerciales deben obtener precios similares para los productos, su grupo de precios y las configuraciones asociadas deben coincidir. Sin embargo, el sistema no aplica esta coherencia. Por lo tanto, los usuarios de la sede central de Commerce correspondientes son responsables de garantizar que los valores y las configuraciones de las propiedades coincidan para todos los clientes en una jerarquía determinada.

Los usuarios de la sede central de Commerce pueden ver los valores de propiedades de todos los registros de clientes de la jerarquía en una vista en paralelo. Seleccione las propiedades de registro de cliente relevantes seleccionando los nombres de las pestañas en el menú desplegable. Los usuarios pueden ver y editar directamente los valores de propiedad desde esta vista. Como alternativa, si desea aplicar todos los valores del registro de cliente administrador a todos los registros de cliente usuario, seleccione **Reemplazar** en los detalles de la jerarquía de clientes.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar un sitio de comercio electrónico B2B](set-up-b2b-site.md)

[Administrar usuarios socios comerciales en sitios de comercio electrónico B2B](manage-b2b-users.md)

[Configurar el método de pago de la cuenta del cliente para sitios de comercio electrónico B2B](payment-method.md)

[Establecer límites de cantidad de productos para sitios de comercio electrónico B2B](quantity-limits.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]