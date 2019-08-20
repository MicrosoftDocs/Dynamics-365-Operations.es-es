---
title: Espacio de trabajo móvil de inventario disponible
description: Este tema proporciona información sobre del espacio de trabajo móvil Inventario disponible. Este espacio de trabajo le ayuda a obtener información del inventario reservado y disponible en cualquier momento y en cualquier lugar.
author: Mirzaab
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 68b285ba78a9bd654e7bfcfe8d4c6b0207346eab
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845603"
---
# <a name="inventory-on-hand-mobile-workspace"></a>Espacio de trabajo móvil de inventario disponible

[!include [banner](../includes/banner.md)]

Este tema proporciona información sobre del espacio de trabajo móvil **Inventario disponible**. Este espacio de trabajo le ayuda a obtener información del inventario reservado y disponible en cualquier momento y en cualquier lugar.

Este espacio de trabajo móvil se debe usar con la aplicación Microsoft Dynamics 365 for Unified Operations mobile.

## <a name="overview"></a>Información general
Por lo general, las empresas tienen múltiples envíos y múltiples recepciones de inventario cada día. Estos movimientos cambian constantemente el estado del inventario disponible. El espacio de trabajo móvil **Inventario disponible** le permite ver el estado de inventario disponible entre empresas, de modo que puede obtener la información más reciente sobre los datos de inventario en el dispositivo móvil que elija. Independientemente de si trabaja en el almacén, compras, ventas, fabricación o administración, o tiene otras funciones, puede tener acceso a los datos de inventario disponible en cualquier momento y en cualquier lugar. 

El espacio de trabajo móvil proporciona una vista inmediata del estado disponible en las instalaciones. Le permite ver el inventario disponible en las instalaciones, las reservas de material actuales y el inventario disponible no reservado. También puede introducir los números de artículo para consultar el inventario disponible y realizar una búsqueda filtrada para los productos o variantes disponibles. 

El espacio de trabajo móvil proporciona específicamente estas características:

-   Puede buscar por número de producto o por nombre de producto para encontrar productos para ver el estado de inventario disponible.
-   Para los productos seleccionados, puede ver la información siguiente:

    -   Inventario disponible por sitio
    -   Inventario disponible por almacén
    -   Inventario disponible por ubicación
    -   Inventario disponible por lote (para productos controlados por lote)
    -   Inventario disponible por estado de inventario
    
-   El inventario disponible del producto se muestra de las siguientes formas:

    -   Por inventario físico (Esta vista representa la cantidad total).
    -   Por inventario reservado (Esta vista representa la cantidad reservada).
    -   Por inventario físico disponible (Esta vista representa la cantidad disponible que no tiene reservas.)

## <a name="prerequisites"></a>Requisitos previos
Los requisitos previos varían, en función de la versión de Microsoft Dynamics 365 que se ha implementado para su organización.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations"></a>Requisitos previos si usa Microsoft Dynamics 365 for Finance and Operations 
Si Microsoft Dynamics 365 for Finance and Operations se ha implementado para su organización, el administrador del sistema debe publicar el espacio de trabajo móvil **Inventario disponible**. Para obtener instrucciones, consulte [Publicar un espacio de trabajo móvil](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Los requisitos previos si usa Microsoft Dynamics 365 for Operations versión 1611 con la actualización de plataforma 3 o posterior
Si se ha implementado Microsoft Dynamics 365 for Operations versión 1611 con actualización de plataforma 3 o posterior en su organización, el administrador del sistema debe cumplir los requisitos siguientes. 

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

<td>KB 4013633 es una sustitución de actualización o de metadatos X++ que contiene el espacio de trabajo móvil <strong>Inventario disponible</strong>. Para implementar KB 4013633, el administrador del sistema debe seguir estos pasos.
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Descargar la revisión de metadatos de Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Instalar la revisión de metadatos</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Crear un paquete desplegable</a> que contenga el modelo <strong>SCMMobile</strong> y luego cargar el paquete desplegable en LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Aplicar el paquete implementable</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Publique el espacio de trabajo móvil <strong>Inventario disponible</strong>.</td>
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

## <a name="view-the-on-hand-inventory-for-a-product-by-using-the-inventory-on-hand-mobile-workspace"></a>Visualización del inventario disponible de un producto mediante el espacio de trabajo móvil disponible del inventario

1.  En el dispositivo móvil, seleccione el espacio de trabajo **Inventario disponible**.

2.  Seleccione **Comprobar el inventario disponible de un artículo**. Verá una lista de los productos que se cargan en su aplicación para su uso sin conexión. Hay 50 artículos cargados de forma predeterminada, pero un desarrollador puede cambiar este número. Para obtener más información, los desarrolladores deben ver [Plataforma móvil](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
3.  Si el artículo no está en la lista, seleccione **Buscar más**. Busque por número de producto o cambie a una búsqueda por nombre de producto.

4.  Seleccione un producto. Si el artículo tiene una imagen, esta se muestra.
5.  Seleccione una de las siguientes opciones para ver el estado de inventario disponible:

    -   Ver el inventario disponible por sitio
    -   Ver el inventario disponible por almacén
    -   Ver inventario disponible por ubicación
    -   Ver inventario disponible por lote (para productos controlados por lote)
    -   Ver inventario disponible por estado de inventario

    El inventario disponible del producto se muestra de las siguientes formas:
    -   Por inventario físico (Esta vista representa la cantidad total).
    -   Por inventario reservado (Esta vista representa la cantidad reservada).
    -   Por inventario físico disponible (Esta vista representa la cantidad disponible que no tiene reservas.)
