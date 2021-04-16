---
title: Exportar datos de las filiales a archivos
description: Este tema explica cómo prepararse para exportar datos de Microsoft Dynamics 365 Finance y luego importarlos a una entidad jurídica consolidada.
author: jinniew
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2018-5-31
ms.dyn365.ops.version: 8.0.1
ms.openlocfilehash: bae0a28c59f327e47378eef6392d5e304bbde9a8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826187"
---
# <a name="export-subsidiary-data-to-files"></a><span data-ttu-id="b2f1a-103">Exportar datos de las filiales a archivos</span><span class="sxs-lookup"><span data-stu-id="b2f1a-103">Export subsidiary data to files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b2f1a-104">Use la página **Exportar** (**Administración del sistema \> Espacios de trabajo \> Import/Export**) para prepararse para exportar datos subsidiarios a archivos que luego se pueden importar a una entidad legal consolidada.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-104">You use the **Export** page (**System administration \> Workspaces \> Import/Export**) to prepare to export subsidiary data to files that can then be imported into a consolidated legal entity.</span></span> <span data-ttu-id="b2f1a-105">Para obtener más información sobre los procesos de importación y exportación, consulte [Resumen de tareas de importación y exportación de datos](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="b2f1a-105">For more information about the import and export processes, see [Data import and export jobs overview](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).</span></span>

1. <span data-ttu-id="b2f1a-106">Cree una entidad jurídica para el proceso de consolidación.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-106">Create a legal entity for the consolidation process.</span></span> <span data-ttu-id="b2f1a-107">Para obtener más información sobre cómo crear entidades jurídicas, consulte [Crear una entidad jurídica](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md).</span><span class="sxs-lookup"><span data-stu-id="b2f1a-107">For information about how to create legal entities, see [Create a legal entity](../../fin-ops-core/fin-ops/organization-administration/tasks/create-legal-entity.md).</span></span> <span data-ttu-id="b2f1a-108">Para obtener más información, consulte [Preparar una entidad jurídica para su uso en el proceso de consolidación](prepare-company-for-consolidation.md) y [Establecer una entidad jurídica filial para la consolidación](set-up-subsidiary-company-for-consolidation.md).</span><span class="sxs-lookup"><span data-stu-id="b2f1a-108">For more information, see [Prepare a legal entity for use in the consolidation process](prepare-company-for-consolidation.md) and [Set up a subsidiary legal entity for consolidation](set-up-subsidiary-company-for-consolidation.md).</span></span> 

2. <span data-ttu-id="b2f1a-109">Vaya a **Consolidaciones \> Saldos de empresas exportadoras**.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-109">Go to **Consolidations \> Export company balances**.</span></span> <span data-ttu-id="b2f1a-110">En la página **Saldos de empresas exportadoras**, en la pestaña **Criterios**, especifique los detalles de la consolidación, configurando los siguientes campos.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-110">On the **Export company balances** page, on the **Criteria** tab, specify the details of the consolidation by setting the following fields.</span></span>

    | <span data-ttu-id="b2f1a-111">Campo</span><span class="sxs-lookup"><span data-stu-id="b2f1a-111">Field</span></span>                             | <span data-ttu-id="b2f1a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2f1a-112">Description</span></span> |
    |-----------------------------------|-------|
    | <span data-ttu-id="b2f1a-113">Cuenta principal</span><span class="sxs-lookup"><span data-stu-id="b2f1a-113">Main account</span></span>                      | <span data-ttu-id="b2f1a-114">Especifique las cuentas a consolidar.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-114">Specify the accounts to consolidate.</span></span> <span data-ttu-id="b2f1a-115">Para incluir todas las cuentas, deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-115">To include all accounts, leave this field blank.</span></span> |
    | <span data-ttu-id="b2f1a-116">Usar cuenta de consolidación</span><span class="sxs-lookup"><span data-stu-id="b2f1a-116">Use consolidation account</span></span>         | <span data-ttu-id="b2f1a-117">Si ha especificado cuentas de consolidación, establezca esta opción en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-117">If you've specified consolidation accounts, set this option to **Yes**.</span></span> |
    | <span data-ttu-id="b2f1a-118">Seleccionar cuenta de consolidación de</span><span class="sxs-lookup"><span data-stu-id="b2f1a-118">Select consolidation account from</span></span> | <span data-ttu-id="b2f1a-119">Seleccione **Cuenta principal** o **Grupo de cuentas de consolidación**.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-119">Select either **Main account** or **Consolidation account group**.</span></span> |
    | <span data-ttu-id="b2f1a-120">Grupo de cuentas de consolidación</span><span class="sxs-lookup"><span data-stu-id="b2f1a-120">Consolidation account group</span></span>       | <span data-ttu-id="b2f1a-121">Seleccione un grupo de cuentas de consolidación para la cuenta de consolidación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-121">Select a consolidation account group for the consolidation account that you selected.</span></span> |
    | <span data-ttu-id="b2f1a-122">Período de consolidación</span><span class="sxs-lookup"><span data-stu-id="b2f1a-122">Consolidation period</span></span>              | <span data-ttu-id="b2f1a-123">Especifique las fechas "desde" y "hasta" para la consolidación.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-123">Specify "from" and "to" dates for the consolidation.</span></span> |
    | <span data-ttu-id="b2f1a-124">Incluir importes reales</span><span class="sxs-lookup"><span data-stu-id="b2f1a-124">Include actual amounts</span></span>            | <span data-ttu-id="b2f1a-125">Establezca esta opción en **Sí** para incluir las cantidades reales.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-125">Set this option to **Yes** to include actual amounts.</span></span> |
    | <span data-ttu-id="b2f1a-126">Incluir importes de presupuesto</span><span class="sxs-lookup"><span data-stu-id="b2f1a-126">Include budget amounts</span></span>            | <span data-ttu-id="b2f1a-127">Establezca esta opción en **Sí** para incluir importes de presupuesto en las consolidaciones.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-127">Set this option to **Yes** to include budget amounts in consolidations.</span></span> |
    | <span data-ttu-id="b2f1a-128">Modelos presupuestarios</span><span class="sxs-lookup"><span data-stu-id="b2f1a-128">Budget models</span></span>                     | <span data-ttu-id="b2f1a-129">Especifique el modelo de presupuesto a incluir.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-129">Specify the budget model to include.</span></span> |

3. <span data-ttu-id="b2f1a-130">En la pestaña **Dimensiones financieras**, especifique los detalles de la consolidación:</span><span class="sxs-lookup"><span data-stu-id="b2f1a-130">On the **Financial dimensions** tab, specify the details of the consolidation:</span></span>

    - <span data-ttu-id="b2f1a-131">Especifique la información de dimensiones financieras que debe transferirse desde las transacciones en las cuentas filiales a las transacciones en la entidad jurídica consolidada.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-131">Specify the financial dimension information that should be transferred from the transactions in the subsidiary accounts to the transactions in the consolidated legal entity.</span></span>
    - <span data-ttu-id="b2f1a-132">Seleccione las dimensiones financieras en la lista.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-132">Select financial dimensions in the list.</span></span>
    - <span data-ttu-id="b2f1a-133">Identificar la especificación correcta para cada dimensión financiera que se consolida.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-133">Identify the correct specification for each financial dimension that is consolidated.</span></span> <span data-ttu-id="b2f1a-134">Las opciones disponibles incluyen **Dimensión**, **Dimensión de grupo**, **Cuentas de la empresa** y **Cuenta**.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-134">The available options include **Dimension**, **Group dimension**, **Company accounts**, and **Account**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="b2f1a-135">La opción **Dimensión de grupo** le permite definir el valor de dimensión que utiliza el grupo de empresas que se está consolidando.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-135">The **Group dimension** option lets you define the dimension value that is used by the group of companies that is being consolidated.</span></span>

    - <span data-ttu-id="b2f1a-136">Especifique el orden de los segmentos en el que consolidar.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-136">Specify the segment order to consolidate in.</span></span>

4. <span data-ttu-id="b2f1a-137">En la pestaña **Entidades legales**, siga estos pasos para especificar la entidad jurídica que está exportando:</span><span class="sxs-lookup"><span data-stu-id="b2f1a-137">On the **Legal entities** tab, follow these steps to specify the legal entity that you're exporting:</span></span>

    1. <span data-ttu-id="b2f1a-138">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-138">Select **New**.</span></span>
    2. <span data-ttu-id="b2f1a-139">En el campo **Entidad jurídica de origen**, introduzca la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-139">In the **Source legal entity** field, enter the legal entity.</span></span>

        <span data-ttu-id="b2f1a-140">Si se aplican los mismos criterios a varias filiales que se encuentran en la misma base de datos, puede transferir datos desde dichas filiales a los archivos de exportación individuales en una sola operación:</span><span class="sxs-lookup"><span data-stu-id="b2f1a-140">If the same criteria apply to several subsidiaries that are in the same database, you can transfer data from those subsidiaries to separate export files in a single operation:</span></span>

        1. <span data-ttu-id="b2f1a-141">Cree una línea para cada entidad jurídica filial cuyas cuentas deben exportarse a los archivos.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-141">Create a line for each subsidiary legal entity for which accounts should be exported to files.</span></span> <span data-ttu-id="b2f1a-142">Estos archivos se importarán más adelante a la entidad jurídica consolidada.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-142">These files will be imported into the consolidated legal entity later.</span></span>
        2. <span data-ttu-id="b2f1a-143">Para cada filial, especifique el nombre de la filial, así como el nombre del archivo de exportación que se creará durante la operación.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-143">For each subsidiary, enter the subsidiary name and the name of the export file that will be created during the export job.</span></span>

    3. <span data-ttu-id="b2f1a-144">En el campo **Tipo de cuenta de diferencias de conversión**, seleccione **Ganancia y perdida** o **Balance de situación**.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-144">In **Account type of conversion differences** field, Select **Profit and loss** or **Balance sheet**.</span></span>
    4. <span data-ttu-id="b2f1a-145">Introduzca un nombre de archivo para el archivo de exportación que se creará.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-145">Enter a file name for the export file that will be created.</span></span>

5. <span data-ttu-id="b2f1a-146">Seleccione **Aceptar** para ejecutar la exportación.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-146">Select **OK** to run the export.</span></span>

<span data-ttu-id="b2f1a-147">Una vez completada la exportación, recibirá un mensaje que muestra el número de registros guardados en cada archivo.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-147">When the export is completed, you receive a message that shows the number of records that were saved in each file.</span></span> <span data-ttu-id="b2f1a-148">A continuación, puede importar los archivos a la entidad jurídica consolidada.</span><span class="sxs-lookup"><span data-stu-id="b2f1a-148">You can then import the files into the consolidated legal entity.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]