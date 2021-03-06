---
title: Características de Platform quitadas u obsoletas
description: En este tema se describen las características que se han eliminado, o que está previsto que se eliminen en las Platform updates de las aplicaciones de Finance and Operations.
author: sericks007
ms.date: 05/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 435f7f0090ca16a9e8cfee2d1ceb65bec8457d09
ms.sourcegitcommit: eff3da7ea98758f100d44ff7feec17157afc2e80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111733"
---
# <a name="removed-or-deprecated-platform-features"></a>Características de Platform quitadas u obsoletas

[!include [banner](../includes/banner.md)]

En este tema se describen las características que se han eliminado, o que está previsto que se eliminen en las Platform updates de las aplicaciones de Finance and Operations.

- Una característica *quitada* dejará de estar disponible en el producto.
- Una característica *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Esta lista está pensada para ayudarle a tener en cuenta estas eliminaciones y deprecaciones para su propia planificación. 

La información detallada sobre los objetos de aplicaciones Finance and Operations se puede encontrar en los [Informes de referencia técnica](/dynamics/s-e/global/axtechrefrep_61). Se pueden comparar las diferentes versiones de estos informes para conocer los objetos que se han modificado o quitado en cada versión de aplicaciones Finance and Operations.

## <a name="feature-deprecation-notice-effective-may-2021"></a>Aviso de desactivación de funciones a partir de mayo de 2021

### <a name="globalization-portal-in-lifecycle-services-lcs"></a>Portal de globalización en Lifecycle Services (LCS)

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Estamos abandonando el portal de globalización en LCS ya que esta función ha sido reemplazada por otros servicios basados en LCS. |
| **¿Reemplazado por otra característica?**   | Sí, esta función es reemplazada por LCS [Búsqueda de temas](../lifecycle-services/issue-search-lcs.md) y [Servicio de envío de alertas regulatorias dinámicas](../lcs-solutions/submit-localization-alerts.md). |
| **Áreas de producto afectadas**         | Portal de globalización en LCS|
| **Opción de implementación**              | Implementación en la nube |
| **Estado**                         | En desuso: fecha de eliminación planificada en mayo de 2022. |


## <a name="feature-removed-effective-january-28-2021"></a>Función eliminada a partir del 28 de enero de 2021

### <a name="batch-job-to-handle-sql-index-defragmentation"></a>Trabajo por lotes para administrar la desfragmentación del índice de SQL

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Con el fin de reducir los gastos generales de operación, monitoreo y mantenimiento de la administración de índices por parte de los clientes, esta característica ha sido eliminada. |
| **¿Reemplazado por otra característica?**   | En el futuro, los servicios de Microsoft realizarán el mantenimiento del índice. Esto ocurrirá continuamente sin afectar las cargas de trabajo de los usuarios. |
| **Áreas de producto afectadas**         | Aplicaciones de Finance and Operations|
| **Opción de implementación**              | Implementación en la nube: afecta a los entornos de producción administrados por Microsoft y a los entornos sandbox de nivel 2 a 5. |
| **Estado**                         | Esta característica se ha eliminado. |


## <a name="platform-updates-for-version-10017-of-finance-and-operations-apps"></a>Platform updates para la versión 10.0.17 de aplicaciones Finance and Operations


### <a name="visual-studio-2015"></a>Visual Studio 2015

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Para admitir las últimas versiones de Visual Studio, se deben realizar algunos cambios en las extensiones X++ para Visual Studio. Estos cambios son incompatibles con Visual Studio 2015. |
| **¿Reemplazado por otra característica?**   | Visual Studio 2017 reemplazará a Visual Studio 2015 como versión implementada y necesaria. |
| **Áreas de producto afectadas**         | Herramientas de desarrollo de Visual Studio |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: tras la actualización, las herramientas X++ anteriores se eliminarán de Visual Studio 2015, y las herramientas actualizadas no se instalarán en Visual Studio 2015. No hay impacto en las compilaciones alojadas. Para compilar máquinas virtuales, la canalización de compilación (definición de compilación) debe actualizarse manualmente para cambiar la dependencia de MSBuild 14.0 (Visual Studio 2015) a MSBuild 15.0 (Visual Studio 2017) como se describe en [Actualizar una canalización heredada en Azure Pipelines](../dev-tools/pipeline-msbuild-update.md). |

### <a name="user-avatar"></a>Avatar de usuario 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El avatar de usuario que se muestra en el lado derecho de la barra de navegación se recuperó mediante una API del control de encabezado de Dynamics 365, que ha quedado en desuso. |
| **¿Reemplazado por otra característica?**   | Los usuarios verán sus iniciales en un círculo en la barra de navegación. Este es el mismo objeto visual que se usa actualmente en las máquinas de desarrollo. |
| **Áreas de producto afectadas**         | Cliente web |
| **Opción de implementación**              | Todos |
| **Estado**                         | Se quitó desde la versión 10.0.17. |

### <a name="enterprise-portal-ep-deprecation"></a>Desactivación del Enterprise Portal (EP)  

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los artefactos de metadatos asociados con Dynamics AX 2012 Enterprise Portal (EP) han quedado obsoletos, ya que EP nunca fue compatible con aplicaciones de Finance and Operations. |
| **¿Reemplazado por otra característica?**   | N.º |
| **Áreas de producto afectadas**         | Cliente web |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: todo el código EP está programado para ser eliminado en el lanzamiento de octubre de 2021. |

## <a name="platform-updates-for-version-10015-of-finance-and-operations-apps"></a>Platform updates para la versión 10.0.15 de aplicaciones Finance and Operations

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>La compatibilidad de Internet Explorer 11 con Dynamics 365 está en desuso

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | A partir de diciembre de 2020, queda en desuso la compatibilidad de Microsoft Internet Explorer 11 con todos los productos de Dynamics 365 e Internet Explorer 11 no se admitirá después de agosto de 2021.<br><br>Esto afectará a los clientes que usan productos Dynamics 365 que están diseñados para usarse a través de una interfaz de Internet Explorer 11. Después de agosto de 2021, Internet Explorer 11 no será compatible con dichos productos de Dynamics 365. |
| **¿Reemplazado por otra característica?**   | Recomendamos que los clientes hagan la transición a Microsoft Edge.|
| **Áreas de producto afectadas**         | Todos los productos Dynamics 365 |
| **Opción de implementación**              | Todos|
| **Estado**                         | En desuso: Internet Explorer 11 no se admitirá después de agosto de 2021.|


### <a name="visual-studio-add-in-to-apply-metadata-hotfixes"></a>Complemento de Visual Studio para aplicar revisiones de metadatos

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Las revisiones de metadatos ya no son compatibles con las actualizaciones del servicio [One Version](../../fin-ops/get-started/one-version.md) que se introdujeron en julio de 2018 con la versión 8.1. |
| **¿Reemplazado por otra característica?**   | Las revisiones de metadatos individuales no están disponibles para las versiones compatibles. En su lugar, se aplican actualizaciones de calidad acumulativas. |
| **Áreas de producto afectadas**         | Complementos de Visual Studio |
| **Opción de implementación**              | Máquinas virtuales de desarrollo |
| **Estado**                         | Con la versión 10.0.15, el complemento ya no se incluye en las herramientas de Visual Studio. |


## <a name="platform-updates-for-version-10014-of-finance-and-operations-apps"></a>Platform updates para la versión 10.0.14 de aplicaciones Finance and Operations

### <a name="online-users-page"></a>Página de usuarios en línea 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Esta es una página heredada que se creó para la arquitectura cliente/servidor anterior. La información de esta página no siempre es precisa, lo que puede resultar confuso y engañoso. |
| **¿Reemplazado por otra característica?**   | Proporcionaremos una página nueva en una actualización futura.|
| **Áreas de producto afectadas**         | Administración del sistema |
| **Opción de implementación**              | Todos |
| **Estado**                         | Para octubre de 2021, este formulario se habrá eliminado.   |


## <a name="platform-updates-for-version-10013-of-finance-and-operations-apps"></a>Platform updates para la versión 10.0.13 de aplicaciones Finance and Operations


### <a name="custom-code-defined-in-ssrs-report-properties"></a>Código personalizado definido en las propiedades de informe de SSRS 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | En general, el código personalizado ofrece ventajas limitadas y requiere una gran cantidad de recursos y procesamiento. El código personalizado lo utilizan principalmente los autores de informes para llamar a métodos públicos desde un ensamblado de código personalizado. Sin embargo, el servicio alojado en la nube no admite referencias a ensamblados personalizados para informes de SSRS. |
| **¿Reemplazado por otra característica?**   | Los autores de informes pueden optar por seguir haciendo referencia a las API de .NET públicas para operaciones de matemáticas, conversión y formato desde cualquier expresión de cuadro de texto. Para obtener más información, consulte [Agregar código a un informe (SSRS)](/sql/reporting-services/report-design/add-code-to-a-report-ssrs?view=sql-server-ver15).  |
| **Áreas de producto afectadas**         | Subconjunto de diseños de informes de aplicaciones definidos en un RDL que contiene código personalizado. |
| **Opción de implementación**              | Todos |
| **Estado**                         | Con la versión 10.0.13, el compilador comenzará a emitir una advertencia para las instancias en las que se detecte código personalizado en una definición de informe de SSRS. Para solucionar el problema, abra la definición de diseño del informe y quite todos los artefactos de código personalizados. Esta advertencia se reemplazará con un error del compilador en una actualización futura.   |

### <a name="upgrade-of-three-jquery-component-libraries"></a>Actualización de tres bibliotecas de componentes jQuery 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Se están actualizando tres bibliotecas de componentes jQuery para las correcciones de seguridad y para mantener la moneda.   
| **¿Reemplazado por otra característica?**   | Las siguientes bibliotecas se ven afectadas: jQuery (a la versión 3.5.0 de la versión 2.1.4), jQuery UI (a la versión 1.12.1 de la versión 1.11.4), jQuery qTip (a la versión 3.0.3 de 2.2.1). La guía de migración ha sido proporcionada en línea por jQuery.  |
| **Áreas de producto afectadas**         | Controles extensibles, específicamente código JavaScript personalizado que utiliza API obsoletas o eliminadas |
| **Opción de implementación**              | Todos |
| **Estado**                         | Con la versión 10.0.13/Actualización de plataforma 37, los clientes pueden pasar opcionalmente a las últimas bibliotecas habilitando la característica "Actualizar tres bibliotecas de componentes jQuery". El cambio a las nuevas bibliotecas será obligatorio con la versión de abril de 2021 para dar tiempo a la migración de las API afectadas.   |

### <a name="existing-grid-controlforcelegacygrid-api"></a>Control de cuadrícula existente/API forceLegacyGrid()

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El control de cuadrícula existente se está reemplazando por el nuevo control de cuadrícula. |
| **¿Reemplazado por otra característica?**   | El [nuevo control de cuadrícula](../..//fin-ops/get-started/grid-capabilities.md) |
| **Áreas de producto afectadas**         | Cliente web |
| **Opción de implementación**              | Todos |
| **Estado**                         | En la versión 10.0.13, el nuevo control de cuadrícula generalmente está disponible, y los clientes pueden activar esta función opcionalmente. El nuevo control de cuadrícula será obligatorio en la versión de octubre de 2021. Cuando el nuevo control de cuadrícula pase a ser obligatorio, la API **forceLegacyGrid()** se dejará de aplicar. |

### <a name="personalization-without-saved-views"></a>Personalización sin vistas guardadas 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El subsistema de personalización se ha revisado con la característica de vistas guardadas, para que tenga un mejor rendimiento y ofrezca capacidades adicionales. |
| **¿Reemplazado por otra característica?**   | Vistas guardadas |
| **Áreas de producto afectadas**         | Cliente web |
| **Opción de implementación**              | Todos |
| **Estado**                         | En la versión 10.0.13/Platform update 37, la función de vistas guardadas generalmente está disponible, y los clientes pueden activar esta característica opcionalmente. El característica de vistas guardadas será obligatoria en la versión de octubre de 2021. |


## <a name="platform-updates-for-version-10012-of-finance-and-operations-apps"></a>Platform updates para la versión 10.0.12 de aplicaciones Finance and Operations

### <a name="grid-or-group-control-form-extensions-containing-invalid-field-references"></a>Extensiones de formulario de control de grupo o cuadrícula que contienen referencias de campo no válidas

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | La propiedad del grupo de datos en los controles de cuadrícula o grupo se usa para mostrar automáticamente todos los campos de un grupo de campos. Un control de cuadrícula o grupo agregado por extensión podría contener campos que ya no están definidos en el grupo de campos, o podrían faltar campos que están definidos en el grupo de campos. Esto puede causar un comportamiento incoherente en tiempo de ejecución. Las actualizaciones de plataforma para la versión 10.0.12 de las aplicaciones de Finance and Operations clasifican ahora este problema como una *advertencia* de compilador. Para solucionar este problema, abra la extensión del formulario y guárdelo.
| **¿Reemplazado por otra característica?**   | Esta advertencia del compilador se reemplazará con un error del compilador en una actualización futura. |
| **Áreas de producto afectadas**         | Herramientas de desarrollo de Visual Studio |
| **Opción de implementación**              | Todos |
| **Estado**                         | Se introduce una advertencia del compilador en actualizaciones de plataformas para la versión 10.0.12 de aplicaciones de Finance and Operations. |

## <a name="platform-updates-for-version-10011-of-finance-and-operations-apps"></a>Platform updates para la versión 10.0.11 de aplicaciones Finance and Operations

### <a name="explicit-safe-lists-for-self-service-environments"></a>Lista segura explícita para entornos de autoservicio

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El proceso para mover IP a listas seguras ha cambiado. El autoservicio ya no admite la lista segura de IP. |
| **¿Reemplazado por otra característica?**   | Para más información, consulte [Configuración de acceso condicional de Azure Active Directory](/appcenter/general/configuring-aad-conditional-access).|
| **Áreas de producto afectadas**         | Seguridad |
| **Opción de implementación**              | Nube |
| **Estado**                         | Obsoleto: esta característica está totalmente en desuso para las implementaciones en autoservicio. |

### <a name="visual-studio-2015"></a>Visual Studio 2015

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Para admitir las últimas versiones de Visual Studio, se deben realizar algunos cambios en las extensiones X++ para Visual Studio. Estos cambios son incompatibles con Visual Studio 2015. |
| **¿Reemplazado por otra característica?**   | Visual Studio 2017 reemplazará a Visual Studio 2015 como versión implementada y necesaria. |
| **Áreas de producto afectadas**         | Herramientas de desarrollo de Visual Studio |
| **Opción de implementación**              | Todos |
| **Estado**                         | Las máquinas virtuales implementadas en la versión 10.0.13 (Platform update 37) o posterior contienen Visual Studio 2017. La versión 10.0.16 (Platform update 40) es la versión final con soporte para Visual Studio 2015. Máquinas virtuales con solo Visual Studio 2015 no se podrán actualizar a la versión 10.0.17 (Platform update 41). |

### <a name="field-groups-containing-invalid-field-references"></a>Grupos de campos que contienen referencias de campo no válidas

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Los grupos de campos en las definiciones de metadatos de la tabla pueden contener referencias de campo que no son válidas. Si estos grupos de campos se implementan, pueden provocar errores del tiempo de ejecución en Financial Reporting y Microsoft SQL Server Reporting Services (SSRS). La Platform update 23 introdujo una *advertencia* de compilador que permitió abordar este problema de metadatos. Platform updates para la versión 10.0.11 de las aplicaciones Finance and Operations clasifican este problema como un *error* de compilador.<p>Para arreglar este problema, siga estos pasos.</p><ol><li>Quite la referencia de campo no válida de la definición del grupo de campos de tabla.</li><li>Vuelva a compilar.</li><li>Asegúrese de abordar cualquier error.</li></ol> |
| **¿Reemplazado por otra característica?**   | Este error del compilador reemplaza permanentemente la advertencia del compilador.  |
| **Áreas de producto afectadas**         | Herramientas de desarrollo de Visual Studio |
| **Opción de implementación**              | Todos |
| **Estado**                         | En desuso: la advertencia del compilador es un error del compilador en las Platform updates para la versión 10.0.11 de aplicaciones Finance and Operations. |

### <a name="isv-licenses-created-by-using-the-sha1-hashing-algorithm"></a>Licencias de ISV creadas utilizando el algoritmo de hash SHA1

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | El proceso para crear licencias de proveedores de software independientes (ISV) ha cambiado. Para más información, ver [Licencia de proveedor de software independiente (ISV)](../dev-tools/isv-licensing.md#appendix-create-self-signed-certificates-for-test-purposes). |
| **¿Reemplazado por otra característica?**   | Sí. Use Windows PowerShell para crear licencias. |
| **Áreas de producto afectadas**         | Herramientas de desarrollo de Visual Studio |
| **Opción de implementación**              | Todos |
| **Estado**                         | Obsoleto: las licencias de ISV que se crearon utilizando el algoritmo de hash SHA1. Este algoritmo dependía de los certificados que se crearon utilizando la utilidad MakeCert, y esta utilidad ha quedado en desuso.<br><br>Obsoleto: el uso de SHA1 para fines de seguridad o hashing. SHA1 dejará de funcionar a principios de 2021. Por lo tanto, ya no debe usarse.<br><br>Eliminado: soporte para Transport Layer Security (TLS) 1.0 y TLS 1.1 solicitudes entrantes o salientes. |

## <a name="platform-update-32"></a>Platform update 32

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>El cuadro de diálogo de cambio de solicitud de flujo de trabajo ya no incluye la lista desplegable de selección de usuario

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Este era un problema de seguridad porque la solicitud de cambio se podía enviar a un usuario no deseado. Esto también fue un problema de usabilidad porque obligó al usuario a determinar quién era el creador del flujo de trabajo y seleccionarlos manualmente.  |
| **¿Reemplazado por otra característica?**   | No |
| **Áreas de producto afectadas**         | Flujo de trabajo |
| **Opción de implementación**              | Todas |
| **Estado**                         | La lista desplegable de selección de usuario se eliminó del cuadro de diálogo de solicitud de cambio en la Platform update 32. Las solicitudes de cambio de solicitud se enviarán automáticamente al originador según lo previsto. Para obtener más información sobre esta funcionalidad, consulte [Acciones en procesos de aprobación de flujo de trabajo](../../fin-ops/organization-administration/workflow-actions.md?toc=%2fdynamics365%2fcommerce%2ftoc.json#request-change). |

### <a name="embedded-drill-through-links-are-no-longer-supported-in-paginated-documents-rendered-by-the-cloud-hosted-service"></a>Los vínculos de obtención de detalles integrados ya no se admiten en los documentos paginados que genera el servicio hospedado en la nube 

| &nbsp;  | &nbsp; |
|------------|--------------------|
| **Motivo de la depreciación/eliminación** | Las direcciones URL de navegación integradas en documentos generados por el servicio pueden contener datos empresariales confidenciales. Vamos a eliminar la compatibilidad con los vínculos de obtención de detalles integrados en los documentos como medida de seguridad para mejorar la protección de los datos del cliente. Los usuarios también se beneficiarán de un rendimiento mejorado al producir documentos de manera interactiva como consecuencia de este cambio.  |
| **¿Reemplazado por otra característica?**   | Nº |
| **Áreas de producto afectadas**         | Notificación |
| **Opción de implementación**              | Todos |
| **Estado**                         | Esta característica se está quitando de manera activa del servicio.<br><br>El cliente moderno ofrece numerosas opciones para producir vistas que incluyen vínculos generados automáticamente para facilitar la navegación de la aplicación. Se recomienda usar los documentos paginados que genera el servicio para las comunicaciones externas que se envían por correo electrónico, se archivan y se imprimen para los destinatarios. Hemos mejorado la experiencia de vista previa de documentos directamente en el explorador, que ofrece acceso directo a impresoras locales. Para obtener más información, consulte [Mostrar vista previa de documentos PDF con un visor incrustado](../analytics/preview-pdf-documents.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Anuncios anteriores sobre características quitadas u obsoletas
Para obtener más información sobre las características que se han eliminado o desaprobado en versiones anteriores, consulte [Funciones eliminadas o en desuso en versiones anteriores](../migration-upgrade/deprecated-features.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
