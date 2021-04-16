---
title: Contenedores de envío
description: Este tema describe cómo configurar contenedores de envío para el módulo de costo de entrega.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMContainerTypeTable, ITMContainerTable, ITMContainerUnitTypeTable, ITMRefrigerationTypeTable, ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 2f7e9435aa3d0d06e1cc51457a6343b807d76dc7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833722"
---
# <a name="shipping-container-setup"></a>Configuración del contenedor de envío

[!include [banner](../../includes/banner.md)]

Este tema describe cómo configurar contenedores de envío para el módulo **Costo descargado**.

## <a name="set-up-shipping-container-types"></a><a id="shipping-container-types"></a>configurar tipos de contenedor de envío

Los tipos de contenedores de envío definen los tipos de contenedores de envío que están disponibles para su uso durante el envío y los viajes.

Para trabajar con los tipos de contenedores de envío, vaya a **Coste de aterrizaje \> Configuración de contenedores \> Tipos de contenedores de envío**. Allí, puede ver, agregar y eliminar registros para sus tipos de contenedor. En la tabla siguiente se describen los campos disponibles para cada registro.

| Campo | Descripción |
|---|---|
| Tipo de contenedor de envío | Escriba un nombre/número de identificador único para el tipo de contenedor. |
| Descripción | Especifique una descripción del grupo de tipo de contenedor de envío. |
| Volumen | Ingrese el volumen máximo permitido en contenedores de envío de este tipo. |
| Importancia | Ingrese el peso máximo permitido en contenedores de envío de este tipo. |
| Retornable | Especifique si los contenedores de envío de este tipo se pueden devolver al proveedor después de que se utilicen durante un viaje. Si esta opción se establece en *Sí*, pueden aplicarse costos adicionales por la devolución de contenedores de envío de este tipo al puerto de origen. |

## <a name="set-up-shipping-containers"></a>Configuración de contenedores de envío

Utiliza los registros de contenedores de envío para identificar cada contenedor que usa durante los viajes. Cuando crea un viaje, puede seleccionar un contenedor específico para él en la lista de todos los registros de contenedores de envío que ha definido aquí. Esta función es especialmente útil si su empresa posee sus propios contenedores de envío.

No es necesario que ingrese los números de contenedor de envío para los contenedores de envío que se usarán solo una vez. En su lugar, puede agregar el número de contenedor de envío cuando cree un viaje.

Los registros de contenedores de envío se utilizan solo en el costo de entrega. No están disponibles en el módulo estándar **Gestión de transporte** (TMS).

Para trabajar con contenedores de envío, vaya a **Coste de aterrizaje \> Configuración de contenedores \> Contenedores de envío**. Allí, puede ver, agregar y eliminar registros para sus contenedores de envío. En la tabla siguiente se describen los campos disponibles para cada registro.

| Campo | Descripción |
|---|---|
| Contenedor de envío | Escriba un nombre/número de identificador único para el contenedor de envío. |
| Tipo de contenedor de envío | Seleccione el tipo de contenedor de envío. Para obtener más información, consulte la sección [Configurar tipos de contenedor de envío](#shipping-container-types) anteriormente en este tema. |

> [!NOTE]
> - La configuración del contenedor de envío es opcional. Por lo general, lo usará solo si su empresa posee sus propios contenedores de envío o, a menudo, reutiliza los mismos contenedores de envío.
> - No se calculan dígitos de control para los números de contenedores de envío.

## <a name="set-up-unit-types"></a><a name="unit-types"></a>Configurar tipos de unidad

Los tipos de unidades establecen agrupaciones y métodos de identificación adicionales para los contenedores de envío. El tipo de unidad se usa típicamente para identificar el tipo de contenedor en el que se empaquetan las mercancías, como paletas o tambores. Puede seleccionar un tipo de unidad cuando configura un contenedor en la página **Todos los contenedores de envío**.

Los tipos de unidad se utilizan solo en el costo de aterrizaje. No están disponibles en TMS.

Para trabajar con tipos de unidades, vaya a **Coste de aterrizaje \> Configuración de contenedores \> Tipos de unidades**. Allí, puede ver, agregar y eliminar registros para sus tipos de unidades. En la tabla siguiente se describen los campos disponibles para cada registro.

| Campo | Descripción |
|---|---|
| Tipo de unidad | Escriba un nombre/número de identificador único para el tipo de unidad. |
| Descripción | Especifique una descripción del tipo de unidad. |

## <a name="set-up-refrigeration-types"></a><a name="refrigeration-types"></a>Configuración de los tipos de refrigeración

Los tipos de refrigeración establecen grupos y métodos de identificación adicionales para contenedores de envío (normalmente contenedores refrigerados). Puede seleccionar un tipo de refrigeración cuando configura un contenedor en la página **Todos los contenedores de envío**.

Para trabajar con tipos de refrigeración, vaya a **Coste de aterrizaje \> Configuración de contenedores \> Tipos de refrigeración**. Allí, puede ver, agregar y eliminar registros para sus tipos de refrigeración. En la tabla siguiente se describen los campos disponibles para cada registro.

| Campo | Descripción |
|---|---|
| Tipo de refrigeración | Escriba un nombre/número de identificador único para el tipo de refrigeración. |
| Descripción | Especifique una descripción del tipo de refrigeración. |
