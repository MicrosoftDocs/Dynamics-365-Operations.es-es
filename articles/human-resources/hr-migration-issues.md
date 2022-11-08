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
ms.openlocfilehash: 28c2c10a9293d00e26dfcc80ab08b89a122a6135
ms.sourcegitcommit: 088a7b5eb9a3b68710dfe012abf4c24776978750
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "9733481"
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

## <a name="licensing"></a>Licencias

No hay cambios en las licencias para Dynamics 365 Human Resources en las siguientes áreas: 

- **Requisito de compra de un número mínimo de licencias**
- **Licencias para un entorno de producción y espacio aislado**: si tiene licencias independientes de Human Resources que incluyen un entorno de producción y un entorno de espacio aislado, la misma cantidad de licencias estará disponible en la infraestructura de finanzas y operaciones, sin coste adicional.
- **Licencias adicionales de espacio aislado**: si ha adquirido licencias de espacio aislado adicionales para la aplicación independiente de Human Resources, la misma cantidad de licencias de espacio aislado estará disponible para los entornos de espacio aislado en la infraestructura de finanzas y operaciones. 
