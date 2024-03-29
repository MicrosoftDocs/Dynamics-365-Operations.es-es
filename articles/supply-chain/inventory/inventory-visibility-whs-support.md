---
title: Soporte de Inventory Visibility para elementos de WMS
description: Este artículo describe el soporte para la visibilidad del inventario para artículos que están habilitados para procesos de gestión de almacenes (artículos WMS).
author: yufeihuang
ms.date: 11/04/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-10
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: bed402ecf20c19e81b2687efd90dba600460971a
ms.sourcegitcommit: 49f8973f0e121eac563876d50bfff00c55344360
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2022
ms.locfileid: "9762764"
---
# <a name="inventory-visibility-support-for-wms-items"></a>Soporte de Inventory Visibility para elementos de WMS

[!include [banner](../includes/banner.md)]

Este artículo describe el soporte para la visibilidad del inventario para artículos que están habilitados para procesos de gestión de almacenes (WMS). La característica que agrega esta capacidad a Inventory Visibility se denomina *WMS avanzado*.

## <a name="wms-items"></a>Artículos WMS

Un artículo WMS es un artículo habilitado para WMS y procesados en un almacén que también está habilitado para WMS.

Para obtener más información sobre WMS y el módulo **Warehouse management** en Microsoft Dynamics 365 Supply Chain Management, consulte la [Descripción general de la gestión de almacenes](../warehousing/warehouse-management-overview.md).

## <a name="scope-of-the-feature"></a>Ámbito de la característica

La función WMS avanzada para Inventory Visibility se centra en los cálculos de cantidad disponible que se basan en consultas disponibles. La característica no está diseñada para permitirle usar Inventory Visibility para administrar las actividades de procesamiento del almacén en general. Inventory Visibility no expone conceptos específicos del almacén a sus usuarios. Algunos ejemplos de estos conceptos:

- Jerarquía de reservas
- Si un artículo o almacén está habilitado para WMS
- Id. de grupo de secuencias de unidades
- Procesos específicos del almacén, como envíos, cargas, oleadas y trabajo

Inventory Visibility infiere esta información, en función de los datos que se envían desde Supply Chain Management. Los datos específicos de WMS (en otras palabras, los datos de la tabla `WHSInventReserve`) no están visibles para los usuarios.

Cuando utiliza la función WMS avanzada para la visibilidad del inventario, todos los resultados de las consultas serán idénticos a los resultados de las consultas que se realizan directamente en Supply Chain Management. Sin embargo, no serán idénticos a los resultados de las consultas realizadas mediante la Warehouse Management mobile app, porque la aplicación móvil utiliza una lógica de cálculo ligeramente diferente.

## <a name="when-to-use-the-feature"></a>Cuándo usar la característica

Le recomendamos que utilice la característica WMS para Inventory Visibility en escenarios donde se cumplan todas las condiciones siguientes:

- Está sincronizando los datos de Supply Chain Management con Inventory Visibility.
- Está utilizando WMS en Supply Chain Management.
- Los usuarios hacen reservas para artículos de WMS en niveles por debajo del nivel de almacén (por ejemplo, en el nivel de matrícula de entidad de almacén porque está procesando trabajo de almacén).

En otros escenarios, los resultados de las consultas disponibles serán los mismos, independientemente de si la función WMS avanzada para Inventory Visibility está habilitada. Además, el rendimiento será mejor si no habilita la característica en estos escenarios, porque hay menos cálculos y menos gastos generales.

## <a name="enable-the-wms-feature-for-inventory-visibility"></a>Habilitar la característica WMS para Inventory Visibility

Para habilitar la característica WMS para Inventory Visibility siga los siguientes pasos.

1. Inicie sesión en Supply Chain Management como administrador.
1. Abra el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y habilite las funciones siguientes en este orden:

    1. *Integración de Visibilidad de inventario*
    1. *Habilitar artículos de almacén en Visibilidad de inventario*

1. Vaya a **Gestión del inventario \> Configuración \> Parámetros de integración de Visibilidad de inventario**.
1. En la pestaña **Habilitar artículos WMS**, configure la opción **Habilitar artículos WMS** en *Sí*.
1. Inicie sesión en su entorno de Power Apps y abra **Visibilidad de inventario**.
1. Abra la página **Configuración** y luego en la pestable **Gestión de características**, active la característica *AdvancedWHS*.
1. En Supply Chain Management, vaya a **Gestión de inventario \> Tareas periódicas \> Integración de Inventory Visibility**.
1. En el panel de acciones, seleccione **Deshabilitar** para deshabilitar temporalmente Inventory Visibility.
1. En el Panel de acciones, seleccione **Habilitar** para volver a habilitar Inventory Visibility. El complemento se vuelve a cargar y la nueva característica ahora está habilitada. Sus datos relacionados con WMS comienzan a sincronizarse con Inventory Visibility.

## <a name="query-on-hand-quantities-of-wms-items"></a>Consultar cantidades disponibles de artículos WMS

Para consultar artículo de WMS, utilice la misma [interfaz de programación de aplicaciones (API) y sintaxis de mensajes](inventory-visibility-api.md) que usa para artículos que no son WMS. No tiene que especificar si un artículo es WMS o no WMS. Inventory Visibility distingue automáticamente los artículos, en función de los datos almacenados.

Los resultados de las consultas de artículos WMS son esencialmente los mismos que los resultados de los artículos que no son WMS. La única diferencia es que las siguientes medidas físicas del origen de datos `fno` se calculan en función de la lógica WMS en Supply Chain Management:

- `AvailOrdered`
- `AvailPhysical`
- `ReservOrdered`
- `ReservPhysical`

Todas las demás medidas físicas se calculan tal como están cuando la característica WMS para Inventory Visibility está deshabilitada.

Para obtener información detallada sobre cómo funcionan los cálculos disponibles para los artículos de WMS, consulte el libro blanco [Reservas en Warehouse management](https://www.microsoft.com/download/details.aspx?id=43284).

## <a name="on-hand-list-view-and-data-entity-for-wms-items"></a>Vista de lista disponible y entidad de datos para artículos WMS

La página **Precargar el resumen de visibilidad del inventario** proporciona una vista para la entidad *Resultados de precarga de consultas de índice disponibles*. A diferencia de la entidad *Resumen de inventario*, la entidad *Resultados de precarga de consultas de índice disponibles* proporciona una lista de inventario disponible para productos junto con dimensiones seleccionadas. La visibilidad de inventario sincroniza los datos de resumen precargados cada 15 minutos.

Si utiliza Inventory Visibility con artículos WMS y desea ver la lista disponible de artículos WMS, le recomendamos que habilite la característica *Precargar el resumen de visibilidad del inventario* (consulte también [Precargar una consulta disponible optimizada](inventory-visibility-power-platform.md#preload-streamlined-onhand-query)). Una entidad de datos correspondiente en Dataverse almacena el resultado de la precarga de su consulta, que se actualiza cada 15 minutos. El nombre de la entidad de datos es `Onhand Index Query Preload Result`.

> [!IMPORTANT]
> La entidad de Dataverse es de solo lectura. Puede ver y exportar los datos en las entidades de Inventory Visibility, pero **no los modifique**.

Los cambios en las cantidades de artículos de WMS que se almacenan en el origen de datos de Supply Chain Management (`fno`) están prohibidos. Este comportamiento coincide con el comportamiento de otras características de Inventory Visibility. Esta restricción se aplica para ayudar a evitar conflictos.

## <a name="wms-item-compatibility-for-other-functions-in-inventory-visibility"></a>Compatibilidad de artículos WMS para otras funciones en Inventory Visibility

Se admiten [reservas provisionales](inventory-visibility-reservations.md) y [asignación de inventario](inventory-visibility-allocation.md) de artículo WMS. Puede incluir medidas físicas relacionadas con WMS en los cálculos de asignación y reservas provisionales.

## <a name="calculate-available-to-promise-quantities"></a>Calcular las cantidades netas no comprometidas

La solución es totalmente compatible con [neto no comprometido (NNC)](inventory-visibility-available-to-promise.md) para artículos WHS. Puede definir cálculos de NNC sin preocuparse por los detalles específicos de WHS.
