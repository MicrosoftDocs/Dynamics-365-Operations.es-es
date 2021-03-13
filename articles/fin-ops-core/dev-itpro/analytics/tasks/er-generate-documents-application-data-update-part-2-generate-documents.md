---
title: Diseñar configuraciones para generar documentos que tengan datos de la aplicación
description: 'Este tema describe cómo diseñar las configuraciones de los informes electrónicos (ER) para generar un documento electrónico. (Parte 1: importar configuraciones).'
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 417c419dc6925bac337fe74a2f057395316ec75d
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092931"
---
# <a name="design-configurations-to-generate-documents-that-have-application-data"></a><span data-ttu-id="2d991-104">Diseñar configuraciones para generar documentos que tengan datos de la aplicación</span><span class="sxs-lookup"><span data-stu-id="2d991-104">Design configurations to generate documents that have application data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2d991-105">Para completar los pasos de este procedimiento, primero debe completar el procedimiento, "ER: Generar documentos con la actualización de los datos de la aplicación (Parte 1: Configuraciones de importación)".</span><span class="sxs-lookup"><span data-stu-id="2d991-105">To complete the steps in this procedure, you must first complete the procedure, ER Generate documents with application data update (Part 1: Import configurations).</span></span>



<span data-ttu-id="2d991-106">Los pasos de este procedimiento explican cómo diseñar las configuraciones de los informes electrónicos (ER) para generar un documento electrónico.</span><span class="sxs-lookup"><span data-stu-id="2d991-106">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document.</span></span> <span data-ttu-id="2d991-107">En este procedimiento, ejecute la configuración del formato importado de ER que se ha creado para la empresa de ejemplo, Litware, Inc. para generar documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="2d991-107">In this procedure, you run the ER imported format configuration that has been created for the sample company, Litware, Inc. to generate electronic documents.</span></span>



<span data-ttu-id="2d991-108">Este procedimiento se ha creado para los usuarios con los roles Administrador del sistema o Desarrollador de informes electrónicos asignados.</span><span class="sxs-lookup"><span data-stu-id="2d991-108">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="2d991-109">Estos pasos se pueden completar mediante el conjunto de datos de DEMF.</span><span class="sxs-lookup"><span data-stu-id="2d991-109">These steps can be completed using the DEMF dataset.</span></span> 



<span data-ttu-id="2d991-110">Antes de comenzar, cambie el contexto del país para la empresa de DEMF de Alemania (DEU) al Bélgica (BEL).</span><span class="sxs-lookup"><span data-stu-id="2d991-110">Before you begin, change the country context for the DEMF company from DEU (Germany) to BEL (Belgium).</span></span> <span data-ttu-id="2d991-111">Haga clic en Administración de organizaciones > Organizaciones > Entidades jurídicas para actualizar el código de país en la dirección principal de la entidad jurídica DEMF.</span><span class="sxs-lookup"><span data-stu-id="2d991-111">Click Organization administration > Organizations > Legal entities to update the country code in the primary address of the legal entity DEMF.</span></span> <span data-ttu-id="2d991-112">Reinicie la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2d991-112">Restart your application.</span></span>


## <a name="run-imported-er-format"></a><span data-ttu-id="2d991-113">Ejecutar formato de ER importado</span><span class="sxs-lookup"><span data-stu-id="2d991-113">Run imported ER format</span></span>
1. <span data-ttu-id="2d991-114">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="2d991-114">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="2d991-115">En el árbol, expanda "Intrastat (modelo)".</span><span class="sxs-lookup"><span data-stu-id="2d991-115">In the tree, expand 'Intrastat (model)'.</span></span>
3. <span data-ttu-id="2d991-116">En el árbol, seleccione "Intrastat (modelo)\Intrastat (formato)".</span><span class="sxs-lookup"><span data-stu-id="2d991-116">In the tree, select 'Intrastat (model)\Intrastat (format)'.</span></span>
4. <span data-ttu-id="2d991-117">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="2d991-117">Click Run.</span></span>
    * <span data-ttu-id="2d991-118">Ejecute la versión de borrador de la configuración del formato de ER para generar el informe de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="2d991-118">Run the draft version of the ER format configuration to generate the Intrastat report.</span></span>  
5. <span data-ttu-id="2d991-119">En el campo Especificar nombre de archivo, escriba“intrastat.xml”.</span><span class="sxs-lookup"><span data-stu-id="2d991-119">In the Enter file name field, type 'intrastat.xml'.</span></span>
    * <span data-ttu-id="2d991-120">Especifique el nombre del archivo.</span><span class="sxs-lookup"><span data-stu-id="2d991-120">Specify the name of the file.</span></span>  
6. <span data-ttu-id="2d991-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="2d991-121">Click OK.</span></span>
    * <span data-ttu-id="2d991-122">Revise el archivo XML generado.</span><span class="sxs-lookup"><span data-stu-id="2d991-122">Review the generated XML file.</span></span>  
7. <span data-ttu-id="2d991-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="2d991-123">Close the page.</span></span>
8. <span data-ttu-id="2d991-124">Vaya a Impuestos > Declaraciones > Comercio exterior > Intrastat.</span><span class="sxs-lookup"><span data-stu-id="2d991-124">Go to Tax > Declarations > Foreign trade > Intrastat.</span></span>
    * <span data-ttu-id="2d991-125">Abra este formulario para ver las transacciones de Intrastat que se incluyen en el documento electrónico generado.</span><span class="sxs-lookup"><span data-stu-id="2d991-125">Open this form to view the Intrastat transactions that are included in the generated electronic document.</span></span>  
9. <span data-ttu-id="2d991-126">Haga clic en de archivo de Intrastat.</span><span class="sxs-lookup"><span data-stu-id="2d991-126">Click Intrastat archive.</span></span>
    * <span data-ttu-id="2d991-127">Dado que el formato de informe electrónico ejecutado no contiene ningún valor para la actualización de los datos de la aplicación, los detalles del informe de Intrastat completado no se han almacenado.</span><span class="sxs-lookup"><span data-stu-id="2d991-127">Because the executed ER format does not contain any settings for application data update, the details of the completed Intrastat report have not been archived.</span></span>  
10. <span data-ttu-id="2d991-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="2d991-128">Close the page.</span></span>
11. <span data-ttu-id="2d991-129">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="2d991-129">Close the page.</span></span>

