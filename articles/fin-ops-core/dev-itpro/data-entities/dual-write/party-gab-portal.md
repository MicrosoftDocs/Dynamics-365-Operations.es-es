---
title: Usar portales de Microsoft Power Apps con el modelo de datos de parte
description: Este tema describe los cambios en los roles web para portales de Microsoft Power Apps debido al modelo de datos de parte en escritura dual.
author: RamaKrishnamoorthy
ms.date: 03/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-22
ms.openlocfilehash: 8242a74b8b2251a8489b772f5c4746b113fe2987
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8060929"
---
# <a name="using-microsoft-power-apps-portals-with-the-party-data-model"></a>Usar portales de Microsoft Power Apps con el modelo de datos de parte

[!INCLUDE[banner](../../includes/banner.md)]



La versión de la solución de orquestación de aplicaciones de escritura dual 2.0.999.0 y posteriores incluye cambios en el modelo de datos en la libreta de direcciones global y de partes para las tablas Cuenta y Contacto. Los cambios permiten relaciones de varios a varios que admiten escenarios empresariales avanzados. Estos cambios no son compatibles con los roles web del portal, incluido el portal del cliente, que se envían listos para usar o que existían en su ambiente antes de instalar la escritura dual. Para que los roles web funcionen como se esperaba, debe crear nuevos roles web utilizando el nuevo modelo de datos. 

En resumen, la forma en que interactúan las tablas ha cambiado, pero los permisos de las tablas en el portal del cliente no han cambiado. Este tema explica cómo crear nuevos roles web que funcionen con el nuevo modelo de datos avanzado.

Este diagrama muestra la relación de la tabla **sin** el modelo de datos de parte y de libreta de direcciones global:

   ![sin modelo de parte.](media/without-party-model.PNG)

Este diagrama muestra la relación de la tabla **con** el modelo de datos de parte y de libreta de direcciones global:

   ![con modelo de parte.](media/with-party-model.png)

## <a name="create-a-new-table-permission"></a>Crear un permiso de tabla nuevo

Para crear estos nuevos permisos de tabla, siga estos pasos:

1. Inicie sesión en [Power Apps](https://make.powerapps.com) y vaya a sus aplicaciones.
2. Seleccione su aplicación de Administración de portales.
3. En la barra lateral, seleccione **Seguridad > Permisos de tabla**.

    Debe crear tres permisos nuevos:

    + Conexión de tabla **Contacto** a **Parte**
    + Conexión de tabla **Parte** a **Cuenta**
    + Conexión de tabla **Cuenta** a **Pedido**

4. Cree y guarde un nuevo permiso para la conexión de contacto a parte, estableciendo estos parámetros:

    + **Nombre**: conexión de tabla **Parte** a **Cuenta** (o su elección)
    + **Nombre de tabla**: msdyn_contactforparty
    + **Sitio web**: portal del cliente
    + **Ámbito**: contacto
    + **Privilegios**: Seleccionar todo
    + **Roles web**: usuarios autenticados, representante del cliente (o su elección)

5. Cree y guarde un nuevo permiso para la conexión de parte a contacto, estableciendo estos parámetros:

    + **Nombre**: conexión de parte a cuenta (o su elección)
    + **Nombre de tabla**: cuenta
    + **Sitio web**: portal del cliente
    + **Ámbito**: primario
    + **Privilegios**: Seleccionar todo
    + **Permiso de tabla principal**: conexión de contacto a parte

6. Cree y guarde un nuevo permiso para la conexión de cuenta a pedido, estableciendo estos parámetros:

    + **Nombre**: conexión de cuenta a pedido (o su elección)
    + **Nombre de tabla**: salesorder
    + **Sitio web**: portal del cliente
    + **Ámbito**: primario
    + **Privilegios**: Seleccionar todo
    + **Permiso de tabla principal**: conexión de parte a cuenta

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
