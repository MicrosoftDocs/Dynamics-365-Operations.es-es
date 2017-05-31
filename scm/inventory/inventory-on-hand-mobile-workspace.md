---
title: "Espacio de trabajo móvil de inventario disponible"
description: "Este tema proporciona información acerca del espacio de trabajo móvil de inventario disponible, que está disponible para la aplicación móvil de Microsoft Dynamics 365 for Operations. Este espacio de trabajo le ayuda a obtener información del inventario reservado y disponible en cualquier momento y en cualquier lugar."
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
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7387df37e047d5ab7a90b696a6ffa249094499c4
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="inventory-on-hand-mobile-workspace"></a>Espacio de trabajo móvil de inventario disponible

[!include[banner](../includes/banner.md)]


Este tema proporciona información acerca del espacio de trabajo móvil de inventario disponible, que está disponible para la aplicación móvil de Microsoft Dynamics 365 for Operations. Este espacio de trabajo le ayuda a obtener información del inventario reservado y disponible en cualquier momento y en cualquier lugar.

<a name="overview-of-the-inventory-on-hand-mobile-workspace"></a>Visión general del espacio de trabajo móvil de inventario disponible
--------------------------------------------------

Por lo general, las empresas tienen múltiples envíos y múltiples recepciones de inventario cada día. Estos movimientos cambian constantemente el estado del inventario disponible. El espacio de trabajo móvil de **inventario disponible** le permite ver el estado de inventario disponible entre empresas, de modo que puede obtener la información más reciente sobre los datos de inventario en el dispositivo móvil que elija. Independientemente de si trabaja en el almacén, compras, ventas, fabricación o administración, o tiene otras funciones, puede tener acceso a los datos de inventario disponible en cualquier momento y en cualquier lugar. 

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
Para poder usar el espacio de trabajo **móvil disponible** , asegúrese de que el administrador del sistema tenga los requisitos previos siguientes en vigor.

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
<td>Microsoft Dynamics 365 for Operations versión 1611 con actualización de plataforma 3 o posterior debe estar implementado.</td>
<td>Administrador del sistema</td>
<td>Si todavía no tiene Dynamics 365 for Operations implementado en su organización, el administrador del sistema debería ver <a href="/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment">Implementar un entorno de demostración de Microsoft Dynamics 365 for Operations</a>.</td>
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
<td>El espacio de trabajo <strong>móvil disponible</strong> debe estar publicado en la aplicación móvil Dynamics 365 for Operations.</td>
<td>Administrador del sistema</td>
<td><ol>
<li>Inicie Dynamics 365 for Operations en su explorador.</li>
<li>En la página <strong>Parámetros del sistema</strong>, seleccione <strong>Gestionar espacios de trabajo móviles</strong>.</li>
<li>Seleccione el espacio de trabajo <strong>Inventario disponible</strong>.</li>
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

## <a name="view-the-onhand-inventory-for-a-product-by-using-the-inventory-onhand-mobile-workspace"></a>Visualización del inventario disponible de un producto mediante el espacio de trabajo móvil disponible del inventario
1.  En el dispositivo móvil, seleccione el espacio de trabajo **Inventario disponible**.
2.  Seleccione **Comprobar el inventario disponible de un artículo**. Verá una lista de los productos que se cargan en su aplicación para su uso sin conexión. Hay 50 artículos cargados de forma predeterminada, pero un desarrollador puede cambiar este número. Para obtener más información, los desarrolladores deben ver [Plataforma móvil Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform).
3.  Si el artículo no está en la lista, seleccione **Buscar más** para realizar una búsqueda en línea en Dynamics 365 for Operations. Busque por número de producto o cambie a una búsqueda por nombre de producto.
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






