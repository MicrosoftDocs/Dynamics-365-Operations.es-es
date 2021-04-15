---
title: Configurar y administrar el registro de la base de datos
description: Puede realizar un seguimiento de los cambios en las tablas y campos en Dynamics 365 Human Resources con registro de base de datos.
author: andreabichsel
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: d22ff9f3ce68c81f37840342c795d7d162eb027b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801344"
---
# <a name="configure-and-manage-database-logging"></a><span data-ttu-id="1d495-103">Configurar y administrar el registro de la base de datos</span><span class="sxs-lookup"><span data-stu-id="1d495-103">Configure and manage database logging</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="1d495-104">Puede realizar un seguimiento de los cambios en las tablas y campos en Dynamics 365 Human Resources con registro de base de datos.</span><span class="sxs-lookup"><span data-stu-id="1d495-104">You can track changes to tables and fields in Dynamics 365 Human Resources with database logging.</span></span> <span data-ttu-id="1d495-105">En este tema se describe cómo:</span><span class="sxs-lookup"><span data-stu-id="1d495-105">This topic describes how to:</span></span>

- <span data-ttu-id="1d495-106">Administrar la seguridad y el rendimiento para el registro de la base de datos</span><span class="sxs-lookup"><span data-stu-id="1d495-106">Manage security and performance for database logging</span></span>
- <span data-ttu-id="1d495-107">Configurar nivel de registro de base de datos</span><span class="sxs-lookup"><span data-stu-id="1d495-107">Set up database logging</span></span>
- <span data-ttu-id="1d495-108">Limpiar registros de bases de datos</span><span class="sxs-lookup"><span data-stu-id="1d495-108">Clean up database logs</span></span>

## <a name="overview-of-database-logging"></a><span data-ttu-id="1d495-109">Descripción general del registro de la base de datos</span><span class="sxs-lookup"><span data-stu-id="1d495-109">Overview of database logging</span></span>

<span data-ttu-id="1d495-110">El registro de la base de datos lleva el seguimiento de los cambios específicos en las tablas y campos en Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1d495-110">Database logging tracks specific changes to Microsoft Dynamics 365 Human Resources tables and fields.</span></span> <span data-ttu-id="1d495-111">Estos cambios incluyen insertar, actualizar o eliminar.</span><span class="sxs-lookup"><span data-stu-id="1d495-111">These changes include inserting, updating, or deleting.</span></span> <span data-ttu-id="1d495-112">El registro de la base de datos almacena un registro de cambios en las tablas o campos en la tabla de registro de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1d495-112">Database logging stores a record of changes to tables or fields in the database log table.</span></span>

<span data-ttu-id="1d495-113">Los usos comerciales del registro de la base de datos incluyen:</span><span class="sxs-lookup"><span data-stu-id="1d495-113">The business uses of database logging include:</span></span>

- <span data-ttu-id="1d495-114">Crear un registro de auditoría de cambios para tablas específicas que contengan información confidencial.</span><span class="sxs-lookup"><span data-stu-id="1d495-114">Creating an audit record of changes to specific tables that contain sensitive information.</span></span>
- <span data-ttu-id="1d495-115">Seguimiento de transacciones individuales.</span><span class="sxs-lookup"><span data-stu-id="1d495-115">Tracking single transactions.</span></span> <span data-ttu-id="1d495-116">El registro de la base de datos no está destinado a llevar el seguimiento de transacciones automatizadas que se ejecutan en trabajos por lotes.</span><span class="sxs-lookup"><span data-stu-id="1d495-116">Database logging isn't intended for tracking automated transactions that run in batch jobs.</span></span>

## <a name="security-for-database-logging"></a><span data-ttu-id="1d495-117">Seguridad para el registro de la base de datos</span><span class="sxs-lookup"><span data-stu-id="1d495-117">Security for database logging</span></span>

<span data-ttu-id="1d495-118">Los registros de las bases de datos pueden contener datos confidenciales.</span><span class="sxs-lookup"><span data-stu-id="1d495-118">Database logs can contain sensitive data.</span></span> <span data-ttu-id="1d495-119">Limite el acceso para incluir solo roles de seguridad que necesiten acceso a los datos de registro.</span><span class="sxs-lookup"><span data-stu-id="1d495-119">Limit access to include only security roles that need access to the log data.</span></span>

## <a name="database-logging-and-performance"></a><span data-ttu-id="1d495-120">Registro de base de datos y rendimiento</span><span class="sxs-lookup"><span data-stu-id="1d495-120">Database logging and performance</span></span>

<span data-ttu-id="1d495-121">Pese a que puede ser valioso desde una perspectiva de negocio, el registro de bases de datos puede resultar caro si se mide por gestión y uso de recursos.</span><span class="sxs-lookup"><span data-stu-id="1d495-121">While valuable from a business perspective, database logging can be expensive in resource use and management.</span></span> <span data-ttu-id="1d495-122">Las implicaciones para el rendimiento del registro de la base de datos incluyen:</span><span class="sxs-lookup"><span data-stu-id="1d495-122">The performance implications of database logging include:</span></span>

- <span data-ttu-id="1d495-123">La tabla de registro de la base de datos puede crecer rápidamente y causar un aumento en el tamaño de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1d495-123">The database log table can grow quickly and cause an increase in the size of the database.</span></span> <span data-ttu-id="1d495-124">El crecimiento depende de la cantidad de datos registrados que decida conservar.</span><span class="sxs-lookup"><span data-stu-id="1d495-124">Growth depends on the amount of logged data that you decide to keep.</span></span> <span data-ttu-id="1d495-125">De forma predeterminada, la tabla de registro de la base de datos conserva solo los datos de registro durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="1d495-125">By default, the database log table maintains only 30 days of log data.</span></span> 

- <span data-ttu-id="1d495-126">El registro de bases de datos puede afectar negativamente a los procesos automatizados de larga duración, como las importaciones de datos de larga ejecución.</span><span class="sxs-lookup"><span data-stu-id="1d495-126">Database logging can adversely affect long-running automated processes, such as long-running data imports.</span></span>

### <a name="best-practices"></a><span data-ttu-id="1d495-127">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="1d495-127">Best practices</span></span>

<span data-ttu-id="1d495-128">Para mejorar el rendimiento, limite las entradas en el registro seleccionando campos específicos en lugar de tablas enteras.</span><span class="sxs-lookup"><span data-stu-id="1d495-128">To improve performance, limit log entries by selecting specific fields to log instead of whole tables.</span></span> <span data-ttu-id="1d495-129">Para ayudar a conservar el rendimiento general, el registro de bases de datos está limitado a 20 tablas.</span><span class="sxs-lookup"><span data-stu-id="1d495-129">To help maintain overall performance, database logging is limited to 20 tables.</span></span>

> [!NOTE]
> <span data-ttu-id="1d495-130">Para campos individuales, solo se pueden registrar las actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="1d495-130">Only updates can be logged for individual fields.</span></span>

## <a name="set-up-database-logging"></a><span data-ttu-id="1d495-131">Configurar nivel de registro de base de datos</span><span class="sxs-lookup"><span data-stu-id="1d495-131">Set up database logging</span></span>

<span data-ttu-id="1d495-132">Puede usar el asistente **Registro de cambios en la base de datos** para configurar el registro de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="1d495-132">You can use the **Logging database changes** wizard to set up database logging.</span></span> <span data-ttu-id="1d495-133">El asistente proporciona una forma flexible de configurar el registro de tablas o campos.</span><span class="sxs-lookup"><span data-stu-id="1d495-133">The wizard provides a flexible way to set up logging for tables or fields.</span></span>

1. <span data-ttu-id="1d495-134">Vaya a **Administración del sistema> Enlaces > Base de datos > Configuración del registro de bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="1d495-134">Go to **System administration > Links > Database > Database log setup**.</span></span> <span data-ttu-id="1d495-135">Seleccione **Nuevo** para comenzar el asistente **Registro de cambios en la base de datos**.</span><span class="sxs-lookup"><span data-stu-id="1d495-135">Select **New** to start the **Logging database changes** wizard.</span></span>
2. <span data-ttu-id="1d495-136">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1d495-136">Select **Next**.</span></span> 
3. <span data-ttu-id="1d495-137">En la página **Tablas y campos** del asistente, seleccione las tablas y los campos en los que desea habilitar el registro de la base de datos y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1d495-137">On the **Tables and fields** page of the wizard, select the the tables and fields on which you want to enable database logging, and select **Next**.</span></span>

   > [!Note]
   > <span data-ttu-id="1d495-138">El registro de la base de datos no está disponible en todas las tablas de la base de datos de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1d495-138">Database logging is not available on all tables in the Human Resources database.</span></span> <span data-ttu-id="1d495-139">La selección de **Mostrar todas las tablas**, situada a continuación de la lista, expande la lista de tablas y campos para mostrar todas las tablas de la base de datos para las que está disponible el registro de la base de datos, pero esto será un subconjunto de la lista completa de tablas de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1d495-139">Selecting **Show all tables** below the list expands the list of tables and fields to show all database tables for which database logging is available, but this will be a subset of the full list of database tables.</span></span>

4. <span data-ttu-id="1d495-140">En la página **Tipos de cambio** del asistente, seleccione las operaciones de datos para las que desea realizar un seguimiento de los cambios para cada uno de los campos y tablas, y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1d495-140">On the **Types of change** page of the wizard, select the data operations for which you want to track changes for each of the tables and fields, and select **Next**.</span></span> <span data-ttu-id="1d495-141">Consulte la tabla siguiente para obtener una descripción de las operaciones de datos disponibles para el registro.</span><span class="sxs-lookup"><span data-stu-id="1d495-141">See the table below for a description of the data operations that are available for logging.</span></span>
5. <span data-ttu-id="1d495-142">En la página **Terminar**, revise los cambios que se realizarán y seleccione **Terminar**.</span><span class="sxs-lookup"><span data-stu-id="1d495-142">On the **Finish** page, review the changes that will be made, and select **Finish**.</span></span>

| <span data-ttu-id="1d495-143">Operación</span><span class="sxs-lookup"><span data-stu-id="1d495-143">Operation</span></span> | <span data-ttu-id="1d495-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d495-144">Description</span></span> |
| -- | -- |
| <span data-ttu-id="1d495-145">Realizar seguimiento de transacciones nuevas</span><span class="sxs-lookup"><span data-stu-id="1d495-145">Track new transactions</span></span> | <span data-ttu-id="1d495-146">Cree un registro para los nuevos registros que se crean en la tabla.</span><span class="sxs-lookup"><span data-stu-id="1d495-146">Create a log for new records that are created in the table.</span></span> |
| <span data-ttu-id="1d495-147">Actualización</span><span class="sxs-lookup"><span data-stu-id="1d495-147">Update</span></span> | <span data-ttu-id="1d495-148">Cree un registro para las actualizaciones de los registros de la tabla o actualizaciones de los campos seleccionados individualmente en la tabla.</span><span class="sxs-lookup"><span data-stu-id="1d495-148">Create a log for updates to table records, or updates to individually selected fields in the table.</span></span> <span data-ttu-id="1d495-149">Si selecciona registrar las actualizaciones para la tabla, se crea un registro de registro cada vez que se realiza una actualización en cualquier campo de cualquier registro de la tabla.</span><span class="sxs-lookup"><span data-stu-id="1d495-149">If you select to log updates for the table, then a log record is created each time an update is made to any field of any record on the table.</span></span> <span data-ttu-id="1d495-150">Si selecciona registrar actualizaciones para campos específicos, se crea un registro solo cuando se realizan actualizaciones en esos campos de registros de tabla.</span><span class="sxs-lookup"><span data-stu-id="1d495-150">If you select to log updates for specific fields, then a log record is created only when updates are made to those fields of table records.</span></span> |
| <span data-ttu-id="1d495-151">Suprimir</span><span class="sxs-lookup"><span data-stu-id="1d495-151">Delete</span></span> | <span data-ttu-id="1d495-152">Cree un registro de los registros eliminados de la tabla.</span><span class="sxs-lookup"><span data-stu-id="1d495-152">Create a log for records deleted from the table.</span></span> |
| <span data-ttu-id="1d495-153">Asignar nuevo nombre a la clave</span><span class="sxs-lookup"><span data-stu-id="1d495-153">Rename key</span></span> | <span data-ttu-id="1d495-154">Cree un registro de registros cuando se cambie el nombre de una clave de tabla.</span><span class="sxs-lookup"><span data-stu-id="1d495-154">Create a log record when a table key is renamed.</span></span> |


## <a name="clean-up-database-logs"></a><span data-ttu-id="1d495-155">Limpiar registros de bases de datos</span><span class="sxs-lookup"><span data-stu-id="1d495-155">Clean up database logs</span></span>

<span data-ttu-id="1d495-156">Puede eliminar todo o parte de los registros de la base de datos, utilizando las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="1d495-156">You can delete all or part of the database logs, using the following options:</span></span>

- <span data-ttu-id="1d495-157">Seleccione todos los registros para una tabla en particular.</span><span class="sxs-lookup"><span data-stu-id="1d495-157">Select all logs for a particular table.</span></span>
- <span data-ttu-id="1d495-158">Seleccione tipos específicos de registro de base de datos.</span><span class="sxs-lookup"><span data-stu-id="1d495-158">Select specific types of database log.</span></span>
- <span data-ttu-id="1d495-159">Seleccione una fecha y hora en que se creó un registro.</span><span class="sxs-lookup"><span data-stu-id="1d495-159">Select a date and time that a log was created.</span></span>

<span data-ttu-id="1d495-160">Siga estos pasos para configurar la limpieza del registro de bases de datos:</span><span class="sxs-lookup"><span data-stu-id="1d495-160">To set up database log cleanup, follow these steps:</span></span> 

1. <span data-ttu-id="1d495-161">Vaya a **Administración del sistema > Enlaces > Base de datos > Registro de bases de datos**.</span><span class="sxs-lookup"><span data-stu-id="1d495-161">Go to **System administration > Links > Database > Database log**.</span></span> <span data-ttu-id="1d495-162">Seleccione **Limpiar registro**.</span><span class="sxs-lookup"><span data-stu-id="1d495-162">Select **Clean up log**.</span></span>

2. <span data-ttu-id="1d495-163">Elija un método de selección de registros para eliminar especificando una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="1d495-163">Choose a method of selecting logs to delete by entering one of the following options:</span></span>

   - <span data-ttu-id="1d495-164">ID de tabla</span><span class="sxs-lookup"><span data-stu-id="1d495-164">Table ID</span></span>
   - <span data-ttu-id="1d495-165">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="1d495-165">Type of log</span></span>
   - <span data-ttu-id="1d495-166">Fecha y hora de creación</span><span class="sxs-lookup"><span data-stu-id="1d495-166">Created date and time</span></span>

3. <span data-ttu-id="1d495-167">Utilice la pestaña **Limpieza de registro de bases de datos** para determinar cuándo ejecutar la tarea de limpieza del registro.</span><span class="sxs-lookup"><span data-stu-id="1d495-167">Use the **Database log cleanup** tab to determine when to run the log cleanup task.</span></span> <span data-ttu-id="1d495-168">De forma predeterminada, los registros de la base de datos están disponibles durante 30 días.</span><span class="sxs-lookup"><span data-stu-id="1d495-168">By default, database logs are available for 30 days.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
