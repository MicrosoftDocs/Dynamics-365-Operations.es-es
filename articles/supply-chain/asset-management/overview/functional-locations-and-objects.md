---
title: Ubicaciones funcionales y activos
description: En este tema se describen las ubicaciones técnicas y los activos en Administración de activos. Administración de activos es un módulo avanzado para gestionar activos y trabajos de mantenimiento en Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 5271b673d758608cae8e43d72b7e75b259d5f142
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024623"
---
# <a name="functional-locations-and-assets"></a>Ubicaciones funcionales y activos

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

En este tema se describen las ubicaciones técnicas y los activos en Administración de activos. Administración de activos es un módulo avanzado para gestionar activos y trabajos de mantenimiento en Dynamics 365 Supply Chain Management.

## <a name="overview"></a>Información general

Administración de activos se integra de manera fluida con varios módulos de Finance and Operations. La ilustración siguiente muestra las interfaces con otros módulos.

![Figura 1](media/01-overview-image.png)

Administración de activos permite administrar y realizar todas las tareas relacionadas con la gestión y el mantenimiento de muchos tipos de equipos de la empresa eficientemente. Los equipos incluyen las máquinas, los equipos de producción y los vehículos. Administración de activos también admite soluciones de numerosos sectores.

La ilustración siguiente muestra una visión general de la funcionalidad principal que cubre Administración de activos.

![Figura 2](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a>Ubicaciones funcionales y activos

Las ubicaciones funcionales se utilizan para gestionar activos en las ubicaciones. Esta administración incluye el seguimiento de los costes de los activos en las ubicaciones funcionales. Las ubicaciones funcionales se estructuran jerárquicamente y pueden tener sububicaciones. La estructura de las ubicaciones funcionales es estática. Es decir, las ubicaciones no pueden cambiar de lugar. Los activos se pueden instalar en las ubicaciones funcionales y, según convenga, se pueden instalar en otras ubicaciones funcionales posteriormente.

Los costes de los activos siempre siguen la ubicación del activo. Es decir, si se instala un activo en una nueva ubicación funcional, el activo usa automáticamente las dimensiones financieras relacionadas con la nueva ubicación funcional. Por lo tanto, los costes de activo siempre están relacionados con la ubicación funcional en la que el activo está instalado actualmente. Este control automático de las dimensiones financieras ayuda a garantizar el seguimiento completo de los costes si su empresa lleva a cabo un control de los proyectos y produce informes según las ubicaciones funcionales.

La forma en que se crea la jerarquía de ubicaciones funcionales depende de los requisitos de la empresa para mantener el equipo interno o reparar el equipo del cliente. En la ilustración siguiente se muestra un ejemplo de ubicaciones funcionales que se basan en ubicaciones geográficas.

![Figura 3](media/03-overview-image.png)

En la ilustración siguiente se muestra un ejemplo de ubicaciones funcionales que se basan en clientes.

![Figura 4](media/04-overview-image.png)
