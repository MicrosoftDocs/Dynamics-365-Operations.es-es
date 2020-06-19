---
title: Características de Platform quitadas u obsoletas
description: En este tema se describen las características que se han eliminado, o que está previsto que se eliminen en las Platform updates de las aplicaciones de Finance and Operations.
author: sericks007
manager: AnnBe
ms.date: 06/02/2020
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
ms.openlocfilehash: 6fc699907d30fff2d05e752ea055cae8d1134d9b
ms.sourcegitcommit: 3eaa71c889545318737b3bc88b05eae1a47ad2c0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2020
ms.locfileid: "3433931"
---
# <a name="removed-or-deprecated-platform-features"></a>Características de Platform quitadas u obsoletas

[!include [banner](../includes/banner.md)]

En este tema se describen las características que se han eliminado, o que está previsto que se eliminen en las Platform updates de las aplicaciones de Finance and Operations.

- Una característica *quitada* dejará de estar disponible en el producto.
- Una característica *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Esta lista está pensada para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación. 

> [!NOTE]
> La información detallada sobre los objetos de aplicaciones Finance and Operations se puede encontrar en los [Informes de referencia técnica](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Se pueden comparar las diferentes versiones de estos informes para conocer los objetos que se han modificado o quitado en cada versión de aplicaciones Finance and Operations.

## <a name="platform-updates-for-version-10012-of-finance-and-operations-apps"></a>Platform updates para la versión 10.0.12 de aplicaciones Finance and Operations

### <a name="grid-or-group-control-form-extensions-containing-invalid-field-references"></a>Extensiones de formulario de control de grupo o cuadrícula que contienen referencias de campo no válidas

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La propiedad del grupo de datos en los controles de cuadrícula o grupo se usa para mostrar automáticamente todos los campos de un grupo de campos. Un control de cuadrícula o grupo agregado por extensión podría contener campos que ya no están definidos en el grupo de campos, o podrían faltar campos que están definidos en el grupo de campos. Esto puede causar un comportamiento incoherente en tiempo de ejecución. Las actualizaciones de plataforma para la versión 10.0.12 de las aplicaciones de Finance and Operations clasifican ahora este problema como una *advertencia* de compilador. Para solucionar este problema, abra la extensión del formulario y guárdelo.
| **¿Reemplazado por otra característica?**   | Esta advertencia del compilador se reemplazará con un error del compilador en una actualización futura. |
| **Áreas de producto afectadas**         | Herramientas de desarrollo de Visual Studio |
| **Opción de implementación**              | Todos |
| **Estado**                         | Se introduce una advertencia del compilador en actualizaciones de plataformas para la versión 10.0.12 de aplicaciones de Finance and Operations. |

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>Platform updates para la versión 10.0.11 de aplicaciones Finance and Operations

### <a name="explicit-whitelisting-for-self-service-environments"></a>Lista blanca explícita para entornos de autoservicio

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El proceso para la lista blanca de IP ha cambiado. El autoservicio ya no admite la lista blanca de IP. |
| **¿Reemplazado por otra característica?**   | Para más información, consulte [Configuración de acceso condicional de Azure Active Directory](https://docs.microsoft.com/appcenter/general/configuring-aad-conditional-access).|
| **Áreas de producto afectadas**         | Seguridad |
| **Opción de implementación**              | Nube |
| **Estado**                         | **Obsoleto:** esta característica está totalmente en desuso para las implementaciones en autoservicio. |

### <a name="visual-studio-2015"></a>Visual Studio 2015

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Para admitir las últimas versiones de Visual Studio, se deben realizar algunos cambios en las extensiones X++ para Visual Studio. Estos cambios son incompatibles con Visual Studio 2015. |
| **¿Reemplazado por otra característica?**   | Visual Studio 2017 reemplazará a Visual Studio 2015 como versión implementada y necesaria. |
| **Áreas de producto afectadas**         | Herramientas de desarrollo de Visual Studio |
| **Opción de implementación**              | Todos |
| **Estado**                         | Una vez anunciada la disponibilidad de nuevas máquinas virtuales (VM) con Visual Studio 2017, las máquinas virtuales existentes con solo Visual Studio 2015 tendrán que volver a implementarse con la oleadda 1 de 2021. |

### <a name="field-groups-containing-invalid-field-references"></a>Grupos de campos que contienen referencias de campo no válidas

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los grupos de campos en las definiciones de metadatos de la tabla pueden contener referencias de campo que no son válidas. Si estos grupos de campos se implementan, pueden provocar errores del tiempo de ejecución en Financial Reporting y Microsoft SQL Server Reporting Services (SSRS). La Platform update 23 introdujo una *advertencia* de compilador que permitió abordar este problema de metadatos. Platform updates para la versión 10.0.11 de las aplicaciones Finance and Operations clasifican este problema como un *error* de compilador.<p>Para arreglar este problema, siga estos pasos.</p><ol><li>Quite la referencia de campo no válida de la definición del grupo de campos de tabla.</li><li>Vuelva a compilar.</li><li>Asegúrese de abordar cualquier error.</li></ol> |
| **¿Reemplazado por otra característica?**   | Este error del compilador reemplaza permanentemente la advertencia del compilador.  |
| **Áreas de producto afectadas**         | Herramientas de desarrollo de Visual Studio |
| **Opción de implementación**              | Todos |
| **Estado**                         | **Obsoleto:** la advertencia del compilador es un error del compilador en las Platform updates para la versión 10.0.11 de aplicaciones Finance and Operations. |

### <a name="isv-licenses-created-by-using-the-sha1-hashing-algorithm"></a>Licencias de ISV creadas utilizando el algoritmo de hash SHA1

|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El proceso para crear licencias de proveedores de software independientes (ISV) ha cambiado. Para más información, ver [Licencia de proveedor de software independiente (ISV)](../dev-tools/isv-licensing.md#appendix-create-self-signed-certificates-for-test-purposes). |
| **¿Reemplazado por otra característica?**   | Sí. Use Windows PowerShell para crear licencias. |
| **Áreas de producto afectadas**         | Herramientas de desarrollo de Visual Studio |
| **Opción de implementación**              | Todos |
| **Estado**                         | <strong>Obsoleto:</strong> las licencias de ISV que se crearon utilizando el algoritmo de hash SHA1. Este algoritmo dependía de los certificados que se crearon utilizando la utilidad MakeCert, y esta utilidad ha quedado en desuso.<p><strong>Obsoleto:</strong> el uso de SHA1 para fines de seguridad o hashing. SHA1 dejará de funcionar a principios de 2021. Por lo tanto, ya no debe usarse.<p><strong>Eliminado:</strong> soporte para Transport Layer Security (TLS) 1.0 y TLS 1.1 solicitudes entrantes o salientes. |

## <a name="platform-update-32"></a>Platform update 32

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>El cuadro de diálogo de cambio de solicitud de flujo de trabajo ya no incluye la lista desplegable de selección de usuario
|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Este era un problema de seguridad porque la solicitud de cambio se podía enviar a un usuario no deseado. Esto también fue un problema de usabilidad porque obligó al usuario a determinar quién era el creador del flujo de trabajo y seleccionarlos manualmente.  |
| **¿Reemplazado por otra característica?**   | No |
| **Áreas de producto afectadas**         | Flujo de trabajo |
| **Opción de implementación**              | Todas |
| **Estado**                         | La lista desplegable de selección de usuario se eliminó del cuadro de diálogo de solicitud de cambio en la Platform update 32. Las solicitudes de cambio de solicitud se enviarán automáticamente al originador según lo previsto. Para obtener más información sobre esta funcionalidad, consulte [Acciones en procesos de aprobación de flujo de trabajo](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change). |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>Los vínculos de obtención de detalles integrados ya no se admiten en los documentos paginados que genera el servicio hospedado en la nube 
|   |  |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Las direcciones URL de navegación integradas en documentos generados por el servicio pueden contener datos empresariales confidenciales. Vamos a eliminar la compatibilidad con los vínculos de obtención de detalles integrados en los documentos como medida de seguridad para mejorar la protección de los datos del cliente. Los usuarios también se beneficiarán de un rendimiento mejorado al producir documentos de manera interactiva como consecuencia de este cambio.  |
| **¿Reemplazado por otra característica?**   | Nº |
| **Áreas de producto afectadas**         | Notificación |
| **Opción de implementación**              | Todos |
| **Estado**                         | Esta característica se está quitando de manera activa del servicio.<br><br>El cliente moderno ofrece numerosas opciones para producir vistas que incluyen vínculos generados automáticamente para facilitar la navegación de la aplicación. Se recomienda usar los documentos paginados que genera el servicio para las comunicaciones externas que se envían por correo electrónico, se archivan y se imprimen para los destinatarios. Hemos mejorado la experiencia de vista previa de documentos directamente en el explorador, que ofrece acceso directo a impresoras locales. Para obtener más información, consulte [Mostrar vista previa de documentos PDF con un visor incrustado](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/preview-pdf-documents). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Anuncios anteriores sobre características quitadas u obsoletas
Para obtener más información sobre las características que se han eliminado o desaprobado en versiones anteriores, consulte [Funciones eliminadas o en desuso en versiones anteriores](../migration-upgrade/deprecated-features.md).

