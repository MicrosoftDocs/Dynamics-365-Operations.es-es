---
title: Configurar tarjeta de trabajo para dispositivos
description: Este tema describe las diversas opciones para configurar el dispositivo de tarjeta de trabajo.
author: johanhoffmann
manager: tfehr
ms.date: 05/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistrationSetupTouch
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: fc698ac7e0cfc8d6b196abf35658688ad1bc8bc7
ms.sourcegitcommit: 6319a07ee6c36ebb28acaf205bc79d2fd8f7dd5d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2020
ms.locfileid: "3413179"
---
# <a name="configure-job-card-for-devices"></a><span data-ttu-id="f16b5-103">Configurar tarjeta de trabajo para dispositivos</span><span class="sxs-lookup"><span data-stu-id="f16b5-103">Configure job card for devices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f16b5-104">El dispositivo de tarjeta de trabajo se usa para que los trabajadores de la tienda registren su trabajo diario, como cuando se inician los trabajos, informando de comentarios sobre los trabajos, registrando actividades indirectas e informando de ausencias.</span><span class="sxs-lookup"><span data-stu-id="f16b5-104">The job card device is used by the shop floor workers to register their daily work, such as when jobs are started, reporting feedback on jobs, registering indirect activities, and reporting absence.</span></span> <span data-ttu-id="f16b5-105">Estos registros son la base para seguir el progreso y el coste de las órdenes de producción y para calcular la base del pago de los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="f16b5-105">These registrations are the basis for tracking progress and cost on production orders and for calculating the basis for the workers' pay.</span></span> <span data-ttu-id="f16b5-106">Este tema describe las diversas opciones para configurar los dispositivos de tarjeta de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f16b5-106">This topic describes the various options for configuring job card devices.</span></span>

## <a name="enable-new-features-in-feature-management"></a><span data-ttu-id="f16b5-107">Habilitar nuevas características en la administración de características</span><span class="sxs-lookup"><span data-stu-id="f16b5-107">Enable new features in feature management</span></span>

<span data-ttu-id="f16b5-108">Algunas de las configuraciones descritas en este tema deben estar habilitadas en su sistema para poder estar disponibles para usted.</span><span class="sxs-lookup"><span data-stu-id="f16b5-108">A few of the settings described in this topic must be enabled on your system before they will be available to you.</span></span> <span data-ttu-id="f16b5-109">Utilice la página de [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para habilitar cualquiera o todas las siguientes características, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f16b5-109">Use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) page to enable any or all of the following features as required.</span></span>

### <a name="generate-license-plate"></a><span data-ttu-id="f16b5-110">Generar matrícula de entidad de almacén</span><span class="sxs-lookup"><span data-stu-id="f16b5-110">Generate license plate</span></span>

<span data-ttu-id="f16b5-111">Para que esta característica esté disponible, habilite las siguientes características en [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (en orden):</span><span class="sxs-lookup"><span data-stu-id="f16b5-111">To make this feature available, enable the following features in [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (in order):</span></span>

1. <span data-ttu-id="f16b5-112">Matrícula de entidad de almacén para notificaciones agregada al dispositivo de tarjetas de trabajo</span><span class="sxs-lookup"><span data-stu-id="f16b5-112">License plate for reporting as finished added to the Job Card Device</span></span>
1. <span data-ttu-id="f16b5-113">Habilitar la generación automática de matrícula de entidad de almacén al informar como terminado en el dispositivo de tarjetas de trabajo</span><span class="sxs-lookup"><span data-stu-id="f16b5-113">Enable automatic generation of license plate number when reporting as finished in the job card device</span></span>

### <a name="print-label"></a><span data-ttu-id="f16b5-114">Imprimir etiqueta</span><span class="sxs-lookup"><span data-stu-id="f16b5-114">Print label</span></span>

<span data-ttu-id="f16b5-115">Para que esta característica esté disponible, habilite las siguientes características en [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (en orden):</span><span class="sxs-lookup"><span data-stu-id="f16b5-115">To make this feature available, enable the following features in [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (in order):</span></span>

1. <span data-ttu-id="f16b5-116">Matrícula de entidad de almacén para notificaciones agregada al dispositivo de tarjetas de trabajo</span><span class="sxs-lookup"><span data-stu-id="f16b5-116">License plate for reporting as finished added to the Job Card Device</span></span>
1. <span data-ttu-id="f16b5-117">Imprimir etiqueta desde dispositivo de tarjeta de trabajo</span><span class="sxs-lookup"><span data-stu-id="f16b5-117">Print label from Job Card Device</span></span>

### <a name="allow-locking-of-touch-screen"></a><span data-ttu-id="f16b5-118">Permitir el bloqueo de la pantalla táctil</span><span class="sxs-lookup"><span data-stu-id="f16b5-118">Allow locking of touch screen</span></span>

<span data-ttu-id="f16b5-119">Para que esta característica esté disponible, habilite la siguiente característica en la [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):</span><span class="sxs-lookup"><span data-stu-id="f16b5-119">To make this feature available, enable the following feature in [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):</span></span>

- <span data-ttu-id="f16b5-120">(Vista previa) Función para bloquear un dispositivo de tarjeta de trabajo y un terminal de tarjetas de trabajo para que se puedan desinfectar</span><span class="sxs-lookup"><span data-stu-id="f16b5-120">(Preview) Feature for locking job card device and job card terminal so that they can be sanitized</span></span>

## <a name="manage-your-device-configurations"></a><span data-ttu-id="f16b5-121">Administrar las configuraciones del dispositivo</span><span class="sxs-lookup"><span data-stu-id="f16b5-121">Manage your device configurations</span></span>

<span data-ttu-id="f16b5-122">Para establecer las configuraciones del dispositivo, vaya a **Control de producción > Configuración > Ejecución de fabricación > Configurar tarjeta de trabajo para dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="f16b5-122">To set up your device configurations, go to **Production control > Setup > Manufacturing execution > Configure job card for devices**.</span></span> <span data-ttu-id="f16b5-123">La página **Configurar la tarjeta de trabajo para dispositivos** se abre, mostrando una lista de configuraciones existentes.</span><span class="sxs-lookup"><span data-stu-id="f16b5-123">The **Configure job card for devices** page opens, which shows a list of existing configurations.</span></span> <span data-ttu-id="f16b5-124">A partir de aquí, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f16b5-124">From here, you can do the following:</span></span> 

- <span data-ttu-id="f16b5-125">Seleccione cualquier configuración de dispositivo enumerada en la columna izquierda para verla y editarla.</span><span class="sxs-lookup"><span data-stu-id="f16b5-125">Select any device configuration listed in the left column to view and edit it.</span></span>
- <span data-ttu-id="f16b5-126">Seleccione **Nuevo** en el panel Acciones para agregar una nueva configuración de dispositivo a la lista.</span><span class="sxs-lookup"><span data-stu-id="f16b5-126">Select **New** on the Action Pane to add a new device configuration to the list.</span></span> <span data-ttu-id="f16b5-127">Luego escriba un nombre en el campo **Configuración** para identificar la nueva configuración.</span><span class="sxs-lookup"><span data-stu-id="f16b5-127">Then enter a name in the **Configuration** field to identify the new configuration.</span></span> <span data-ttu-id="f16b5-128">El valor que introduzca aquí debe ser único entre todas las configuraciones de dispositivos, y no podrá editarlo más tarde.</span><span class="sxs-lookup"><span data-stu-id="f16b5-128">The value you enter here must be unique among all device configurations, and you won't be able to edit it later.</span></span>

<span data-ttu-id="f16b5-129">Consulte las siguientes secciones para obtener detalles sobre cada una de las configuraciones para configurar dispositivos de tarjeta de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f16b5-129">Refer to following sections for details about each of the settings for configuring job card devices.</span></span>

## <a name="general-settings"></a><span data-ttu-id="f16b5-130">Configuración general</span><span class="sxs-lookup"><span data-stu-id="f16b5-130">General settings</span></span>

<span data-ttu-id="f16b5-131">La ficha desplegable **General** le permite configurar cada una de las diversas opciones disponibles para la configuración del dispositivo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f16b5-131">The **General** FastTab lets you configure each of the various options available for the selected device configuration.</span></span> <span data-ttu-id="f16b5-132">Los siguientes parámetros están disponibles:</span><span class="sxs-lookup"><span data-stu-id="f16b5-132">The following settings are available:</span></span>

- <span data-ttu-id="f16b5-133">**Informar de cantidad a la salida del trabajo**: establezca esto en **Sí** para solicitar a los trabajadores que den su opinión sobre los trabajos en curso al salir del trabajo. Cuando se establece en **No**, los trabajadores no serán avisados.</span><span class="sxs-lookup"><span data-stu-id="f16b5-133">**Report quantity at clock-out** - Set this to **Yes** to prompt workers to report feedback on jobs in progress when clocking out. When set to **No**, workers won't not be prompted.</span></span>
- <span data-ttu-id="f16b5-134">**bloquear empleado**: cuando esta opción está establecida en **No**, cada trabajador cerrará sesión inmediatamente después de registrarse (como un nuevo trabajo) y luego el dispositivo volverá a la página de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="f16b5-134">**Lock employee** -  When this option is set to **No**, each worker will be logged out immediately after they make a registration (such as a new job), and then the device will return to the log-in page.</span></span> <span data-ttu-id="f16b5-135">Cuando esta opción se establece en **Sí**, cada trabajador permanecerá conectado al dispositivo de la tarjeta de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f16b5-135">When this option is set to **Yes**, each worker will stay logged in to the job card device.</span></span> <span data-ttu-id="f16b5-136">Sin embargo, el trabajador aún podrá cerrar sesión manualmente para permitir que otro trabajador inicie sesión mientras el dispositivo de la tarjeta de trabajo sigue ejecutándose con la misma cuenta de usuario del sistema.</span><span class="sxs-lookup"><span data-stu-id="f16b5-136">However, the worker will still be able to log out manually to allow another worker to log in while the job card device remains running under the same system user account.</span></span> <span data-ttu-id="f16b5-137">Para obtener más información sobre estos tipos de cuentas, consulte [Usuarios asignados](#assigned-users).</span><span class="sxs-lookup"><span data-stu-id="f16b5-137">For more information about these types of accounts, see [Assigned users](#assigned-users).</span></span>
- <span data-ttu-id="f16b5-138">**Escáner de código de barras**: establezca esto en **Sí** para proporcionar una opción en el dispositivo de la tarjeta de trabajo que permite a los trabajadores registrar el inicio de un nuevo trabajo escaneando un código de barras.</span><span class="sxs-lookup"><span data-stu-id="f16b5-138">**Barcode scanner** - Set this to **Yes** to provide an option on the job card device that allows workers register the start of a new job by scanning a bar code.</span></span>
- <span data-ttu-id="f16b5-139">**Usear el tiempo real de registro**: establezca esto en **Sí** para establecer que el tiempo para que cada nuevo registro sea igual al tiempo exacto en que un trabajador envió el registro.</span><span class="sxs-lookup"><span data-stu-id="f16b5-139">**Use the actual time of registration** - Set this to **Yes** to set the time for each new registration to be equal to the exact time that registration was submitted by a worker.</span></span> <span data-ttu-id="f16b5-140">Establézcalo en **No** para utilizar el tiempo de inicio de sesión en su lugar.</span><span class="sxs-lookup"><span data-stu-id="f16b5-140">Set to **No** to use the log-in time instead.</span></span> <span data-ttu-id="f16b5-141">Por lo general, querrá configurar esto en **Sí**, caso de que haya habilitado las opciones **Bloquear empleado** y/o **Trabajador único**, donde los trabajadores a menudo permanecen con sesión iniciada durante períodos más largos.</span><span class="sxs-lookup"><span data-stu-id="f16b5-141">You'll usually want to set this to **Yes** if you have enabled the **Lock employee** and/or **Single worker** options, where workers often remain logged in for longer periods.</span></span>
- <span data-ttu-id="f16b5-142">**Trabajador único**: establezca esta opción en **Sí** si solo un trabajador usa cada dispositivo de tarjeta de trabajo en el que esta configuración está activa.</span><span class="sxs-lookup"><span data-stu-id="f16b5-142">**Single worker** - Set this option to **Yes** if only one worker uses each job card device where this configuration is active.</span></span> <span data-ttu-id="f16b5-143">Cuando se selecciona esta opción, la opción **Bloquear empleado** se configura automáticamente en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="f16b5-143">When this option is selected, the **Lock employee** option is automatically set to **Yes**.</span></span> <span data-ttu-id="f16b5-144">Además, esta opción elimina el requisito (y la capacidad) de que el trabajador inicie sesión con un identificador de distintivo (o similar).</span><span class="sxs-lookup"><span data-stu-id="f16b5-144">In addition, this option removes the requirement (and ability) for the worker to log in using a badge ID (or similar).</span></span> <span data-ttu-id="f16b5-145">En cambio, el trabajador inicia sesión en Supply Chain Management utilizando una cuenta de usuario del sistema vinculada a un *trabajador con tiempo registrado* (desde la tabla *trabajadores*) y se conecta al dispositivo de la tarjeta de trabajo como ese trabajador al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="f16b5-145">Instead the worker signs in to Supply Chain Management using a system user account linked to a *time registered worker* (from the *workers* table) and gets logged in to the job card device as that worker at the same time.</span></span>  <span data-ttu-id="f16b5-146">Para obtener más información sobre estos tipos de cuentas, consulte [Usuarios asignados](#assigned-users).</span><span class="sxs-lookup"><span data-stu-id="f16b5-146">For more information about these types of accounts, see [Assigned users](#assigned-users).</span></span>
- <span data-ttu-id="f16b5-147">**Permitir a los trabajadores establecer filtros personales**: establezca esta opción en **Sí** para permitir que los trabajadores filtren los trabajos que se les muestran en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f16b5-147">**Allow workers to set personal filters** - Set this option to **Yes** to allow workers to filter the jobs shown to them on the device.</span></span> <span data-ttu-id="f16b5-148">El trabajador puede modificar valores para cualquiera de los tres criterios de filtro: **Unidad de producción**, **Grupo de recursos** y **Recurso**.</span><span class="sxs-lookup"><span data-stu-id="f16b5-148">The worker can modify values for any of the three filter criteria: **Production unit**, **Resource group** and **Resource**.</span></span> <span data-ttu-id="f16b5-149">Solo se mostrarán en el dispositivo los trabajos programados en recursos que coincidan con los criterios de filtro seleccionados.</span><span class="sxs-lookup"><span data-stu-id="f16b5-149">Only jobs that are scheduled on resources matching the selected filter criteria will be shown on the device.</span></span> <span data-ttu-id="f16b5-150">También puede asignar valores predeterminados para cualquiera o todos estos criterios, y estos se aplicarán incluso con esta opción no seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f16b5-150">You can also assign default values for any or all of these criteria, and those will apply even with this option is not selected.</span></span>
- <span data-ttu-id="f16b5-151">**Permitir bloquear la pantalla táctil**: establezca esta opción en **Sí** para permitir que los trabajadores bloqueen la pantalla táctil del dispositivo de la tarjeta de trabajo para que puedan desinfectarla.</span><span class="sxs-lookup"><span data-stu-id="f16b5-151">**Allow locking the touchscreen** - Set this option to **Yes** to allow workers to lock the job card device touchscreen so they can sanitize it.</span></span> <span data-ttu-id="f16b5-152">Cuando está habilitado, se añade un botón **Bloqueo de pantalla para desinfectar** a la página de inicio de sesión del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f16b5-152">When enabled, a **Lock screen for sanitizing** button is added to the device log-in page.</span></span> <span data-ttu-id="f16b5-153">Cuando un trabajador selecciona este botón, la pantalla táctil se bloquea temporalmente para evitar entradas no deseadas y se muestra un temporizador de cuenta descendente.</span><span class="sxs-lookup"><span data-stu-id="f16b5-153">When a worker selects this button, the touchscreen temporarily locks to prevent unintended input and a countdown timer is shown.</span></span> <span data-ttu-id="f16b5-154">El trabajador ahora puede limpiar de forma segura el dispositivo y la pantalla.</span><span class="sxs-lookup"><span data-stu-id="f16b5-154">The worker can now safely clean the device and the screen.</span></span> <span data-ttu-id="f16b5-155">Cuando finaliza la cuenta descendente, la pantalla táctil se desbloquea automáticamente de nuevo.</span><span class="sxs-lookup"><span data-stu-id="f16b5-155">When the countdown completes, the touchscreen automatically unlocks again.</span></span>
- <span data-ttu-id="f16b5-156">**Duración del bloqueo de pantalla**: cuando la opción**Permitir bloqueo de pantalla táctil** está habilitada, use esta opción para especificar la cantidad de segundos que la pantalla táctil debe estar bloqueada para desinfectar.</span><span class="sxs-lookup"><span data-stu-id="f16b5-156">**Screen lock duration** - When the **Allow locking touchscreen** option is enabled, use this option so specify number of seconds the touchscreen should be locked for sanitizing.</span></span> <span data-ttu-id="f16b5-157">La duración debe estar entre 5 y 120 segundos.</span><span class="sxs-lookup"><span data-stu-id="f16b5-157">The duration must be between 5 and 120 seconds.</span></span>
- <span data-ttu-id="f16b5-158">**Unidad de producción**: seleccione una unidad de producción para aplicar como criterio de filtro predeterminado para la lista de trabajos que se muestra a cada trabajador.</span><span class="sxs-lookup"><span data-stu-id="f16b5-158">**Production unit** - Select a production unit to be applied as a default filter criterion for the list of jobs shown to each worker.</span></span> <span data-ttu-id="f16b5-159">El dispositivo solo mostrará inicialmente los trabajos programados en los recursos agrupados en la unidad de producción seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f16b5-159">Only jobs that are scheduled on resources grouped under the selected production unit will initially be displayed by the device.</span></span> <span data-ttu-id="f16b5-160">Si **Permitir a los trabajadores establecer filtros personales** está habilitado, los trabajadores podrán editar este valor; de lo contrario, este filtro siempre se aplicará cuando la configuración de este dispositivo esté activa.</span><span class="sxs-lookup"><span data-stu-id="f16b5-160">If **Allow workers to set personal filters** is enabled, workers will be able to edit this value, otherwise this filter will always apply when this device configuration is active.</span></span>
- <span data-ttu-id="f16b5-161">**Grupo de recursos**: seleccione un grupo de recursos a aplicar como criterio de filtro predeterminado para la lista de trabajos que se muestra a cada trabajador.</span><span class="sxs-lookup"><span data-stu-id="f16b5-161">**Resource group** - Select a resource group to be applied as a default filter criterion for the list of jobs shown to each worker.</span></span> <span data-ttu-id="f16b5-162">El dispositivo solo mostrará inicialmente en el dispositivo los trabajos programados en el grupo de recursos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f16b5-162">Only jobs that are scheduled on resources grouped under the selected resource group will initially be displayed by the device.</span></span> <span data-ttu-id="f16b5-163">Si **Permitir a los trabajadores establecer filtros personales** está habilitado, los trabajadores podrán editar este valor; de lo contrario, este filtro siempre se aplicará cuando la configuración de este dispositivo esté activa.</span><span class="sxs-lookup"><span data-stu-id="f16b5-163">If **Allow workers to set personal filters** is enabled, workers will be able to edit this value, otherwise this filter will always apply when this device configuration is active.</span></span>
- <span data-ttu-id="f16b5-164">**Recurso**: seleccione un recurso a aplicar como criterio de filtro predeterminado para la lista de trabajos que se muestra a cada trabajador.</span><span class="sxs-lookup"><span data-stu-id="f16b5-164">**Resource** - Select a resource to be applied as a default filter criterion for the list of jobs shown to each worker.</span></span> <span data-ttu-id="f16b5-165">El dispositivo solo mostrará inicialmente los trabajos programados en el recurso seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f16b5-165">Only jobs that are scheduled on the selected resource will initially be displayed by the device.</span></span> <span data-ttu-id="f16b5-166">Si **Permitir a los trabajadores establecer filtros personales** está habilitado, los trabajadores podrán editar este valor; de lo contrario, este filtro siempre se aplicará cuando la configuración de este dispositivo esté activa.</span><span class="sxs-lookup"><span data-stu-id="f16b5-166">If **Allow workers to set personal filters** is enabled, workers will be able to edit this value, otherwise this filter will always apply when this device configuration is active.</span></span>
- <span data-ttu-id="f16b5-167">**Generar matrícula**: establezca esta opción en **Sí** para generar una nueva matrícula cada vez que un trabajador usa el dispositivo de la tarjeta de trabajo para informar como terminado.</span><span class="sxs-lookup"><span data-stu-id="f16b5-167">**Generate license plate** - Set this option to **Yes** to generate a new license plate each time a worker uses the job card device to report as finished.</span></span> <span data-ttu-id="f16b5-168">El número de matrícula de entidad de almacén se genera a partir de una secuencia numérica configurada en la página **Parámetros de gestión de almacén**.</span><span class="sxs-lookup"><span data-stu-id="f16b5-168">The license plate number is generated from a number sequence set up on the **Warehouse management parameters** page.</span></span> <span data-ttu-id="f16b5-169">Cuando se establece en **No**, los trabajadores deben especificar una matrícula existente al informar de la terminación.</span><span class="sxs-lookup"><span data-stu-id="f16b5-169">When set to **No**, workers must specify an existing license plate when reporting as finished.</span></span>
- <span data-ttu-id="f16b5-170">**Etiqueta de impresión**: establezca esta opción en **Sí** para imprimir una etiqueta de matrícula cuando un trabajador usa el dispositivo de la tarjeta de trabajo para informar de terminación.</span><span class="sxs-lookup"><span data-stu-id="f16b5-170">**Print label** - Set this option to **Yes** to print a license plate label when a worker uses the job card device to report as finished.</span></span> <span data-ttu-id="f16b5-171">La configuración de la etiqueta se configura en la ruta del documento, como se describe en [Diseño de ruta de documento para etiqueta de matrícula](../warehousing/document-routing-layout-for-license-plates.md).</span><span class="sxs-lookup"><span data-stu-id="f16b5-171">The configuration of the label is set up in document routing, as described in [Document routing layout for license plate labels](../warehousing/document-routing-layout-for-license-plates.md).</span></span>

<a name="assigned-users"></a>

## <a name="assigned-users"></a><span data-ttu-id="f16b5-172">Usuarios asignados</span><span class="sxs-lookup"><span data-stu-id="f16b5-172">Assigned users</span></span>

<span data-ttu-id="f16b5-173">Utilice la ficha desplegable **Usuarios asignados** para asociar uno o más usuarios del sistema con la configuración actual del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f16b5-173">Use the **Assigned users** FastTab to associate one or more system users with the current device configuration.</span></span> <span data-ttu-id="f16b5-174">A cada usuario del sistema solo se le puede asignar una configuración de dispositivo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f16b5-174">Each system user can only be assigned one job device configuration.</span></span>

<span data-ttu-id="f16b5-175">Al configurar un dispositivo, un trabajador de TI generalmente inicia sesión en Supply Chain Management utilizando una cuenta de usuario del sistema.</span><span class="sxs-lookup"><span data-stu-id="f16b5-175">When setting up a device, an IT worker typically signs in to Supply Chain Management using a system user account.</span></span> <span data-ttu-id="f16b5-176">A partir de entonces, la configuración del dispositivo de trabajo asociada con ese usuario del sistema se aplica mientras el usuario del sistema permanezca conectado.</span><span class="sxs-lookup"><span data-stu-id="f16b5-176">Thereafter, the job device configuration associated with that system user applies for as long as that system user remains signed in.</span></span> <span data-ttu-id="f16b5-177">Estas cuentas de usuario del sistema generalmente están limitadas para permitir el acceso solo a la página del dispositivo de la tarjeta de trabajo y a ninguna otra parte de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f16b5-177">These system user accounts are typically limited to allow access only to the job card device page and no other part of Supply Chain Management.</span></span>

<span data-ttu-id="f16b5-178">Después de que el usuario del sistema haya iniciado sesión y se haya cargado la configuración del dispositivo de trabajo, los trabajadores pueden iniciar sesión en el dispositivo de la tarjeta de trabajo utilizando su cuenta de *trabajador de tiempo registrado* (por ejemplo, escaneando un código de barras en su credencial) para que puedan comenzar nuevos trabajos y realizar otros tipos de registros.</span><span class="sxs-lookup"><span data-stu-id="f16b5-178">After the system user is signed in and the job device configuration is loaded, workers can then log in to the job card device using their *time registered worker* account (for example, by scanning a bar code on their badge) so they can start new jobs and make other kinds of registrations.</span></span> <span data-ttu-id="f16b5-179">Varios trabajadores pueden iniciar y cerrar sesión durante el día, mientras que la misma configuración de dispositivo permanece vigente en esa máquina porque el usuario del sistema permanece con sesión iniciada en Supply Chain Management durante el día.</span><span class="sxs-lookup"><span data-stu-id="f16b5-179">Various workers can log in and out during the day, while the same device configuration remains in effect on that machine because the system user remains signed in to Supply Chain Management for the day.</span></span>

<span data-ttu-id="f16b5-180">Sin embargo, como se mencionó anteriormente, cuando utiliza una configuración de dispositivo con la opción **Trabajador único**, los propios trabajadores suelen iniciar sesión en Supply Chain Management utilizando un usuario del sistema vinculado a su propia cuenta *trabajador de tiempo registrado*, por lo que cargan la configuración del dispositivo e inician sesión como trabajador en el dispositivo de la tarjeta de trabajo al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="f16b5-180">However, as mentioned previously, when you use a device configuration with the **Single worker** option, workers themselves typically sign in to Supply Chain Management using a system user linked to their own *time registered worker* account, so they load the device configuration and log in as a worker on the job card device at the same time.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f16b5-181">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f16b5-181">Additional resources</span></span>

[<span data-ttu-id="f16b5-182">Informar de terminación desde el dispositivo de tarjeta de trabajo</span><span class="sxs-lookup"><span data-stu-id="f16b5-182">Report as finished from the job card device</span></span>](report-finished-job-device.md)