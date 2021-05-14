---
title: Habilitar la gestión de la calidad y las disconformidades
description: Este tema proporciona una descripción general del proceso para instalar y configurar características de administración de calidad y disconformidad en Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome, InventParameters, InventProblemType, InventProblemTypeSetup, InventQuarantineZone, InventTestDiagnosticType, InventTestReportSetup, SysUserManagement, InventTestRelatedOperations
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 67d5da648e31d07d054246f5d308a6c6cdeb506c
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956263"
---
# <a name="enable-quality-and-nonconformance-management"></a><span data-ttu-id="c9efb-103">Habilitar la gestión de la calidad y las disconformidades</span><span class="sxs-lookup"><span data-stu-id="c9efb-103">Enable quality and nonconformance management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c9efb-104">Este tema proporciona una descripción general del proceso para instalar y configurar características de administración de calidad y disconformidad en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c9efb-104">This topic provides an overview of the process for setting up and configuring quality and nonconformance management features in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="enable-quality-and-nonconformance-management"></a><a name="enable-qm"></a><span data-ttu-id="c9efb-105">Habilitar la gestión de la calidad y las disconformidades</span><span class="sxs-lookup"><span data-stu-id="c9efb-105">Enable quality and nonconformance management</span></span>

<span data-ttu-id="c9efb-106">Siga estos pasos para habilitar la gestión de calidad en su sistema.</span><span class="sxs-lookup"><span data-stu-id="c9efb-106">Follow these steps to enable quality management on your system.</span></span>

1. <span data-ttu-id="c9efb-107">Vaya a **Gestión del inventario \> Configuración \> Parámetros de la gestión de inventario y almacenes**.</span><span class="sxs-lookup"><span data-stu-id="c9efb-107">Go to **Inventory management \> Setup \> Inventory and warehouse management parameters**.</span></span>
1. <span data-ttu-id="c9efb-108">En la pestaña **Gestión de calidad**, establezca la opción **Utilizar la gestión de la calidad** en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="c9efb-108">On the **Quality management** tab, set the **Use quality management** option to *Yes*.</span></span>
1. <span data-ttu-id="c9efb-109">Use el campo **Índice por hora** para especificar una tasa de mano de obra por hora en la divisa local.</span><span class="sxs-lookup"><span data-stu-id="c9efb-109">In the **Hourly rate** field, enter an hourly labor rate in the local currency.</span></span> <span data-ttu-id="c9efb-110">El índice por hora se usa para calcular los costes de operaciones relacionadas con un caso de disconformidad.</span><span class="sxs-lookup"><span data-stu-id="c9efb-110">The hourly rate is used to calculate costs for operations that are related to a nonconformance.</span></span> <span data-ttu-id="c9efb-111">El índice por hora y los costes calculados proporcionan información de referencia para un caso de disconformidad.</span><span class="sxs-lookup"><span data-stu-id="c9efb-111">The hourly rate and calculated costs provide reference information for a nonconformance.</span></span> <span data-ttu-id="c9efb-112">No interactúan con otra función.</span><span class="sxs-lookup"><span data-stu-id="c9efb-112">They don't interact with other functionality.</span></span>
1. <span data-ttu-id="c9efb-113">Seleccione **Configuración de informes**.</span><span class="sxs-lookup"><span data-stu-id="c9efb-113">Select **Report setup**.</span></span>
1. <span data-ttu-id="c9efb-114">Agregue nuevas líneas para los distintos tipos de informes y seleccione el tipo de documento que se utilizará para cada informe.</span><span class="sxs-lookup"><span data-stu-id="c9efb-114">Add new lines for the various report types, and select the type of document to use for each report.</span></span>
1. <span data-ttu-id="c9efb-115">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c9efb-115">Close the page.</span></span>
1. <span data-ttu-id="c9efb-116">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c9efb-116">Close the page.</span></span>

## <a name="quality-management-configuration-process"></a><span data-ttu-id="c9efb-117">Procesar la configuración de administración de calidad</span><span class="sxs-lookup"><span data-stu-id="c9efb-117">Quality management configuration process</span></span>

<span data-ttu-id="c9efb-118">Antes de que pueda comenzar a utilizar las funciones de gestión de calidad y generar pedidos de calidad, debe configurar el sistema y los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="c9efb-118">Before you can start to use the quality management features and generate quality orders, you must configure the system and prerequisites.</span></span> <span data-ttu-id="c9efb-119">A continuación, se muestra una lista de los pasos necesarios para configurar la gestión de calidad.</span><span class="sxs-lookup"><span data-stu-id="c9efb-119">Here is a list of the steps that are required to configure quality management.</span></span>

1. <span data-ttu-id="c9efb-120">[Habilitar la gestión de la calidad y las disconformidades](#enable-qm).</span><span class="sxs-lookup"><span data-stu-id="c9efb-120">[Enable quality and nonconformance management](#enable-qm).</span></span>
1. <span data-ttu-id="c9efb-121">Opcional: [Configurar instrumentos de prueba](quality-test-instruments.md).</span><span class="sxs-lookup"><span data-stu-id="c9efb-121">Optional: [Configure test instruments](quality-test-instruments.md).</span></span>
1. <span data-ttu-id="c9efb-122">[Configurar pruebas](quality-tests.md).</span><span class="sxs-lookup"><span data-stu-id="c9efb-122">[Configure tests](quality-tests.md).</span></span>
1. <span data-ttu-id="c9efb-123">[Configurar las variables de prueba y los resultados](quality-test-variables.md).</span><span class="sxs-lookup"><span data-stu-id="c9efb-123">[Configure test variables and outcomes](quality-test-variables.md).</span></span>
1. <span data-ttu-id="c9efb-124">[Configurar grupos de prueba](quality-test-groups.md).</span><span class="sxs-lookup"><span data-stu-id="c9efb-124">[Configure test groups](quality-test-groups.md).</span></span>
1. <span data-ttu-id="c9efb-125">Opcional: [Configurar grupos de calidad y vincular a productos](quality-groups.md).</span><span class="sxs-lookup"><span data-stu-id="c9efb-125">Optional: [Configure quality groups, and link to products](quality-groups.md).</span></span>
1. <span data-ttu-id="c9efb-126">Opcional: [Configurar asociaciones de calidad](quality-associations.md).</span><span class="sxs-lookup"><span data-stu-id="c9efb-126">Optional: [Configure quality associations](quality-associations.md).</span></span>

<span data-ttu-id="c9efb-127">Una vez completada la configuración, puede comenzar a crear y procesar pedidos de calidad.</span><span class="sxs-lookup"><span data-stu-id="c9efb-127">After the configuration is completed, you can start to create and process quality orders.</span></span> <span data-ttu-id="c9efb-128">Para obtener más información sobre cómo crear y trabajar con pedidos de calidad, vea [Pedidos de calidad](quality-orders.md).</span><span class="sxs-lookup"><span data-stu-id="c9efb-128">For more information about how to create and work with quality orders, see [Quality orders](quality-orders.md).</span></span>

## <a name="nonconformance-management-configuration-process"></a><span data-ttu-id="c9efb-129">Procesar la configuración de administración de disconformidades</span><span class="sxs-lookup"><span data-stu-id="c9efb-129">Nonconformance management configuration process</span></span>

<span data-ttu-id="c9efb-130">Antes de que pueda comenzar a utilizar las funciones de disonformidad y generar pedidos de disconfomidad, debe configurar el sistema y los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="c9efb-130">Before you can start to use the nonconformance management features and generate nonconformances, you must configure the system and prerequisites.</span></span> <span data-ttu-id="c9efb-131">A continuación, se muestra una lista de los pasos necesarios para configurar la gestión de disconformidades.</span><span class="sxs-lookup"><span data-stu-id="c9efb-131">Here is a list of the steps that are required to configure nonconformance management.</span></span>

1. <span data-ttu-id="c9efb-132">[Habilitar la gestión de la calidad y las disconformidades](#enable-qm).</span><span class="sxs-lookup"><span data-stu-id="c9efb-132">[Enable quality and nonconformance management](#enable-qm).</span></span>
1. <span data-ttu-id="c9efb-133">[Confiurar los trabajadores responsables de aprobar disconformidades](quality-responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="c9efb-133">[Configure workers who are responsible for approving nonconformances](quality-responsible-workers.md).</span></span>
1. <span data-ttu-id="c9efb-134">[Configurar tipos de problemas](quality-problem-types.md).</span><span class="sxs-lookup"><span data-stu-id="c9efb-134">[Configure problem types](quality-problem-types.md).</span></span>
1. <span data-ttu-id="c9efb-135">[Configurar zonas de cuarentena](quality-quarantine-zones.md).</span><span class="sxs-lookup"><span data-stu-id="c9efb-135">[Configure quarantine zones](quality-quarantine-zones.md).</span></span>
1. <span data-ttu-id="c9efb-136">[Configurar tipos de diagnóstico](quality-diagnostic-types.md).</span><span class="sxs-lookup"><span data-stu-id="c9efb-136">[Configure diagnostic types](quality-diagnostic-types.md).</span></span>
1. <span data-ttu-id="c9efb-137">[Configurar operaciones](quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="c9efb-137">[Configure operations](quality-operations.md).</span></span>
1. <span data-ttu-id="c9efb-138">Opcional: [Configurar cargos de calidad](quality-charges.md).</span><span class="sxs-lookup"><span data-stu-id="c9efb-138">Optional: [Configure quality charges](quality-charges.md).</span></span>

<span data-ttu-id="c9efb-139">Una vez completada la configuración, puede comenzar a crear y procesar disconformidades.</span><span class="sxs-lookup"><span data-stu-id="c9efb-139">After the configuration is completed, you can start to create and process nonconformances.</span></span> <span data-ttu-id="c9efb-140">Para obtener más información sobre cómo crear y trabajar con disconformidades, consulte [Crear y procesar disconformidades](tasks/create-process-non-conformance.md).</span><span class="sxs-lookup"><span data-stu-id="c9efb-140">For more information about how to create and work with nonconformances, see [Create and process nonconformances](tasks/create-process-non-conformance.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c9efb-141">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c9efb-141">Additional resources</span></span>

- [<span data-ttu-id="c9efb-142">Información general de la administración de la calidad</span><span class="sxs-lookup"><span data-stu-id="c9efb-142">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="c9efb-143">Habilitar la gestión de la calidad y las no conformidades</span><span class="sxs-lookup"><span data-stu-id="c9efb-143">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="c9efb-144">Administración de la calidad para procesos de almacén</span><span class="sxs-lookup"><span data-stu-id="c9efb-144">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
