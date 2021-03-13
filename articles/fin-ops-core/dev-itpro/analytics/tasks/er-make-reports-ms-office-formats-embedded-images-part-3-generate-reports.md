---
title: Generar informes en los formatos de Office que tengan imágenes incrustadas
description: Este tema describe cómo diseñar las configuraciones de informes electrónicos (ER) para generar documentos electrónicos en Excel y Word que contienen imágenes insertadas.
author: NickSelin
manager: AnnBe
ms.date: 06/13/2017
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
ms.openlocfilehash: 7e15162251e5d6fa91c5a938fd846ef5b5c8cd7f
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093832"
---
# <a name="generate-reports-in-office-format-that-have-embedded-images"></a><span data-ttu-id="fa0fa-103">Generar informes en los formatos de Office que tengan imágenes incrustadas</span><span class="sxs-lookup"><span data-stu-id="fa0fa-103">Generate reports in Office format that have embedded images</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fa0fa-104">En los pasos siguientes se explica cómo un usuario con rol de "Administrador de sistema" o "Desarrollador de informes electrónicos" puede diseñar configuraciones de informe electrónico (ER) para generar documentos electrónicos en formatos de MS Office (Excel y Word) que contienen imágenes incrustadas.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-104">The following steps explain how a user playing either 'System administrator' or 'Electronic reporting developer' role can design Electronic reporting (ER) configurations to generate electronic documents in MS office formats (Excel and Word) containing embedded images.</span></span>

<span data-ttu-id="fa0fa-105">En este ejemplo, usará configuraciones de ER creadas para una empresa de ejemplo "Litware, Inc".</span><span class="sxs-lookup"><span data-stu-id="fa0fa-105">In this example, you will use created ER configurations for sample company, 'Litware, Inc.'.</span></span>  <span data-ttu-id="fa0fa-106">Para completar estos pasos, primero debe completar los pasos de la guía de tareas "ER crea informes en los formatos de MS Office con imágenes incrustadas (Parte 2: Revisar configuraciones)”.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-106">To complete these steps, you must first complete the steps in the "ER Make reports in MS Office formats with embedded images (Part 2: Review configurations)" task guide.</span></span> <span data-ttu-id="fa0fa-107">Estos pasos se pueden llevar a cabo en la empresa "USMF".</span><span class="sxs-lookup"><span data-stu-id="fa0fa-107">These steps can be performed in 'USMF' company.</span></span>


## <a name="run-format-with-initial-model-mapping"></a><span data-ttu-id="fa0fa-108">Ejecutar formato con asignación de modelo inicial</span><span class="sxs-lookup"><span data-stu-id="fa0fa-108">Run format with initial model mapping</span></span>
1. <span data-ttu-id="fa0fa-109">Vaya a Gestión de efectivo y de banco > Cuentas bancarias > Cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-109">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="fa0fa-110">Use un filtro rápido para filtrar por el campo Cuenta bancaria, por el valor ''USMF OPER".</span><span class="sxs-lookup"><span data-stu-id="fa0fa-110">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="fa0fa-111">En el panel de acciones, haga clic en Configurar.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-111">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="fa0fa-112">Haga clic en Comprobar.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-112">Click Check.</span></span>
5. <span data-ttu-id="fa0fa-113">Haga clic en Imprimir prueba.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-113">Click Print test.</span></span>
    * <span data-ttu-id="fa0fa-114">Ejecute el formato para probar.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-114">Run the format for testing purposes.</span></span>  
6. <span data-ttu-id="fa0fa-115">Seleccione Sí en el campo Formato de cheque negociable.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-115">Select Yes in the Negotiable check format field.</span></span>
7. <span data-ttu-id="fa0fa-116">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-116">Click OK.</span></span>
    * <span data-ttu-id="fa0fa-117">Revise el resultado creado.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-117">Review the created output.</span></span> <span data-ttu-id="fa0fa-118">El logotipo de la empresa se mostrará en el informe junto con la firma de la persona autorizada.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-118">The company logo is presented in the report as well as the authorized person's signature.</span></span> <span data-ttu-id="fa0fa-119">La imagen de firma se obtiene en el campo del tipo de datos “Contenedor” del registro de diseño de cheques que está asociado a la cuenta bancaria seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-119">The signature image is taken from the field of the 'Container' data type of the cheque layout record that is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="fa0fa-120">Expanda la sección Copias.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-120">Expand the Copies section.</span></span>
9. <span data-ttu-id="fa0fa-121">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-121">Click Edit.</span></span>
10. <span data-ttu-id="fa0fa-122">En el campo de marca de agua, introduzca "Imprimir marca de agua como Anulada".</span><span class="sxs-lookup"><span data-stu-id="fa0fa-122">In the Watermark field, enter 'Print watermark as Void'.</span></span>
    * <span data-ttu-id="fa0fa-123">Cambie la configuración del diseño de la marca de agua para mostrar el texto de la marca de agua en la generación de documentos en un elemento de forma de Excel.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-123">Change the watermark layout setting to show the watermark text in generating document in an Excel shape element.</span></span>  
11. <span data-ttu-id="fa0fa-124">Haga clic en Imprimir prueba.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-124">Click Print test.</span></span>
12. <span data-ttu-id="fa0fa-125">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-125">Click OK.</span></span>
    * <span data-ttu-id="fa0fa-126">Revise el resultado creado.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-126">Review the created output.</span></span> <span data-ttu-id="fa0fa-127">La marca de agua se mostrará en el informe creado de acuerdo a la opción de selección.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-127">The watermark is shown in the created report in accordance to the selection option.</span></span>  
13. <span data-ttu-id="fa0fa-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-128">Close the page.</span></span>
14. <span data-ttu-id="fa0fa-129">En el panel Acción, haga clic en Administrar pagos.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-129">On the Action Pane, click Manage payments.</span></span>
15. <span data-ttu-id="fa0fa-130">Haga clic en Cheques.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-130">Click Checks.</span></span>
16. <span data-ttu-id="fa0fa-131">Haga clic en Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-131">Click Show filters.</span></span>
17. <span data-ttu-id="fa0fa-132">Aplique los filtros siguientes: escriba un valor de filtro de "381","385","389" en el campo "Número de cheque” con el operador de filtro “es uno de”.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-132">Apply the following filters: Enter a filter value of "381","385","389" on the "Check number" field using the "is one of" filter operator.</span></span>
18. <span data-ttu-id="fa0fa-133">En la lista, marque todas las filas.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-133">In the list, mark all rows.</span></span>
19. <span data-ttu-id="fa0fa-134">Haga clic en Imprimir copia de cheque.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-134">Click Print check copy.</span></span>
    * <span data-ttu-id="fa0fa-135">Ejecute el formato para reimprimir los cheques seleccionados.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-135">Run the format to reprint the selected cheques.</span></span>  
    * <span data-ttu-id="fa0fa-136">Revise el resultado creado.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-136">Review the created output.</span></span> <span data-ttu-id="fa0fa-137">Se han vuelto a imprimir los cheques seleccionados.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-137">The selected cheques have been reprinted.</span></span> <span data-ttu-id="fa0fa-138">El logotipo de la empresa y las etiquetas no se imprimen ya que se muestran en el formulario preimpreso.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-138">The company logo and labels are not printed out since they are presented on the pre-printed form.</span></span>  

## <a name="modify-the-mapping-of-the-imported-data-model"></a><span data-ttu-id="fa0fa-139">Modificar la asignación del modelo de datos importado</span><span class="sxs-lookup"><span data-stu-id="fa0fa-139">Modify the mapping of the imported data model</span></span>
1. <span data-ttu-id="fa0fa-140">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-140">Close the page.</span></span>
2. <span data-ttu-id="fa0fa-141">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-141">Close the page.</span></span>
3. <span data-ttu-id="fa0fa-142">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-142">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="fa0fa-143">En el árbol, seleccione "Modelo para cheques".</span><span class="sxs-lookup"><span data-stu-id="fa0fa-143">In the tree, select 'Model for cheques'.</span></span>
5. <span data-ttu-id="fa0fa-144">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-144">Click Designer.</span></span>
6. <span data-ttu-id="fa0fa-145">Haga clic en Asignar modelo a origen de datos.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-145">Click Map model to datasource.</span></span>
7. <span data-ttu-id="fa0fa-146">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-146">Click Designer.</span></span>
    * <span data-ttu-id="fa0fa-147">Cambiaremos el enlace del elemento de la firma del modelo de datos para obtener la imagen de firma a partir del archivo que se ha adjuntado al registro del diseño de cheques que está asociado a la cuenta bancaria seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-147">We will change the binding of the data model's signature item to get the signature image from the file that has been attached to the cheque layout record that is associated with the selected bank account.</span></span>  
8. <span data-ttu-id="fa0fa-148">Desactive Mostrar detalles.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-148">Turn off Show details.</span></span>
9. <span data-ttu-id="fa0fa-149">En el árbol, expanda "Diseño".</span><span class="sxs-lookup"><span data-stu-id="fa0fa-149">In the tree, expand 'layout'.</span></span>
10. <span data-ttu-id="fa0fa-150">En el árbol, expanda "Diseño\firma".</span><span class="sxs-lookup"><span data-stu-id="fa0fa-150">In the tree, expand 'layout\signature'.</span></span>
11. <span data-ttu-id="fa0fa-151">En el árbol, seleccione "diseño\firma\imagen = cuentadecheque."<Relaciones".DiseñoChequeBancario.Firma1Bmp'.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-151">In the tree, select 'layout\signature\image = chequesaccount.'<Relations'.BankChequeLayout.Signature1Bmp'.</span></span>
12. <span data-ttu-id="fa0fa-152">En el árbol, expanda "cuentadecheque".</span><span class="sxs-lookup"><span data-stu-id="fa0fa-152">In the tree, expand 'chequesaccount'.</span></span>
13. <span data-ttu-id="fa0fa-153">En el árbol, expanda "cuentadecheque\<Relaciones".</span><span class="sxs-lookup"><span data-stu-id="fa0fa-153">In the tree, expand 'chequesaccount\<Relations'.</span></span>
14. <span data-ttu-id="fa0fa-154">En el árbol, expanda "cuentadecheque\<Relaciones\DiseñodeChequeBancario".</span><span class="sxs-lookup"><span data-stu-id="fa0fa-154">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout'.</span></span>
15. <span data-ttu-id="fa0fa-155">En el árbol, expanda "cuentadecheque\<Relaciones\DiseñodeChequeBancario\<Relaciones".</span><span class="sxs-lookup"><span data-stu-id="fa0fa-155">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations'.</span></span>
16. <span data-ttu-id="fa0fa-156">En el árbol, expanda "cuentadecheque\<Relaciones\DiseñodeChequeBancario\<Relaciones\<Documentos'.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-156">In the tree, expand 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents'.</span></span>
17. <span data-ttu-id="fa0fa-157">En el árbol, seleccione 'cuentadecheque\<Relaciones\DiseñodeChequeBancario\<Relaciones\<Documentos\obtenerContenidodeArchivocomoContenedor()'.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-157">In the tree, select 'chequesaccount\<Relations\BankChequeLayout\<Relations\<Documents\getFileContentAsContainer()'.</span></span>
18. <span data-ttu-id="fa0fa-158">Haga clic en Enlazar.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-158">Click Bind.</span></span>
19. <span data-ttu-id="fa0fa-159">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-159">Click Save.</span></span>
20. <span data-ttu-id="fa0fa-160">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-160">Close the page.</span></span>
21. <span data-ttu-id="fa0fa-161">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-161">Close the page.</span></span>
22. <span data-ttu-id="fa0fa-162">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-162">Close the page.</span></span>
23. <span data-ttu-id="fa0fa-163">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-163">Close the page.</span></span>

## <a name="run-format-using-the-adjusted-model-mapping"></a><span data-ttu-id="fa0fa-164">Ejecutar formato con la asignación de modelo ajustado</span><span class="sxs-lookup"><span data-stu-id="fa0fa-164">Run format using the adjusted model mapping</span></span>
1. <span data-ttu-id="fa0fa-165">Vaya a Gestión de efectivo y de banco > Cuentas bancarias > Cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-165">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
2. <span data-ttu-id="fa0fa-166">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-166">Use the Quick Filter to find records.</span></span> <span data-ttu-id="fa0fa-167">Por ejemplo, filtre por el campo Cuenta bancaria, con un valor de 'USMF OPER'.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-167">For example, filter on the Bank account field with a value of 'USMF OPER'.</span></span>
3. <span data-ttu-id="fa0fa-168">En el panel de acciones, haga clic en Configurar.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-168">On the Action Pane, click Set up.</span></span>
4. <span data-ttu-id="fa0fa-169">Haga clic en Comprobar.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-169">Click Check.</span></span>
5. <span data-ttu-id="fa0fa-170">Haga clic en Imprimir prueba.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-170">Click Print test.</span></span>
6. <span data-ttu-id="fa0fa-171">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-171">Click OK.</span></span>
    * <span data-ttu-id="fa0fa-172">Revise el resultado creado.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-172">Review the created output.</span></span> <span data-ttu-id="fa0fa-173">La imagen de los datos adjuntos de la gestión de documentos se muestra como la firma de una persona autorizada.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-173">The image from the Document Management attachment is presented as the signature of an authorized person.</span></span>  

## <a name="use-ms-word-document-as-a-template-in-the-imported-format"></a><span data-ttu-id="fa0fa-174">Use el documento de MS Word como plantilla en el formato importado</span><span class="sxs-lookup"><span data-stu-id="fa0fa-174">Use MS Word document as a template in the imported format</span></span>
1. <span data-ttu-id="fa0fa-175">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-175">Close the page.</span></span>
2. <span data-ttu-id="fa0fa-176">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-176">Close the page.</span></span>
3. <span data-ttu-id="fa0fa-177">Vaya a Administración de la organización > Informes electrónicos > Configuraciones.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-177">Go to Organization administration > Electronic reporting > Configurations.</span></span>
4. <span data-ttu-id="fa0fa-178">En el árbol, expanda "Modelo para cheques".</span><span class="sxs-lookup"><span data-stu-id="fa0fa-178">In the tree, expand 'Model for cheques'.</span></span>
5. <span data-ttu-id="fa0fa-179">En el árbol, seleccione "Modelo para cheques\Formato de impresión de cheques".</span><span class="sxs-lookup"><span data-stu-id="fa0fa-179">In the tree, select 'Model for cheques\Cheques printing format'.</span></span>
6. <span data-ttu-id="fa0fa-180">Haga clic en Diseñador.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-180">Click Designer.</span></span>
7. <span data-ttu-id="fa0fa-181">Haga clic en Archivos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-181">Click Attachments.</span></span>
8. <span data-ttu-id="fa0fa-182">Haga clic Eliminar.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-182">Click Delete.</span></span>
9. <span data-ttu-id="fa0fa-183">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-183">Click Yes.</span></span>
10. <span data-ttu-id="fa0fa-184">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-184">Click New.</span></span>
11. <span data-ttu-id="fa0fa-185">Haga clic en Archivo.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-185">Click File.</span></span>
    * <span data-ttu-id="fa0fa-186">Haga clic en Examinar y seleccione el archivo “Cheque template Word.docx" descargado previamente.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-186">Click Browse and select the downloaded in advance 'Cheque template Word.docx' file.</span></span>  
12. <span data-ttu-id="fa0fa-187">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-187">Close the page.</span></span>
13. <span data-ttu-id="fa0fa-188">En el campo Plantilla, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-188">In the Template field, enter or select a value.</span></span>
14. <span data-ttu-id="fa0fa-189">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-189">Click Save.</span></span>
15. <span data-ttu-id="fa0fa-190">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-190">Close the page.</span></span>
16. <span data-ttu-id="fa0fa-191">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-191">Click Edit.</span></span>
17. <span data-ttu-id="fa0fa-192">Seleccione Sí en el campo Borrador de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-192">Select Yes in the Run Draft field.</span></span>
18. <span data-ttu-id="fa0fa-193">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-193">Close the page.</span></span>
19. <span data-ttu-id="fa0fa-194">Vaya a Gestión de efectivo y de banco > Cuentas bancarias > Cuentas bancarias.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-194">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
20. <span data-ttu-id="fa0fa-195">Use un filtro rápido para filtrar por el campo Cuenta bancaria, por el valor ''USMF OPER".</span><span class="sxs-lookup"><span data-stu-id="fa0fa-195">Use the Quick Filter to filter on the Bank account field with a value of 'USMF OPER'.</span></span>
21. <span data-ttu-id="fa0fa-196">Haga clic en Comprobar.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-196">Click Check.</span></span>
22. <span data-ttu-id="fa0fa-197">Haga clic en Imprimir prueba.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-197">Click Print test.</span></span>
23. <span data-ttu-id="fa0fa-198">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-198">Click OK.</span></span>
    * <span data-ttu-id="fa0fa-199">Revise el resultado creado.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-199">Review the created output.</span></span> <span data-ttu-id="fa0fa-200">El resultado se ha generado como documento de Word con las imágenes incrustadas que presentan el logotipo de la empresa, la firma de una persona autorizada y el texto seleccionado de la marca de agua.</span><span class="sxs-lookup"><span data-stu-id="fa0fa-200">The output has been generated as a Word document with embedded images presenting the company logo, the signature of an authorized person and the selected text of the watermark.</span></span>  

