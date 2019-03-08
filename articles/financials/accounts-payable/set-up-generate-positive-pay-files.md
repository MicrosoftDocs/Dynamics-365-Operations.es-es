---
title: Configurar y generar archivos de pago positivo
description: Este artículo explica cómo configurar un pago positivo y generar archivos de pago positivo.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 0a15669c477223b922d8892d675eaa1df2563714
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "346097"
---
# <a name="set-up-and-generate-positive-pay-files"></a><span data-ttu-id="3cb57-103">Configurar y generar archivos de pago positivo</span><span class="sxs-lookup"><span data-stu-id="3cb57-103">Set up and generate positive pay files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3cb57-104">Este artículo explica cómo configurar un pago positivo y generar archivos de pago positivo.</span><span class="sxs-lookup"><span data-stu-id="3cb57-104">This article explains how to set up positive pay and generate positive pay files.</span></span> 

<span data-ttu-id="3cb57-105">Configure los pagos positivos para generar una lista electrónica de cheques que se proporcionan al banco.</span><span class="sxs-lookup"><span data-stu-id="3cb57-105">Set up positive pay to generate an electronic list of checks that is provided to the bank.</span></span> <span data-ttu-id="3cb57-106">A continuación, cuando el cheque se envía al banco, el banco lo compara con la lista de cheques.</span><span class="sxs-lookup"><span data-stu-id="3cb57-106">Then, when a check is presented to the bank, the bank compares it with the list of checks.</span></span> <span data-ttu-id="3cb57-107">Si el cheque coincide con un cheque de la lista, el banco lo compensa.</span><span class="sxs-lookup"><span data-stu-id="3cb57-107">If the check matches a check in the list, the bank clears it.</span></span> <span data-ttu-id="3cb57-108">Si el cheque no coincide con un cheque en la lista, el banco lo retiene para su revisión.</span><span class="sxs-lookup"><span data-stu-id="3cb57-108">If the check doesn't match a check in the list, the bank holds it for review.</span></span>

## <a name="security-for-positive-pay-files"></a><span data-ttu-id="3cb57-109">Seguridad para los archivos de pago positivo</span><span class="sxs-lookup"><span data-stu-id="3cb57-109">Security for positive pay files</span></span>
<span data-ttu-id="3cb57-110">Los archivos de pago positivo pueden contener información confidencial acerca de los beneficiarios y los importes del cheque.</span><span class="sxs-lookup"><span data-stu-id="3cb57-110">Positive pay files can contain sensitive information about payees and check amounts.</span></span> <span data-ttu-id="3cb57-111">Por lo tanto, asegúrese de usar medidas de seguridad adecuadas desde el momento en que los archivos se generan, hasta que los reciba el banco.</span><span class="sxs-lookup"><span data-stu-id="3cb57-111">Therefore, make sure that you use appropriate security measures from the time that the files are generated until they are received by the bank.</span></span> <span data-ttu-id="3cb57-112">Los archivos de pago positivo se descarga en la ubicación que especifica el explorador web.</span><span class="sxs-lookup"><span data-stu-id="3cb57-112">Positive pay files are downloaded to the location that is specified by your web browser.</span></span> <span data-ttu-id="3cb57-113">Dado que los archivos de pago positivo pueden contener información confidencial, es importante que solo los usuarios autorizados tengan acceso para generar y ver esta información en Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3cb57-113">Because positive pay files can contain sensitive information, it's important that only authorized users have access to generate and view this information in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="3cb57-114">Use la siguiente tabla para ayudarle a determinar los privilegios necesarios.</span><span class="sxs-lookup"><span data-stu-id="3cb57-114">Use the following table to help you determine the privileges that are required.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3cb57-115">Tarea</span><span class="sxs-lookup"><span data-stu-id="3cb57-115">Task</span></span></th>
<th><span data-ttu-id="3cb57-116">Privilegio</span><span class="sxs-lookup"><span data-stu-id="3cb57-116">Privilege</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3cb57-117">Generar archivos de pago positivo en la página de lista <strong>Cuentas bancarias</strong> o en la página <strong>Cuentas bancarias</strong>.</span><span class="sxs-lookup"><span data-stu-id="3cb57-117">Generate positive pay files from the <strong>Bank accounts</strong> list page or the <strong>Bank accounts</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="3cb57-118"><strong>Mantener información de pago positivo bancario</strong> (BankPositivePayProcess)</span><span class="sxs-lookup"><span data-stu-id="3cb57-118"><strong>Maintain bank positive pay information</strong> (BankPositivePayProcess)</span></span></li>
<li><span data-ttu-id="3cb57-119"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span><span class="sxs-lookup"><span data-stu-id="3cb57-119"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3cb57-120">Generar archivos de pago positivo para varias entidades jurídicas y cuentas bancarias desde la página <strong>Generar archivo de pago positivo</strong>.</span><span class="sxs-lookup"><span data-stu-id="3cb57-120">Generate positive pay files for multiple legal entities and bank accounts from the <strong>Generate a positive pay file</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="3cb57-121"><strong>Mantener información de pago positivo bancario</strong> (BankPositivePayProcess)</span><span class="sxs-lookup"><span data-stu-id="3cb57-121"><strong>Maintain bank positive pay information</strong> (BankPositivePayProcess)</span></span></li>
<li><span data-ttu-id="3cb57-122"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span><span class="sxs-lookup"><span data-stu-id="3cb57-122"><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3cb57-123">Ver archivos de pago positivo en la página <strong>Resumen de archivo de pago positivo</strong>.</span><span class="sxs-lookup"><span data-stu-id="3cb57-123">View positive pay files on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="3cb57-124"><strong>Mostrar información de pago positivo bancario para varias entidades jurídicas</strong> (BankPositivePayView)</span><span class="sxs-lookup"><span data-stu-id="3cb57-124"><strong>View bank positive pay information for multiple legal entities</strong> (BankPositivePayView)</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="3cb57-125">Confirmar un archivo de pago positivo en la página <strong>Resumen de archivo de pago positivo</strong>.</span><span class="sxs-lookup"><span data-stu-id="3cb57-125">Confirm a bank positive pay file on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="3cb57-126"><strong>Confirmar archivo de pago positivo</strong> (BankPositivePayConfirm)</span><span class="sxs-lookup"><span data-stu-id="3cb57-126"><strong>Confirm positive payment file</strong> (BankPositivePayConfirm)</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="3cb57-127">Recuperar un archivo de pago positivo en la página <strong>Resumen de archivo de pago positivo</strong>.</span><span class="sxs-lookup"><span data-stu-id="3cb57-127">Recall a bank positive pay file on the <strong>Positive pay file summary</strong> page.</span></span></td>
<td><span data-ttu-id="3cb57-128"><strong>Recuperar un archivo de pago positivo</strong> (BankPositivePayRecall)</span><span class="sxs-lookup"><span data-stu-id="3cb57-128"><strong>Recall positive pay file</strong> (BankPositivePayRecall)</span></span></td>
</tr>
</tbody>
</table>

## <a name="set-up-a-positive-pay-format"></a><span data-ttu-id="3cb57-129">Configurar un formato de pago positivo</span><span class="sxs-lookup"><span data-stu-id="3cb57-129">Set up a positive pay format</span></span>
<span data-ttu-id="3cb57-130">Los archivos de pago positivo se crean mediante entidades de datos.</span><span class="sxs-lookup"><span data-stu-id="3cb57-130">Positive pay files are created by using data entities.</span></span> <span data-ttu-id="3cb57-131">Para poder generar un archivo de pago positivo, debe configurar un formato de entrada de transformación que se usará para traducir la información del cheque en un formato que puede comunicarse con el banco.</span><span class="sxs-lookup"><span data-stu-id="3cb57-131">Before you can generate a positive pay file, you must set up a transformation input format that will be used to translate the check information into a format that can communicate with the bank.</span></span> <span data-ttu-id="3cb57-132">En la página **Formato de pago positivo**, puede crear un identificador de formato de archivo y una descripción.</span><span class="sxs-lookup"><span data-stu-id="3cb57-132">On the **Positive pay format** page, you can create a file format identifier and a description.</span></span> <span data-ttu-id="3cb57-133">El formato de entrada de transformación debe ser del tipo XML</span><span class="sxs-lookup"><span data-stu-id="3cb57-133">The transformation input format must be of the XML type.</span></span> <span data-ttu-id="3cb57-134">El formato específico depende del archivo de transformación que esté usando.</span><span class="sxs-lookup"><span data-stu-id="3cb57-134">The specific format depends on the transformation file that you're using.</span></span> <span data-ttu-id="3cb57-135">Por ejemplo, el archivo Extensible Stylesheet Language Transformations (XSLT) de ejemplo que se proporciona usa el formato **Elemento XML**.</span><span class="sxs-lookup"><span data-stu-id="3cb57-135">For example, the sample Extensible Stylesheet Language Transformations (XSLT) file that is provided uses the **XML-Element** format.</span></span> <span data-ttu-id="3cb57-136">Use la acción **Archivo de carga usado para la transformación** para especificar la ubicación del archivo de transformación para el formato que el banco requiere.</span><span class="sxs-lookup"><span data-stu-id="3cb57-136">Use the **Upload file used for transformation** action to specify the location of the transform file for the format that your bank requires.</span></span>

## <a name="example-xslt-file-for-positive-pay-file"></a><span data-ttu-id="3cb57-137">Ejemplo: archivo XSLT para archivo de pago positivo</span><span class="sxs-lookup"><span data-stu-id="3cb57-137">Example: XSLT file for positive pay file</span></span>
    <xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:msxsl="urn:schemas-microsoft-com:xslt" exclude-result-prefixes="msxsl xslthelper" xmlns="urn:iso:std:iso:20022:tech:xsd:pain.001.001.02" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xslthelper="http://schemas.microsoft.com/BizTalk/2003/xslthelper">
      <xsl:output method="xml" omit-xml-declaration="no" version="1.0" encoding="utf-8"/>
      <xsl:template match="/">
        <xsl:value-of select="'
    '" />
        <Document>
          <xsl:value-of select="'
    '" />
          <!--Header Begin-->
          <xsl:value-of select='string("Vendor ID,Vendor Name,Voided,Document Type,Check Date,Check Number,Check Amount,Checkbook ID,Vendor Class ID,Posted Date")'/>
          <xsl:value-of select="'
    '" />
          <!--Header End-->
          <xsl:for-each select="Document/BankPositivePayExportEntity">
            <!--Cheque Detail begin-->
            <xsl:value-of select='RECIPIENTACCOUNTNUM/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='BANKNEGINSTRECIPIENTNAME/text()'/>
            <xsl:value-of select="','" />
            <xsl:choose>
              <xsl:when test='CHEQUESTATUS/text()=normalize-space("Void") or CHEQUESTATUS/text()=normalize-space("Rejected") or CHEQUESTATUS/text()=normalize-space("Cancelled")'>
                <xsl:value-of select='string("Yes")'/>
              </xsl:when>
              <xsl:when test='CHEQUESTATUS/text()=normalize-space("Payment")'>
                <xsl:value-of select='string("No")'/>
              </xsl:when>
              <xsl:otherwise>
                <xsl:value-of select='string(" ")'/>
              </xsl:otherwise>
            </xsl:choose>
            <xsl:value-of select="','" />
            <xsl:value-of select='string("Payment")'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='TRANSDATE/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='CHEQUENUM/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='AMOUNTCUR/text()'/>
            <xsl:value-of select="','" />
            <xsl:value-of select='string("BOA-#1812")'/>
            <xsl:value-of select="','" />
            <xsl:choose>
              <xsl:when test='RECIPIENTTYPE/text()=normalize-space("Vend")'>
                <xsl:value-of select='VENDGROUP/text()'/>
              </xsl:when>
              <xsl:otherwise>
                <xsl:value-of select='CUSTGROUP/text()'/>
              </xsl:otherwise>
            </xsl:choose>
            <xsl:value-of select="','" />
            <xsl:value-of select='TRANSDATE/text()'/>
            <xsl:value-of select="'
    '" />
          </xsl:for-each>
        </Document>
      </xsl:template>
    </xsl:stylesheet>

## <a name="assign-the-positive-pay-format-to-a-bank-account"></a><span data-ttu-id="3cb57-138">Asignar el formato de pago positivo a una cuenta bancaria</span><span class="sxs-lookup"><span data-stu-id="3cb57-138">Assign the positive pay format to a bank account</span></span>
<span data-ttu-id="3cb57-139">Para cada cuenta bancaria para la que desea generar información de pago positivo, debe asignar el formato de pago positivo que ha especificado en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="3cb57-139">For each bank account that you want to generate positive pay information for, you must assign the positive pay format that you specified in the previous section.</span></span> <span data-ttu-id="3cb57-140">En la página **Cuentas bancarias**, seleccione el formato de pago positivo que se corresponde con la cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="3cb57-140">On the **Bank accounts** page, select the positive pay format that corresponds to the bank account.</span></span> <span data-ttu-id="3cb57-141">En el campo **Fecha inicial de pago positivo**, escriba la primera fecha para generar archivos de pago positivo.</span><span class="sxs-lookup"><span data-stu-id="3cb57-141">In the **Positive pay start date** field, enter the first date to generate positive pay files.</span></span> <span data-ttu-id="3cb57-142">Es importante que especifique una fecha en este campo.</span><span class="sxs-lookup"><span data-stu-id="3cb57-142">It's important that you enter a date in this field.</span></span> <span data-ttu-id="3cb57-143">De lo contrario, el primer archivo de pago positivo que genere incluirá todos los cheques que se han creado para esta cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="3cb57-143">Otherwise, the first positive pay file that you generate will include all checks that have ever been created for this bank account.</span></span>

## <a name="assign-a-number-sequence-for-positive-pay-files"></a><span data-ttu-id="3cb57-144">Asignar una secuencia numérica para los archivos de pago positivo</span><span class="sxs-lookup"><span data-stu-id="3cb57-144">Assign a number sequence for positive pay files</span></span>
<span data-ttu-id="3cb57-145">Cada archivo de pago positivo debe tener un número único.</span><span class="sxs-lookup"><span data-stu-id="3cb57-145">Each positive pay file must have a unique number.</span></span> <span data-ttu-id="3cb57-146">Utilice la pestaña **Secuencias numéricas** de la página **Parámetros de gestión de efectivo y bancos** para crear una secuencia numérica para los archivos de pago positivo.</span><span class="sxs-lookup"><span data-stu-id="3cb57-146">Use the **Number sequences** tab on the **Cash and bank management parameters** page to create a number sequence for positive pay files.</span></span>

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a><span data-ttu-id="3cb57-147">Generar un archivo de pago positivo para una cuenta bancaria única</span><span class="sxs-lookup"><span data-stu-id="3cb57-147">Generate a positive pay file for a single bank account</span></span>
<span data-ttu-id="3cb57-148">Puede generar un archivo de pago positivo para una única entidad jurídica y una única cuenta bancaria.</span><span class="sxs-lookup"><span data-stu-id="3cb57-148">You can generate a positive pay file for a single legal entity and a single bank account.</span></span> <span data-ttu-id="3cb57-149">Para obtener información acerca de cómo generar archivos de pago positivo para múltiples entidades jurídicas y cuentas bancarias al mismo tiempo, vea la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="3cb57-149">For information about how to generate positive pay files for multiple legal entities and bank accounts at the same time, see the next section.</span></span> <span data-ttu-id="3cb57-150">Para generar un archivo de pago positivo para una entidad jurídica única y una cuenta bancaria única, abra el cuadro de diálogo **Generar archivo de pago positivo** en la página **Cuentas bancarias**.</span><span class="sxs-lookup"><span data-stu-id="3cb57-150">To generate a positive pay file for a single legal entity and a single bank account, open the **Generate a positive pay file** dialog box from the **Bank accounts** page.</span></span> <span data-ttu-id="3cb57-151">En el campo **Fecha límite**, especifique la última fecha del cheque que se debe incluir en el archivo de pago positivo.</span><span class="sxs-lookup"><span data-stu-id="3cb57-151">In the **Cut-off date** field, enter the last check date to include in the positive pay file.</span></span> <span data-ttu-id="3cb57-152">Todos los cheques que no se han incluido en un archivo de pago positivo antes del final de esta fecha de cheque se incluyen en el archivo.</span><span class="sxs-lookup"><span data-stu-id="3cb57-152">All checks that haven’t been included in a positive pay file by the end of this check date are included in the file.</span></span>

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a><span data-ttu-id="3cb57-153">Generar un archivo de pago positivo para múltiples cuentas bancarias</span><span class="sxs-lookup"><span data-stu-id="3cb57-153">Generate a positive pay file for multiple bank accounts</span></span>
<span data-ttu-id="3cb57-154">Para generar un archivo de pago positivo para varias entidades jurídicas, use la tarea periódica **Generar archivo de pago positivo**.</span><span class="sxs-lookup"><span data-stu-id="3cb57-154">To generate a positive pay file for multiple bank accounts, use the **Generate a positive pay file** periodic task.</span></span> <span data-ttu-id="3cb57-155">Seleccione el formato de pago positivo para el archivo y especifique si se debe generar el archivo para todas las entidades jurídicas o para una entidad jurídica seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3cb57-155">Select the positive pay format for the file, and specify whether to generate the file for all legal entities or for a selected legal entity.</span></span> <span data-ttu-id="3cb57-156">También puede generar el archivo de pago positivo para todas las cuentas bancarias que usan el formato de pago positivo o para una cuenta bancaria seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3cb57-156">You can also generate the positive pay file for all bank accounts that use the specified positive pay format or for a selected bank account.</span></span> <span data-ttu-id="3cb57-157">En el campo **Fecha límite**, especifique la última fecha del cheque que se debe incluir en el archivo de pago positivo.</span><span class="sxs-lookup"><span data-stu-id="3cb57-157">In the **Cut-off date** field, enter the last check date to include in the positive pay file.</span></span> <span data-ttu-id="3cb57-158">Todos los cheques que no se han incluido en un archivo de pago positivo antes del final de esta fecha de cheque se incluyen en el archivo.</span><span class="sxs-lookup"><span data-stu-id="3cb57-158">All checks that haven’t been included in a positive pay file by the end of this check date are included in the file.</span></span>

## <a name="view-the-results-of-positive-pay-file-generation"></a><span data-ttu-id="3cb57-159">Ver los resultados de la generación de archivos de pago positivo</span><span class="sxs-lookup"><span data-stu-id="3cb57-159">View the results of positive pay file generation</span></span>
<span data-ttu-id="3cb57-160">Tras generar el archivo de pago positivo, puede ver los resultados en la página **Resumen de archivo de pago positivo**.</span><span class="sxs-lookup"><span data-stu-id="3cb57-160">After the positive pay file is generated, you can view the results on the **Positive pay file summary** page.</span></span> <span data-ttu-id="3cb57-161">Para ver los detalles de los cheques individuales, use la página de detalles **Archivo de pago positivo**.</span><span class="sxs-lookup"><span data-stu-id="3cb57-161">To view the details of the individual checks, use the **Positive pay file** details page.</span></span>

## <a name="confirm-a-positive-pay-file"></a><span data-ttu-id="3cb57-162">Confirmar un archivo de pago positivo</span><span class="sxs-lookup"><span data-stu-id="3cb57-162">Confirm a positive pay file</span></span>
<span data-ttu-id="3cb57-163">Después de que se hayan pagado los cheques que aparecen en un archivo de pago positivo, recibirá un número de confirmación del banco.</span><span class="sxs-lookup"><span data-stu-id="3cb57-163">After the checks that are listed in a positive pay file have been paid, you receive a confirmation number from your bank.</span></span> <span data-ttu-id="3cb57-164">A continuación puede confirmar el archivo de pago positivo.</span><span class="sxs-lookup"><span data-stu-id="3cb57-164">You can then confirm the positive pay file.</span></span> <span data-ttu-id="3cb57-165">En la página **Resumen de archivo de pago positivo**, seleccione un archivo de pago positivo que tenga un estado **Creado** y, a continuación, seleccione la acción **Especificar confirmación**.</span><span class="sxs-lookup"><span data-stu-id="3cb57-165">On the **Positive pay file summary** page, select a positive pay file that has a status of **Created**, and then select the **Enter confirmation** action.</span></span> <span data-ttu-id="3cb57-166">Al confirmar un archivo de pago positivo, se registra el número de confirmación que ha recibido del banco.</span><span class="sxs-lookup"><span data-stu-id="3cb57-166">When you confirm a positive pay file, the confirmation number that you received from the bank is recorded.</span></span>

## <a name="recall-a-positive-pay-file"></a><span data-ttu-id="3cb57-167">Recuperar un archivo de pago positivo</span><span class="sxs-lookup"><span data-stu-id="3cb57-167">Recall a positive pay file</span></span>
<span data-ttu-id="3cb57-168">Si debe cambiar un archivo de pago positivo, puede recuperarlo.</span><span class="sxs-lookup"><span data-stu-id="3cb57-168">If you must change a positive pay file, you can recall it.</span></span> <span data-ttu-id="3cb57-169">En la página **Resumen de archivo de pago positivo**, seleccione un archivo de pago positivo que tenga un estado **Creado** y, a continuación, seleccione la acción **Recuperar**.</span><span class="sxs-lookup"><span data-stu-id="3cb57-169">On the **Positive pay file summary** page, select a positive pay file that has a status of **Created**, and then select the **Recall** action.</span></span> <span data-ttu-id="3cb57-170">Para cada cheque del archivo de pago positivo, se restablece el campo que indica si el cheque se ha incluido en un archivo de pago positivo.</span><span class="sxs-lookup"><span data-stu-id="3cb57-170">For each check in the positive pay file, the field that indicates whether that check has been included in a positive pay file is reset.</span></span> <span data-ttu-id="3cb57-171">A continuación puede crear un nuevo archivo de pago positivo que incluya el cheque que se ha recuperado.</span><span class="sxs-lookup"><span data-stu-id="3cb57-171">You can then create a new positive pay file that includes the check that was recalled.</span></span>



