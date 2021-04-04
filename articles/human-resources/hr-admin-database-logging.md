---
title: Configurar y administrar el registro de la base de datos
description: Puede realizar un seguimiento de los cambios en las tablas y campos en Dynamics 365 Human Resources con registro de base de datos.
author: andreabichsel
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8057ebd0bc061c6bf78d8674c45e0885ffce681c
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467658"
---
# <a name="configure-and-manage-database-logging"></a><span data-ttu-id="aa565-103">Configurar y administrar el registro de la base de datos</span><span class="sxs-lookup"><span data-stu-id="aa565-103">Configure and manage database logging</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="aa565-104">Puede realizar un seguimiento de los cambios en las tablas y campos en Dynamics 365 Human Resources con registro de base de datos.</span><span class="sxs-lookup"><span data-stu-id="aa565-104">You can track changes to tables and fields in Dynamics 365 Human Resources with database logging.</span></span> <span data-ttu-id="aa565-105">En este tema se describe cómo:</span><span class="sxs-lookup"><span data-stu-id="aa565-105">This topic describes how to:</span></span>

- <span data-ttu-id="aa565-106">Administrar la seguridad y el rendimiento para el registro de la base de datos</span><span class="sxs-lookup"><span data-stu-id="aa565-106">Manage security and performance for database logging</span></span>
- <span data-ttu-id="aa565-107">Configurar nivel de registro de base de datos</span><span class="sxs-lookup"><span data-stu-id="aa565-107">Set up database logging</span></span>
- <span data-ttu-id="aa565-108">Limpiar registros de bases de datos</span><span class="sxs-lookup"><span data-stu-id="aa565-108">Clean up database logs</span></span>

## <a name="overview-of-database-logging"></a><span data-ttu-id="aa565-109">Descripción general del registro de la base de datos</span><span class="sxs-lookup"><span data-stu-id="aa565-109">Overview of database logging</span></span>

<span data-ttu-id="aa565-110">El registro de la base de datos lleva el seguimiento de los cambios específicos en las tablas y campos en Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="aa565-110">Database logging tracks specific changes to Microsoft Dynamics 365 Human Resources tables and fields.</span></span> <span data-ttu-id="aa565-111">Estos cambios incluyen insertar, actualizar o eliminar.</span><span class="sxs-lookup"><span data-stu-id="aa565-111">These changes include inserting, updating, or deleting.</span></span> <span data-ttu-id="aa565-112">El registro de la base de datos almacena un registro de cambios en las tablas o campos en la tabla de registro de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aa565-112">Database logging stores a record of changes to tables or fields in the database log table.</span></span>

<span data-ttu-id="aa565-113">Los usos comerciales del registro de la base de datos incluyen:</span><span class="sxs-lookup"><span data-stu-id="aa565-113">The business uses of database logging include:</span></span>

- <span data-ttu-id="aa565-114">Crear un registro de auditoría de cambios para tablas específicas que contengan información confidencial.</span><span class="sxs-lookup"><span data-stu-id="aa565-114">Creating an audit record of changes to specific tables that contain sensitive information.</span></span>
- <span data-ttu-id="aa565-115">Seguimiento de transacciones individuales.</span><span class="sxs-lookup"><span data-stu-id="aa565-115">Tracking single transactions.</span></span> <span data-ttu-id="aa565-116">El registro de la base de datos no está destinado a llevar el seguimiento de transacciones automatizadas que se ejecutan en trabajos por lotes.</span><span class="sxs-lookup"><span data-stu-id="aa565-116">Database logging isn't intended for tracking automated transactions that run in batch jobs.</span></span>

## <a name="security-for-database-logging"></a><span data-ttu-id="aa565-117">Seguridad para el registro de la base de datos</span><span class="sxs-lookup"><span data-stu-id="aa565-117">Security for database logging</span></span>

<span data-ttu-id="aa565-118">Los registros de las bases de datos pueden contener datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="aa565-118">Database logs can contain sensitive data.</span></span> <span data-ttu-id="aa565-119">Limite el acceso para incluir solo roles de seguridad que necesiten acceso a los datos de registro.</span><span class="sxs-lookup"><span data-stu-id="aa565-119">Limit access to include only security roles that need access to the log data.</span></span>

## <a name="database-logging-and-performance"></a><span data-ttu-id="aa565-120">Registro de base de datos y rendimiento</span><span class="sxs-lookup"><span data-stu-id="aa565-120">Database logging and performance</span></span>

<span data-ttu-id="aa565-121">Pese a que puede ser valioso desde una perspectiva de negocio, el registro de bases de datos puede resultar caro si se mide por gestión y uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="aa565-121">While valuable from a business perspective, database logging can be expensive in resource use and management.</span></span> <span data-ttu-id="aa565-122">Las implicaciones para el rendimiento del registro de la base de datos incluyen:</span><span class="sxs-lookup"><span data-stu-id="aa565-122">The performance implications of database logging include:</span></span>

- <span data-ttu-id="aa565-123">La tabla de registro de la base de datos puede crecer rápidamente y causar un aumento en el tamaño de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="aa565-123">The database log table can grow quickly and cause an increase in the size of the database.</span></span> <span data-ttu-id="aa565-124">El crecimiento depende de la cantidad de datos registrados que decida conservar.</span><span class="sxs-lookup"><span data-stu-id="aa565-124">Growth depends on the amount of logged data that you decide to keep.</span></span> <span data-ttu-id="aa565-125">De forma predeterminada, la tabla de registro de la base de datos conserva solo los datos de registro durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="aa565-125">By default, the database log table maintains only 30 days of log data.</span></span> 

- <span data-ttu-id="aa565-126">El registro de bases de datos puede afectar negativamente a los procesos automatizados de larga duración, como las importaciones de datos de larga ejecución.</span><span class="sxs-lookup"><span data-stu-id="aa565-126">Database logging can adversely affect long-running automated processes, such as long-running data imports.</span></span>

### <a name="best-practices"></a><span data-ttu-id="aa565-127">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="aa565-127">Best practices</span></span>

<span data-ttu-id="aa565-128">Para mejorar el rendimiento, limite las entradas en el registro seleccionando campos específicos en lugar de tablas enteras.</span><span class="sxs-lookup"><span data-stu-id="aa565-128">To improve performance, limit log entries by selecting specific fields to log instead of whole tables.</span></span> <span data-ttu-id="aa565-129">Para ayudar a conservar el rendimiento general, el registro de bases de datos está limitado a 20 tablas.</span><span class="sxs-lookup"><span data-stu-id="aa565-129">To help maintain overall performance, database logging is limited to 20 tables.</span></span>

> [!NOTE]
> <span data-ttu-id="aa565-130">Para campos individuales, solo se pueden registrar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="aa565-130">Only updates can be logged for individual fields.</span></span>

## <a name="set-up-database-logging"></a><span data-ttu-id="aa565-131">Configurar nivel de registro de base de datos</span><span class="sxs-lookup"><span data-stu-id="aa565-131">Set up database logging</span></span>

<span data-ttu-id="aa565-132">Puede usar el asistente **Registro de cambios en la base de datos** para configurar el registro de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="aa565-132">You can use the **Logging database changes** wizard to set up database logging.</span></span> <span data-ttu-id="aa565-133">El asistente proporciona una forma flexible de configurar el registro de tablas o campos.</span><span class="sxs-lookup"><span data-stu-id="aa565-133">The wizard provides a flexible way to set up logging for tables or fields.</span></span>

1. <span data-ttu-id="aa565-134">Vaya a **Administración del sistema> Enlaces > Base de datos > Configuración del registro de bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="aa565-134">Go to **System administration > Links > Database > Database log setup**.</span></span> <span data-ttu-id="aa565-135">Seleccione **Nuevo** para comenzar el asistente **Registro de cambios en la base de datos**.</span><span class="sxs-lookup"><span data-stu-id="aa565-135">Select **New** to start the **Logging database changes** wizard.</span></span>
2. <span data-ttu-id="aa565-136">Complete el asistente.</span><span class="sxs-lookup"><span data-stu-id="aa565-136">Complete the wizard.</span></span>

## <a name="clean-up-database-logs"></a><span data-ttu-id="aa565-137">Limpiar registros de bases de datos</span><span class="sxs-lookup"><span data-stu-id="aa565-137">Clean up database logs</span></span>

<span data-ttu-id="aa565-138">Puede eliminar todo o parte de los registros de la base de datos, utilizando las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="aa565-138">You can delete all or part of the database logs, using the following options:</span></span>

- <span data-ttu-id="aa565-139">Seleccione todos los registros para una tabla en particular.</span><span class="sxs-lookup"><span data-stu-id="aa565-139">Select all logs for a particular table.</span></span>
- <span data-ttu-id="aa565-140">Seleccione tipos específicos de registro de base de datos.</span><span class="sxs-lookup"><span data-stu-id="aa565-140">Select specific types of database log.</span></span>
- <span data-ttu-id="aa565-141">Seleccione una fecha y hora en que se creó un registro.</span><span class="sxs-lookup"><span data-stu-id="aa565-141">Select a date and time that a log was created.</span></span>

<span data-ttu-id="aa565-142">Siga estos pasos para configurar la limpieza del registro de bases de datos:</span><span class="sxs-lookup"><span data-stu-id="aa565-142">To set up database log cleanup, follow these steps:</span></span> 

1. <span data-ttu-id="aa565-143">Vaya a **Administración del sistema > Enlaces > Base de datos > Registro de bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="aa565-143">Go to **System administration > Links > Database > Database log**.</span></span> <span data-ttu-id="aa565-144">Seleccione **Limpiar registro**.</span><span class="sxs-lookup"><span data-stu-id="aa565-144">Select **Clean up log**.</span></span>

2. <span data-ttu-id="aa565-145">Elija un método de selección de registros para eliminar especificando una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="aa565-145">Choose a method of selecting logs to delete by entering one of the following options:</span></span>

   - <span data-ttu-id="aa565-146">ID de tabla</span><span class="sxs-lookup"><span data-stu-id="aa565-146">Table ID</span></span>
   - <span data-ttu-id="aa565-147">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="aa565-147">Type of log</span></span>
   - <span data-ttu-id="aa565-148">Fecha y hora de creación</span><span class="sxs-lookup"><span data-stu-id="aa565-148">Created date and time</span></span>

3. <span data-ttu-id="aa565-149">Utilice la pestaña **Limpieza de registro de bases de datos** para determinar cuándo ejecutar la tarea de limpieza del registro.</span><span class="sxs-lookup"><span data-stu-id="aa565-149">Use the **Database log cleanup** tab to determine when to run the log cleanup task.</span></span> <span data-ttu-id="aa565-150">De forma predeterminada, los registros de la base de datos están disponibles durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="aa565-150">By default, database logs are available for 30 days.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]