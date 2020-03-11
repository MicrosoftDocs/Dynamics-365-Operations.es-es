---
title: Solución de problemas de la importación de archivos de extractos bancarios
description: Es importante que el archivo de extracto bancario del banco coincida con el diseño admitido por Microsoft Dynamics 365 Finance. Debido a los estrictos estándares para extractos bancarios, la mayoría de las integraciones funcionarán correctamente. Sin embargo, a veces, el archivo de extracto no se puede importar o tiene resultados incorrectos. Normalmente, estos problemas son originados por pequeñas diferencias en el archivo de extracto bancario. En este artículo se explica cómo corregir estas diferencias y resolver los problemas.
author: ShylaThompson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5e7e6897f19dc0303ffbd3111f93669a91daa1b
ms.sourcegitcommit: 4f668b23f5bfc6d6502858850d2ed59d7a79cfbb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "3059385"
---
# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="e2b5f-107">Solución de problemas de la importación de archivos de extractos bancarios</span><span class="sxs-lookup"><span data-stu-id="e2b5f-107">Bank statement file import troubleshooting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e2b5f-108">Es importante que el archivo de extracto bancario del banco coincida con el diseño admitido por Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-108">It's important that the bank statement file from the bank match the layout that Microsoft Dynamics 365 Finance supports.</span></span> <span data-ttu-id="e2b5f-109">Debido a los estrictos estándares para extractos bancarios, la mayoría de las integraciones funcionarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="e2b5f-110">Sin embargo, a veces, el archivo de extracto no se puede importar o tiene resultados incorrectos.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="e2b5f-111">Normalmente, estos problemas son originados por pequeñas diferencias en el archivo de extracto bancario.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="e2b5f-112">En este artículo se explica cómo corregir estas diferencias y resolver los problemas.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-112">This article explains how to fix these differences and resolve the issues.</span></span>

<a name="what-is-the-error"></a><span data-ttu-id="e2b5f-113">¿Qué es el error?</span><span class="sxs-lookup"><span data-stu-id="e2b5f-113">What is the error?</span></span>
------------------

<span data-ttu-id="e2b5f-114">Tras intentar importar un archivo de extracto bancario, vaya al historial de trabajos de administración de datos y sus detalles de ejecución para encontrar el error.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="e2b5f-115">El error puede resultar de ayuda al señalar la instrucción, el saldo o la línea de extracto.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="e2b5f-116">Sin embargo, es poco probable que proporcione suficiente información para ayudarle a identificar el campo o el elemento que está ocasionando el problema.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="e2b5f-117">¿Cuáles son las diferencias?</span><span class="sxs-lookup"><span data-stu-id="e2b5f-117">What are the differences?</span></span>
<span data-ttu-id="e2b5f-118">Compare la definición del diseño de archivos de banco con la definición de importación de Finance y observe los posibles diferencias en los campos y elementos.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-118">Compare the bank file layout definition to the Finance import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="e2b5f-119">Compare el archivo de extracto bancario con el archivo de muestra relacionado de Finance.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-119">Compare the bank statement file to the related sample Finance file.</span></span> <span data-ttu-id="e2b5f-120">En los archivos ISO20022 las diferencia se verán fácilmente.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-120">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="time-zone-differences-on-imported-bank-statements"></a><span data-ttu-id="e2b5f-121">Diferencias de zona horaria de extractos bancarios importados</span><span class="sxs-lookup"><span data-stu-id="e2b5f-121">Time zone differences on imported bank statements</span></span>
<span data-ttu-id="e2b5f-122">Los valores de fecha y hora en el archivo de importación pueden ser distintos de los valores de fecha y hora que se muestran en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-122">The date-time values in the import file can differ from the date-time values that are shown in Finance and Operations.</span></span> <span data-ttu-id="e2b5f-123">Para evitar esta discrepancia, especifique una preferencia de zona horaria en la página **Configurar orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-123">To prevent this discrepancy, enter a time zone preference on the **Configure data sources** page.</span></span> <span data-ttu-id="e2b5f-124">Consulte [Configurar el proceso avanzado de importación de conciliación bancaria](set-up-advanced-bank-reconciliation-import-process.md) para obtener más información sobre cómo especificar una preferencia de zona horaria.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-124">See [Set up the advanced bank reconciliation import process](set-up-advanced-bank-reconciliation-import-process.md) for more information about entering a time zone preference.</span></span>

## <a name="transformations"></a><span data-ttu-id="e2b5f-125">Transformaciones</span><span class="sxs-lookup"><span data-stu-id="e2b5f-125">Transformations</span></span>
<span data-ttu-id="e2b5f-126">Normalmente, el cambio se debe realizar en una de tres transformaciones.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-126">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="e2b5f-127">Cada transformación se escribe para un estándar específico.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-127">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="e2b5f-128">Nombre del recurso</span><span class="sxs-lookup"><span data-stu-id="e2b5f-128">Resource name</span></span>                                         | <span data-ttu-id="e2b5f-129">Nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="e2b5f-129">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="e2b5f-130">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="e2b5f-130">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="e2b5f-131">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="e2b5f-131">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="e2b5f-132">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="e2b5f-132">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="e2b5f-133">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="e2b5f-133">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="e2b5f-134">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="e2b5f-134">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="e2b5f-135">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="e2b5f-135">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="e2b5f-136">Depuración de transformaciones</span><span class="sxs-lookup"><span data-stu-id="e2b5f-136">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="e2b5f-137">Ajustar los archivos BAI2 y MT940</span><span class="sxs-lookup"><span data-stu-id="e2b5f-137">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="e2b5f-138">Los archivos BAI2 y MT940 son archivos basados en texto y requieren un ajuste para habilitar la depuración del Lenguaje de transformación basado en hojas de estilo (XSLT).</span><span class="sxs-lookup"><span data-stu-id="e2b5f-138">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="e2b5f-139">El programa realiza este ajuste cuando se importa un archivo.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-139">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="e2b5f-140">Cree un archivo XML y copie el siguiente texto en él.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-140">Create an XML file, and copy the following text into it.</span></span>

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  <span data-ttu-id="e2b5f-141">Copie el contenido del archivo de extracto bancario y péguelo en el archivo XML de modo que reemplace **PASTESTATEMENTFILEHERE**.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-141">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="e2b5f-142">Depurar XSLT</span><span class="sxs-lookup"><span data-stu-id="e2b5f-142">Debug the XSLT</span></span>

<span data-ttu-id="e2b5f-143">Para obtener más información, vea <https://msdn.microsoft.com/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-143">For more information, see <https://msdn.microsoft.com/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="e2b5f-144">Iniciar Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-144">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="e2b5f-145">Crear una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-145">Create a console application.</span></span>
3.  <span data-ttu-id="e2b5f-146">Abra el XSLT adecuado.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-146">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="e2b5f-147">Haga clic en el XLST y su página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-147">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="e2b5f-148">Establezca la entrada en la ubicación del archivo del extracto bancario.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-148">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="e2b5f-149">Defina una ubicación y un nombre de archivo para la salida.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-149">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="e2b5f-150">Establezca los puntos de interrupción necesarios.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-150">Set the required break points.</span></span>
8.  <span data-ttu-id="e2b5f-151">En el menú, haga clic en **XML** &gt; **Iniciar depuración de XSLT**.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-151">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="e2b5f-152">Aplicar formato a la salida de XSLT</span><span class="sxs-lookup"><span data-stu-id="e2b5f-152">Format the XSLT output</span></span>

<span data-ttu-id="e2b5f-153">Cuando se ejecuta la transformación, crea un archivo de salida que pueda ver en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-153">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="e2b5f-154">Use Ctrl+A, Ctrl+K y Ctrl+D para dar formato rápidamente al archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-154">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="e2b5f-155">Ajustar la transformación</span><span class="sxs-lookup"><span data-stu-id="e2b5f-155">Adjust the transformation</span></span>

<span data-ttu-id="e2b5f-156">Ajuste la transformación para obtener el elemento o el campo adecuado en el archivo de extracto bancario.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-156">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="e2b5f-157">A continuación, asigne ese campo o artículo al elemento de Finance adecuado.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-157">Then map that field or element to the appropriate Finance element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="e2b5f-158">Indicador de débito o crédito</span><span class="sxs-lookup"><span data-stu-id="e2b5f-158">Debit/credit indicator</span></span>

<span data-ttu-id="e2b5f-159">A veces, los débitos se pueden importar como créditos y los créditos se pueden importar como débitos.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-159">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="e2b5f-160">Para resolver este problema, debe cambiar el XSLT adecuado.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-160">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="e2b5f-161">Si los extractos bancarios proceden de varios bancos, asegúrese de que todos usen el mismo enfoque de débito/crédito o cree transformaciones independientes.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-161">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="e2b5f-162">Plantilla GetAmountCreditDebitIndicator de BAI2XML-to-Reconciliation.xlst</span><span class="sxs-lookup"><span data-stu-id="e2b5f-162">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="e2b5f-163">Plantilla GetCreditDebit de ISO20022XML-to-Reconcilation.xslt</span><span class="sxs-lookup"><span data-stu-id="e2b5f-163">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="e2b5f-164">Plantilla GetCreditDebitIndicator de MT940XML-to-Reconcilation.xslt</span><span class="sxs-lookup"><span data-stu-id="e2b5f-164">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="e2b5f-165">Ejemplos de diseños técnicos y formatos de extracto bancario</span><span class="sxs-lookup"><span data-stu-id="e2b5f-165">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="e2b5f-166">En la tabla siguiente se muestran ejemplos de las definiciones de diseño técnico para los archivos de importación de conciliación bancaria avanzados y tres archivos de ejemplo de extracto bancario relacionados.</span><span class="sxs-lookup"><span data-stu-id="e2b5f-166">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="e2b5f-167">Puede descargar los archivos de ejemplo y los diseños técnicos aquí: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span><span class="sxs-lookup"><span data-stu-id="e2b5f-167">You can download the example files and technical layouts here: https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/exofbankstfotechlayouts</span></span>  


| <span data-ttu-id="e2b5f-168">Definición de diseño técnico</span><span class="sxs-lookup"><span data-stu-id="e2b5f-168">Technical layout definition</span></span>                             | <span data-ttu-id="e2b5f-169">Archivo de ejemplo de extracto bancario</span><span class="sxs-lookup"><span data-stu-id="e2b5f-169">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="e2b5f-170">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="e2b5f-170">DynamicsAXMT940Layout</span></span>                                   | <span data-ttu-id="e2b5f-171">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="e2b5f-171">MT940StatementExample</span></span>                |
| <span data-ttu-id="e2b5f-172">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="e2b5f-172">DynamicsAXISO20022Layout</span></span>                                | <span data-ttu-id="e2b5f-173">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="e2b5f-173">ISO20022StatementExample</span></span>             |
| <span data-ttu-id="e2b5f-174">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="e2b5f-174">DynamicsAXBAI2Layout</span></span>                                    | <span data-ttu-id="e2b5f-175">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="e2b5f-175">BAI2StatementExample</span></span>                 |





