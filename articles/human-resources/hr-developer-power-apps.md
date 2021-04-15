---
title: Ampliar Talent con Power Apps y Power Automate
description: En este artículo se describen algunos ejemplos de los escenarios de la extensibilidad para Microsoft Dynamics 365 Human Resources que usan Microsoft Power Apps y Microsoft Power Automate.
author: negudava
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ad55de4b660de89d323f32a1ce2911d880c24ec5
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793570"
---
# <a name="extend-with-power-apps-and-power-automate"></a><span data-ttu-id="b2758-103">Ampliar con Power Apps y Power Automate</span><span class="sxs-lookup"><span data-stu-id="b2758-103">Extend with Power Apps and Power Automate</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="b2758-104">En este artículo se describen algunos ejemplos de los escenarios de la extensibilidad para Microsoft Dynamics 365 Human Resources que usan Microsoft Power Apps y Microsoft Power Automate.</span><span class="sxs-lookup"><span data-stu-id="b2758-104">This article describes some examples of extensibility scenarios for Microsoft Dynamics 365 Human Resources that use Microsoft Power Apps and Microsoft Power Automate.</span></span> <span data-ttu-id="b2758-105">Puede importar el paquete de la solución que está asociado a cada ejemplo en el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="b2758-105">You can import the solution package that is associated with each example into your Power Apps environment.</span></span> <span data-ttu-id="b2758-106">Puede utilizar los paquetes como orientación o punto de partida para los escenarios del instrumento aplicables a la organización.</span><span class="sxs-lookup"><span data-stu-id="b2758-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2758-107">Si desea usar las plantillas y las aplicaciones que se describen en este tema “tal cual”, asegúrese de probarlas para asegurarse de que cubren todas las situaciones que son específicas de su implementación.</span><span class="sxs-lookup"><span data-stu-id="b2758-107">If you want to use the templates and apps that are described in this topic "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b2758-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b2758-108">Prerequisites</span></span>

- <span data-ttu-id="b2758-109">Para importar los paquetes, los usuarios deben tener el permiso **Fabricante de entorno**.</span><span class="sxs-lookup"><span data-stu-id="b2758-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="b2758-110">Para exportar o importar aplicaciones, los usuarios deben tener una licencia Power Apps Plan 2 o una licencia de prueba de Power Apps Plan 2.</span><span class="sxs-lookup"><span data-stu-id="b2758-110">To export or import apps, users must have a Power Apps Plan 2 license or a Power Apps Plan 2 trial license.</span></span>

## <a name="integration-with-microsoft-365-power-automate"></a><span data-ttu-id="b2758-111">Integration con Microsoft 365, Power Automate</span><span class="sxs-lookup"><span data-stu-id="b2758-111">Integration with Microsoft 365, Power Automate</span></span>

<span data-ttu-id="b2758-112">La aplicación **Integración con Microsoft 365** se puede utilizar para extraer información de equipos para usuarios que han iniciado sesión desde Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b2758-112">The **Integration with Microsoft 365** app can be used to extract team information for signed-in users from Microsoft 365.</span></span> <span data-ttu-id="b2758-113">Hace referencia a los trabajadores de Recursos Humanos para extraer tipos de identificación de empleados.</span><span class="sxs-lookup"><span data-stu-id="b2758-113">It references workers in Human Resources to extract employee identification types.</span></span> <span data-ttu-id="b2758-114">Los directores pueden comprobar las fechas de vencimiento de los tipos de identificación de empleados.</span><span class="sxs-lookup"><span data-stu-id="b2758-114">Managers can check expiration dates of employee ID types.</span></span> <span data-ttu-id="b2758-115">También pueden enviar un recordatorio por correo electrónico si el tipo de id. de empleado va a expirar.</span><span class="sxs-lookup"><span data-stu-id="b2758-115">They can also send an email reminder if the employee ID type is expiring.</span></span> <span data-ttu-id="b2758-116">Power Automate se integra con Power Apps para enviar este recordatorio.</span><span class="sxs-lookup"><span data-stu-id="b2758-116">Power Automate integrates with Power Apps to send this reminder.</span></span> <span data-ttu-id="b2758-117">La confirmación se devolverá a Power Apps desde Power Automate cuando se envíe el recordatorio.</span><span class="sxs-lookup"><span data-stu-id="b2758-117">Confirmation will be sent back to Power Apps from Power Automate when the reminder is sent.</span></span> <span data-ttu-id="b2758-118">Los tipos de identificación incluyen el permiso de conducir, el pasaporte y otras formas aceptables de identificación.</span><span class="sxs-lookup"><span data-stu-id="b2758-118">Identification types include driver's license, passport, and other acceptable forms of ID.</span></span>

<span data-ttu-id="b2758-119">Puede ampliar esta aplicación para otros escenarios.</span><span class="sxs-lookup"><span data-stu-id="b2758-119">You can extend this app for other scenarios.</span></span> <span data-ttu-id="b2758-120">Por ejemplo, puede usarla para mostrar la información de las vacaciones del equipo, eventos de calendario y cualquier evento específico del equipo.</span><span class="sxs-lookup"><span data-stu-id="b2758-120">For example, you can use it to show team vacation information, calendar events, and any team-specific events.</span></span>

<span data-ttu-id="b2758-121">Para descargar la aplicación **Integración con Microsoft 365, Power Automate**, vaya a [Integración con Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2081787) en el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b2758-121">To download the **Integration with Microsoft 365, Power Automate** app, go to [Integration with Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2081787) on the Microsoft Download Center.</span></span>

## <a name="power-automate--sql-connect-and-execute"></a><span data-ttu-id="b2758-122">Power Automate – Conectar y ejecutar SQL</span><span class="sxs-lookup"><span data-stu-id="b2758-122">Power Automate – SQL Connect and execute</span></span>

<span data-ttu-id="b2758-123">La plantilla **Power Automate - Conectar y ejecutar SQL** se conecta a Microsoft SQL Server y activa la ejecución de consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="b2758-123">The **Power Automate – SQL Connect and execute** template connects to Microsoft SQL Server and enables SQL queries to be run.</span></span>

<span data-ttu-id="b2758-124">Aunque esta plantilla lee y actualiza las tablas SQL, puede ampliarla y usarla para otros escenarios.</span><span class="sxs-lookup"><span data-stu-id="b2758-124">Although this template reads and updates SQL tables, you can extend it and use it for other scenarios.</span></span> <span data-ttu-id="b2758-125">Por ejemplo, puede usarla para rellenar una tabla de ensayo de Dataverse con registros de SQL Server, y para sincronizar periódicamente la tabla de ensayo mediante una inserción incremental desde SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b2758-125">For example, you can use it to fill a staging table in Dataverse with records from SQL Server, and to periodically synchronize the staging table by using an incremental push from SQL Server.</span></span>

<span data-ttu-id="b2758-126">La consulta avanzada está integrada con Flow para permitir la transformación de datos y la inserción incremental.</span><span class="sxs-lookup"><span data-stu-id="b2758-126">Advanced Query is integrated with Flow to enable Data transformation and incremental push.</span></span>

<span data-ttu-id="b2758-127">Para descargar la plantilla **Power Automate - Conectar y ejecutar SQL**, vaya a [Power Automate - Conectar y ejecutar SQL](https://go.microsoft.com/fwlink/?linkid=2081789) en el Centro de descarga de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b2758-127">To download the **Power Automate – SQL Connect and execute** template, go to [Power Automate – SQL Connect and execute](https://go.microsoft.com/fwlink/?linkid=2081789) on the Microsoft Download Center.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b2758-128">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b2758-128">Additional resources</span></span>

[<span data-ttu-id="b2758-129">La Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="b2758-129">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]