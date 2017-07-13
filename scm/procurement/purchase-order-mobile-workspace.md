---
title: "Área de trabajo de móvil de la aprobación del pedido de compra"
description: "Este tema proporciona información acerca del Espacio de trabajo móvil de la aprobación del pedido de compra, que le permite ver pedidos de compra y responder a ellos con acciones. Por ejemplo, puede aprobar o rechazar un pedido de compra."
author: mkirknel
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.search.scope: Core, Operations, UnifiedOperations, Retail
ms.custom: 30211
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: a2ab719b971c325be184d1d950f6c03815e4cea2
ms.contentlocale: es-es
ms.lasthandoff: 06/20/2017


---

# Área de trabajo de móvil de la aprobación del pedido de compra
<a id="purchase-order-approval-mobile-workspace" class="xliff"></a>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]

Este tema proporciona información sobre el espacio de trabajo móvil **Aprobación del pedido de compra**. Este espacio de trabajo le permite ver pedidos de compra y responder a ellos con acciones. Por ejemplo, puede aprobar o rechazar un pedido de compra.
 
## Información general
<a id="overview" class="xliff"></a> 
Los pedidos de compra que requieren aprobación pasan por un flujo de trabajo de aprobación. El flujo de trabajo puede incluir varios pasos que requieren que una o más personas realicen una acción. Por ejemplo, una persona puede tener que completar una tarea o aprobar el pedido de compra. 

El espacio de trabajo móvil **Aprobación de pedido de compra** le permite ver fácilmente y responder a los pedidos de compra desde el dispositivo móvil. Este espacio de trabajo también le permite realizar las mismas acciones que el cliente web de Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition.

## Requisitos previos
<a id="prerequisites" class="xliff"></a>
Los requisitos varían en función de la versión de Finance and Operations que se haya implementado en su organización.

### Requisitos previos si usa Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, actualización de julio 2017
<a id="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-update" class="xliff"></a> 
Si Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (actualización de julio de 2017) se ha implementado en su organización, el administrador del sistema debe publicar el espacio de trabajo móvil **Aprobación del pedido de compra**. Para obtener instrucciones, consulte [Publicar un espacio de trabajo móvil](/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace).

### Requisitos si usa Microsoft Dynamics 365 for Operations versión 1611 con actualización de plataforma 3 o posterior
<a id="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later" class="xliff"></a>
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
<td>Implementar 4017918 KB.</td>
<td>Administrador del sistema</td>
<td>KB 4017918 es una actualización X++ o revisión de metadatos que contiene el espacio de trabajo móvil <strong>Aprobación del pedido de compra</strong>. Para implementar KB 4017918, el administrador del sistema debe seguir estos pasos.
<ol>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/download-hotfix-lcs">Descargar la revisión de metadatos en Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">Instalar la revisión de metadatos</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/create-apply-deployable-package">Crear un paquete desplegable</a> que contenga el modelo <strong>SCMMobile</strong> y luego cargar el paquete desplegable en LCS.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">Aplicar el paquete implementable</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Publique el espacio de trabajo <strong>Aprobación del pedido de compra</strong>.</td>
<td>Administrador del sistema</td>
<td>Consulte <a href="/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace">Publicar un espacio de trabajo móvil</a>.</td>
</tr>
</tbody>
</table>

## Descargar e instalar la aplicación móvil
<a id="download-and-install-the-mobile-app" class="xliff"></a>
Descargue e instale la aplicación móvil Microsoft Dynamics 365 for Unified Operations:

- [Para teléfonos Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)


## Iniciar sesión en la aplicación móvil
<a id="sign-in-to-the-mobile-app" class="xliff"></a>

1. Inicie la aplicación en su dispositivo móvil.
2. Escriba la dirección URL de Microsoft Dynamics 365.
3. La primera vez que se inicie sesión, se le solicitará su nombre de usuario y contraseña. Escriba sus credenciales.
4. Tras iniciar sesión, se mostrarán los espacios de trabajo disponibles para su empresa. Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, tendrá que actualizar la lista de espacios de trabajo móviles.

![Espacio de trabajo de aprobación del pedido de compra en la lista de espacios de trabajo disponibles](./media/po-workspaces.png)

## Visualización de los pedidos asignados al usuario
<a id="view-orders-that-are-assigned-to-you" class="xliff"></a>
1. En el dispositivo móvil, seleccione el espacio de trabajo **Aprobación del pedido de compra**.
2. Seleccione **Pedidos asignados a mí** para ver todos los pedidos de compra para los que le han pedido tomar medidas en el flujo de trabajo de aprobación del pedido de compra.
3. Seleccione un pedido. En la página **Detalles de pedido** , verá la información y las líneas de encabezado del pedido. También puede encontrar instrucciones de la tarea del flujo de trabajo.
4. Seleccione **Distribuciones contables** para abrir la página **Distribuciones contables para el encabezado**.
5. Vuelva a la página **Detalles de pedido** y seleccione una línea. Desde los detalles de la línea de pedido, también puede explorar las distribuciones contables específicas de línea.

## Realice una acción en el pedido de compra
<a id="complete-an-action-on-the-purchase-order" class="xliff"></a>
Una vez que haya visualizado el pedido de compra que se le ha asignado y leído las instrucciones del flujo de trabajo, debe estar listo para tomar medidas.

1. En el dispositivo móvil, seleccione el espacio de trabajo **Aprobación del pedido de compra**.
2. Seleccione **Pedidos asignados a mí** para ver todos los pedidos de compra para los que le han pedido tomar medidas en el flujo de trabajo de aprobación del pedido de compra.
3. Seleccione un pedido y vea la página de detalles.
4. Seleccione **Acciones** para mostrar las acciones disponibles. Las acciones disponibles dependen de la tarea que se le haya asignado.

    | Acción de tarea    | Acción de aprobación  |
    |----------------|------------------|
    | Completo       | Aprobar          |
    | Devolución         | Rechazar           |
    | Solicitar cambio | Solicitar cambio   |
    | Delegar       | Delegar         |

5. Seleccione la acción adecuada.
6. En la página **Completar tarea**, escriba un comentario. Tenga en cuenta que si selecciona la acción **Delegar**, debe seleccionar un usuario en el que delegar la tarea.
7. Seleccione **Listo**. Después de actualizar su espacio de trabajo, el pedido de compra ya no estará en su lista. 

