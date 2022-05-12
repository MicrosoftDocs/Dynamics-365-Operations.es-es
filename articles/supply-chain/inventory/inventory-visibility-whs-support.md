---
title: Soporte de Inventory Visibility para elementos de WHS
description: Este tema describe el soporte para la visibilidad del inventario para artículos que están habilitados para procesos de almacén avanzados (artículos WHS).
author: yufeihuang
ms.date: 03/10/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-03-10
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: cfbff05697f4159cb74d110887b8029f28fbf96b
ms.sourcegitcommit: 1050e58e621d9a0454895ed07c286936f8c03320
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2022
ms.locfileid: "8625411"
---
# <a name="inventory-visibility-support-for-whs-items"></a>Soporte de Inventory Visibility para elementos de WHS

[!include [banner](../includes/banner.md)]

Este tema describe el soporte para la visibilidad del inventario para artículos que están habilitados para procesos de almacén avanzados (artículos WHS). La característica que agrega esta capacidad a Inventory Visibility se denomina *WHS avanzado*.

## <a name="whs-items"></a>Artículos WHS

Un artículo WHS es un artículo habilitado para procesos avanzados de almacén (WHS) avanzados y procesados en un almacén que también está habilitado para WHS.

Para obtener más información sobre WHS y el módulo **Warehouse management** en Microsoft Dynamics 365 Supply Chain Management, consulte la [Descripción general de la gestión de almacenes](../warehousing/warehouse-management-overview.md).

## <a name="scope-of-the-feature"></a>Ámbito de la característica

La función WHS avanzada para Inventory Visibility se centra en los cálculos de cantidad disponible que se basan en consultas disponibles. La característica no está diseñada para permitirle usar Inventory Visibility para administrar las actividades de procesamiento del almacén en general. Inventory Visibility no expone conceptos específicos del almacén a sus usuarios. Algunos ejemplos de estos conceptos:

- Jerarquía de reservas
- Si un artículo o almacén está habilitado para WHS
- Id. de grupo de secuencias de unidades
- Procesos específicos del almacén, como envíos, cargas, oleadas y trabajo

Inventory Visibility infiere esta información, en función de los datos que se envían desde Supply Chain Management. Los datos específicos de WHS (en otras palabras, los datos de la tabla `WHSInventReserve`) no están visibles para los usuarios.

Cuando utiliza la función WHS avanzada para la visibilidad del inventario, todos los resultados de las consultas serán idénticos a los resultados de las consultas que se realizan directamente en Supply Chain Management. Sin embargo, no serán idénticos a los resultados de las consultas realizadas mediante la Warehouse Management mobile app, porque la aplicación móvil utiliza una lógica de cálculo ligeramente diferente.

## <a name="when-to-use-the-feature"></a>Cuándo usar la característica

Le recomendamos que utilice la función WHS avanzada para Inventory Visibility en escenarios donde se cumplan todas las condiciones siguientes:

- Está sincronizando los datos de Supply Chain Management con Inventory Visibility.
- Está utilizando WHS en Supply Chain Management.
- Los usuarios hacen reservas para artículos de WHS en niveles distintos al nivel de almacén (por ejemplo, porque está utilizando trabajo de almacén).

En otros escenarios, los resultados de las consultas disponibles serán los mismos, independientemente de si la función WHS avanzada para Inventory Visibility está habilitada. Además, el rendimiento será mejor si no habilita la característica en estos escenarios, porque hay menos cálculos y menos gastos generales.

## <a name="enable-the-advanced-whs-feature-for-inventory-visibility"></a>Habilitar la función WHS avanzada para Inventory Visibility

Para habilitar la función WHS avanzada para Inventory Visibility siga los siguientes pasos.

1. Inicie sesión en Supply Chain Management como administrador.
1. Abra el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y habilite las funciones siguientes en este orden:

    1. *Integración de Visibilidad de inventario*
    1. *Habilitar artículos de almacén en Visibilidad de inventario*

1. Vaya a **Gestión del inventario \> Configuración \> Parámetros de integración de Visibilidad de inventario**.
1. En la pestaña **Habilitar artículos WHS**, configure la opción **Habilitar artículos WHS** en *Sí*.
1. Iniciar sesión en Power Apps.
1. Abra la página **Configuración** y luego en la pestable **Gestión de características**, active la característica *AdvancedWHS*.
1. En Supply Chain Management, vaya a **Gestión de inventario \> Tareas periódicas \> Integración de Inventory Visibility**.
1. En el panel de acciones, seleccione **Deshabilitar** para deshabilitar temporalmente Inventory Visibility.
1. En el Panel de acciones, seleccione **Habilitar** para volver a habilitar Inventory Visibility. El complemento se vuelve a cargar y la nueva característica ahora está habilitada. Sus datos relacionados con WHS comienzan a sincronizarse con Inventory Visibility.

## <a name="query-on-hand-quantities-of-whs-items"></a>Consultar cantidades disponibles de artículos WHS

Para consultar artículo de WHS, utilice la misma [interfaz de programación de aplicaciones (API) y sintaxis de mensajes](inventory-visibility-api.md) que usa para artículos que no son WHS. No tiene que especificar si un artículo es WHS o no WHS. Inventory Visibility distingue automáticamente los artículos, en función de los datos almacenados.

Los resultados de las consultas de artículos WHS son esencialmente los mismos que los resultados de los artículos que no son WHS. La única diferencia es que las siguientes medidas físicas del origen de datos `fno` se calculan en función de la lógica WHS en Supply Chain Management:

- `AvailOrdered`
- `AvailPhysical`
- `ReservOrdered`
- `ReservPhysical`

Todas las demás medidas físicas se calculan tal como están cuando la función WHS avanzada para Inventory Visibility está desactivada.

Para obtener información detallada sobre cómo funcionan los cálculos disponibles para los artículos de WHS, consulte el libro blanco [Reservas en Warehouse management](https://www.microsoft.com/download/details.aspx?id=43284).

Las entidades de datos que se exportan a Dataverse aún no se pueden actualizar las cantidades de los artículos WHS. Las cantidades que se muestran en las entidades de datos son correctas tanto para artículos no WHS como para cantidades que no se ven afectadas por la lógica WHS (es decir, medidas excepto `AvailPhysical`, `AvailOrdered`, `ReservPhysical` y `ReservOrdered` en el origen de datos `fno`).

Los cambios en las cantidades de artículos de WHS que se almacenan en el origen de datos de Supply Chain Management están prohibidos. En cuanto a otras características de Inventory Visibility, esta restricción se aplica para ayudar a prevenir conflictos.

## <a name="soft-reservations-on-whs-items-in-inventory-visibility"></a>Reservas flexibles en los artículos de WHS en Inventory Visibility

En general, las [reservas flexibles](inventory-visibility-reservations.md) en los artículos WHS son compatibles. Puede incluir medidas físicas relacionadas con WHS en los cálculos de reservas flexibles. 

En una limitación conocida, el cálculo *disponible para reserva* no se admite actualmente para artículos WHS. Por lo tanto, si hay una reserva por encima de las dimensiones actuales donde se está produciendo una reserva flexible, el cálculo *disponible para reserva* es incorrecto. Las reservas flexibles no se verán afectadas cuando la opción **ifCheckAvailForReserv** está deshabilitada en la [API de reserva flexible](inventory-visibility-api.md#create-one-reservation-event).

Esta restricción también se aplica a las funciones y personalizaciones que se basan en reservas flexibles (como la asignación).

## <a name="calculate-available-to-promise-quantities"></a>Calcular las cantidades netas no comprometidas

La solución es totalmente compatible con [neto no comprometido (NNC)](inventory-visibility-available-to-promise.md) para artículos WHS. Puede definir cálculos de NNC sin preocuparse por los detalles específicos de WHS.
