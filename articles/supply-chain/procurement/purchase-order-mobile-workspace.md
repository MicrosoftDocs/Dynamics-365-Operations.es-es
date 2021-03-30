---
title: Área de trabajo de móvil de la aprobación del pedido de compra
description: Este tema proporciona información acerca del Espacio de trabajo móvil de la aprobación del pedido de compra, que le permite ver pedidos de compra y responder a ellos con acciones. Por ejemplo, puede aprobar o rechazar un pedido de compra.
author: RichardLuan
manager: tfehr
ms.date: 12/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchVendorPortalRequests
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30211
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 37c0fc273091af260089229ad9ee66b52dce3831
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215994"
---
# <a name="purchase-order-approval-mobile-workspace"></a>Área de trabajo de móvil de la aprobación del pedido de compra

[!include [banner](../includes/banner.md)]

Este tema proporciona información sobre el espacio de trabajo móvil **Aprobación del pedido de compra**. Este espacio de trabajo le permite ver pedidos de compra y responder a ellos con acciones. Por ejemplo, puede aprobar o rechazar un pedido de compra.
 
## <a name="overview"></a>Información general 
Los pedidos de compra que requieren aprobación pasan por un flujo de trabajo de aprobación. El flujo de trabajo puede incluir varios pasos que requieren que una o más personas realicen una acción. Por ejemplo, una persona puede tener que completar una tarea o aprobar el pedido de compra. 

El espacio de trabajo móvil **Aprobación de pedido de compra** le permite ver fácilmente y responder a los pedidos de compra desde el dispositivo móvil. Este espacio de trabajo también le permite realizar las mismas acciones que el cliente web.

## <a name="prerequisites"></a>Requisitos previos
Los requisitos varían en función de la versión de Supply Chain Management que se haya implementado en su organización.

### <a name="prerequisites-if-you-use-supply-chain-management"></a>Requisitos previos si usa Supply Chain Management 
Si Supply Chain Management se ha implementado para su organización, el administrador del sistema debe publicar el espacio de trabajo móvil **Aprobación del pedido de compra**. Para obtener instrucciones, consulte [Publicar un espacio de trabajo móvil](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

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
<td>Implementar 4017918 KB.</td>
<td>Administrador del sistema</td>
<td>KB 4017918 es una actualización X++ o revisión de metadatos que contiene el espacio de trabajo móvil <strong>Aprobación del pedido de compra</strong>. Para implementar KB 4017918, el administrador del sistema debe seguir estos pasos.
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Descargar la revisión de metadatos de Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Instalar la revisión de metadatos</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Crear un paquete desplegable</a> que contenga el modelo <strong>SCMMobile</strong> y luego cargar el paquete desplegable en LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Aplicar el paquete implementable</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Publique el espacio de trabajo <strong>Aprobación del pedido de compra</strong>.</td>
<td>Administrador del sistema</td>
<td>Consulte <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Publicar un espacio de trabajo móvil</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>Descargar e instalar la aplicación móvil
Descargar e instalar la aplicación móvil de Finance and Operations:

- [Para teléfonos Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Para iPhones](https://go.microsoft.com/fwlink/?linkid=850663)


## <a name="sign-in-to-the-mobile-app"></a>Iniciar sesión en la aplicación móvil

1. Inicie la aplicación en su dispositivo móvil.
2. Especifique la dirección URL Microsoft Dynamics 365.
3. La primera vez que se inicie sesión, se le solicitará su nombre de usuario y contraseña. Escriba sus credenciales.
4. Tras iniciar sesión, se mostrarán los espacios de trabajo disponibles para su empresa. Tenga en cuenta que si el administrador del sistema publica un nuevo espacio de trabajo más tarde, tendrá que actualizar la lista de espacios de trabajo móviles.

![Espacio de trabajo de aprobación del pedido de compra en la lista de espacios de trabajo disponibles](./media/po-workspaces.png)

## <a name="view-orders-that-are-assigned-to-you"></a>Visualización de los pedidos asignados al usuario
1. En el dispositivo móvil, seleccione el espacio de trabajo **Aprobación del pedido de compra**.
2. Seleccione **Pedidos asignados a mí** para ver todos los pedidos de compra para los que le han pedido tomar medidas en el flujo de trabajo de aprobación del pedido de compra.
3. Seleccione un pedido. En la página **Detalles de pedido** , verá la información y las líneas de encabezado del pedido. También puede encontrar instrucciones de la tarea del flujo de trabajo.
4. Seleccione **Distribuciones contables** para abrir la página **Distribuciones contables para el encabezado**.
5. Vuelva a la página **Detalles de pedido** y seleccione una línea. Desde los detalles de la línea de pedido, también puede explorar las distribuciones contables específicas de línea.

## <a name="complete-an-action-on-the-purchase-order"></a>Realice una acción en el pedido de compra
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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]