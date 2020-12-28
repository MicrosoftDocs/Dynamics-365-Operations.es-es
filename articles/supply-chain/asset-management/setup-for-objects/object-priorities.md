---
title: Niveles de servicio de activos
description: Este tema explica los niveles de servicio de activos en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35e7a55b1ba230be6bb72b20fcd805ea061b648e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436761"
---
# <a name="asset-service-levels"></a>Niveles de servicio de activos

[!include [banner](../../includes/banner.md)]

 

Este tema explica los niveles de servicio de activos en Administración de activos. Los niveles de servicio de activos están relacionados con los activos y se transfieren a las solicitudes de mantenimiento y a las órdens de trabajo. Se utilizan para calcular la prioridad de las órdenes de trabajo durante la programación de estas. Los niveles de servicio de activo se pueden cambiar, si es necesario.

Para obtener más información sobre la configuración relacionada con el cálculo de puntuaciones para la programación de órdenes de trabajo, consulte [Parámetros de administración de activos](../setup-for-objects/enterprise-asset-management-parameters.md). Debe configurar al menos un registro predeterminado para el nivel de servicio de activo. Este registro predeterminado se usa si no se encuentra ninguna otra coincidencia durante la programación de las órdenes de trabajo.

**Ejemplo 1:** el nivel de servicio predeterminado que se usa si no se encuentra ninguna otra coincidencia. En este registro, solo se selecciona un nivel de servicio.

**Ejemplo 2:** alto nivel de servicio que se usa para programar los trabajos para un motor de camión Volvo. En este registro, debe seleccionar un tipo de activo relevante (como **Motor de camión**), un fabricante (**Volvo**) y un nivel de servicio.

## <a name="set-up-asset-service-levels"></a>Configurar niveles de servicio de activos

1. Seleccione **Administración de activos** \> **Configuración** \> **Niveles de servicio de activos**.
2. Seleccione **Nuevo** para crear un registro.
3. En función del nivel de detalle necesario para el nivel de servicio de activo, realice las selecciones relevantes en **Ubicación funcional**, **Tipo de activo**, **Fabricante**, **Modelo**, **Activo**, **Tipo de pedido de trabajo** y **Nivel de servicio**.

    > [!NOTE]
    > Cuando se usa el nivel de servicio de activo para las solicitudes de mantenimiento y las órdenes de trabajo, la gestión de activos recorre todos los registros de nivel de servicio de activo para comprobar si hay una coincidencia posible. Comprueba siempre primero la combinación más específica. Es decir, Administración de activos primero busca una coincidencia para el campo **Tipo de orden de trabajo**. Si no se encuentra ninguna coincidencia, comprueba si hay una coincidencia para el campo **Activo**, y así sucesivamente. Como puede ver en el diseño de la página **Niveles de servicio de activos**, este comportamiento significa que, para encontrar la combinación más específica, Administración de activos comprueba cada registro de derecha a izquierda en busca de una coincidencia. Si no se encuentra ninguna coincidencia, se utiliza el registro predeterminado que no tiene ninguna selección en esos campos.

4. En el campo **Nivel de servicio**, seleccione un número que indique el nivel de servicio (la prioridad).


> [!NOTE]
> Si cambia un registro de nivel de servicio de activo en la página **Niveles de servicio de activos** después de haberlo utilizado en una orden de trabajo, el nivel de servicio de las solicitudes de mantenimiento y las órdenes de trabajo no se actualiza como corresponde.
