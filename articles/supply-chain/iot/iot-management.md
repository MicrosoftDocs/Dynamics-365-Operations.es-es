---
title: Supervisar y administrar Inteligencia IoT
description: Este tema explica cómo supervisar y administrar Inteligencia IoT.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 15021281b9ec33cd0552bca16e3054d0d3cdd589
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437104"
---
# <a name="monitor-and-manage-iot-intelligence"></a><span data-ttu-id="d48b9-103">Supervisar y administrar Inteligencia IoT</span><span class="sxs-lookup"><span data-stu-id="d48b9-103">Monitor and manage IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d48b9-104">Este tema explica cómo supervisar y administrar Inteligencia IoT.</span><span class="sxs-lookup"><span data-stu-id="d48b9-104">This topic explains how to monitor and manage IoT Intelligence.</span></span>

## <a name="monitor-scenarios-in-microsoft-dynamics-365-supply-chain-management"></a><a id="monitor-scenarios"></a><span data-ttu-id="d48b9-105">Supervisar escenarios en Microsoft Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="d48b9-105">Monitor scenarios in Microsoft Dynamics 365 Supply Chain Management</span></span>

<span data-ttu-id="d48b9-106">Puede monitorear el procesamiento de Inteligencia IoT desde varios lugares:</span><span class="sxs-lookup"><span data-stu-id="d48b9-106">You can monitor IoT Intelligence processing from several places:</span></span>

+ <span data-ttu-id="d48b9-107">**Módulos \> Control de producción \> Consultas e informes \> Inteligencia IoT \> Notificaciones**: mire la lista de notificaciones no resueltas.</span><span class="sxs-lookup"><span data-stu-id="d48b9-107">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Notifications** – View the list of unresolved notifications.</span></span>
+ <span data-ttu-id="d48b9-108">**Módulos \> Control de producción \> Consultas e informes \> Inteligencia IoT \> Notificaciones cerradas**: mire la lista de notificaciones que se han resuelto o desestimado.</span><span class="sxs-lookup"><span data-stu-id="d48b9-108">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Closed notifications** – View the list of notifications that have been resolved or dismissed.</span></span>
+ <span data-ttu-id="d48b9-109">**Módulos \> Control de producción \> Consultas e informes \> Inteligencia IoT \> Claves métricas**: mire las claves métricas para los gráficos de series temporales **Estado del recurso**.</span><span class="sxs-lookup"><span data-stu-id="d48b9-109">**Modules \> Production control \> Inquiries and reports \> IoT Intelligence \> Metric keys** – View the metric keys for the **Resource Status** times series charts.</span></span>
+ <span data-ttu-id="d48b9-110">**Módulos \> Control de producción \> Ejecución de fabricación \> Estado del recurso**: siga métricas específicas mediante el cuadro de diálogo **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="d48b9-110">**Modules \> Production control \> Manufacturing execution \> Resource status** – Track specific metrics by using the **Configure** dialog box.</span></span> <span data-ttu-id="d48b9-111">Si un escenario detecta una excepción, una notificación muestra los detalles de la excepción.</span><span class="sxs-lookup"><span data-stu-id="d48b9-111">If a scenario detects an exception, a notification shows the details of the exception.</span></span>
+ <span data-ttu-id="d48b9-112">**Espacios de trabajo \> Gestión de planta de producción \> Notificaciones**: mire la lista de notificaciones no resueltas.</span><span class="sxs-lookup"><span data-stu-id="d48b9-112">**Workspaces \> Production floor management \> Notifications** – View the list of unresolved notifications.</span></span>

## <a name="modify-a-running-iot-intelligence-scenario"></a><span data-ttu-id="d48b9-113">Modificar un escenario de Inteligencia IoT en ejecución</span><span class="sxs-lookup"><span data-stu-id="d48b9-113">Modify a running IoT Intelligence scenario</span></span>

<span data-ttu-id="d48b9-114">Cuando se ejecuta un escenario, puede realizar estos cambios:</span><span class="sxs-lookup"><span data-stu-id="d48b9-114">When a scenario is running, you can make these changes:</span></span>

+ <span data-ttu-id="d48b9-115">Agregue nuevas definiciones de esquema de sensor.</span><span class="sxs-lookup"><span data-stu-id="d48b9-115">Add new sensor schema definitions.</span></span>
+ <span data-ttu-id="d48b9-116">Seleccione nuevos valores de datos de señal.</span><span class="sxs-lookup"><span data-stu-id="d48b9-116">Select new signal data values.</span></span>
+ <span data-ttu-id="d48b9-117">Cancele la selección de valores de datos de señal existentes.</span><span class="sxs-lookup"><span data-stu-id="d48b9-117">Cancel the selection of existing signal data values.</span></span>
+ <span data-ttu-id="d48b9-118">Agregue y asigne nuevos valores de datos de señal.</span><span class="sxs-lookup"><span data-stu-id="d48b9-118">Add and map new signal data values.</span></span>
+ <span data-ttu-id="d48b9-119">Actualice valores de umbral.</span><span class="sxs-lookup"><span data-stu-id="d48b9-119">Update threshold values.</span></span>

<span data-ttu-id="d48b9-120">Cuando se ejecuta un escenario, están prohibidos estos cambios:</span><span class="sxs-lookup"><span data-stu-id="d48b9-120">When a scenario is running, these changes are prohibited:</span></span>

+ <span data-ttu-id="d48b9-121">Elimine o modifique cualquier definición de esquema que esté consumiendo actualmente un escenario habilitado.</span><span class="sxs-lookup"><span data-stu-id="d48b9-121">Delete or modify any schema definitions that are currently consumed by an enabled scenario.</span></span>
+ <span data-ttu-id="d48b9-122">Cambiar las rutas de esquema seleccionadas del escenario habilitado.</span><span class="sxs-lookup"><span data-stu-id="d48b9-122">Change the enabled scenario's selected schema paths.</span></span>

## <a name="simulation-options"></a><span data-ttu-id="d48b9-123">Opciones de simulación</span><span class="sxs-lookup"><span data-stu-id="d48b9-123">Simulation options</span></span>

<span data-ttu-id="d48b9-124">Puede simular señales de máquina de fábrica.</span><span class="sxs-lookup"><span data-stu-id="d48b9-124">You can simulate factory machine signals.</span></span> <span data-ttu-id="d48b9-125">Para obtener más información, consulte estos temas:</span><span class="sxs-lookup"><span data-stu-id="d48b9-125">For more information, see these topics:</span></span>

+ [<span data-ttu-id="d48b9-126">Conecte IoT DevKit AZ3166 a Azure IoT Hub</span><span class="sxs-lookup"><span data-stu-id="d48b9-126">Connect IoT DevKit AZ3166 to Azure IoT Hub</span></span>](https://docs.microsoft.com/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [<span data-ttu-id="d48b9-127">Conecte el simulador en línea Raspberry Pi a Azure IoT Hub (Node.js)</span><span class="sxs-lookup"><span data-stu-id="d48b9-127">Connect Raspberry Pi online simulator to Azure IoT Hub (Node.js)</span></span>](https://docs.microsoft.com/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [<span data-ttu-id="d48b9-128">Descripción general del acelerador de solución de simulación de dispositivo</span><span class="sxs-lookup"><span data-stu-id="d48b9-128">Device Simulation solution accelerator overview</span></span>](https://docs.microsoft.com/azure/iot-accelerators/iot-accelerators-device-simulation-overview)
