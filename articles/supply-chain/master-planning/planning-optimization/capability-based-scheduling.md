---
title: Programación con selección de recursos según la capacidad
description: Este artículo describe la selección de recursos durante la programación de capacidad infinita al especificar capacidades como requisitos de recursos para una operación.
author: t-benebo
ms.date: 9/3/2021
ms.topic: article
ms.search.form: RouteInventProd, WrkCtrTable, WrkCtrCapability
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-09-03
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 26b2b65a2d565052b188f4d70f0cc0a773cd7b43
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847973"
---
# <a name="scheduling-with-resource-selection-based-on-capability"></a>Programación con selección de recursos según la capacidad

[!include [banner](../../includes/banner.md)]

Al especificar los requisitos de recursos para una operación de una ruta de producción, se define lo que se requiere para realizar esa operación. Por ejemplo, una operación puede requerir un recurso específico o un grupo de recursos, o una combinación de habilidades o capacidades. Este artículo describe la selección de recursos durante la programación de capacidad infinita al especificar capacidades como requisitos de recursos para una operación.

## <a name="turn-on-the-capability-based-scheduling-feature"></a>Activar la función de programación según la capacidad

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar la configuración de [administración de características](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de características**, la función aparece de la siguiente forma:

- **Módulo:** *Planificación maestra*
- **Nombre de la función:** *Programación de capacidad infinita para Optimización de planificación*

Para más información sobre esta función, consulte [Programación con capacidad infinita](infinite-capacity-planning.md).

## <a name="capability-based-scheduling"></a>Programación según la capacidad

Una capacidad es la posibilidad de que un recurso de operaciones realice una actividad específica. Un único recurso de operaciones puede tener más de una capacidad asignada, y una única capacidad puede asignarse a más de un recurso. Las capacidades se pueden asignar a todos los tipos de recursos, como herramientas, proveedores, máquinas, ubicaciones, instalaciones y recursos humanos.

Cuando especifica capacidades como requisitos de recursos, puede aplazar la asignación de recursos hasta que se programen los pedidos. En lugar de asignar recursos o grupos de recursos específicos a una operación de ruta, puede definir las capacidades que se requieren para cada operación de ruta. Luego, durante la programación, el sistema hace coincidir las capacidades requeridas con las capacidades definidas para los recursos. El sistema selecciona solo los recursos que satisfacen los requisitos.

Para asignar capacidades a un recurso de operación, use la ficha desplegable **Capacidades** de la página **Recursos**. Para asignar recursos a una capacidad, use la ficha desplegable **Recursos** de la página **Capacidades de recursos**. Ambas páginas son accesibles en **Control de producción \> Configuración \> Recursos**, en el panel de navegación. Ambas fichas desplegables incluyen una cuadrícula que enumera los recursos que están asociados con un recurso o capacidad seleccionados. Ambas fichas desplegables incluyen una barra de herramientas que puede usar para agregar, eliminar y editar filas en la cuadrícula. La cuadrícula incluye las siguientes columnas:

- **Recurso** o **Capacidad**: seleccione el recurso o la capacidad que está siendo asignado por la fila.
- **Descripción**: introduzca una descripción breve del recurso o de la capacidad.
- **Eficaz**: especifique la primera fecha en la que se aplica la asignación de recursos o capacidades. Durante la programación, el sistema no utilizará un recurso o capacidad que tenga una asignación de capacidad vencida, incluso si ese recurso satisface los requisitos.
- **Expiración**: especifique la última fecha en la que se aplica la asignación de recursos o capacidades. Durante la programación, el sistema no utilizará un recurso o capacidad que tenga una asignación de capacidad vencida, incluso si ese recurso satisface los requisitos.
- **Nivel**: especifique el nivel de competencia que debe tener el recurso para la capacidad. Entonces, si especifica un valor **Nivel mínimo necesario** para el recurso o requisito de capacidad, el motor de programación considera el nivel de competencia durante la selección de recursos. El sistema selecciona solo los recursos que tienen la capacidad necesaria en un nivel que iguale o supere el nivel mínimo que se especifica en el requisito de recurso.
- **Prioridad**: este campo aún no es compatible con Optimización de planificación. Sin embargo, si está utilizando el motor de planificación integrado, puede utilizar el campo **Prioridad** en la asignación del recurso o de la capacidad para definir la prioridad del recurso. Entonces, si *Prioridad* se selecciona en el campo **Selección del recurso principal**, en la página **Parámetros de programación**, el sistema selecciona primero el recurso que tiene la máxima prioridad (es decir, el de menor valor numérico en el campo **Prioridad**) durante la programación.

## <a name="example"></a>Ejemplo

Este ejemplo muestra cómo el motor de programación selecciona recursos, según la capacidad.

Una ruta de producción tiene cinco operaciones: *10*, *20*, *30*, *40* y *50*. Cada operación de ruta requiere un recurso que tiene diferentes capacidades. Por ejemplo, la operación de ruta *10* requiere un recurso que tenga la capacidad de montar un altavoz (*0050 Conjunto de altavoz*) y la capacidad para trabajar la madera (*1010 Capacidades de madera*). La operación de ruta *50* requiere un recurso que tenga la capacidad de empaquetar un producto (*0070 Capacidad de embalaje*).

![Capacidad usada para programación.](media/capability-based-scheduling.png "Capacidad usada para programación.")

Durante la programación, el motor busca recursos que satisfagan los requisitos operativos. Por ejemplo, el motor de programación selecciona recursos *00101* para realizar la operación *10*, porque este recurso es el primer recurso que se encuentra que tiene ambas capacidades requeridas. El motor de programación selecciona el recurso *00301* para realizar la operación *50*, porque este recurso es el único recurso con capacidad de empaquetar.

A continuación, considere cómo se ve afectado este ejemplo cuando se utilizan los niveles de competencia:

- La operación *10* requiere un nivel mínimo de competencia de *7* para la capacidad *0059 Ensamblado*.
- El recurso *00101* tiene un nivel de competencia de *5* para la capacidad *0059 Ensamblado*.
- El recurso *00102* tiene un nivel de competencia de *10* para la capacidad *0059 Ensamblado*.

En este caso, durante la programación de capacidad infinita, el motor de programación selecciona el recurso *00102* para realizar la operación *10*, porque este recurso, a diferencia del recurso *00101*, tiene el nivel de competencia requerido para la capacidad.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
