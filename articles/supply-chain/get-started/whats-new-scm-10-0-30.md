---
title: Versión preliminar de Dynamics 365 Supply Chain Management 10.0.30 (noviembre de 2022)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Supply Chain Management 10.0.30.
author: kamaybac
ms.date: 09/08/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-09-08
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 477b27bf77d2a3ef91a5c2d39f2dfb06d8ad4e59
ms.sourcegitcommit: 562ea02e1f7409f18ee1cc4750a838bff4381e91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2022
ms.locfileid: "9429133"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10030-november-2022"></a>Versión preliminar de Dynamics 365 Supply Chain Management 10.0.30 (noviembre de 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

En este artículo se enumeran las características nuevas o modificadas en Microsoft Dynamics 365 Supply Chain Management versión preliminar 10.0.30. Esta versión tiene el número de compilación 10.0.1362 y está disponible con la siguiente programación:

- **Versión preliminar:** septiembre de 2022
- **Disponibilidad general de la versión (actualización automática):** octubre de 2022
- **Disponibilidad general de la versión (actualización automática):** noviembre de 2022

## <a name="features-included-in-this-release"></a>Características incluidas en esta versión

La tabla siguiente enumera las características incluidas en esta versión. Puede que haya actualizaciones de este artículo para incluir características que se agregaron a la compilación después de la publicación original del artículo.

| Área de características | Característica | Más información | Habilitada por   |
|---|---|---|---|
| Fabricación | [Supervisar equipos con Sensor Data Intelligence](/dynamics365-release-plan/2022wave2/finance-operations/dynamics365-supply-chain-management/monitor-equipment-sensor-data-intelligence) | [Página de inicio del sensor de Data Intelligence](../sensor-data-intelligence/sdi-home-page.md) | Administración de características:<br>*(Versión preliminar) Inteligencia de datos de sensor* |
| Gestión de almacenes | Desvíos de varios niveles para la aplicación móvil Warehouse Management <!-- KFM: Add link when RP updates --> | [Configurar desvíos para pasos en los elementos del menú del dispositivo móvil](../warehousing/warehouse-app-detours.md) | Administración de características:<br>*Desvíos de varios niveles para la aplicación móvil Warehouse Management* |

## <a name="feature-enhancements-included-in-this-release"></a>Mejoras de características incluidas en esta versión

La tabla siguiente enumera las mejoras de características incluidas en esta versión. Cada una de estas mejoras proporciona una mejora incremental de una función existente. Debido a que son solo mejoras, no se enumeran en el [plan de versión](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). Sin embargo, para garantizar que estas mejoras no entren en conflicto con sus preferencias o personalizaciones existentes, cada una de ellas está desactivada de forma predeterminada (a menos que se indique lo contrario).

Si desea activar o desactivar alguna de estas funciones, debe hacerlo en [gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Módulo | Nombre de la característica en la administración de características | Más información |
|---|---|---|
| Control de producción | Información disponible en la página de pedidos de producción que se van a liberar | Agrega una columna para la cantidad de inventario disponible del artículo de línea en la sección de líneas de la página de **Pedidos de producción que se van a liberar**. |
| Gestión del transporte | Asignar envíos a segmentos de ruta relacionados | Esta característica permite que el sistema distribuya los costos de flete de envío con mayor precisión, incluso para cargas con múltiples envíos entregados a varios destinos de segmento a lo largo de una sola ruta. Asigna cada envío al segmento de ruta más adecuado en función de las direcciones de destino del envío y el segmento. Luego, la función calcula el costo del flete de cada envío como una proporción del costo total del flete de la carga, según el peso, el volumen, la cantidad y la distancia recorrida relativos del envío. Esta función solo se aplica a los envíos gestionados mediante el módulo de gestión de transporte (TMS). |

## <a name="additional-resources"></a>Recursos adicionales

### <a name="platform-updates-for-finance-and-operations-apps"></a>Platform update para aplicaciones de Finanzas y Operaciones

Microsoft Dynamics 365 Supply Chain Management 10.0.30 incluye Platform updates. Para obtener más información, consulte [Platform updates para la versión 10.0.30 de aplicaciones de Finanzas y Operaciones (noviembre de 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-30.md). <!--KFM: Confirm link -->

### <a name="bug-fixes"></a>Correcciones de errores

Para obtener información sobre las correcciones de errores incluidas en cada una de las actualizaciones que forman parte de la versión 10.0.29, inicie sesión en Lifecycle Services (LCS) y consulte el [artículo de KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=745468).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 1 de 2022

¿Le gustaría conocer las nuevas y futuras funcionalidades disponibles en nuestra plataforma y en nuestras aplicaciones empresariales?

Consulte [Dynamics 365 y las nubes de la industria: plan del lanzamiento de versiones 2 de 2022](/dynamics365-release-plan/2022wave2/). Hemos recogido absolutamente todos los detalles en un solo documento que puede usar para la planificación.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Características de Supply Chain Management quitadas o en desuso

En el artículo [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) se describen las características que se han quitado o cuya eliminación o puesta en desuso están programadas para Supply Chain Management.

- Una característica *quitada* dejará de estar disponible en el producto.
- Una característica *en desuso* no está en el desarrollo activo y se podría quitar en una actualización futura.

Antes de eliminar una característica del producto, se anunciará el aviso de desuso en el artículo [Características quitadas o en desuso en Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 meses antes de su eliminación.

Para los cambios importantes que solo afectan al tiempo de compilación y tienen binarios compatibles con entornos de espacio aislado y de producción, el tiempo de puesta en desuso será inferior a 12 meses. Por lo general, son actualizaciones funcionales que hay que hacer en el compilador.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
