---
title: Visión general de la gestión de cambios de ingeniería
description: Este tema proporciona una descripción general de la gestión de cambios de ingeniería, que le ayuda a planificar y gestionar el control de versiones del producto y gestionar los ciclos de vida del producto y los cambios de ingeniería.
author: t-benebo
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: d7c0839ffbea80904ca12d1cba7ba9880f721cdd
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947529"
---
# <a name="engineering-change-management-overview"></a>Visión general de la gestión de cambios de ingeniería

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a>Resumen de características

Los fabricantes actuales requieren una sólida gestión de datos de productos, control de versiones y gestión de cambios de ingeniería para tener éxito en un mundo en el que los ciclos de vida de los productos se reducen constantemente, los requisitos de calidad y fiabilidad aumentan y un mayor enfoque en la seguridad del producto.

La gestión de cambios de ingeniería aporta estructura y disciplina al proceso de gestión de datos de productos y permite que los productos se definan, publiquen y revisen de una manera controlada que sea compatible con los flujos de trabajo. Mediante las versiones de productos y la gestión de cambios de ingeniería, puede documentar, evaluar el impacto y aplicar los cambios de ingeniería a lo largo de todo el ciclo de vida de un producto.

La gestión de cambios de ingeniería le ayuda a planificar y gestionar el control de versiones del producto y gestionar los ciclos de vida del producto y los cambios de ingeniería. A continuación se muestra una lista de sus principales características:

- Versiones de productos
- Funcionalidad de lanzamiento de producto mejorada que le permite mantener los datos maestros del producto en una entidad legal (la empresa de ingeniería) y publicar el producto liberado completamente configurado para otras entidades legales
- Reglas para validar que se ingrese la información requerida antes de que se active una versión del producto (verificaciones de preparación)
- Gestión mejorada del ciclo de vida del producto a través de un control detallado sobre cuándo se puede usar un producto lanzado en procesos comerciales específicos
- Solicitudes de cambios de ingeniería que son compatibles con los flujos de trabajo
- Pedidos de cambios de ingeniería que son compatibles con los flujos de trabajo

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

El video anterior ([Capacidades de gestión de cambios en Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) está incluido en la [lista de reproducción de Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible en YouTube.

## <a name="turn-on-the-engineering-change-management-and-version-dimension-features-for-your-system"></a>Active la gestión de cambios de ingeniería y las funciones de dimensión de versión para su sistema.

Antes de que pueda usar la administración de cambios de ingeniería, debe activar la característica *Gestión de cambios de ingeniería* y su clave de configuración. Si también desea realizar un seguimiento de la dimensión de la versión de los productos en las transacciones (opcional), también debe habilitar la función *Dimensión de la versión del producto* y su clave de configuración.

Primero, active esas funciones siguiendo estos pasos.

1. Vaya al espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
1. Busque actualizaciones.
1. Active la característica llamada **Administración de cambios de ingeniería**.
1. Si desea utilizarlo, active también la función que se denomina **Versión de dimensión del producto**.

Luego, active las claves de configuración siguiendo estos pasos.

1. Coloque su sistema en modo de mantenimiento como se describe en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Vaya a **Administración del sistema \> Configuración \> Configuración de licencias**.
1. Expanda el nodo **Comercio**.
1. Habilite la clave de configuración para la función principal seleccionando la casilla **Gestión de cambios de ingeniería**. (No es necesario expandir el nodo a menos que también desee deshabilitar una o ambas subfunciones).
1. Si también desea utilizar la dimensión de versión, seleccione también la casilla **Dimensión del producto: versión**. (Esta casilla está más abajo en la lista, no anidada debajo del nodo **Gestión de cambios de ingeniería**).
1. Desactive el modo de mantenimiento como se describe en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

> [!IMPORTANT]
> A partir de abril de 2022, las claves de licencia para **Gestión de cambios de ingeniería** y **Dimensión del producto: versión** estará habilitado de forma predeterminada para todas las instalaciones nuevas, pero seguirá pudiendo deshabilitarlas si es necesario.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
