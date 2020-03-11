---
title: Configurar y generar archivos de pago positivo
description: Este tema explica cómo configurar un pago positivo y generar archivos de pago positivo.
author: abruer
manager: AnnBe
ms.date: 03/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 0c44d172e8ed9cdb9c26501b3f4eb9fef4f8cf0b
ms.sourcegitcommit: 4f668b23f5bfc6d6502858850d2ed59d7a79cfbb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "3059410"
---
# <a name="set-up-and-generate-positive-pay-files"></a>Configurar y generar archivos de pago positivo

[!include [banner](../includes/banner.md)]

Este tema explica cómo configurar un pago positivo y generar archivos de pago positivo. 

Configure los pagos positivos para generar una lista electrónica de cheques que se proporcionan al banco. A continuación, cuando el cheque se envía al banco, el banco lo compara con la lista de cheques. Si el cheque coincide con un cheque de la lista, el banco lo compensa. Si el cheque no coincide con un cheque en la lista, el banco lo retiene para su revisión.

## <a name="security-for-positive-pay-files"></a>Seguridad para los archivos de pago positivo
Los archivos de pago positivo pueden contener información confidencial acerca de los beneficiarios y los importes del cheque. Por lo tanto, asegúrese de usar medidas de seguridad adecuadas desde el momento en que los archivos se generan, hasta que los reciba el banco. Los archivos de pago positivo se descarga en la ubicación que especifica el explorador web. Dado que los archivos de pago positivo pueden contener información confidencial, es importante que solo los usuarios autorizados tengan acceso para generar y ver esta información en Microsoft Dynamics 365 Finance. Use la siguiente tabla para ayudarle a determinar los privilegios necesarios.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tarea</th>
<th>Privilegio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Generar archivos de pago positivo en la página de lista <strong>Cuentas bancarias</strong> o en la página <strong>Cuentas bancarias</strong>.</td>
<td><ul>
<li><strong>Mantener información de pago positivo bancario</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="even">
<td>Generar archivos de pago positivo para varias entidades jurídicas y cuentas bancarias desde la página <strong>Generar archivo de pago positivo</strong>.</td>
<td><ul>
<li><strong>Mantener información de pago positivo bancario</strong> (BankPositivePayProcess)</li>
<li><strong>BankPositivePayExportEntityView</strong> (BankPositivePayExportEntityView)</li>
</ul></td>
</tr>
<tr class="odd">
<td>Ver archivos de pago positivo en la página <strong>Resumen de archivo de pago positivo</strong>.</td>
<td><strong>Mostrar información de pago positivo bancario para varias entidades jurídicas</strong> (BankPositivePayView)</td>
</tr>
<tr class="even">
<td>Confirmar un archivo de pago positivo en la página <strong>Resumen de archivo de pago positivo</strong>.</td>
<td><strong>Confirmar archivo de pago positivo</strong> (BankPositivePayConfirm)</td>
</tr>
<tr class="odd">
<td>Recuperar un archivo de pago positivo en la página <strong>Resumen de archivo de pago positivo</strong>.</td>
<td><strong>Recuperar un archivo de pago positivo</strong> (BankPositivePayRecall)</td>
</tr>
</tbody>
</table>

## <a name="set-up-a-positive-pay-format"></a>Configurar un formato de pago positivo
Los archivos de pago positivo se crean mediante entidades de datos. Para poder generar un archivo de pago positivo, debe configurar un formato de entrada de transformación que se usará para traducir la información del cheque en un formato que puede comunicarse con el banco. En la página **Formato de pago positivo**, puede crear un identificador de formato de archivo y una descripción. El formato de entrada de transformación debe ser del tipo XML El formato específico depende del archivo de transformación que esté usando. Por ejemplo, el archivo Extensible Stylesheet Language Transformations (XSLT) de ejemplo que se proporciona usa el formato **Elemento XML**. Use la acción **Archivo de carga usado para la transformación** para especificar la ubicación del archivo de transformación para el formato que el banco requiere.

## <a name="example-xslt-file-for-positive-pay-file"></a>Ejemplo: archivo XSLT para archivo de pago positivo

```xml
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
      <xsl:for-each select="Document/BANKPOSITIVEPAYEXPORTENTITY">
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
```

## <a name="assign-the-positive-pay-format-to-a-bank-account"></a>Asignar el formato de pago positivo a una cuenta bancaria
Para cada cuenta bancaria para la que desea generar información de pago positivo, debe asignar el formato de pago positivo que ha especificado en la sección anterior. En la página **Cuentas bancarias**, seleccione el formato de pago positivo que se corresponde con la cuenta bancaria. En el campo **Fecha inicial de pago positivo**, escriba la primera fecha para generar archivos de pago positivo. Es importante que especifique una fecha en este campo. De lo contrario, el primer archivo de pago positivo que genere incluirá todos los cheques que se han creado para esta cuenta bancaria.

## <a name="assign-a-number-sequence-for-positive-pay-files"></a>Asignar una secuencia numérica para los archivos de pago positivo
Cada archivo de pago positivo debe tener un número único. Utilice la pestaña **Secuencias numéricas** de la página **Parámetros de gestión de efectivo y bancos** para crear una secuencia numérica para los archivos de pago positivo.

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a>Generar un archivo de pago positivo para una cuenta bancaria única
Puede generar un archivo de pago positivo para una única entidad jurídica y una única cuenta bancaria. Para obtener información acerca de cómo generar archivos de pago positivo para múltiples entidades jurídicas y cuentas bancarias al mismo tiempo, vea la siguiente sección. Para generar un archivo de pago positivo para una entidad jurídica única y una cuenta bancaria única, abra el cuadro de diálogo **Generar archivo de pago positivo** en la página **Cuentas bancarias**. En el campo **Fecha límite**, especifique la última fecha del cheque que se debe incluir en el archivo de pago positivo. Todos los cheques que no se han incluido en un archivo de pago positivo antes del final de esta fecha de cheque se incluyen en el archivo.

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a>Generar un archivo de pago positivo para múltiples cuentas bancarias
Para generar un archivo de pago positivo para varias entidades jurídicas, use la tarea periódica **Generar archivo de pago positivo**. Seleccione el formato de pago positivo para el archivo y especifique si se debe generar el archivo para todas las entidades jurídicas o para una entidad jurídica seleccionada. También puede generar el archivo de pago positivo para todas las cuentas bancarias que usan el formato de pago positivo o para una cuenta bancaria seleccionada. En el campo **Fecha límite**, especifique la última fecha del cheque que se debe incluir en el archivo de pago positivo. Todos los cheques que no se han incluido en un archivo de pago positivo antes del final de esta fecha de cheque se incluyen en el archivo.

## <a name="view-the-results-of-positive-pay-file-generation"></a>Ver los resultados de la generación de archivos de pago positivo
Tras generar el archivo de pago positivo, puede ver los resultados en la página **Resumen de archivo de pago positivo**. Para ver los detalles de los cheques individuales, use la página de detalles **Archivo de pago positivo**.

## <a name="confirm-a-positive-pay-file"></a>Confirmar un archivo de pago positivo
Después de que se hayan pagado los cheques que aparecen en un archivo de pago positivo, recibirá un número de confirmación del banco. A continuación puede confirmar el archivo de pago positivo. En la página **Resumen de archivo de pago positivo**, seleccione un archivo de pago positivo que tenga un estado **Creado** y, a continuación, seleccione la acción **Especificar confirmación**. Al confirmar un archivo de pago positivo, se registra el número de confirmación que ha recibido del banco.

## <a name="recall-a-positive-pay-file"></a>Recuperar un archivo de pago positivo
Si debe cambiar un archivo de pago positivo, puede recuperarlo. En la página **Resumen de archivo de pago positivo**, seleccione un archivo de pago positivo que tenga un estado **Creado** y, a continuación, seleccione la acción **Recuperar**. Para cada cheque del archivo de pago positivo, se restablece el campo que indica si el cheque se ha incluido en un archivo de pago positivo. A continuación puede crear un nuevo archivo de pago positivo que incluya el cheque que se ha recuperado.



