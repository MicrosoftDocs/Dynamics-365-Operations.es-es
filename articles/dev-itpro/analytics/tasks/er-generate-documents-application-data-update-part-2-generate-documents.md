--- 
title: "Diseñar configuraciones para generar documentos con datos de la aplicación"
description: "Para completar los pasos de este procedimiento, primero debe completar el procedimiento, ER Generar documentos con la actualización de los datos de la aplicación (Parte 1: Configuraciones de importación)\"."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: c883897b63decdbf983e3294899adc20b20e319f
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="design-configurations-to-generate-documents-with-application-data"></a><span data-ttu-id="d44e1-103">Diseñar configuraciones para generar documentos con datos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="d44e1-103">Design configurations to generate documents with application data</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d44e1-104">Para completar los pasos de este procedimiento, primero debe completar el procedimiento, "ER: Generar documentos con la actualización de los datos de la aplicación (Parte 1: Configuraciones de importación)".</span><span class="sxs-lookup"><span data-stu-id="d44e1-104">To complete the steps in this procedure, you must first complete the procedure, ER Generate documents with application data update (Part 1: Import configurations).</span></span>



<span data-ttu-id="d44e1-105">Los pasos de este procedimiento explican cómo diseñar las configuraciones de los informes electrónicos (ER) para generar un documento electrónico.</span><span class="sxs-lookup"><span data-stu-id="d44e1-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document.</span></span> <span data-ttu-id="d44e1-106">En este procedimiento, ejecute la configuración del formato importado de ER que se ha creado para la empresa de ejemplo, Litware, Inc. para generar documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="d44e1-106">In this procedure, you run the ER imported format configuration that has been created for the sample company, Litware, Inc. to generate electronic documents.</span></span>



<span data-ttu-id="d44e1-107">Este procedimiento se ha creado para los usuarios con los roles Administrador del sistema o Desarrollador de informes electrónicos asignados.</span><span class="sxs-lookup"><span data-stu-id="d44e1-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="d44e1-108">Estos pasos se pueden completar mediante el conjunto de datos de DEMF.</span><span class="sxs-lookup"><span data-stu-id="d44e1-108">These steps can be completed using the DEMF dataset.</span></span> 



<span data-ttu-id="d44e1-109">Antes de comenzar, cambie el contexto del país para la empresa de DEMF de Alemania (DEU) al Bélgica (BEL).</span><span class="sxs-lookup"><span data-stu-id="d44e1-109">Before you begin, change the country context for the DEMF company from DEU (Germany) to BEL (Belgium).</span></span> <span data-ttu-id="d44e1-110">Haga clic en Administración de organizaciones > Organizaciones > Entidades jurídicas para actualizar el código de país en la dirección principal de la entidad jurídica DEMF.</span><span class="sxs-lookup"><span data-stu-id="d44e1-110">Click Organization administration > Organizations > Legal entities to update the country code in the primary address of the legal entity DEMF.</span></span> <span data-ttu-id="d44e1-111">Reinicie la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d44e1-111">Restart your application.</span></span>


## <a name="run-imported-er-format"></a><span data-ttu-id="d44e1-112">Ejecutar formato de ER importado</span><span class="sxs-lookup"><span data-stu-id="d44e1-112">Run imported ER format</span></span>
1. <span data-ttu-id="d44e1-113">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="d44e1-113">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="d44e1-114">En el árbol, expanda "Intrastat (modelo)".</span><span class="sxs-lookup"><span data-stu-id="d44e1-114">In the tree, expand 'Intrastat (model)'.</span></span>
3. <span data-ttu-id="d44e1-115">En el árbol, seleccione "Intrastat (modelo)\Intrastat (formato)".</span><span class="sxs-lookup"><span data-stu-id="d44e1-115">In the tree, select 'Intrastat (model)\Intrastat (format)'.</span></span>
4. <span data-ttu-id="d44e1-116">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="d44e1-116">Click Run.</span></span>
    * <span data-ttu-id="d44e1-117">Ejecute la versión de borrador de la configuración del formato de ER para generar el informe de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="d44e1-117">Run the draft version of the ER format configuration to generate the Intrastat report.</span></span>  
5. <span data-ttu-id="d44e1-118">En el campo Especificar nombre de archivo, escriba“intrastat.xml”.</span><span class="sxs-lookup"><span data-stu-id="d44e1-118">In the Enter file name field, type 'intrastat.xml'.</span></span>
    * <span data-ttu-id="d44e1-119">Especifique el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="d44e1-119">Specify the name of the file.</span></span>  
6. <span data-ttu-id="d44e1-120">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d44e1-120">Click OK.</span></span>
    * <span data-ttu-id="d44e1-121">Revise el archivo XML generado.</span><span class="sxs-lookup"><span data-stu-id="d44e1-121">Review the generated XML file.</span></span>  
7. <span data-ttu-id="d44e1-122">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d44e1-122">Close the page.</span></span>
8. <span data-ttu-id="d44e1-123">Vaya a Impuestos > Declaraciones > Comercio exterior > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="d44e1-123">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
    * <span data-ttu-id="d44e1-124">Abra este formulario para ver las transacciones de Intrastat que se incluyen en el documento electrónico generado.</span><span class="sxs-lookup"><span data-stu-id="d44e1-124">Open this form to view the Intrastat transactions that are included in the generated electronic document.</span></span>  
9. <span data-ttu-id="d44e1-125">Haga clic en de archivo de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="d44e1-125">Click Intrastat archive.</span></span>
    * <span data-ttu-id="d44e1-126">Dado que el formato de informe electrónico ejecutado no contiene ningún valor para la actualización de los datos de la aplicación, los detalles del informe de Intrastat completado no se han almacenado.</span><span class="sxs-lookup"><span data-stu-id="d44e1-126">Because the executed ER format does not contain any settings for application data update, the details of the completed Intrastat report have not been archived.</span></span>  
10. <span data-ttu-id="d44e1-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d44e1-127">Close the page.</span></span>
11. <span data-ttu-id="d44e1-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d44e1-128">Close the page.</span></span>


