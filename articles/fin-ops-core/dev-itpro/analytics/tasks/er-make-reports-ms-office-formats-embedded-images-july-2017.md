---
title: Diseñar configuraciones para generar informes en los formatos de Office que tengan imágenes incrustadas
description: Este tema describe cómo diseñar las configuraciones que generan documentos electrónicos en formato Excel y Word que contienen imágenes insertadas.
author: NickSelin
ms.date: 04/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5eea178a351716425706f481ae66c5b5183a52e5
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944566"
---
# <a name="design-configurations-to-generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="f4799-103">Diseñar configuraciones para generar informes en los formatos de Office que tengan imágenes incrustadas</span><span class="sxs-lookup"><span data-stu-id="f4799-103">Design configurations to generate reports in Office format that have embedded images</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f4799-104">Para completar los pasos de este procedimiento, primero complete el procedimiento, "ER: Crear un proveedor de configuraciones y marcarlo como activo".</span><span class="sxs-lookup"><span data-stu-id="f4799-104">To complete the steps in this procedure, first complete the procedure, "ER Create a configuration provider and mark it as active."</span></span> <span data-ttu-id="f4799-105">Este procedimiento explica cómo diseñar las configuraciones de informes electrónicos (ER) para generar documentos de Microsoft Excel o Word que contienen imágenes incrustadas.</span><span class="sxs-lookup"><span data-stu-id="f4799-105">This procedure explains how to design Electronic reporting (ER) configurations to generate a Microsoft Excel or Word document that contains embedded images.</span></span> <span data-ttu-id="f4799-106">En este procedimiento, creará las configuraciones de ER necesarias para la empresa de ejemplo, Litware, Inc. Estos pasos se pueden completar mediante el conjunto de datos de USMF.</span><span class="sxs-lookup"><span data-stu-id="f4799-106">In this procedure, you will create the required ER configurations for the sample company, Litware, Inc. These steps can be completed using the USMF dataset.</span></span> <span data-ttu-id="f4799-107">Este procedimiento se ha creado para los usuarios con los roles Administrador del sistema o Desarrollador de informes electrónicos asignados.</span><span class="sxs-lookup"><span data-stu-id="f4799-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="f4799-108">Antes de comenzar, debe descargar y guardar los archivos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f4799-108">Before you begin, download and save the following files:</span></span> 

| <span data-ttu-id="f4799-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="f4799-109">Description</span></span>                                          | <span data-ttu-id="f4799-110">Nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="f4799-110">File name</span></span>                   |
|------------------------------------------------------|-----------------------------|
| <span data-ttu-id="f4799-111">Configuración del modelo datos de ER</span><span class="sxs-lookup"><span data-stu-id="f4799-111">ER data model configuration</span></span>                          | [<span data-ttu-id="f4799-112">Model for cheques.xml</span><span class="sxs-lookup"><span data-stu-id="f4799-112">Model for cheques.xml</span></span>](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| <span data-ttu-id="f4799-113">Configuración del formato de ER</span><span class="sxs-lookup"><span data-stu-id="f4799-113">ER format configuration</span></span>                              | [<span data-ttu-id="f4799-114">Cheques printing format.xml</span><span class="sxs-lookup"><span data-stu-id="f4799-114">Cheques printing format.xml</span></span>](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| <span data-ttu-id="f4799-115">Imagen del logotipo de la empresa</span><span class="sxs-lookup"><span data-stu-id="f4799-115">Company logo image</span></span>                                   | [<span data-ttu-id="f4799-116">Company logo.png</span><span class="sxs-lookup"><span data-stu-id="f4799-116">Company logo.png</span></span>](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| <span data-ttu-id="f4799-117">Imagen de firma</span><span class="sxs-lookup"><span data-stu-id="f4799-117">Signature image</span></span>                                      | [<span data-ttu-id="f4799-118">Signature image.png</span><span class="sxs-lookup"><span data-stu-id="f4799-118">Signature image.png</span></span>](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| <span data-ttu-id="f4799-119">Imagen de firma alternativa</span><span class="sxs-lookup"><span data-stu-id="f4799-119">Alternative signature image</span></span>                          | [<span data-ttu-id="f4799-120">Signature image 2.png</span><span class="sxs-lookup"><span data-stu-id="f4799-120">Signature image 2.png</span></span>](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| <span data-ttu-id="f4799-121">Plantilla de Microsoft Word para imprimir cheques de pago</span><span class="sxs-lookup"><span data-stu-id="f4799-121">Microsoft Word template for printing payment checks</span></span>  | [<span data-ttu-id="f4799-122">Consultar plantilla Word.docx</span><span class="sxs-lookup"><span data-stu-id="f4799-122">Cheque template Word.docx</span></span>](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |

## <a name="verify-prerequisites"></a><span data-ttu-id="f4799-123">Comprobar los requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f4799-123">Verify prerequisites</span></span>  
 1. <span data-ttu-id="f4799-124">Vaya a Administración de la organización > Espacios de trabajo > Informes electrónicos.</span><span class="sxs-lookup"><span data-stu-id="f4799-124">Go to Organization administration > Workspaces > Electronic reporting.</span></span>  
 2. <span data-ttu-id="f4799-125">Asegúrese de que el proveedor de configuración de la empresa de ejemplo “Litware, Inc.” está disponible y marcado como Activo.</span><span class="sxs-lookup"><span data-stu-id="f4799-125">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="f4799-126">Si no ve a este proveedor de configuración, complete los pasos del procedimiento "Creación de un proveedor de configuración y marcarlo como activo".</span><span class="sxs-lookup"><span data-stu-id="f4799-126">If you don't see this configuration provider, complete the steps in the procedure, "Create a configuration provider and mark it as active."</span></span>   
 3. <span data-ttu-id="f4799-127">Haga clic en Configuraciones de informes.</span><span class="sxs-lookup"><span data-stu-id="f4799-127">Click Reporting configurations.</span></span>  
 
## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="f4799-128">Añada una nueva configuración para el modelo ER</span><span class="sxs-lookup"><span data-stu-id="f4799-128">Add a new ER model configuration</span></span>  
 1. <span data-ttu-id="f4799-129">En lugar de crear un nuevo modelo, puede cargar el archivo de configuración del modelo de ER (modelo para cheques.xml) que se guardó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f4799-129">Instead of creating a new model, you can load the ER model configuration file (Model for cheques.xml) that you saved earlier.</span></span> <span data-ttu-id="f4799-130">Este archivo contiene el modelo de datos de ejemplo para los cheques de pago y la asignación de modelo de datos a los componentes de datos de la aplicación Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="f4799-130">This file contains the sample data model for payment cheques and the mapping of the data model to the data components of the Dynamics 365 for Operations application.</span></span>   
 2. <span data-ttu-id="f4799-131">En las versiones de ficha desplegable, haga clic en Exchange.</span><span class="sxs-lookup"><span data-stu-id="f4799-131">On the Versions FastTab, click Exchange.</span></span>   
 3. <span data-ttu-id="f4799-132">Haga clic en Cargar desde un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="f4799-132">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="f4799-133">Haga clic en Examinar, y seleccione el modelo para cheques.xml.</span><span class="sxs-lookup"><span data-stu-id="f4799-133">Click Browse, and then select Model for cheques.xml.</span></span>   
 5. <span data-ttu-id="f4799-134">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f4799-134">Click OK.</span></span>  
 6. <span data-ttu-id="f4799-135">El modelo cargado se utilizará como origen de datos de la información para generar documentos que contengan imágenes en Excel y Word.</span><span class="sxs-lookup"><span data-stu-id="f4799-135">The loaded model will be used as a data source of information to generate documents that contain images in Excel and Word.</span></span>  

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="f4799-136">Añada una nueva configuración para el formato de ER</span><span class="sxs-lookup"><span data-stu-id="f4799-136">Add a new ER format configuration</span></span>  
 1. <span data-ttu-id="f4799-137">En lugar de crear un nuevo formato, puede cargar el archivo de configuración del formato de ER (formato de impresión de cheques .xml) que guardó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f4799-137">Instead of creating a new format, you can load the ER format configuration file (Cheques printing format.xml) that you saved earlier.</span></span> <span data-ttu-id="f4799-138">Este archivo contiene el diseño de ejemplo de formato para imprimir cheques utilizando el formulario preimpreso y la asignación de este formato al modelo de datos “modelo para cheques”.</span><span class="sxs-lookup"><span data-stu-id="f4799-138">This file contains the sample layout of the format to print cheques using the pre-printed form and the mapping of this format to the 'Model for cheques' data model.</span></span>   
 2. <span data-ttu-id="f4799-139">Haga clic en Intercambiar.</span><span class="sxs-lookup"><span data-stu-id="f4799-139">Click Exchange.</span></span>  
 3. <span data-ttu-id="f4799-140">Haga clic en Cargar desde un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="f4799-140">Click Load from XML file.</span></span>  
 4. <span data-ttu-id="f4799-141">Haga clic en Examinar y seleccione el archivo Cheques printing format.xml.</span><span class="sxs-lookup"><span data-stu-id="f4799-141">Click Browse and select the Cheques printing format.xml file.</span></span>   
 5. <span data-ttu-id="f4799-142">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f4799-142">Click OK.</span></span>  
 6. <span data-ttu-id="f4799-143">En el árbol, expanda "Modelo para cheques".</span><span class="sxs-lookup"><span data-stu-id="f4799-143">In the tree, expand 'Model for cheques'.</span></span>  
 7. <span data-ttu-id="f4799-144">En el árbol, seleccione "Modelo para cheques\Formato de impresión de cheques".</span><span class="sxs-lookup"><span data-stu-id="f4799-144">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>  
 8. <span data-ttu-id="f4799-145">El formato cargado se utilizará para generar documentos que contengan imágenes en Excel y Word.</span><span class="sxs-lookup"><span data-stu-id="f4799-145">The loaded format will be used to generate documents that contain images in Excel and Word.</span></span>   

## <a name="configure-er-user-parameters"></a><span data-ttu-id="f4799-146">Configurar los parámetros de usuario de ER</span><span class="sxs-lookup"><span data-stu-id="f4799-146">Configure ER user parameters</span></span>  
 1. <span data-ttu-id="f4799-147">En el panel de acciones, haga clic en Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="f4799-147">On the Action Pane, click Configurations.</span></span>  
 2. <span data-ttu-id="f4799-148">Haga clic en Parámetros de usuario.</span><span class="sxs-lookup"><span data-stu-id="f4799-148">Click User parameters.</span></span>  
 3. <span data-ttu-id="f4799-149">Seleccione Sí en el campo Parámetros de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f4799-149">Select Yes in the Run settings field.</span></span>  
  <span data-ttu-id="f4799-150">Desconecte el indicador de "Ejecución de borrador" para iniciar la versión de borrador del formato seleccionado en lugar del completado.</span><span class="sxs-lookup"><span data-stu-id="f4799-150">Turn on the 'Run draft' flag to start the draft version of the selected format instead of the completed one.</span></span>  
 4. <span data-ttu-id="f4799-151">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f4799-151">Click OK.</span></span>  

## <a name="configure-cash--bank-management-parameters"></a><span data-ttu-id="f4799-152">Configure los parámetros de administración de efectivo y bancos</span><span class="sxs-lookup"><span data-stu-id="f4799-152">Configure Cash & bank management parameters</span></span>  
 1. <span data-ttu-id="f4799-153">Vaya a Gestión de efectivo y de banco > Cuentas bancarias > Cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="f4799-153">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>  
 2. <span data-ttu-id="f4799-154">Use un filtro rápido para filtrar por el campo Cuenta bancaria, por el valor ''USMF OPER".</span><span class="sxs-lookup"><span data-stu-id="f4799-154">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>  
 3. <span data-ttu-id="f4799-155">En el panel de acciones, haga clic en Configurar.</span><span class="sxs-lookup"><span data-stu-id="f4799-155">On the Action Pane, click Set up.</span></span>  
 4. <span data-ttu-id="f4799-156">Haga clic en Comprobar.</span><span class="sxs-lookup"><span data-stu-id="f4799-156">Click Check.</span></span>  
 5. <span data-ttu-id="f4799-157">Expanda la sección Configuración.</span><span class="sxs-lookup"><span data-stu-id="f4799-157">Expand the Setup section.</span></span>  
 6. <span data-ttu-id="f4799-158">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="f4799-158">Click Edit.</span></span>  
 7. <span data-ttu-id="f4799-159">Seleccione Sí en el campo Logotipo de la empresa.</span><span class="sxs-lookup"><span data-stu-id="f4799-159">Select Yes in the Company logo field.</span></span>  
 8. <span data-ttu-id="f4799-160">Haga clic en Logotipo de la empresa.</span><span class="sxs-lookup"><span data-stu-id="f4799-160">Click Company logo.</span></span>  
 9. <span data-ttu-id="f4799-161">Haga clic en Cambiar.</span><span class="sxs-lookup"><span data-stu-id="f4799-161">Click Change.</span></span>  
 10. <span data-ttu-id="f4799-162">Haga clic Examinar y seleccione el archivo que ha descargado anteriormente, Company logo.png.</span><span class="sxs-lookup"><span data-stu-id="f4799-162">Click Browse and select the file that you downloaded earlier, Company logo.png.</span></span>   
 11. <span data-ttu-id="f4799-163">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="f4799-163">Click Save.</span></span>  
 12. <span data-ttu-id="f4799-164">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f4799-164">Close the page.</span></span>  
 13. <span data-ttu-id="f4799-165">Expanda la sección Firma.</span><span class="sxs-lookup"><span data-stu-id="f4799-165">Expand the Signature section.</span></span>  
 14. <span data-ttu-id="f4799-166">Seleccione Sí en el campo Imprimir la primera firma.</span><span class="sxs-lookup"><span data-stu-id="f4799-166">Select Yes in the Print first signature field.</span></span>  
 15. <span data-ttu-id="f4799-167">Haga clic en Cambiar.</span><span class="sxs-lookup"><span data-stu-id="f4799-167">Click Change.</span></span>  
 16. <span data-ttu-id="f4799-168">Haga clic Examinar y seleccione el archivo que ha descargado anteriormente, Signature image.png.</span><span class="sxs-lookup"><span data-stu-id="f4799-168">Click Browse and select the file that you downloaded earlier, Signature image.png.</span></span>   
 17. <span data-ttu-id="f4799-169">Expanda la sección Copias.</span><span class="sxs-lookup"><span data-stu-id="f4799-169">Expand the Copies section.</span></span>  
 18. <span data-ttu-id="f4799-170">En el campo Marca de agua, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="f4799-170">In the Watermark field, select an option.</span></span>  
 19. <span data-ttu-id="f4799-171">Seleccione Sí en el campo Formato de exportación electrónica genérica.</span><span class="sxs-lookup"><span data-stu-id="f4799-171">Select Yes in the Generic electronic Export format field.</span></span>  
 20. <span data-ttu-id="f4799-172">Seleccione la configuración "Cheques printing form".</span><span class="sxs-lookup"><span data-stu-id="f4799-172">Select 'Cheques printing form' configuration.</span></span>  
 21. <span data-ttu-id="f4799-173">Ahora el formato seleccionado de ER se usará para imprimir los cheques.</span><span class="sxs-lookup"><span data-stu-id="f4799-173">Now the selected ER format will be used for printing cheques.</span></span>  
 22. <span data-ttu-id="f4799-174">Haga clic en Vincular.</span><span class="sxs-lookup"><span data-stu-id="f4799-174">Click Attach.</span></span>  
 23. <span data-ttu-id="f4799-175">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f4799-175">Click New.</span></span>  
 24. <span data-ttu-id="f4799-176">Haga clic en Archivo.</span><span class="sxs-lookup"><span data-stu-id="f4799-176">Click File.</span></span>  
 25. <span data-ttu-id="f4799-177">Haga clic Examinar y seleccione el archivo que ha descargado anteriormente, Signature image 2.png.</span><span class="sxs-lookup"><span data-stu-id="f4799-177">Click Browse and select the file that you downloaded earlier, Signature image 2.png.</span></span>   
 26. <span data-ttu-id="f4799-178">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f4799-178">Close the page.</span></span>  
 27. <span data-ttu-id="f4799-179">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f4799-179">Close the page.</span></span>  
 28. <span data-ttu-id="f4799-180">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f4799-180">Close the page.</span></span>  
 29. <span data-ttu-id="f4799-181">Vaya a Gestión de efectivo y bancos > Configurar > Parámetros de gestión de efectivo y bancos.</span><span class="sxs-lookup"><span data-stu-id="f4799-181">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>  
 30. <span data-ttu-id="f4799-182">Seleccione Sí en el campo Permitir la creación de validaciones de cuenta en cuentas bancarias inactivas:.</span><span class="sxs-lookup"><span data-stu-id="f4799-182">Select Yes in the Allow prenote creation on inactive bank accounts: field.</span></span>  
 31. <span data-ttu-id="f4799-183">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="f4799-183">Click Save.</span></span>  
 32. <span data-ttu-id="f4799-184">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f4799-184">Close the page.</span></span>  


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
