---
title: Activos y órdenes de trabajo
description: En este artículo se describen los activos y las órdenes de trabajo en Administración de activos.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: df2d0fcc5162900ad2ad67f2629d14015f694bd4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869702"
---
# <a name="assets-and-work-orders"></a>Activos y órdenes de trabajo

[!include [banner](../../includes/banner.md)]

 

En este artículo se describen los activos y las órdenes de trabajo en Administración de activos. Los activos y las órdenes de trabajo son las partes centrales de Administración de activos. Un *activo* es una máquina o una pieza de la máquina que requiere mantenimiento y servicio continuos. Los activos se pueden crear en una estructura jerárquica y pueden estar relacionados con ubicaciones funcionales. Los trabajos de mantenimiento pueden planificarse en todos los niveles de la estructura de activos.

Los distintos datos, como la información de producto y la especificación del activo, así como los planes de mantenimiento necesarios, se configuran en cada activo. La ilustración siguiente muestra una visión general de los datos de activos y la afiliación de los activos con los tipos de trabajo. El texto rojo se usa para ejemplos que muestran herencia y dependencias.

![Diagrama que muestra los datos de activos relacionados con los tipos de trabajo.](media/05-overview-image.png)

Cada orden de trabajo tiene un tipo de orden de trabajo, tal como mantenimiento preventivo, mantenimiento correctivo o inspección. La orden de trabajo contiene uno o más trabajos de orden de trabajo. Cada trabajo de la orden de trabajo define un trabajo que se debe realizar en un activo y en un tipo de trabajo relacionado. Ejemplos de tipos de trabajo relacionados son 10 000 km, 50 000 km, revisión de un año e inspección de seguridad. Una orden de trabajo puede estar relacionada con varios activos.

La ilustración siguiente muestra una visión general de los datos clave en una orden de trabajo.

![Diagrama que muestra los datos clave de una orden de trabajo.](media/06-overview-image.png)

Una orden de trabajo puede estar relacionada con otra y los tipos de trabajo pueden contener trabajos posteriores que creen una orden de trabajo. En genearl, no hay dependencias entre las órdenes de trabajo. Por lo tanto, pueden cambiar su estado de ciclo de vida de orden de trabajo y pueden programarse independientemente entre sí.

Las órdenes de trabajo se pueden crear de distintas maneras que guardan relación con el mantenimiento correctivo, preventivo o reactivo. También puede crear órdenes de trabajo de manera manual. La ilustración siguiente muestra una visión general del proceso de creación automática o manual de órdenes de trabajo.

![Diagrama que muestra la creación automática o manual de las órdenes de trabajo.](media/07-overview-image.png)

Se deben cojpletar varios pasos para programar y ejecutar un trabajo de mantenimiento en una orden de trabajo. La ilustración siguiente muestra una visión general del procesameinto de una orden de trabajo.

![Diagrama que muestra la información general de procesamiento de una orden de trabajo.](media/08-overview-image.png)

> [!NOTE]
> Normalmente, cuando se trabaja en Dynamics 365 Supply Chain Management y el módulo **Administración de activos**, se selecciona **Nuevo** para crear un nuevo registro, se selecciona **Editar** para actualizar un registro existente y se selecciona **Guardar** para guardar datos nuevos o modificados.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]