---
title: Solución de problemas de la importación de archivos de extractos bancarios
description: Es importante que el archivo de extracto bancario del banco coincida con el diseño admitido por Microsoft Dynamics 365 Finance. Debido a los estrictos estándares para extractos bancarios, la mayoría de las integraciones funcionarán correctamente. Sin embargo, a veces, el archivo de extracto no se puede importar o tiene resultados incorrectos. Normalmente, estos problemas son originados por pequeñas diferencias en el archivo de extracto bancario. En este artículo se explica cómo corregir estas diferencias y resolver los problemas.
author: panolte
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: roschlom
ms.custom: 141273
ms.assetid: 3ee2f32b-02aa-420b-8990-e6aa5fc6bda3
ms.search.region: global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 14f0e480b93e663f81db5a1edb2ae71b559bb05e
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188569"
---
# <a name="bank-statement-file-import-troubleshooting"></a><span data-ttu-id="0b69b-107">Solución de problemas de la importación de archivos de extractos bancarios</span><span class="sxs-lookup"><span data-stu-id="0b69b-107">Bank statement file import troubleshooting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0b69b-108">Es importante que el archivo de extracto bancario del banco coincida con el diseño admitido por Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="0b69b-108">It's important that the bank statement file from the bank matches the layout that Microsoft Dynamics 365 Finance supports.</span></span> <span data-ttu-id="0b69b-109">Debido a los estrictos estándares para extractos bancarios, la mayoría de las integraciones funcionarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="0b69b-109">Because of strict standards for bank statements, most integrations will work correctly.</span></span> <span data-ttu-id="0b69b-110">Sin embargo, a veces, el archivo de extracto no se puede importar o tiene resultados incorrectos.</span><span class="sxs-lookup"><span data-stu-id="0b69b-110">However, sometimes the statement file can't be imported or has incorrect results.</span></span> <span data-ttu-id="0b69b-111">Normalmente, estos problemas son originados por pequeñas diferencias en el archivo de extracto bancario.</span><span class="sxs-lookup"><span data-stu-id="0b69b-111">Typically, these issues are caused by small differences in the bank statement file.</span></span> <span data-ttu-id="0b69b-112">En este artículo se explica cómo corregir estas diferencias y resolver los problemas.</span><span class="sxs-lookup"><span data-stu-id="0b69b-112">This article explains how to fix these differences and resolve the issues.</span></span>

## <a name="what-is-the-error"></a><span data-ttu-id="0b69b-113">¿Qué es el error?</span><span class="sxs-lookup"><span data-stu-id="0b69b-113">What is the error?</span></span>

<span data-ttu-id="0b69b-114">Tras intentar importar un archivo de extracto bancario, vaya al historial de trabajos de administración de datos y sus detalles de ejecución para encontrar el error.</span><span class="sxs-lookup"><span data-stu-id="0b69b-114">After you try to import a bank statement file, go to the Data management job history and its execution details to find the error.</span></span> <span data-ttu-id="0b69b-115">El error puede resultar de ayuda al señalar la instrucción, el saldo o la línea de extracto.</span><span class="sxs-lookup"><span data-stu-id="0b69b-115">The error can help by pointing to the statement, balance, or statement line.</span></span> <span data-ttu-id="0b69b-116">Sin embargo, es poco probable que proporcione suficiente información para ayudarle a identificar el campo o el elemento que está ocasionando el problema.</span><span class="sxs-lookup"><span data-stu-id="0b69b-116">However, it's unlikely to provide enough information to help you identify the field or element that is causing the issue.</span></span>

> [!NOTE]
> <span data-ttu-id="0b69b-117">Los extractos bancarios importados pueden superponerse solo en un momento determinado del tiempo.</span><span class="sxs-lookup"><span data-stu-id="0b69b-117">Imported bank statements can overlap only for single a point in time.</span></span>  <span data-ttu-id="0b69b-118">Por ejemplo, si un extracto finaliza a las 12:00 a. m. del 1 de enero de 2021, la fecha de inicio del siguiente extracto puede ser las 12:00 a. m. del 1 de enero de 2021 12:00:00 a. m.</span><span class="sxs-lookup"><span data-stu-id="0b69b-118">For example, if a statement ends at 12:00 AM on January 1, 2021, then beginning date for the next statement can be 12:00 AM on Jarnuary 1, 2021 12:00:00 AM.</span></span>

## <a name="what-are-the-differences"></a><span data-ttu-id="0b69b-119">¿Cuáles son las diferencias?</span><span class="sxs-lookup"><span data-stu-id="0b69b-119">What are the differences?</span></span>
<span data-ttu-id="0b69b-120">Compare la definición del diseño de archivos de banco con la definición de importación de Finance y observe los posibles diferencias en los campos y elementos.</span><span class="sxs-lookup"><span data-stu-id="0b69b-120">Compare the bank file layout definition to the Finance import definition, and note any differences in the fields and elements.</span></span> <span data-ttu-id="0b69b-121">Compare el archivo de extracto bancario con el archivo de muestra relacionado de Finance.</span><span class="sxs-lookup"><span data-stu-id="0b69b-121">Compare the bank statement file to the related sample Finance file.</span></span> <span data-ttu-id="0b69b-122">En los archivos ISO20022 las diferencia se verán fácilmente.</span><span class="sxs-lookup"><span data-stu-id="0b69b-122">In the ISO20022 files, any differences should be easy to see.</span></span>

## <a name="time-zone-differences-on-imported-bank-statements"></a><span data-ttu-id="0b69b-123">Diferencias de zona horaria de extractos bancarios importados</span><span class="sxs-lookup"><span data-stu-id="0b69b-123">Time zone differences on imported bank statements</span></span>
<span data-ttu-id="0b69b-124">Los valores de fecha y hora en el archivo de importación pueden ser distintos de los valores de fecha y hora que se muestran en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0b69b-124">The date-time values in the import file can differ from the date-time values that are shown in Finance and Operations.</span></span> <span data-ttu-id="0b69b-125">Para evitar esta discrepancia, especifique una preferencia de zona horaria en la página **Configurar orígenes de datos**.</span><span class="sxs-lookup"><span data-stu-id="0b69b-125">To prevent this discrepancy, enter a time zone preference on the **Configure data sources** page.</span></span> <span data-ttu-id="0b69b-126">Para obtener más información sobre cómo especificar una preferencia de zona horaria, consulte [Configurar el proceso avanzado de importación de conciliación bancaria](set-up-advanced-bank-reconciliation-import-process.md).</span><span class="sxs-lookup"><span data-stu-id="0b69b-126">For more information about entering a time zone preference, see [Set up the advanced bank reconciliation import process](set-up-advanced-bank-reconciliation-import-process.md).</span></span>

## <a name="transformations"></a><span data-ttu-id="0b69b-127">Transformaciones</span><span class="sxs-lookup"><span data-stu-id="0b69b-127">Transformations</span></span>
<span data-ttu-id="0b69b-128">Normalmente, el cambio se debe realizar en una de tres transformaciones.</span><span class="sxs-lookup"><span data-stu-id="0b69b-128">Typically, the change must be made in one of three transformations.</span></span> <span data-ttu-id="0b69b-129">Cada transformación se escribe para un estándar específico.</span><span class="sxs-lookup"><span data-stu-id="0b69b-129">Each transformation is written for a specific standard.</span></span>

| <span data-ttu-id="0b69b-130">Nombre del recurso</span><span class="sxs-lookup"><span data-stu-id="0b69b-130">Resource name</span></span>                                         | <span data-ttu-id="0b69b-131">Nombre de archivo</span><span class="sxs-lookup"><span data-stu-id="0b69b-131">File name</span></span>                          |
|-------------------------------------------------------|------------------------------------|
| <span data-ttu-id="0b69b-132">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="0b69b-132">BankStmtImport\_BAI2CSV\_to\_BAI2XML\_xslt</span></span>            | <span data-ttu-id="0b69b-133">BAI2CSV-to-BAI2XML.xslt</span><span class="sxs-lookup"><span data-stu-id="0b69b-133">BAI2CSV-to-BAI2XML.xslt</span></span>            |
| <span data-ttu-id="0b69b-134">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span><span class="sxs-lookup"><span data-stu-id="0b69b-134">BankStmtImport\_ISO20022XML\_to\_Reconciliation\_xslt</span></span> | <span data-ttu-id="0b69b-135">ISO20022XML-to-Reconciliation.xslt</span><span class="sxs-lookup"><span data-stu-id="0b69b-135">ISO20022XML-to-Reconciliation.xslt</span></span> |
| <span data-ttu-id="0b69b-136">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span><span class="sxs-lookup"><span data-stu-id="0b69b-136">BankStmtImport\_MT940TXT\_to\_MT940XML\_xslt</span></span>          | <span data-ttu-id="0b69b-137">MT940TXT-to-MT940XML.xslt</span><span class="sxs-lookup"><span data-stu-id="0b69b-137">MT940TXT-to-MT940XML.xslt</span></span>          |

## <a name="debugging-transformations"></a><span data-ttu-id="0b69b-138">Depuración de transformaciones</span><span class="sxs-lookup"><span data-stu-id="0b69b-138">Debugging transformations</span></span>
### <a name="adjust-the-bai2-and-mt940-files"></a><span data-ttu-id="0b69b-139">Ajustar los archivos BAI2 y MT940</span><span class="sxs-lookup"><span data-stu-id="0b69b-139">Adjust the BAI2 and MT940 files</span></span>

<span data-ttu-id="0b69b-140">Los archivos BAI2 y MT940 son archivos basados en texto y requieren un ajuste para habilitar la depuración del Lenguaje de transformación basado en hojas de estilo (XSLT).</span><span class="sxs-lookup"><span data-stu-id="0b69b-140">The BAI2 and MT940 files are text-based files and require an adjustment to enable Extensible Stylesheet Language Transformations (XSLT) debugging.</span></span> <span data-ttu-id="0b69b-141">El programa realiza este ajuste cuando se importa un archivo.</span><span class="sxs-lookup"><span data-stu-id="0b69b-141">The program makes this adjustment when a file is imported.</span></span>

1.  <span data-ttu-id="0b69b-142">Cree un archivo XML y copie el siguiente texto en él.</span><span class="sxs-lookup"><span data-stu-id="0b69b-142">Create an XML file, and copy the following text into it.</span></span>

    ```xml
    <Batch><![CDATA[PASTESTATEMENTFILEHERE
        ]]></Batch>
    ```
    
2.  <span data-ttu-id="0b69b-143">Copie el contenido del archivo de extracto bancario y péguelo en el archivo XML de modo que reemplace **PASTESTATEMENTFILEHERE**.</span><span class="sxs-lookup"><span data-stu-id="0b69b-143">Copy the contents of the bank statement file, and paste them into the XML file so that they replace **PASTESTATEMENTFILEHERE**.</span></span>

### <a name="debug-the-xslt"></a><span data-ttu-id="0b69b-144">Depurar XSLT</span><span class="sxs-lookup"><span data-stu-id="0b69b-144">Debug the XSLT</span></span>

<span data-ttu-id="0b69b-145">Para obtener más información, vea <https://msdn.microsoft.com/library/ms255605.aspx>.</span><span class="sxs-lookup"><span data-stu-id="0b69b-145">For more information, see <https://msdn.microsoft.com/library/ms255605.aspx>.</span></span>

1.  <span data-ttu-id="0b69b-146">Iniciar Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0b69b-146">Start Microsoft Visual Studio.</span></span>
2.  <span data-ttu-id="0b69b-147">Crear una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="0b69b-147">Create a console application.</span></span>
3.  <span data-ttu-id="0b69b-148">Abra el XSLT adecuado.</span><span class="sxs-lookup"><span data-stu-id="0b69b-148">Open the appropriate XSLT.</span></span>
4.  <span data-ttu-id="0b69b-149">Haga clic en el XLST y su página de propiedades.</span><span class="sxs-lookup"><span data-stu-id="0b69b-149">Click the XLST and its properties page.</span></span>
5.  <span data-ttu-id="0b69b-150">Establezca la entrada en la ubicación del archivo del extracto bancario.</span><span class="sxs-lookup"><span data-stu-id="0b69b-150">Set the input to the location of the bank statement file.</span></span>
6.  <span data-ttu-id="0b69b-151">Defina una ubicación y un nombre de archivo para la salida.</span><span class="sxs-lookup"><span data-stu-id="0b69b-151">Define a location and file name for the output.</span></span>
7.  <span data-ttu-id="0b69b-152">Establezca los puntos de interrupción necesarios.</span><span class="sxs-lookup"><span data-stu-id="0b69b-152">Set the required break points.</span></span>
8.  <span data-ttu-id="0b69b-153">En el menú, haga clic en **XML** &gt; **Iniciar depuración de XSLT**.</span><span class="sxs-lookup"><span data-stu-id="0b69b-153">On the menu, click **XML** &gt; **Start XSLT Debugging**.</span></span>

### <a name="format-the-xslt-output"></a><span data-ttu-id="0b69b-154">Aplicar formato a la salida de XSLT</span><span class="sxs-lookup"><span data-stu-id="0b69b-154">Format the XSLT output</span></span>

<span data-ttu-id="0b69b-155">Cuando se ejecuta la transformación, crea un archivo de salida que pueda ver en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0b69b-155">When the transformation runs, it creates an output file that you can view in Visual Studio.</span></span> <span data-ttu-id="0b69b-156">Use Ctrl+A, Ctrl+K y Ctrl+D para dar formato rápidamente al archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="0b69b-156">Use Ctrl+A, Ctrl+K, and Ctrl+D to quickly format the output file.</span></span>

### <a name="adjust-the-transformation"></a><span data-ttu-id="0b69b-157">Ajustar la transformación</span><span class="sxs-lookup"><span data-stu-id="0b69b-157">Adjust the transformation</span></span>

<span data-ttu-id="0b69b-158">Ajuste la transformación para obtener el elemento o el campo adecuado en el archivo de extracto bancario.</span><span class="sxs-lookup"><span data-stu-id="0b69b-158">Adjust the transformation to get the appropriate field or element in the bank statement file.</span></span> <span data-ttu-id="0b69b-159">A continuación, asigne ese campo o artículo al elemento de Finance adecuado.</span><span class="sxs-lookup"><span data-stu-id="0b69b-159">Then map that field or element to the appropriate Finance element.</span></span>

### <a name="debitcredit-indicator"></a><span data-ttu-id="0b69b-160">Indicador de débito o crédito</span><span class="sxs-lookup"><span data-stu-id="0b69b-160">Debit/credit indicator</span></span>

<span data-ttu-id="0b69b-161">A veces, los débitos se pueden importar como créditos y los créditos se pueden importar como débitos.</span><span class="sxs-lookup"><span data-stu-id="0b69b-161">Sometimes, debits might be imported as credits, and credits might be imported as debits.</span></span> <span data-ttu-id="0b69b-162">Para resolver este problema, debe cambiar el XSLT adecuado.</span><span class="sxs-lookup"><span data-stu-id="0b69b-162">To resolve this issue, you must change the appropriate XSLT.</span></span> <span data-ttu-id="0b69b-163">Si los extractos bancarios proceden de varios bancos, asegúrese de que todos usen el mismo enfoque de débito/crédito o cree transformaciones independientes.</span><span class="sxs-lookup"><span data-stu-id="0b69b-163">If bank statements come from multiple banks, make sure that they all use the same debit/credit approach, or create separate transformations.</span></span>

-   <span data-ttu-id="0b69b-164">Plantilla GetAmountCreditDebitIndicator de BAI2XML-to-Reconciliation.xlst</span><span class="sxs-lookup"><span data-stu-id="0b69b-164">BAI2XML-to-Reconciliation.xlst GetAmountCreditDebitIndicator template</span></span>
-   <span data-ttu-id="0b69b-165">Plantilla GetCreditDebit de ISO20022XML-to-Reconcilation.xslt</span><span class="sxs-lookup"><span data-stu-id="0b69b-165">ISO20022XML-to-Reconcilation.xslt GetCreditDebit template</span></span>
-   <span data-ttu-id="0b69b-166">Plantilla GetCreditDebitIndicator de MT940XML-to-Reconcilation.xslt</span><span class="sxs-lookup"><span data-stu-id="0b69b-166">MT940XML-to-Reconcilation.xslt GetCreditDebitIndicator template</span></span>

## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a><span data-ttu-id="0b69b-167">Ejemplos de diseños técnicos y formatos de extracto bancario</span><span class="sxs-lookup"><span data-stu-id="0b69b-167">Examples of bank statement formats and technical layouts</span></span>
<span data-ttu-id="0b69b-168">En la tabla siguiente se muestran ejemplos de las definiciones de diseño técnico para los archivos de importación de conciliación bancaria avanzados y tres archivos de ejemplo de extracto bancario relacionados.</span><span class="sxs-lookup"><span data-stu-id="0b69b-168">The following table lists examples of the technical layout definitions for advanced bank reconciliation import files and three related bank statement example files.</span></span> <span data-ttu-id="0b69b-169">Puede descargar los archivos de ejemplo y los diseños técnicos aquí: [Ejemplos de archivos de importación](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)</span><span class="sxs-lookup"><span data-stu-id="0b69b-169">You can download the example files and technical layouts here: [Import file examples](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)</span></span>  

| <span data-ttu-id="0b69b-170">Definición de diseño técnico</span><span class="sxs-lookup"><span data-stu-id="0b69b-170">Technical layout definition</span></span>                             | <span data-ttu-id="0b69b-171">Archivo de ejemplo de extracto bancario</span><span class="sxs-lookup"><span data-stu-id="0b69b-171">Bank statement example file</span></span>          |
|---------------------------------------------------------|--------------------------------------|
| <span data-ttu-id="0b69b-172">DynamicsAXMT940Layout</span><span class="sxs-lookup"><span data-stu-id="0b69b-172">DynamicsAXMT940Layout</span></span>                                   | [<span data-ttu-id="0b69b-173">MT940StatementExample</span><span class="sxs-lookup"><span data-stu-id="0b69b-173">MT940StatementExample</span></span>](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)                |
| <span data-ttu-id="0b69b-174">DynamicsAXISO20022Layout</span><span class="sxs-lookup"><span data-stu-id="0b69b-174">DynamicsAXISO20022Layout</span></span>                                | [<span data-ttu-id="0b69b-175">ISO20022StatementExample</span><span class="sxs-lookup"><span data-stu-id="0b69b-175">ISO20022StatementExample</span></span>](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| <span data-ttu-id="0b69b-176">DynamicsAXBAI2Layout</span><span class="sxs-lookup"><span data-stu-id="0b69b-176">DynamicsAXBAI2Layout</span></span>                                    | [<span data-ttu-id="0b69b-177">BAI2StatementExample</span><span class="sxs-lookup"><span data-stu-id="0b69b-177">BAI2StatementExample</span></span>](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)                 |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
