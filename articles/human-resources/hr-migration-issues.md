---
title: Problemas conocidos de la fusión de infraestructura de Dynamics 365 Human Resources
description: Este artículo enumera los problemas que pueden producirse durante la fusión de la infraestructura de Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3fe21df8be010ace3070ad08ed95f3d3efc7b01d
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838565"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-known-issues"></a>Problemas conocidos de la fusión de infraestructura de Dynamics 365 Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="shared-dataverse-environments"></a>Entornos de Dataverse compartidos

El marco de doble escritura no admite la vinculación de dos entornos de aplicaciones de finanzas y operaciones al mismo entorno de Dataverse. Si tiene un entorno de Dataverse compartido con los dos elementos siguientes, debe duplicar el entorno de Dataverse o dividirlo:

- Una aplicación de finanzas y operaciones
- Un entorno de Human Resources actual

## <a name="environment-type-requirements"></a>Requisitos de tipo de entorno

Se requieren los siguientes tipos de entorno para poder realizar la migración:

- Si no tiene ningún entorno independiente de espacio aislado, debe crear uno para validar la migración.
- Si tiene varios entornos independientes de producción, uno de ellos puede migrarse. Póngase en contacto con el soporte técnico de Microsoft para marcar otros entornos como espacios aislados.

## <a name="teams-integration"></a>Integración de Teams

La aplicación de Human Resources existente en Teams se está cambiando actualmente a una solución de Microsoft Power Platform. Para más información, consulte [Aplicación de recursos humanos en Teams](hr-admin-teams-leave-app.md).

## <a name="dual-write-integration"></a>Integración de doble escritura

La doble escritura es una infraestructura lista para usar que proporciona interacción casi en tiempo real entre aplicaciones de interacción con los clientes y aplicaciones de finanzas y operaciones. Si su organización utiliza escritura dual para las integraciones, es posible que se vea afectado por algunos de los problemas que se encontraron. Para obtener más información sobre tablas y problemas de Dataverse, consulte [Tablas de Dataverse](hr-developer-entities.md).

