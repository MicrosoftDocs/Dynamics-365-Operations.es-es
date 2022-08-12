---
title: Resumen de gestión de cambios de ingeniería (contiene vídeo)
description: Este artículo proporciona una descripción general de la gestión de cambios de ingeniería, que le ayuda a planificar y gestionar el control de versiones del producto y gestionar los ciclos de vida del producto y los cambios de ingeniería.
author: t-benebo
ms.date: 01/11/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 3a27548fff9728c74814fb92438da1d0c17b5e2b
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067404"
---
# <a name="engineering-change-management-overview"></a>Información general de la gestión de cambios de ingeniería

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a>Resumen de características

Los fabricantes actuales requieren una sólida gestión de datos de productos, control de versiones y gestión de cambios de ingeniería para tener éxito en un mundo en el que los ciclos de vida de los productos se reducen constantemente, los requisitos de calidad y fiabilidad aumentan y un mayor enfoque en la seguridad del producto.

La gestión de cambios de ingeniería aporta estructura y disciplina al proceso de gestión de datos de productos y permite que los productos se definan, publiquen y revisen de una manera controlada que sea compatible con los flujos de trabajo. Mediante las versiones de productos y la gestión de cambios de ingeniería, puede documentar, evaluar el impacto y aplicar los cambios de ingeniería a lo largo de todo el ciclo de vida de un producto.

La gestión de cambios de ingeniería le ayuda a planificar y gestionar el control de versiones del producto y gestionar los ciclos de vida del producto y los cambios de ingeniería. A continuación se muestra una lista de sus principales características:

- Versiones de productos
- Funcionalidad de lanzamiento de producto mejorada que le permite mantener los datos maestros del producto en una entidad legal (la empresa de ingeniería) y publicar el producto liberado completamente configurado para otras entidades legales
- Reglas para validar que se ingrese la información requerida antes de que se active una versión del producto (verificaciones de preparación)
- Gestión mejorada del ciclo de vida del producto a través de un control detallado sobre cuándo se puede usar un producto lanzado en procesos comerciales específicos
- Solicitudes de cambios de ingeniería que son compatibles con los flujos de trabajo
- Pedidos de cambios de ingeniería que son compatibles con los flujos de trabajo

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HE6B]

El vídeo anterior ([Capacidades de gestión de cambios en Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) está incluido en la [lista de reproducción de finanzas y operaciones](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible en YouTube.

## <a name="turn-on-the-engineering-change-management-features-for-your-system"></a>Active las funciones de gestión de cambios de ingeniería para su sistema

Antes de que pueda usar la administración de cambios de ingeniería, debe activar la característica *Gestión de cambios de ingeniería* y su clave de configuración. Si también desea realizar un seguimiento de la dimensión de la versión de los productos en las transacciones (opcional), también debe habilitar la función *Dimensión de la versión del producto* y su clave de configuración. Una vez que se hayan configurado esos requisitos previos según sea necesario, podrá activar funciones opcionales adicionales para la gestión de cambios de ingeniería.

### <a name="turn-the-basic-engineering-change-management-features-on-or-off"></a>Activar o desactivar las características de gestión de cambios de ingeniería básicos

Para activar o desactivar las características de gestión de cambios de ingeniería básicos, siga estos pasos. A partir de la versión 10.0.25 de Supply Chain Management, la característica *Gestión de cambios en ingeniería* está activada de forma predeterminada.

1. Vaya al espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
1. Busque actualizaciones.
1. Active o desactive la característica llamada *Gestión de cambios de ingeniería*, según necesite.
1. Si también desea realizar un seguimiento de la dimensión de la versión de los productos en las transacciones (opcional), active la característica llamada *Dimensión de la versión del producto*.

### <a name="turn-the-required-configuration-keys-on-or-off"></a>Activar o desactivar las claves de configuración requeridas

Luego, active las claves de configuración siguiendo estos pasos. No están activadas de forma predeterminada.

1. Coloque su sistema en modo de mantenimiento como se describe en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Vaya a **Administración del sistema \> Configuración \> Configuración de licencias**.
1. Expanda el nodo **Comercio**.
1. Active o desactive la clave de configuración para la característia principal con la casilla **Gestión de cambios de ingeniería**.
1. Expanda el nodo **Gestión de cambios de ingeniería** y seleccione o desmarque las siguientes casillas de verificación según sea necesario (según las funciones que desee utilizar):

    - **Búsqueda de atributos**: seleccione esta casilla de verificación para habilitar la [función de búsqueda de atributos](engineering-attributes-and-search.md). Recomendamos habilitar esta función, pero puede desmarcar esta casilla de verificación si no la va a utilizar.
    - **Gestión de cambios para la fabricación de procesos**: seleccione esta casilla de verificación si desea utilizar las funciones de administración de cambios de ingeniería para administrar los cambios en las fórmulas para el proceso de fabricación. Si no tiene que administrar fórmulas, puede desmarcar esta casilla de verificación. Para más información, vea [Gestionar cambios en fórmulas y sus ingredientes](manage-formula-changes.md).

1. Si también desea utilizar la dimensión de versión, seleccione también la casilla **Dimensión del producto: versión**. (Esta casilla se encuentra más abajo en la lista, no anidada en el nodo **Gestión de cambios de ingeniería**). Puede desmarcar esta casilla de verificación si no necesita esta característica.
1. Desactive el modo de mantenimiento como se describe en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. La base de datos debe sincronizarse para asegurarse de que las claves de configuración se han actualizado correctamente para reflejar los cambios. Realice uno de los siguientes pasos, según el tipo de entorno en el que esté trabajando:
    - **Para entornos de nivel 1 (desarrollo)**: abra su proyecto en Microsoft Visual Studio y luego seleccione **Dynamics 365 \> Sincronizar base de datos \> Sincronizar**.
    - **Para entornos de nivel 2 (y superiores)**: la base de datos se sincroniza automáticamente después de activar y desactivar el modo de mantenimiento del entorno, por lo que puede omitir este paso.

### <a name="turn-on-additional-engineering-change-management-features"></a>Active las funciones de gestión de cambios de ingeniería adicionales

Después de activar las funciones básicas de gestión de cambios de ingeniería y habilitar sus claves de configuración, se agregan varias funciones de gestión de cambios de ingeniería adicionales y opcionales a la gestión de funciones. Cada una de esas funciones se enumera en el módulo **Gestión de cambios de ingeniería**. La siguiente tabla describe cada función opcional y proporciona enlaces para obtener más información. A partir de la versión 10.0.25 de Supply Chain Management, todas estas características están activadas de forma predeterminada, pero aún puede optar por desactivarlas.

| Nombre de la característica en la administración de características | Description | Estado de la característica |
|---|---|---|
| Habilitar la administración de cambios en productos existentes | <p>Esta función le permite convertir productos existentes en productos de ingeniería para que pueda comenzar a administrarlos mediante la administración de cambios de ingeniería.</p><p>Para más información, vea [Habilitar la gestión de cambios en productos existentes](change-management-existing-products.md).</p> |
| Notificaciones de ingeniería para producción | <p>Cuando se cambia un producto en ingeniería, puede ser importante notificar a la producción sobre esos cambios. De esa manera, los trabajadores de producción pueden tomar las medidas adecuadas, como la sustitución de componentes, el reemplazo de la lista de materiales (BOM) o el reemplazo de la ruta. Esta función le permite notificar a la producción sobre cambios en los productos que se están produciendo.</p><p>Para más información, ver [Gestionar cambios en productos de ingeniería](engineering-change-management.md).</p> |
| Herencia de atributos mejorada para la administración de cambios de ingeniería | <p>Esta característica simplifica la gestión de atributos para productos terminados o artículos intermedios. Cuando esta función está activada, es más fácil identificar todos los atributos que pertenecen a un elemento y puede seleccionar los atributos que deben propagarse desde ese elemento a su elemento principal. Esta característica es útil cuando, por ejemplo, un componente de un producto terminado es frágil, tóxico o inflamable, porque puede identificar fácilmente el atributo frágil, tóxico o inflamable y propagarlo al producto terminado.</p><p>Para más información, vea [Atributos de ingeniería y búsqueda de atributos de ingeniería](engineering-attributes-and-search.md).</p> |
| Comprobaciones de preparación de producto | <p>Esta función le permite configurar comprobaciones de preparación para productos estándar (que no sean de ingeniería). Utilice verificaciones de preparación del producto para asegurarse de que cada producto esté completamente definido y que todas las políticas requeridas estén configuradas antes de que el producto esté disponible y se utilice en las transacciones. Si desactiva esta función después de haberla utilizado durante un tiempo, se eliminarán todas las comprobaciones de preparación existentes para los productos estándar.</p><p>Para obtener más información, consulte [Preparación del producto](product-readiness.md).</p> |
| Administrar cambios en fórmulas y sus componentes | <p>Esta función le permite realizar un seguimiento de los cambios en los ingredientes, coproductos y subproductos de la fórmula.</p><p>Para más información, vea [Gestionar cambios en fórmulas y sus ingredientes](manage-formula-changes.md).</p> |
| Generación de variantes de productos de ingeniería | <p>Esta función le permite generar variantes para productos de ingeniería, según los valores de dimensión disponibles.</p><p>Para más información, vea [Genere variantes para productos de ingeniería](engineering-variants.md).</p> |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

