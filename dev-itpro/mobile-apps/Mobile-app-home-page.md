---
title: "Página principal de la aplicación móvil Dynamics 365 for Operations"
description: "Este tema describe la aplicación móvil Microsoft Dynamics 365 for Operations y ofrece vínculos a los recursos que pueden ayudarle a implementarla en su organización."
author: sericks007
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations, Platform
ms.custom: 272853
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: sericks
ms.dyn365.ops.intro: Platform update 4
ms.search.validFrom: 2017-02-28
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: e1a9e0eeb45f011ccb2aa091e68aff92782e1ae7
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="dynamics-365-for-operations-mobile-app-home-page"></a>Página principal de la aplicación móvil Dynamics 365 for Operations

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/banner.md)]


Este tema describe la aplicación móvil Microsoft Dynamics 365 for Operations y ofrece vínculos a los recursos que pueden ayudarle a implementarla en su organización.

<a name="overview"></a>Visión general
--------

La aplicación móvil Microsoft Dynamics 365 for Operations permite a su organización tener los procesos de negocio disponibles en dispositivos móviles. Una vez que la administración de TI habilita la característica de espacios de trabajo móviles para su organización, los usuarios pueden iniciar sesión en la aplicación e inmediatamente comenzar a trabajar con procesos empresariales en sus dispositivos móviles. La aplicación móvil Dynamics 365 for Operations incluye las siguientes características que pueden ayudarle a aumentar la productividad:

-   Los usuarios pueden ver, editar, y realizar acciones en datos empresariales, incluso si tienen conectividad de red intermitente o sus dispositivos móviles están completamente sin conexión. Cuando un dispositivo restablece una conexión de red, las operaciones de datos sin conexión se sincronizan automáticamente con Dynamics 365 for Operations.
-   Las administraciones o los desarrolladores de TI pueden crear y publicar espacios de trabajo móviles adaptados para la organización. La aplicación utiliza los activos codificados existentes. Por lo tanto, no tiene tener que volver a implementar los procedimientos de validación, la lógica de negocios, o la configuración de seguridad.
-   Las administraciones o los desarrolladores de TI fácilmente diseñan espacios de trabajo móviles mediante el diseñador de espacios de trabajo interactivo que se incluye en el cliente web de Dynamics 365 for Operations.
-   Los administradores o los desarrolladores de TI pueden opcionalmente optimizar las capacidades sin conexión de los espacios de trabajo usando el marco de extensibilidad de la lógica empresarial. Dado que los datos continúan con su procesamiento mientras el dispositivo está desconectado, los escenarios móviles siguen siendo ricos y fluidos, aunque los dispositivos no tengan conectividad de red constante.

## <a name="elements-of-the-mobile-app"></a>Elementos de la aplicación móvil
La exploración en la aplicación móvil consiste en cuatro conceptos simples: el panel de información, los espacios de trabajo, las páginas, y las acciones. 

[![Conceptos de navegación en la aplicación móvil](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)

-   Al iniciar la aplicación, vaya al **panel de información**.
-   En el panel de información, puede ver una lista de los **espacios de trabajo** que se publican en su entorno de Dynamics 365 for Operations.
-   En cada espacio de trabajo, puede ver una lista de las **páginas** que están disponibles para dicho espacio de trabajo.
-   En una página, puede ver los datos que se obtienen de una o varias páginas de Dynamics 365 for Operations.
-   Desde una página, puede navegar a otras páginas para buscar datos relacionados, como líneas o detalles de entidad.
-   En una página, también puede ver una lista de **acciones** disponibles para dicha página.
-   Las acciones le permiten crear o editar datos existentes.

## <a name="implementation-process"></a>Proceso de implementación
La ilustración siguiente muestra el proceso para implementar la aplicación móvil Dynamics 365 for Operations en la organización. 

[![](./media/mobile-implementation-process_4.png)](./media/mobile-implementation-process_4.png) 

La tabla siguiente incluye vínculos a recursos que pueden ayudarle a implementar la aplicación móvil Microsoft Dynamics 365 for Operations en su organización. Los números de la primera columna corresponden a los pasos numerados de la ilustración anterior.

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>Paso</th>
<th>Función</th>
<th>Acción</th>
<th>Recursos para ayudarle a completar la acción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>1</td>
<td>Administrador del sistema</td>
<td>Implemente Dynamics 365 for Operations para la organización.</td>
<td>Si todavía no tiene Dynamics 365 for Operations implementado en su organización, consulte <a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/deployment/deploy-demo-environment">Implementar un entorno de demostración de Microsoft Dynamics 365 for Operations</a>.</td>
</tr>
<tr class="even">
<td>2</td>
<td>Administrador del sistema</td>
<td>Descargue e instale KB que permitan espacios de trabajo móviles proporcionados por Microsoft.</td>
<td>Consulte la sección &quot;Requisitos previos&quot; del tema que trata sobre los espacios de trabajo móviles que la organización desea utilizar:
<ul>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/cost-accounting/cost-controlling-mobile-workspace">Espacios de trabajo móviles de control de costes</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/inventory-on-hand-mobile-workspace">Espacio de trabajo móvil de inventario disponible</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/sales-orders-mobile-workspace">Espacios de trabajo móviles de pedidos de ventas</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Espacio de trabajo de móvil de colaboración de proveedor</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/project-management/project-time-entry-mobile-workspace">Espacio de trabajo móvil de entrada de horas de proyecto</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>3</td>
<td>Administrador del sistema</td>
<td>Publique los espacios de trabajo móviles que se proporcionan en Microsoft.</td>
<td>Consulte la sección &quot;Requisitos previos&quot; del tema que trata sobre los espacios de trabajo móviles que la organización desea utilizar:
<ul>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/cost-accounting/cost-controlling-mobile-workspace">Espacios de trabajo móviles de control de costes</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/inventory-on-hand-mobile-workspace">Espacio de trabajo móvil de inventario disponible</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/sales-orders-mobile-workspace">Espacios de trabajo móviles de pedidos de ventas</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Espacio de trabajo de móvil de colaboración de proveedor</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/project-management/project-time-entry-mobile-workspace">Espacio de trabajo móvil de entrada de horas de proyecto</a></li>
</ul></td>
</tr>
<tr class="even">
<td>4</td>
<td>Desarrollador o fabricante de software independiente (ISV)</td>
<td>Use el marco móvil de Dynamics 365 for Operations para crear espacios de trabajo móviles personalizados.</td>
<td><ul>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/mobile-apps/mobile-platform">Marco móvil de Microsoft Dynamics 365 for Operations</a></li>
<li><a href="http://ax.help.dynamics.com/en/wiki/operations-mobile-workspace-x-apis/">API del espacio de trabajo Dynamics 365 for Operations X++</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>5</td>
<td>ISV</td>
<td>Cree un paquete desplegable que contenga espacios de trabajo móviles personalizados, y cargue el paquete en Microsoft Dynamics Lifecycle Services (LCS).</td>
<td><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/deployment/create-apply-deployable-package">Generar un paquete desplegable</a></td>
</tr>
<tr class="even">
<td>6</td>
<td>Administrador del sistema</td>
<td>Aplique el paquete desplegable que contiene los espacios de trabajo personalizados que proporciona el ISV.</td>
<td><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/deployment/apply-deployable-package-system">Aplique un paquete desplegable en un sistema Microsoft Dynamics 365 for Operations</a></td>
</tr>
<tr class="odd">
<td>7</td>
<td>Administrador del sistema</td>
<td>Publique los espacios de trabajo personalizados que proporciona el ISV.</td>
<td><a href="https://docs.microsoft.com/en-us/dynamics365/operations/dev-itpro/mobile-apps/publish-mobile-workspace">Publicar un espacio de trabajo móvil</a></td>
</tr>
<tr class="even">
<td>8</td>
<td>Usuario</td>
<td>Descargue e instale la aplicación móvil Dynamics 365 for Operations.</td>
<td><ul>
<li>Para Android: <a href="https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile">Dynamics 365 for Operations en Google Play Store</a></li>
<li>Para iPhone: <a href="https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8">Dynamics 365 for Operations en la tienda de aplicaciones de iTunes</a></li>
</ul></td>
</tr>
<tr class="odd">
<td>9</td>
<td>Usuario</td>
<td>Inicie sesión en la aplicación móvil Dynamics 365 for Operations y úsela. La aplicación incluye los espacios de trabajo móviles que se han publicado.</td>
<td>Microsoft ha ofrecido los espacios de trabajo móviles siguientes:
<ul>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/cost-accounting/cost-controlling-mobile-workspace">Espacios de trabajo móviles de control de costes</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/inventory-on-hand-mobile-workspace">Espacio de trabajo móvil de inventario disponible</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/production-control/sales-orders-mobile-workspace">Espacios de trabajo móviles de pedidos de ventas</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/supply-chain/procurement/vendor-collaboration-mobile-workspace">Espacio de trabajo de móvil de colaboración de proveedor</a></li>
<li><a href="https://docs.microsoft.com/en-us/dynamics365/operations/financials/project-management/project-time-entry-mobile-workspace">Espacio de trabajo móvil de entrada de horas de proyecto</a></li>
</ul></td>
</tr>
</tbody>
</table>



<a name="see-also"></a>Consulte también
--------

[Espacios de trabajo móviles emitidos recientemente para la aplicación móvil Dynamics 365 for Operations](mobile-workspaces-released.md)





