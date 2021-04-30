---
title: Información general sobre integración de Dynamics 365 Commerce y Microsoft Teams
description: Este tema presenta una descripción general de la integración de Microsoft Dynamics 365 Commerce y Microsoft Teams.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b9289aca4f53eb2ae8f1fa06d5f80b7ee0bbab8e
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908476"
---
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-overview"></a>Información general sobre integración de Dynamics 365 Commerce y Microsoft Teams

[!include [banner](includes/banner.md)]

Este tema presenta una descripción general de la integración de Microsoft Dynamics 365 Commerce y Microsoft Teams.

Dynamics 365 Commerce se está integrando con Teams para ayudar a los clientes y sus empleados a mejorar la productividad sincronizando la administración de tareas entre las dos aplicaciones. La perfecta gestión de tareas que ofrece la integración de Commerce y Teams permite a los gerentes y empleados de las tiendas crear listas de tareas, asignar tareas a varias tiendas y realizar un seguimiento del estado de las tareas en todas las tiendas, desde cualquier aplicación.

La integración de Commerce y Teams está disponible a partir de la versión 10.0.18 de Commerce.

## <a name="key-features"></a>Funciones principales

Estas son algunas de las características clave que proporciona la integración de Commerce y Microsoft Teams:

- Aprovisione Teams aprovechando información bien definida de Commerce, como la estructura organizativa y la información sobre tiendas, trabajadores, permisos y contexto empresarial.
- Sincronice fácilmente los cambios en curso (por ejemplo, la adición de nuevas tiendas o la contratación de nuevos empleados) entre Commerce y Teams, pero mantenga a Commerce como la fuente principal de datos de la estructura organizativa.
- Integre la administración de tareas entre Commerce y Teams para ayudar a los trabajadores de la tienda, gerentes de tienda, gerentes regionales y gerentes de comunicaciones a manejar la administración de tareas desde cualquiera de las aplicaciones.

## <a name="prerequisites-for-using-integration-features"></a>Requisitos previos para usar las funciones de integración

Deben cumplirse los siguientes requisitos previos antes de que pueda empezar a utilizar las características de integración de Microsoft Teams:

- Licencia estándar de Microsoft 365 Empresa (esta licencia incluye Teams).
- Cuentas de Azure Active Directory (Azure AD) para todos los gerentes y trabajadores de la tienda
- Sistemas de punto de venta (PDV) configurados con autenticación Azure AD

## <a name="conceptual-architecture"></a>Arquitectura conceptual

La siguiente ilustración muestra la arquitectura conceptual de la integración de Dynamics 365 Commerce y Microsoft Teams, usando una tienda de San Francisco como ejemplo. Tanto Teams como la aplicación Commerce PDV usan Microsoft Planner como repositorio para que las tareas publicadas desde Teams aparezcan en la aplicación PDV y las tareas ad hoc creadas por los gerentes de tienda en la aplicación PDV aparezcan en Teams, lo que resulta en una experiencia de gestión de tareas perfecta entre las aplicaciones.    

![Arquitectura de la integración de Commerce y Teams](media/d365-commerce-teams-integration-conceptual-architecture.png)

## <a name="additional-resources"></a>Recursos adicionales

[Habilitar la integración de Dynamics 365 Commerce y Microsoft Teams](enable-teams-integration.md)

[Aprovisionar Microsoft Teams desde Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Sincronizar la gestión de tareas entre Microsoft Teams y Dynamics 365 Commerce PDV](synchronize-tasks-teams-pos.md)

[Administrar roles de usuario en Microsoft Teams](manage-user-roles-teams.md)

[Asignar tiendas y equipos si estos últimos ya existen en Microsoft Teams](map-stores-existing-teams.md)

[Preguntas frecuentes de la integración de Dynamics 365 Commerce y Microsoft Teams](teams-integration-faq.md)
