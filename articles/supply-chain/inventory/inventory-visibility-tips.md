---
title: Consejos de visibilidad de inventario
description: Este tema proporciona algunos consejos que debe tener en cuenta al configurar y utilizar el complemento de visibilidad de inventario.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 1f6ade36ac184a3c8bf790fc0d899ea01d90c8d2
ms.sourcegitcommit: f5fd2122a889b04e14f18184aabd37f4bfb42974
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/10/2022
ms.locfileid: "7952424"
---
# <a name="inventory-visibility-tips"></a>Consejos de visibilidad de inventario

[!include [banner](../includes/banner.md)]

Aquí tiene algunos consejos que debe tener en cuenta al configurar y utilizar el complemento de visibilidad de inventario:

- Actualmente, el complemento de visibilidad de inventario solo admite entornos de Microsoft Dataverse que fueron creados usando Microsoft Dynamics Lifecycle Services (LCS). Si su entorno de Dataverse se creó de otra forma (por ejemplo, usando el Centro de administración de Power Apps) y si está vinculado a su entorno de Dynamics 365 Supply Chain Management, primero debe comunicarse con el equipo de productos de Visibilidad de inventario para solucionar el problema de asignación. Puede ponerse en contacto con el equipo en [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com). El equipo le informará cuando su entorno esté listo para que instale Inventory Visibility.
- Si tiene más de un entorno LCS, cree una aplicación de Azure Active Directory (Azure AD) diferente para cada entorno. Si usa el mismo ID de aplicación y el mismo ID de inquilino para instalar el complemento de visibilidad de inventario para diferentes entornos, se producirá un problema de token para los entornos más antiguos. Solo será válida la última instancia del complemento de visibilidad de inventario que se instaló.
- Actualmente, la visibilidad de inventario no es compatible con entornos alojados en la nube. Solo es compatible con entornos Tier-2+.
- La interfaz de programación de aplicaciones (API) actualmente admite la consulta de hasta 100 elementos individuales por el valor `ProductID`. También se pueden especificar varios valores `SiteID` y `LocationID` en cada consulta. El límite máximo se define como `NumOf(SiteID) * NumOf(LocationID) <= 100`.
- La API masiva puede devolver un máximo de 512 registros para cada solicitud.
- El origen de datos `fno` está reservado para Supply Chain Management. Si su complemento de visibilidad de inventario está integrado con un entorno de Supply Chain Management, le recomendamos que no elimine las configuraciones relacionadas con `fno` en la [fuente de datos](inventory-visibility-configuration.md#data-source-configuration).
- Visibilidad de inventario no puede cambiar ningún dato para el `fno` de la fuente de datos. El flujo de datos es unidireccional, lo que significa que todas las cantidades cambian para el `fno` de la fuente de datos debe provenir de su entorno de Supply Chain Management. Por lo tanto, no puede usar la API para enviar solicitudes de cambio o reserva disponibles para la fuente de datos `fno`.
- Si agrega una o más medidas nuevas a su entorno de Supply Chain Management, también debe agregarlas en Visibilidad de inventario. Sin embargo, todos los cambios de cantidad para nuevas medidas deben provenir de su entorno de Supply Chain Management.
- Actualmente, la [configuración de la partición](inventory-visibility-configuration.md#partition-configuration) consta de dos dimensiones base (`SiteId` y `LocationId`) que indican cómo se distribuyen los datos. Las operaciones en la misma partición pueden ofrecer un mayor rendimiento a un menor costo. La solución incluye esta configuración de partición por defecto. Por lo tanto, *no es necesario volver a calcular manualmente*. No personalice la configuración de partición predeterminada. Si lo elimina o lo cambia, es probable que provoque un error inesperado.
- Las dimensiones base que se definen en la configuración de la partición no deben definirse en la [configuración de jerarquía de índice de productos](inventory-visibility-configuration.md#index-configuration).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
