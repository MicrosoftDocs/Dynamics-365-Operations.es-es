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
# <a name="dynamics-365-commerce-and-microsoft-teams-integration-overview"></a><span data-ttu-id="a8810-103">Información general sobre integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8810-103">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a8810-104">Este tema presenta una descripción general de la integración de Microsoft Dynamics 365 Commerce y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a8810-104">This topic presents an overview of Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

<span data-ttu-id="a8810-105">Dynamics 365 Commerce se está integrando con Teams para ayudar a los clientes y sus empleados a mejorar la productividad sincronizando la administración de tareas entre las dos aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a8810-105">Dynamics 365 Commerce is integrating with Teams to help customers and their employees improve productivity by synchronizing task management between the two applications.</span></span> <span data-ttu-id="a8810-106">La perfecta gestión de tareas que ofrece la integración de Commerce y Teams permite a los gerentes y empleados de las tiendas crear listas de tareas, asignar tareas a varias tiendas y realizar un seguimiento del estado de las tareas en todas las tiendas, desde cualquier aplicación.</span><span class="sxs-lookup"><span data-stu-id="a8810-106">The seamless task management that Commerce and Teams integration provides lets store managers and employees create task lists, assign tasks to multiple stores, and track the status of tasks across stores, from either application.</span></span>

<span data-ttu-id="a8810-107">La integración de Commerce y Teams está disponible a partir de la versión 10.0.18 de Commerce.</span><span class="sxs-lookup"><span data-stu-id="a8810-107">Commerce and Teams integration is available as of the Commerce version 10.0.18 release.</span></span>

## <a name="key-features"></a><span data-ttu-id="a8810-108">Funciones principales</span><span class="sxs-lookup"><span data-stu-id="a8810-108">Key features</span></span>

<span data-ttu-id="a8810-109">Estas son algunas de las características clave que proporciona la integración de Commerce y Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="a8810-109">Here are some of the key features that the Commerce and Microsoft Teams integration provides:</span></span>

- <span data-ttu-id="a8810-110">Aprovisione Teams aprovechando información bien definida de Commerce, como la estructura organizativa y la información sobre tiendas, trabajadores, permisos y contexto empresarial.</span><span class="sxs-lookup"><span data-stu-id="a8810-110">Provision Teams by taking advantage of well-defined information from Commerce, such as the organizational structure and information about stores, workers, permissions, and business context.</span></span>
- <span data-ttu-id="a8810-111">Sincronice fácilmente los cambios en curso (por ejemplo, la adición de nuevas tiendas o la contratación de nuevos empleados) entre Commerce y Teams, pero mantenga a Commerce como la fuente principal de datos de la estructura organizativa.</span><span class="sxs-lookup"><span data-stu-id="a8810-111">Easily synchronize ongoing changes (for example, the addition of new stores or hiring of new employees) between Commerce and Teams, but keep Commerce as the master source of organizational structure data.</span></span>
- <span data-ttu-id="a8810-112">Integre la administración de tareas entre Commerce y Teams para ayudar a los trabajadores de la tienda, gerentes de tienda, gerentes regionales y gerentes de comunicaciones a manejar la administración de tareas desde cualquiera de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a8810-112">Integrate task management between Commerce and Teams to help store workers, store managers, regional managers, and communications managers handle task management from either application.</span></span>

## <a name="prerequisites-for-using-integration-features"></a><span data-ttu-id="a8810-113">Requisitos previos para usar las funciones de integración</span><span class="sxs-lookup"><span data-stu-id="a8810-113">Prerequisites for using integration features</span></span>

<span data-ttu-id="a8810-114">Deben cumplirse los siguientes requisitos previos antes de que pueda empezar a utilizar las características de integración de Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="a8810-114">The following prerequisites must be in place before you can start to use Microsoft Teams integration features:</span></span>

- <span data-ttu-id="a8810-115">Licencia estándar de Microsoft 365 Empresa (esta licencia incluye Teams).</span><span class="sxs-lookup"><span data-stu-id="a8810-115">Microsoft 365 Business Standard License (This license includes Teams.)</span></span>
- <span data-ttu-id="a8810-116">Cuentas de Azure Active Directory (Azure AD) para todos los gerentes y trabajadores de la tienda</span><span class="sxs-lookup"><span data-stu-id="a8810-116">Azure Active Directory (Azure AD) accounts for all store managers and workers</span></span>
- <span data-ttu-id="a8810-117">Sistemas de punto de venta (PDV) configurados con autenticación Azure AD</span><span class="sxs-lookup"><span data-stu-id="a8810-117">Point of sale (POS) systems that are configured with Azure AD authentication</span></span>

## <a name="conceptual-architecture"></a><span data-ttu-id="a8810-118">Arquitectura conceptual</span><span class="sxs-lookup"><span data-stu-id="a8810-118">Conceptual architecture</span></span>

<span data-ttu-id="a8810-119">La siguiente ilustración muestra la arquitectura conceptual de la integración de Dynamics 365 Commerce y Microsoft Teams, usando una tienda de San Francisco como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a8810-119">The following illustration shows the conceptual architecture of Dynamics 365 Commerce and Microsoft Teams integration, using a San Francisco store as an example.</span></span> <span data-ttu-id="a8810-120">Tanto Teams como la aplicación Commerce PDV usan Microsoft Planner como repositorio para que las tareas publicadas desde Teams aparezcan en la aplicación PDV y las tareas ad hoc creadas por los gerentes de tienda en la aplicación PDV aparezcan en Teams, lo que resulta en una experiencia de gestión de tareas perfecta entre las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a8810-120">Both Teams and the Commerce POS application use Microsoft Planner as a repository so that tasks published from Teams appear in the POS application and ad hoc tasks created by store managers in the POS application appear in Teams, resulting in a seamless task management experience between the applications.</span></span>    

![Arquitectura de la integración de Commerce y Teams](media/d365-commerce-teams-integration-conceptual-architecture.png)

## <a name="additional-resources"></a><span data-ttu-id="a8810-122">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a8810-122">Additional resources</span></span>

[<span data-ttu-id="a8810-123">Habilitar la integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8810-123">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="a8810-124">Aprovisionar Microsoft Teams desde Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="a8810-124">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="a8810-125">Sincronizar la gestión de tareas entre Microsoft Teams y Dynamics 365 Commerce PDV</span><span class="sxs-lookup"><span data-stu-id="a8810-125">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="a8810-126">Administrar roles de usuario en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8810-126">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="a8810-127">Asignar tiendas y equipos si estos últimos ya existen en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8810-127">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="a8810-128">Preguntas frecuentes de la integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8810-128">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
