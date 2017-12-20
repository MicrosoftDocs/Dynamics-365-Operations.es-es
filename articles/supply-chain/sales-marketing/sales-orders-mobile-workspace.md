---
title: "Espacio de trabajo móvil de pedidos de ventas"
description: "Este tema proporciona información sobre el espacio de trabajo móvil Pedidos de ventas. Este espacio de trabajo le permitirá estar informado sobre los pedidos de ventas en cualquier momento y cualquier lugar."
author: Mirzaab
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 267134
ms.assetid: 0ce96511-002b-4de7-b31e-4303f94edc84
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 6e64337f19600b18320550d91c134949c33af7b0
ms.openlocfilehash: 6a613d8b2ea1503b70efad7b14fb340faad0f62e
ms.contentlocale: es-es
ms.lasthandoff: 12/01/2017

---

# <a name="sales-orders-mobile-workspace"></a>Espacio de trabajo móvil de pedidos de ventas

[!include[banner](../includes/banner.md)]

Este tema proporciona información sobre el espacio de trabajo móvil **Pedidos de ventas**. Este espacio de trabajo le permitirá estar informado sobre los pedidos de ventas en cualquier momento y cualquier lugar. 

Este espacio de trabajo móvil se debe usar con la aplicación móvil Microsoft Dynamics 365 for Unified Operations.

## <a name="overview"></a>Información general
El espacio de trabajo móvil **Pedidos de ventas** le permite ver información detallada sobre cada pedido de ventas. Esta información incluye el estado del pedido, la información de contacto para el cliente, y la información de contacto del creador del pedido. El espacio de trabajo móvil **Pedidos de ventas** proporciona una vista inmediata de los pedidos de ventas. Puede ver todos los pedidos de ventas, o ver los pedidos de ventas por cliente o ver la información sobre un pedido de ventas concreto. 

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
Los requisitos previos varían, en función de la versión de Microsoft Dynamics 365 que se ha implementado para su organización.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition"></a>Requisitos previos si usa Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 
Si la Dynamics 365 for Finance and Operations, Enterprise Edition se ha implementado para su organización, el administrador del sistema debe publicar el espacio de trabajo móvil **Pedidos de ventas**. Para obtener instrucciones, consulte [Publicar un espacio de trabajo móvil](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Requisitos si usa Dynamics 365 for Operations versión 1611 con actualización de plataforma 3 o posterior
Si se ha implementado Dynamics 365 for Operations versión 1611 con actualización de plataforma 3 o posterior en su organización, el administrador del sistema debe cumplir los requisitos siguientes. 

<table>
<thead>
<tr class="header">
<th>Requisito previo</th>
<th>Función</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implementar 4013633 KB.</td>
<td>Administrador del sistema</td>

<td>KB 4013633 es una sustitución de actualización o de metadatos X++ que contiene el espacio de trabajo móvil <strong>Pedidos de ventas</strong>. Para implementar KB 4013633, el administrador del sistema debe seguir estos pasos.
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Descargar la revisión de metadatos en Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Instalar la revisión de metadatos</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Crear un paquete desplegable</a> que contenga el modelo <strong>SCMMobile</strong> y luego cargar el paquete desplegable en LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Aplicar el paquete implementable</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Publique el espacio de trabajo móvil <strong>Pedidos de ventas</strong>.</td>
<td>Administrador del sistema</td>
<td>Consulte <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicar un espacio de trabajo móvil</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Descargar e instalar la aplicación móvil
Descargue e instale la aplicación móvil Dynamics 365 for Unified Operations:

-   [Para teléfonos Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Iniciar sesión en la aplicación móvil

1.  Inicie la aplicación en su dispositivo móvil.
2.  Escriba la URL de Dynamics 365.
3.  La primera vez que se inicie sesión, se le solicitará su nombre de usuario y contraseña. Escriba sus credenciales.
4.  Tras iniciar sesión, se mostrarán los espacios de trabajo disponibles para su empresa. Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, tendrá que actualizar la lista de espacios de trabajo móviles.

[![Toque la pantalla para actualizar](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-information-about-sales-orders-for-a-customer-by-using-the-sales-order-mobile-workspace"></a>Visualización de información acerca de los pedidos de ventas para un cliente mediante el espacio de trabajo móvil Pedidos de ventas

1.  En el dispositivo móvil, seleccione el espacio de trabajo **Pedidos de ventas**.
2.  Seleccione **Ver los pedidos de un cliente**
3.  Utilice la información de la cuenta o el nombre del cliente para buscar el cliente.
4.  Seleccione el cliente.
5.  Seleccione **Información de contacto** o **Pedidos de ventas**. Si selecciona **Pedidos de ventas**, se mostrará la lista de pedidos de ventas del cliente.
6.  Seleccione **Pedido de ventas**. Ahora puede ver información sobre las líneas del pedido de ventas, información sobre los envíos, información de contacto del cliente e información de contacto del creador del pedido.

