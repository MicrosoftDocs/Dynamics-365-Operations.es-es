---
title: Generar documentos que tengan datos de la aplicación
description: Para completar los pasos de este procedimiento, debe completar primero el procedimiento, "ER Generar documentos con la actualización de datos de la aplicación (Parte 4 - Modificar formato)".
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c474f4bc7940a429ed62870e00302c93581eb9a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569590"
---
# <a name="generate-documents-that-have-application-data"></a><span data-ttu-id="e0727-103">Generar documentos que tengan datos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="e0727-103">Generate documents that have application data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e0727-104">Para completar los pasos de este procedimiento, debe completar primero el procedimiento, "ER Generar documentos con la actualización de datos de la aplicación (Parte 4: Modificar formato)".</span><span class="sxs-lookup"><span data-stu-id="e0727-104">To complete the steps in this procedure, you must first complete the procedure, "ER Generate documents with application data update (Part 4: Modify format)".</span></span>



<span data-ttu-id="e0727-105">Los pasos de este procedimiento explican cómo diseñar las configuraciones de los informes electrónicos (ER) para generar un documento electrónico y actualizar los datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e0727-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="e0727-106">En este procedimiento, ejecuta la configuración del formato de ER para generar el informe de Intrastat y actualizar los datos de la aplicación para los detalles de almacenamiento del proceso de generación de informes.</span><span class="sxs-lookup"><span data-stu-id="e0727-106">In this procedure, you execute the ER format configuration to generate the Intrastat report and update application data for archiving details of the reporting process.</span></span>



<span data-ttu-id="e0727-107">Este procedimiento se ha creado para los usuarios con los roles Administrador del sistema o Desarrollador de informes electrónicos asignados.</span><span class="sxs-lookup"><span data-stu-id="e0727-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="e0727-108">Estos pasos se pueden completar mediante el conjunto de datos de DEMF.</span><span class="sxs-lookup"><span data-stu-id="e0727-108">These steps can be completed using the DEMF dataset.</span></span> <span data-ttu-id="e0727-109">Antes de comenzar, asegúrese de que el contexto del país para la empresa de DEMF sea Bélgica (BEL).</span><span class="sxs-lookup"><span data-stu-id="e0727-109">Before you begin, make sure that the country context for the DEMF company is BEL (Belgium).</span></span>


## <a name="set-up-foreign-trade-parameters"></a><span data-ttu-id="e0727-110">Configurar parámetros de comercio exterior</span><span class="sxs-lookup"><span data-stu-id="e0727-110">Set up foreign trade parameters</span></span>
1. <span data-ttu-id="e0727-111">Vaya a Impuestos > Configuración > Comercio exterior > Parámetros de comercio exterior.</span><span class="sxs-lookup"><span data-stu-id="e0727-111">Go to Tax > Setup > Foreign trade > Foreign trade parameters.</span></span>
2. <span data-ttu-id="e0727-112">Haga clic en la ficha Secuencias numéricas.</span><span class="sxs-lookup"><span data-stu-id="e0727-112">Click the Number sequences tab.</span></span>

    <span data-ttu-id="e0727-113">Para archivar los detalles del proceso de generación de informes de Intrastat, necesitamos identificar los registros de cada archivo que creamos.</span><span class="sxs-lookup"><span data-stu-id="e0727-113">Archiving details of Intrastat reporting process, we need to identify records of each archive we created.</span></span> <span data-ttu-id="e0727-114">Una secuencia numérica especial se debe configurar para eso.</span><span class="sxs-lookup"><span data-stu-id="e0727-114">A special number sequence must be configured for that.</span></span>  

3. <span data-ttu-id="e0727-115">Seleccione la referencia "Id. de archivo de Intrastat”.</span><span class="sxs-lookup"><span data-stu-id="e0727-115">Select the 'Intrastat archive ID' reference.</span></span>
4. <span data-ttu-id="e0727-116">En el campo Código de secuencia numérica, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e0727-116">In the Number sequence code field, type a value.</span></span>

    <span data-ttu-id="e0727-117">En el campo "Código de secuencia numérica", especifique o seleccione el valor "Fore_2".</span><span class="sxs-lookup"><span data-stu-id="e0727-117">In the 'Number sequence code' field, enter or select the value 'Fore_2'.</span></span>  

5. <span data-ttu-id="e0727-118">ResolveChanges, el código de secuencia de Número.</span><span class="sxs-lookup"><span data-stu-id="e0727-118">ResolveChanges the Number sequence code.</span></span>
6. <span data-ttu-id="e0727-119">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e0727-119">Click Save.</span></span>
7. <span data-ttu-id="e0727-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e0727-120">Close the page.</span></span>

## <a name="run-modified-er-format"></a><span data-ttu-id="e0727-121">Ejecutar el formato de ER modificado</span><span class="sxs-lookup"><span data-stu-id="e0727-121">Run modified ER format</span></span>
1. <span data-ttu-id="e0727-122">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="e0727-122">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="e0727-123">En el árbol, expanda "Intrastat (modelo)".</span><span class="sxs-lookup"><span data-stu-id="e0727-123">In the tree, expand 'Intrastat (model)'.</span></span>
3. <span data-ttu-id="e0727-124">En el árbol, seleccione "Intrastat (modelo)\Intrastat (formato)".</span><span class="sxs-lookup"><span data-stu-id="e0727-124">In the tree, select 'Intrastat (model)\Intrastat (format)'.</span></span>
4. <span data-ttu-id="e0727-125">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="e0727-125">Click Run.</span></span>
5. <span data-ttu-id="e0727-126">En el campo Especificar nombre de archivo, escriba“intrastat2.xml".</span><span class="sxs-lookup"><span data-stu-id="e0727-126">In the Enter file name field, type 'intrastat2.xml'.</span></span>
6. <span data-ttu-id="e0727-127">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="e0727-127">Click OK.</span></span>

## <a name="review-er-format-executions-results"></a><span data-ttu-id="e0727-128">Revisar los resultados de la ejecución del formato de ER</span><span class="sxs-lookup"><span data-stu-id="e0727-128">Review ER format execution's results</span></span>
<span data-ttu-id="e0727-129">Revise el archivo XML generado.</span><span class="sxs-lookup"><span data-stu-id="e0727-129">Review the generated XML file.</span></span>  
1. <span data-ttu-id="e0727-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e0727-130">Close the page.</span></span>
2. <span data-ttu-id="e0727-131">Vaya a Impuestos > Declaraciones > Comercio exterior > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="e0727-131">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>

    <span data-ttu-id="e0727-132">Abra este formulario que contiene las transacciones de Intrastat que se incluyen en el documento electrónico generado.</span><span class="sxs-lookup"><span data-stu-id="e0727-132">Open this form containing Intrastat transactions that have been included to the generated electronic document.</span></span>  

3. <span data-ttu-id="e0727-133">Haga clic en de archivo de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="e0727-133">Click Intrastat archive.</span></span>

    <span data-ttu-id="e0727-134">Dado que el formato de informe electrónico ejecutado contiene ahora valores para la actualización de los datos de la aplicación, los detalles del informe de Intrastat completado no se han almacenado.</span><span class="sxs-lookup"><span data-stu-id="e0727-134">Since the executed ER format contains now settings for application data update, the details of the completed Intrastat reporting have been archived.</span></span> <span data-ttu-id="e0727-135">En este formulario, puede ver el registro de encabezados del archivo creado.</span><span class="sxs-lookup"><span data-stu-id="e0727-135">In this form, you can see the header record of the created archive.</span></span>  

4. <span data-ttu-id="e0727-136">Haga clic en Detalles.</span><span class="sxs-lookup"><span data-stu-id="e0727-136">Click Details.</span></span>

    <span data-ttu-id="e0727-137">En este formulario, puede ver los detalles del archivo creado.</span><span class="sxs-lookup"><span data-stu-id="e0727-137">In this form, you can see the details for the created archive.</span></span>  

5. <span data-ttu-id="e0727-138">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e0727-138">Close the page.</span></span>
6. <span data-ttu-id="e0727-139">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e0727-139">Close the page.</span></span>
7. <span data-ttu-id="e0727-140">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e0727-140">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]