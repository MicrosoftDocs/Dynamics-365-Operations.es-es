---
title: Activos y órdenes de trabajo
description: En este tema se describen los activos y las órdenes de trabajo en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5bd55988578be2b0287b399549f17642bfb1693b
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783568"
---
# <a name="assets-and-work-orders"></a>Activos y órdenes de trabajo

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

En este tema se describen los activos y las órdenes de trabajo en Administración de activos. Los activos y las órdenes de trabajo son las partes centrales de Administración de activos. Un *activo* es una máquina o una pieza de la máquina que requiere mantenimiento y servicio continuos. Los activos se pueden crear en una estructura jerárquica y pueden estar relacionados con ubicaciones funcionales. Los trabajos de mantenimiento pueden planificarse en todos los niveles de la estructura de activos.

Los distintos datos, como la información de producto y la especificación del activo, así como los planes de mantenimiento necesarios, se configuran en cada activo. La ilustración siguiente muestra una visión general de los datos de activos y la afiliación de los activos con los tipos de trabajo. El texto rojo se usa para ejemplos que muestran herencia y dependencias.

![Figura 1](media/05-overview-image.png)

Cada orden de trabajo tiene un tipo de orden de trabajo, tal como mantenimiento preventivo, mantenimiento correctivo o inspección. La orden de trabajo contiene uno o más trabajos de orden de trabajo. Cada trabajo de la orden de trabajo define un trabajo que se debe realizar en un activo y en un tipo de trabajo relacionado. Ejemplos de tipos de trabajo relacionados son 10 000 km, 50 000 km, revisión de un año e inspección de seguridad. Una orden de trabajo puede estar relacionada con varios activos.

La ilustración siguiente muestra una visión general de los datos clave en una orden de trabajo.

![Figura 2](media/06-overview-image.png)

Una orden de trabajo puede estar relacionada con otra y los tipos de trabajo pueden contener trabajos posteriores que creen una orden de trabajo. En genearl, no hay dependencias entre las órdenes de trabajo. Por lo tanto, pueden cambiar su estado de ciclo de vida de orden de trabajo y pueden programarse independientemente entre sí.

Las órdenes de trabajo se pueden crear de distintas maneras que guardan relación con el mantenimiento correctivo, preventivo o reactivo. También puede crear órdenes de trabajo de manera manual. La ilustración siguiente muestra una visión general del proceso de creación automática o manual de órdenes de trabajo.

![Figura 3](media/07-overview-image.png)

Se deben cojpletar varios pasos para programar y ejecutar un trabajo de mantenimiento en una orden de trabajo. La ilustración siguiente muestra una visión general del procesameinto de una orden de trabajo.

![Figura 4](media/08-overview-image.png)

> [!NOTE]
> Normalmente, cuando se trabaja en Microsoft Dynamics 365 for Finance and Operations y el módulo **Administración de activos**, se selecciona **Nuevo** para crear un nuevo registro, se selecciona **Editar** para actualizar un registro existente y se selecciona **Guardar** para guardar datos nuevos o modificados.
