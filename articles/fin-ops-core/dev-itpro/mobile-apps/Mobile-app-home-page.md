---
title: Página principal de aplicación móvil
description: Este tema describe la aplicación móvil de Finance and Operations (Dynamics 365) y ofrece vínculos a los recursos que pueden ayudarle a implementarla en su organización.
author: ChrisGarty
ms.date: 01/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.custom: intro-internal
ms.assetid: c99f818f-27b3-4e45-92b4-74272dad0e17
ms.search.region: Global
ms.author: cgarty
ms.dyn365.ops.version: Platform update 4
ms.search.validFrom: 2017-02-28
ms.openlocfilehash: e13e99515d52e1e24970908a106ae99a7e8b0d80
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6360825"
---
# <a name="mobile-app-home-page"></a>Página principal de aplicación móvil

[!include [banner](../includes/banner.md)]

Este tema describe la aplicación móvil de **Finance and Operations (Dynamics 365)** y ofrece vínculos a los recursos que pueden ayudarle a implementarla en su organización.

## <a name="overview"></a>Visión general

La aplicación móvil permite a su organización tener los procesos de negocio disponibles en dispositivos móviles. Una vez que el administrador de TI habilita los espacios de trabajo móviles para su organización, los usuarios pueden iniciar sesión en la aplicación e inmediatamente comenzar a trabajar con procesos empresariales en sus dispositivos móviles. La aplicación móvil incluye las siguientes características que pueden ayudarle a aumentar la productividad:

- Los usuarios pueden ver, editar, y realizar acciones en datos empresariales, incluso si tienen conectividad de red intermitente o sus dispositivos móviles están completamente sin conexión. Cuando un dispositivo restablece una conexión de red, las operaciones de datos sin conexión se sincronizan automáticamente.
- Las administraciones o los desarrolladores de TI pueden crear y publicar espacios de trabajo móviles adaptados para la organización. La aplicación utiliza los activos codificados existentes. Por lo tanto, no tiene tener que volver a implementar los procedimientos de validación, la lógica de negocios, o la configuración de seguridad.
- Las administraciones o los desarrolladores de TI fácilmente puede diseñar espacios de trabajo móviles mediante el diseñador de espacios de trabajo interactivo que se incluye en el cliente web.
- Los administradores o los desarrolladores de TI pueden opcionalmente optimizar las capacidades sin conexión de los espacios de trabajo usando el marco de extensibilidad de la lógica empresarial. Dado que los datos continúan con su procesamiento mientras el dispositivo está desconectado, los escenarios móviles siguen siendo ricos y fluidos, aunque los dispositivos no tengan conectividad de red constante.

## <a name="elements-of-the-mobile-app"></a>Elementos de la aplicación móvil
La exploración en la aplicación móvil consiste en cuatro conceptos básicos: el panel de información, los espacios de trabajo, las páginas, y las acciones. 

[![Conceptos de navegación en la aplicación móvil.](./media/mobilephoneapp1-1024x536.png)](./media/mobilephoneapp1.png)

1. Al iniciar la aplicación, vaya al **panel de información**.
2. En el panel, puede ver una lista de **espacios de trabajo** que ya sea han publicado.
3. En cada espacio de trabajo, puede ver una lista de las **páginas** que están disponibles para dicho espacio de trabajo.
4. Tras estar una página, puede realizar varias acciones. A continuación se incluyen algunos ejemplos:

    - Ver datos detallados.
    - Navegue a otras páginas, puede navegar a otras páginas para buscar datos relacionados, como líneas o detalles de entidad.
    - Vea una lista **acciones** disponibles para dicha página. Las acciones le permiten crear o editar datos existentes.

## <a name="implementation-process"></a>Proceso de implementación
La ilustración siguiente muestra el proceso para implementar ambos espacios de trabajo móviles que proporciona Microsoft y los espacios de trabajo móviles personalizados. 

[![Proceso de implementación de aplicaciones móviles.](./media/Mobile-implementation-process-5.png)](./media/Mobile-implementation-process-5.png)

La siguiente tabla incluye vínculos a los recursos que pueden ayudarle a implementar ambos espacios de trabajo móviles que proporciona Microsoft y los espacios de trabajo móviles personalizados. Los números de la primera columna corresponden a los pasos numerados de la ilustración anterior.

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
<td>Implemente la aplicación Finance and Operations en su organización.</td>
<td><ul><li>Si aún no ha implementado una versión de Microsoft Dynamics 365, vea <a href="../deployment/deploy-demo-environment.md">Implementar un entorno de demostración</a>.</li><li>Para ver una lista de espacios de trabajo móviles se pueden utilizar, vea <a href="mobile-workspaces-released.md">Espacios de trabajo móviles recientemente liberados</a>.</li></ul></td>
</tr>
<tr class="even">
<td>2</td>
<td>Administrador del sistema</td>
<td><strong>Si está usando Microsoft Dynamics 365 for Operations versión 1611:</strong> descargue e instale KB que permitan espacios de trabajo móviles proporcionados por Microsoft.</td>
<td>Consulte los temas siguientes para obtener más información:
<ul>

<li><a href="../../../finance/cost-accounting/cost-controlling-mobile-workspace.md">Espacios de trabajo móviles de control de costes</a></li>
<li><a href="../../../supply-chain/inventory/inventory-on-hand-mobile-workspace.md">Espacio de trabajo móvil de inventario disponible</a></li>
<li><a href="../../../supply-chain/sales-marketing/sales-orders-mobile-workspace.md">Espacios de trabajo móviles de pedidos de ventas</a></li>
<li><a href="../../../supply-chain/procurement/vendor-collaboration-mobile-workspace.md">Espacio de trabajo de móvil de colaboración de proveedor</a></li>
<li><a href="/dynamics365/project-operations/prod-pma/project-time-entry-mobile-workspace">Espacio de trabajo móvil de entrada de tiempo de proyecto</a></li>
<li><a href="/dynamics365/project-operations/prod-exp/expense-management-mobile-workspace">Espacio de trabajo móvil de gestión de gastos</a></li>

</ul></td>
</tr>
<tr class="odd">
<td>3</td>
<td>Administrador del sistema</td>
<td>Publique los espacios de trabajo móviles que se proporcionan en Microsoft.</td>
<td><a href="publish-mobile-workspace.md">Publicar un espacio de trabajo móvil</a>
</td>
</tr>
<tr class="even">
<td>4</td>
<td>Desarrollador o fabricante de software independiente (ISV)</td>
<td>Use la plataforma móvil para crear espacios de trabajo móviles personalizados.</td>
<td><a href="platform/mobile-platform-home-page.md">Plataforma móvil</a></td>
</tr>
<tr class="odd">
<td>5</td>
<td>ISV</td>
<td>Cree un paquete desplegable que contenga espacios de trabajo móviles personalizados, y cargue el paquete en Microsoft Dynamics Lifecycle Services (LCS).</td>
<td><a href="../deployment/create-apply-deployable-package.md">Crear un paquete implementable</a></td>
</tr>
<tr class="even">
<td>6</td>
<td>Administrador del sistema</td>
<td>Aplique el paquete desplegable que contiene los espacios de trabajo personalizados que proporciona el proveedor de software independiente (ISV).</td>
<td><a href="../deployment/apply-deployable-package-system.md">Aplicar un paquete implementable</a></td>
</tr>
<tr class="odd">
<td>7</td>
<td>Administrador del sistema</td>
<td>Publique los espacios de trabajo personalizados que proporciona el ISV.</td>
<td><a href="publish-mobile-workspace.md">Publicar un espacio de trabajo móvil</a></td>
</tr>
<tr class="even">
<td>8</td>
<td>Usuario</td>
<td>Descargar e instalar la aplicación móvil.</td>
<td>
<a href="https://go.microsoft.com/fwlink/?linkid=850662">Aplicación Finance and Operations para Android</a><BR/>
<a href="https://go.microsoft.com/fwlink/?linkid=850663">Aplicación Finance and Operations para iOS</a><BR/>
(Windows puede no admitido)
</td>
</tr>
<tr class="odd">
<td>9</td>
<td>Usuario</td>
<td>Inicie sesión y utilice la aplicación móvil. La aplicación incluye los espacios de trabajo móviles que ha publicado el administrador del sistema.</td>
<td>Para ver una lista de espacios de trabajo móviles que proporciona Microsoft, vea <a href="mobile-workspaces-released.md">Espacios de trabajo móviles recientemente liberados</a>.
</td>
</tr>
</tbody>
</table>

## <a name="troubleshooting"></a>Solución de problemas
[Recursos de plataforma móvil](platform/mobile-platform-home-page.md#troubleshooting-the-app)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]