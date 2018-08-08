---
title: "Solución de problemas de la importación de archivos de extractos bancarios"
description: "Es importante que el archivo de extracto bancario del banco coincida con el diseño admitido por Microsoft Dynamics 365 for Finance and Operations. Debido a los estrictos estándares para extractos bancarios, la mayoría de las integraciones funcionarán correctamente. Sin embargo, a veces, el archivo de extracto no se puede importar o tiene resultados incorrectos. Normalmente, estos problemas son originados por pequeñas diferencias en el archivo de extracto bancario. En este artículo se explica cómo corregir estas diferencias y resolver los problemas."
author: ShylaThompson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: a4006bf35673e3bb61bcf11619ecc68d295f29eb
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---

# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="a1f88-107">Solución de problemas de la importación de archivos de extractos bancarios</span><span class="sxs-lookup"><span data-stu-id="a1f88-107">Bank statement file import troubleshooting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a1f88-108">Es importante que el archivo de extracto bancario del banco coincida con el diseño admitido por Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a1f88-108">It's important that the bank statement file from the bank match the layout that Microsoft Dynamics 365 for Finance and Operations supports.</span></span> <span data-ttu-id="a1f88-109">Debido a los estrictos estándares para extractos bancarios, la mayoría de las integraciones funcionarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="a1f88-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="a1f88-110">Sin embargo, a veces, el archivo de extracto no se puede importar o tiene resultados incorrectos.</span><span class="sxs-lookup"><span data-stu-id="a1f88-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="a1f88-111">Normalmente, estos problemas son originados por pequeñas diferencias en el archivo de extracto bancario.</span><span class="sxs-lookup"><span data-stu-id="a1f88-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="a1f88-112">En este artículo se explica cómo corregir estas diferencias y resolver los problemas.</span><span class="sxs-lookup"><span data-stu-id="a1f88-112">This article explains how to fix these differences and resolve the issues.</span></span>

<a name="what-is-the-error"></a><span data-ttu-id="a1f88-113">¿Qué es el error?</span><span class="sxs-lookup"><span data-stu-id="a1f88-113">What is the error?</span></span>
------------------

<span data-ttu-id="a1f88-114">Tras intentar importar un archivo de extracto bancario, vaya al historial de trabajos de administración de datos y sus detalles de ejecución para encontrar el error.</span><span class="sxs-lookup"><span data-stu-id="a1f88-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="a1f88-115">El error puede resultar de ayuda al señalar la instrucción, el saldo o la línea de extracto.</span><span class="sxs-lookup"><span data-stu-id="a1f88-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="a1f88-116">Sin embargo, es poco probable que proporcione suficiente información para ayudarle a identificar el campo o el elemento que está ocasionando el problema.</span><span class="sxs-lookup"><span data-stu-id="a1f88-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="a1f88-117">¿Cuáles son las diferencias?</span><span class="sxs-lookup"><span data-stu-id="a1f88-117">What are the differences?</span></span>
<span data-ttu-id="a1f88-118">Compare la definición del diseño de archivos de banco con la definición de importación de Finance and Operations y observe los posibles diferencias en los campos y elementos.</span><span class="sxs-lookup"><span data-stu-id="a1f88-118">Compare the bank file layout definition to the Finance and Operations import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="a1f88-119">Compare el archivo de extracto bancario con el archivo de muestra relacionado de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a1f88-119">Compare the bank statement file to the related sample Finance and Operations file.</span></span> <span data-ttu-id="a1f88-120">En los archivos ISO20022 las diferencia se verán fácilmente.</span><span class="sxs-lookup"><span data-stu-id="a1f88-120">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="transformations"></a><span data-ttu-id="a1f88-121">Transformaciones</span><span class="sxs-lookup"><span data-stu-id="a1f88-121">Transformations</span></span>
<span data-ttu-id="a1f88-122">Normalmente, el cambio se debe realizar en una de tres transformaciones.</span><span class="sxs-lookup"><span data-stu-id="a1f88-122">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="a1f88-123">Cada transformación se escribe para un estándar específico.</span><span class="sxs-lookup"><span data-stu-id="a1f88-123">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="a1f88-124">Nombre del recurso</span><span class="sxs-lookup"><span data-stu-id="a1f88-124">Resource name</span></span>                                         | <span data-ttu-id="a1f88-125">Nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="a1f88-125">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="a1f88-126">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="a1f88-126">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="a1f88-127">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="a1f88-127">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="a1f88-128">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="a1f88-128">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="a1f88-129">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="a1f88-129">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="a1f88-130">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="a1f88-130">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="a1f88-131">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="a1f88-131">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="a1f88-132">Depuración de transformaciones</span><span class="sxs-lookup"><span data-stu-id="a1f88-132">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="a1f88-133">Ajustar los archivos BAI2 y MT940</span><span class="sxs-lookup"><span data-stu-id="a1f88-133">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="a1f88-134">Los archivos BAI2 y MT940 son archivos basados en texto y requieren un ajuste para habilitar la depuración del Lenguaje de transformación basado en hojas de estilo (XSLT).</span><span class="sxs-lookup"><span data-stu-id="a1f88-134">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="a1f88-135">El programa realiza este ajuste cuando se importa un archivo.</span><span class="sxs-lookup"><span data-stu-id="a1f88-135">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="a1f88-136">Cree un archivo XML y copie el siguiente texto en él.</span><span class="sxs-lookup"><span data-stu-id="a1f88-136">Create an XML file, and copy the following text into it.</span></span>

        <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>

2.  <span data-ttu-id="a1f88-137">Copie el contenido del archivo de extracto bancario y péguelo en el archivo XML de modo que reemplace **PASTESTATEMENTFILEHERE**.</span><span class="sxs-lookup"><span data-stu-id="a1f88-137">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="a1f88-138">Depurar XSLT</span><span class="sxs-lookup"><span data-stu-id="a1f88-138">Debug the XSLT</span></span>

<span data-ttu-id="a1f88-139">Para obtener más información, vea <https://msdn.microsoft.com/en-us/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="a1f88-139">For more information, see <https://msdn.microsoft.com/en-us/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="a1f88-140">Inicie Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a1f88-140">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="a1f88-141">Crear una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="a1f88-141">Create a console application.</span></span>
3.  <span data-ttu-id="a1f88-142">Abra el XSLT adecuado.</span><span class="sxs-lookup"><span data-stu-id="a1f88-142">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="a1f88-143">Haga clic en el XLST y su página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="a1f88-143">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="a1f88-144">Establezca la entrada en la ubicación del archivo del extracto bancario.</span><span class="sxs-lookup"><span data-stu-id="a1f88-144">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="a1f88-145">Defina una ubicación y un nombre de archivo para la salida.</span><span class="sxs-lookup"><span data-stu-id="a1f88-145">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="a1f88-146">Establezca los puntos de interrupción necesarios.</span><span class="sxs-lookup"><span data-stu-id="a1f88-146">Set the required break points.</span></span>
8.  <span data-ttu-id="a1f88-147">En el menú, haga clic en **XML** &gt; **Iniciar depuración de XSLT**.</span><span class="sxs-lookup"><span data-stu-id="a1f88-147">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="a1f88-148">Aplicar formato a la salida de XSLT</span><span class="sxs-lookup"><span data-stu-id="a1f88-148">Format the XSLT output</span></span>

<span data-ttu-id="a1f88-149">Cuando se ejecuta la transformación, crea un archivo de salida que pueda ver en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a1f88-149">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="a1f88-150">Use Ctrl+A, Ctrl+K y Ctrl+D para dar formato rápidamente al archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="a1f88-150">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="a1f88-151">Ajustar la transformación</span><span class="sxs-lookup"><span data-stu-id="a1f88-151">Adjust the transformation</span></span>

<span data-ttu-id="a1f88-152">Ajuste la transformación para obtener el elemento o el campo adecuado en el archivo de extracto bancario.</span><span class="sxs-lookup"><span data-stu-id="a1f88-152">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="a1f88-153">A continuación, asigne ese campo o artículo al elemento de Finance and Operations adecuado.</span><span class="sxs-lookup"><span data-stu-id="a1f88-153">Then map that field or element to the appropriate Finance and Operations element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="a1f88-154">Indicador de débito o crédito</span><span class="sxs-lookup"><span data-stu-id="a1f88-154">Debit/credit indicator</span></span>

<span data-ttu-id="a1f88-155">A veces, los débitos se pueden importar como créditos y los créditos se pueden importar como débitos.</span><span class="sxs-lookup"><span data-stu-id="a1f88-155">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="a1f88-156">Para resolver este problema, debe cambiar el XSLT adecuado.</span><span class="sxs-lookup"><span data-stu-id="a1f88-156">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="a1f88-157">Si los extractos bancarios proceden de varios bancos, asegúrese de que todos usen el mismo enfoque de débito/crédito o cree transformaciones independientes.</span><span class="sxs-lookup"><span data-stu-id="a1f88-157">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="a1f88-158">Plantilla GetAmountCreditDebitIndicator de BAI2XML-to-Reconciliation.xlst</span><span class="sxs-lookup"><span data-stu-id="a1f88-158">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="a1f88-159">Plantilla GetCreditDebit de ISO20022XML-to-Reconcilation.xslt</span><span class="sxs-lookup"><span data-stu-id="a1f88-159">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="a1f88-160">Plantilla GetCreditDebitIndicator de MT940XML-to-Reconcilation.xslt</span><span class="sxs-lookup"><span data-stu-id="a1f88-160">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="a1f88-161">Ejemplos de diseños técnicos y formatos de extracto bancario</span><span class="sxs-lookup"><span data-stu-id="a1f88-161">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="a1f88-162">En la tabla siguiente se muestran ejemplos de las definiciones de diseño técnico para los archivos de importación de conciliación bancaria avanzados y tres archivos de ejemplo de extracto bancario relacionados.</span><span class="sxs-lookup"><span data-stu-id="a1f88-162">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="a1f88-163">Puede descargar los archivos de ejemplo y los diseños técnicos aquí: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span><span class="sxs-lookup"><span data-stu-id="a1f88-163">You can download the example files and technical layouts here: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span></span>  


| <span data-ttu-id="a1f88-164">Definición de diseño técnico</span><span class="sxs-lookup"><span data-stu-id="a1f88-164">Technical layout definition</span></span>                             | <span data-ttu-id="a1f88-165">Archivo de ejemplo de extracto bancario</span><span class="sxs-lookup"><span data-stu-id="a1f88-165">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="a1f88-166">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="a1f88-166">DynamicsAXMT940Layout</span></span>                                   | <span data-ttu-id="a1f88-167">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="a1f88-167">MT940StatementExample</span></span>                |
| <span data-ttu-id="a1f88-168">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="a1f88-168">DynamicsAXISO20022Layout</span></span>                                | <span data-ttu-id="a1f88-169">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="a1f88-169">ISO20022StatementExample</span></span>             |
| <span data-ttu-id="a1f88-170">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="a1f88-170">DynamicsAXBAI2Layout</span></span>                                    | <span data-ttu-id="a1f88-171">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="a1f88-171">BAI2StatementExample</span></span>                 |






