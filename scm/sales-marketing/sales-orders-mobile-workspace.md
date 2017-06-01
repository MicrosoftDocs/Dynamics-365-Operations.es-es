---
title: "Espacio de trabajo móvil de pedidos de ventas"
description: "Este tema proporciona información acerca del espacio de trabajo móvil de pedidos de ventas, que está disponible para la aplicación móvil Microsoft Dynamics 365 for Operations. Este espacio de trabajo le permitirá estar informado sobre los pedidos de ventas en cualquier momento y cualquier lugar."
author: YuyuScheller
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Operations, Core
ms.custom: 267134
ms.assetid: 0ce96511-002b-4de7-b31e-4303f94edc84
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 11898146a13756a6bb22a769e37e8773484e0d04
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="sales-orders-mobile-workspace"></a>Espacio de trabajo móvil de pedidos de ventas

[!include[banner](../includes/banner.md)]


Este tema proporciona información acerca del espacio de trabajo móvil de pedidos de ventas, que está disponible para la aplicación móvil Microsoft Dynamics 365 for Operations. Este espacio de trabajo le permitirá estar informado sobre los pedidos de ventas en cualquier momento y cualquier lugar. 

<a name="overview-of-the-sales-orders-mobile-workspace"></a>Visión general del espacio de trabajo móvil de pedidos de ventas
---------------------------------------------

El espacio de trabajo móvil **Pedidos de ventas** tiene acceso a Microsoft Dynamics 365 for Operations y le permite ver información detallada sobre cada pedido de ventas. Esta información incluye el estado del pedido, la información de contacto para el cliente, y la información de contacto del creador del pedido. El espacio de trabajo móvil **Pedidos de ventas** proporciona una vista inmediata de los pedidos de ventas. Puede ver todos los pedidos de ventas, o ver los pedidos de ventas por cliente o ver la información sobre un pedido de ventas concreto. 

El espacio de trabajo móvil proporciona dos perspectivas que le ayudarán a analizar en detalle los pedidos de ventas.

### <a name="view-all-sales-orders"></a>Ver todos los pedidos de ventas

Esta vista muestra todos los pedidos de ventas.

-   Utilice uno de los filtros siguientes para seleccionar los pedidos de ventas que desea ver:
    -   Buscar por pedido de ventas
    -   Buscar por cuenta de cliente
    -   Buscar por nombre del cliente
    -   Buscar por estado
    -   Buscar por estado de liberación
    -   Buscar por fecha y hora de creación
    
-   Tras seleccionar los pedidos de ventas, puede ver los detalles de pedidos específicos. Concretamente, puede ver la siguiente información:
    -   Información del nombre y la dirección del cliente
    -   Diversas fechas del pedido de ventas, como la fecha de envío solicitada y la fecha de envío confirmada
    -   Información de contacto del creador del pedido
    -   Información de contacto del cliente
    -   Líneas de pedido
    -   Envíos que muestran cómo y cuándo se envió un pedido de ventas

### <a name="view-orders-for-a-customer"></a>Ver los pedidos de un cliente

Esta vista muestra pedidos de ventas por cliente.

-   Utilice uno de los filtros siguientes para ver los pedidos de un cliente:
    -   Buscar por nombre
    -   Buscar por cuenta

-   Tras seleccionar un cliente, puede ver la información siguiente:
    -   Nombre y grupo del cliente
    -   Información de contacto del cliente
    -   Pedidos de ventas del cliente y detalles sobre estos pedidos de ventas:
        -   Información del nombre y la dirección del cliente
        -   Diversas fechas del pedido de ventas
        -   Información de contacto del creador del pedido
        -   Información de contacto del cliente
        -   Líneas de pedido
        -   Envíos que muestran cómo y cuándo se envió un pedido de ventas

## <a name="prerequisites"></a>Requisitos previos
Para poder usar el espacio de trabajo móvil **Pedidos de ventas** , asegúrese de que el administrador del sistema tenga los requisitos previos siguientes en vigor.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Requisito previo</th>
<th>Función</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Dynamics 365 for Operations versión 1611 con actualización de plataforma 3 o posterior debe estar implementado.</td>
<td>Administrador del sistema</td>
<td>Si todavía no tiene Dynamics 365 for Operations implementado en su organización, el administrador del sistema debería ver <a href="/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment/">Implementar un entorno de demostración de Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>KB 4013633 debe implementarse.</td>
<td>Administrador del sistema</td>
<td>KB 4013633 (una revisión de metadatos o actualización de X++) contiene cuatro áreas de trabajo móviles para la gestión de cadenas de suministro. Para implementar KB 4013633, el administrador del sistema debe seguir estos pasos:
<ol>
<li>Descargar KB 4013633 de Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="/dynamics365/operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Instalar la revisión de metadatos</a>.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Crear un paquete desplegable</a> que contenga el modelo <strong>SCMMobile</strong> y luego cargar el paquete desplegable en LCS.</li>
<li><a href="/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Aplicar el paquete desplegable</a> a su sistema Dynamics 365 for Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>El espacio de trabajo móvil <strong>Pedidos de ventas</strong> debe estar publicado en la aplicación móvil Dynamics 365 for Operations.</td>
<td>Administrador del sistema</td>
<td><ol>
<li>Inicie Dynamics 365 for Operations en su explorador.</li>
<li>En la página <strong>Parámetros del sistema</strong>, seleccione <strong>Gestionar espacios de trabajo móviles</strong>.</li>
<li>Seleccione el espacio de trabajo <strong>Pedidos de ventas</strong>.</li>
<li>Haga clic en <strong>Publicar espacio de trabajo móvil</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Descargue e instale la aplicación móvil Dynamics 365 for Operations
Descargue e instale la aplicación móvil Microsoft Dynamics 365 for Operations desde la tienda de aplicaciones móviles.

-   Para Android: [Dynamics 365 for Operations en Google Play Store](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   Para iPhone: [Dynamics 365 for Operations en la tienda de aplicaciones de iTunes](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)

## <a name="sign-in-to-the-dynamics-365-for-operations-mobile-app"></a>Inicie sesión en la aplicación móvil Dynamics 365 for Operations
1.  Inicie la aplicación en su dispositivo móvil.
2.  Entre en la URL de Dynamics 365 for Operations.
3.  Escriba la empresa en la que va a iniciar sesión. Por ejemplo, escriba **USMF**.
4.  La primera vez que inicia sesión, se le pedirá el nombre de usuario y la contraseña de su cuenta Dynamics 365 for Operations. Escriba sus credenciales.
5.  Tras iniciar sesión, verá los espacios de trabajo disponibles para su empresa. Tenga en cuenta que si el administrador del sistema más adelante publica un nuevo espacio de trabajo, puede tocar la pantalla para actualizar la lista de espacios de trabajo móviles. 

    [![Toque la pantalla para actualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-information-about-sales-orders-for-a-customer-by-using-the-mobile-workspace"></a>Visualización de información acerca de los pedidos de ventas para un cliente mediante el espacio de trabajo móvil
1.  En el dispositivo móvil, seleccione el espacio de trabajo **Pedidos de ventas**.
2.  Seleccione **Ver los pedidos de un cliente**
3.  Utilice la información de la cuenta o el nombre del cliente para buscar el cliente.
4.  Seleccione el cliente.
5.  Seleccione **Información de contacto** o **Pedidos de ventas**. Si selecciona **Pedidos de ventas**, se mostrará la lista de pedidos de ventas del cliente.
6.  Seleccione **Pedido de ventas**. Ahora puede ver información sobre las líneas del pedido de ventas, información sobre los envíos, información de contacto del cliente e información de contacto del creador del pedido.





