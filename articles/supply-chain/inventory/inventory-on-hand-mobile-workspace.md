---
title: Espacio de trabajo móvil de inventario disponible
description: Este tema proporciona información sobre del área de trabajo móvil Inventario disponible. Este espacio de trabajo le ayuda a obtener información del inventario reservado y disponible en cualquier momento y en cualquier lugar.
author: yufeihuang
ms.date: 05/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yufeihuang
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: b380da99b02fe9b7cd834eabac3498ee3b8e54a4
ms.sourcegitcommit: 336a0ad772fb55d52b4dcf2fafaa853632373820
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2022
ms.locfileid: "8811477"
---
# <a name="inventory-on-hand-mobile-workspace"></a>Espacio de trabajo móvil de inventario disponible

[!include [banner](../includes/banner.md)]
[!include [mobile app deprecation](../../fin-ops-core/dev-itpro/includes/mobile-app-deprecation-banner.md)]

Este tema proporciona información sobre del área de trabajo móvil **Inventario disponible**. Este espacio de trabajo le ayuda a obtener información del inventario reservado y disponible en cualquier momento y en cualquier lugar.

Este espacio de trabajo móvil se debe usar con la aplicación móvil Finance and Operations (Dynamics 365).

## <a name="overview"></a>Información general
Por lo general, las empresas tienen múltiples envíos y múltiples recepciones de inventario cada día. Estos movimientos cambian constantemente el estado del inventario disponible. El área de trabajo móvil **Inventario disponible** le permite ver el estado de inventario disponible entre empresas, de modo que puede obtener la información más reciente sobre los datos de inventario en el dispositivo móvil que elija. Independientemente de si trabaja en el almacén, compras, ventas, fabricación o administración, o tiene otras funciones, puede tener acceso a los datos de inventario disponible en cualquier momento y en cualquier lugar. 

El área de trabajo móvil proporciona una vista inmediata del estado disponible en las instalaciones. Le permite ver el inventario disponible en las instalaciones, las reservas de material actuales y el inventario disponible no reservado. También puede introducir los números de artículo para consultar el inventario disponible y realizar una búsqueda filtrada para los productos o variantes disponibles. 

El área de trabajo móvil proporciona específicamente estas características:

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
Los requisitos varían en función de la versión de Supply Chain Management que se haya implementado en su organización.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Requisitos previos si usa Supply Chain Management
Si Supply Chain Management se ha implementado para su organización, el administrador del sistema debe publicar el área de trabajo móvil **Inventario disponible**. Para obtener instrucciones, consulte [Publicar un espacio de trabajo móvil](../../fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-platform-update-3-or-later"></a>Los requisitos previos si usa la actualización de plataforma 3 o posterior 
Si se ha implementado la actualización de plataforma 3 o posterior en su organización, el administrador del sistema debe cumplir los requisitos siguientes. 

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

<td>KB 4013633 es una sustitución de actualización o de metadatos X++ que contiene el área de trabajo móvil <strong>Inventario disponible</strong>. Para implementar KB 4013633, el administrador del sistema debe seguir estos pasos.
<ol>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs">Descargar la revisión de metadatos de Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Instalar la revisión de metadatos</a>.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/create-apply-deployable-package">Crear un paquete desplegable</a> que contenga el modelo <strong>SCMMobile</strong> y luego cargar el paquete desplegable en LCS.</li>
<li><a href="/dynamics365/fin-ops-core/dev-itpro/deployment/apply-deployable-package-system">Aplicar el paquete implementable</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>Publique el área de trabajo móvil <strong>Inventario disponible</strong>.</td>
<td>Administrador del sistema</td>
<td>Consulte <a href="/dynamics365/fin-ops-core/dev-itpro/mobile-apps/publish-mobile-workspace">Publicar un espacio de trabajo móvil</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Descargar e instalar la aplicación móvil

Descargar e instalar la aplicación móvil de finanzas y operaciones (Dynamics 365):

-   [Para teléfonos Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Iniciar sesión en la aplicación móvil

1.  Inicie la aplicación en su dispositivo móvil.
2.  Escriba la URL de Dynamics 365.
3.  La primera vez que se inicie sesión, se le solicitará su nombre de usuario y contraseña. Escriba sus credenciales.
4.  Tras iniciar sesión, se mostrarán los espacios de trabajo disponibles para su empresa. Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, tendrá que actualizar la lista de espacios de trabajo móviles.

    [![Toque la pantalla para actualizar.](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-on-hand-inventory-for-a-product-by-using-the-inventory-on-hand-mobile-workspace"></a>Visualización del inventario disponible de un producto mediante el área de trabajo móvil disponible del inventario

1.  En el dispositivo móvil, seleccione el área de trabajo **Inventario disponible**.

2.  Seleccione **Comprobar el inventario disponible de un artículo**. Verá una lista de los productos que se cargan en su aplicación para su uso sin conexión. Hay 50 artículos cargados de forma predeterminada, pero un desarrollador puede cambiar este número. Para obtener más información, los desarrolladores deben ver [Plataforma móvil](../../fin-ops-core/dev-itpro/mobile-apps/platform/mobile-platform-home-page.md).
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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
