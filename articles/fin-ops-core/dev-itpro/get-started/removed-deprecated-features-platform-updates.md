---
title: Características de Platform quitadas u obsoletas
description: En este tema se describen las características que se han eliminado, o que está previsto que se eliminen en las Platform updates de las aplicaciones de Finance and Operations.
author: sericks007
manager: AnnBe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: d394f5ca84efc5beb943d349e45a3d2c9639d83c
ms.sourcegitcommit: 75974ae567bb0eacf0f65cac992b34ce5c680b93
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2020
ms.locfileid: "3095783"
---
# <a name="removed-or-deprecated-platform-features"></a>Características de Platform quitadas u obsoletas

[!include [banner](../includes/banner.md)]

En este tema se describen las características que se han eliminado, o que está previsto que se eliminen en las Platform updates de las aplicaciones de Finance and Operations.

- Una función *quitada* dejará de estar disponible en el producto.
- Una función *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Esta lista está pensada para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación. 

> [!NOTE]
> La información detallada sobre los objetos de aplicaciones Finance and Operations se puede encontrar en los [Informes de referencia técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Se pueden comparar las diferentes versiones de estos informes para conocer los objetos que se han modificado o quitado en cada versión de aplicaciones Finance and Operations.

## <a name="platform-update-32"></a>Actualización 32 de la plataforma

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>El cuadro de diálogo de cambio de solicitud de flujo de trabajo ya no incluye la lista desplegable de selección de usuario
|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Este era un problema de seguridad porque la solicitud de cambio se podía enviar a un usuario no deseado. Esto también fue un problema de usabilidad porque obligó al usuario a determinar quién era el creador del flujo de trabajo y seleccionarlos manualmente.  |
| **¿Reemplazado por otra característica?**   | No |
| **Áreas de producto afectadas**         | Flujo de trabajo |
| **Opción de implementación**              | Todas |
| **Estado**                         | La lista desplegable de selección de usuario se eliminó del cuadro de diálogo de solicitud de cambio en la Platform update 32. Las solicitudes de cambio de solicitud se enviarán automáticamente al originador según lo previsto. Para obtener más información sobre esta funcionalidad, vea [Acciones en procesos de aprobación de flujo de trabajo](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change). |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>Los vínculos de obtención de detalles integrados ya no se admiten en los documentos paginados que genera el servicio hospedado en la nube 
|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Las direcciones URL de navegación integradas en documentos generados por el servicio pueden contener datos empresariales confidenciales. Vamos a eliminar la compatibilidad con los vínculos de obtención de detalles integrados en los documentos como medida de seguridad para mejorar la protección de los datos del cliente. Los usuarios también se beneficiarán de un rendimiento mejorado al producir documentos de manera interactiva como consecuencia de este cambio.  |
| **¿Reemplazado por otra característica?**   | Nº |
| **Áreas de producto afectadas**         | Notificación |
| **Opción de implementación**              | Todos |
| **Estado**                         | Esta característica se está quitando de manera activa del servicio.<br><br>El cliente moderno ofrece numerosas opciones para producir vistas que incluyen vínculos generados automáticamente para facilitar la navegación de la aplicación. Se recomienda usar los documentos paginados que genera el servicio para las comunicaciones externas que se envían por correo electrónico, se archivan y se imprimen para los destinatarios. Hemos mejorado la experiencia de vista previa de documentos directamente en el explorador, que ofrece acceso directo a impresoras locales. Para obtener más información, consulte [Mostrar vista previa de documentos PDF con un visor incrustado](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/preview-pdf-documents). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Anuncios anteriores sobre funciones quitadas u obsoletas
Para obtener más información sobre las funciones que se han eliminado o desaprobado en versiones anteriores, consulte [Funciones eliminadas o en desuso en versiones anteriores](../migration-upgrade/deprecated-features.md).

