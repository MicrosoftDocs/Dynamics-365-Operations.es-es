---
title: Configurar y generar archivos de pago positivos mediante el uso de Informes electrónicos
description: Este artículo explica cómo configurar un pago positivo mediante el uso de Informes electrónicos.
author: panolte
ms.date: 03/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 491048c7274ba6bb52e0a4b7a6ea5cd0f5ff4741
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878229"
---
# <a name="set-up-positive-pay-files-by-using-electronic-reporting"></a>Configurar archivos de pago positivos mediante el uso de Informes electrónicos

Este artículo explica cómo configurar un pago positivo y generar archivos de pago positivo usando los informes electrónicos.

> [!NOTE] 
> Antes de usar la función **Generar archivo de pago positivo bancario**, primero deberá actualizar la lista de entidades.
> Vaya a **Administración de datos > Importar / Exportar > Parámetros de marco de trabajo** 
> Ficha desplegable **Configuración de entidad**, seleccione **Actualizar lista de entidades**.


Configure los pagos positivos para generar una lista electrónica de cheques que se proporcionan al banco. Cuando el cheque se envía al banco, el banco lo compara con la lista de cheques. Si el cheque coincide con un cheque de la lista, el banco lo compensa. Si el cheque no coincide con un cheque en la lista, el banco lo retiene para su revisión.

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

## <a name="set-up-the-electronic-reporting-configuration"></a>Establecer la configuración de Informes electrónicos

1. Vaya a **Espacios de trabajo \> Informes electrónicos**.
2. En el mosaico para el proveedor de configuración de **Microsoft**, seleccione **Repositorios**.
3. Seleccione **Global** y luego seleccione **Abierto**.
4. Si se debe establecer una conexión con el repositorio, seleccione el vínculo azul en el cuadro de diálogo.
5. En la lista de configuración, busque y seleccione **Modelo de pago positivo \> Formato de pago positivo**.
6. En la ficha desplegable **Versiones**, seleccione la última versión y después seleccione **Importar**.

## <a name="set-up-a-positive-pay-format"></a>Configurar un formato de pago positivo

1. Vaya a **Gestión de efectivo y bancos \> Configuración \> Formatos de pago positivo**.
2. Seleccione **Nuevo**.
3. Seleccione los campos **Formato de pago** y **Descripción**.
4. Seleccione la casilla **Formato de exportación electrónica genérica**.
5. Seleccione el campo **Configuración del formato de exportación** en **Formato de pago positivo**.

## <a name="assign-a-positive-pay-format-to-a-bank-account"></a>Asignar un formato de pago positivo a una cuenta bancaria
Para cada cuenta bancaria para la que desea generar información de pago positivo, debe asignar el formato de pago positivo que ha especificado en la sección anterior. En la página Cuentas bancarias, seleccione el formato de pago positivo que se corresponde con la cuenta bancaria. En el campo **Fecha inicial de pago positivo**, escriba la primera fecha para generar archivos de pago positivo. 

>[!Important]
> Introduzca una fecha en el campo **Fecha de inicio de pago positivo**. Si se deja en blanco, el primer archivo de pago positivo que se genere incluirá todos los cheques que se han creado para esta cuenta bancaria.

1. Vaya a **Gestión de efectivo y de banco \> Cuentas bancarias \> Cuentas bancarias**.
2. Abra la cuenta bancaria.
3. En la ficha desplegable **General**, establezca el campo **Formato de pago positivo** en el formato que se creó anteriormente.
4. Establezca el campo **Fecha de inicio de pago positivo** en la fecha actual.

## <a name="assign-a-number-sequence-for-positive-pay-files"></a>Asignar una secuencia numérica para los archivos de pago positivo
Cada archivo de pago positivo debe tener un número único. En la página **Parámetros de gestión de efectivo y bancos**, cree una secuencia numérica para los archivos de pago positivo en la pestaña **Secuencias numéricas**.

## <a name="generate-a-positive-pay-file-for-a-single-bank-account"></a>Generar un archivo de pago positivo para una cuenta bancaria única
Puede generar un archivo de pago positivo para una única entidad jurídica y una única cuenta bancaria. Para obtener información acerca de cómo generar archivos de pago positivo para múltiples entidades jurídicas y cuentas bancarias al mismo tiempo, vea la siguiente sección. Para generar un archivo de pago positivo para una entidad jurídica única y una cuenta bancaria única, abra el cuadro de diálogo **Generar archivo de pago positivo** en la página **Cuentas bancarias**. En el campo **Fecha límite**, especifique la última fecha del cheque que se debe incluir en el archivo de pago positivo. Todos los cheques que no se han incluido en un archivo de pago positivo antes del final de esta fecha de cheque se incluyen en el archivo.

1. Vaya a **Gestión de efectivo y de banco \> Cuentas bancarias \> Cuentas bancarias**.
2. Abra una cuenta bancaria para la que esté configurado el pago positivo.
3. Seleccione **Administrar pagos \> Pago positivo \> Archivo de pago positivo**.
4. Seleccione el campo **Fecha límite**. Las comprobaciones que se generaron antes de esta fecha se incluirán.

## <a name="generate-a-positive-pay-file-for-multiple-bank-accounts"></a>Generar un archivo de pago positivo para múltiples cuentas bancarias
Para generar un archivo de pago positivo para varias entidades jurídicas, use la tarea periódica **Archivo de pago positivo**. Seleccione el formato de pago positivo para el archivo y especifique si se debe generar el archivo para todas las entidades jurídicas o para una entidad jurídica seleccionada. También puede generar el archivo de pago positivo para todas las cuentas bancarias que usan el formato de pago positivo o para una cuenta bancaria seleccionada. En el campo **Fecha límite**, especifique la última fecha del cheque que se debe incluir en el archivo de pago positivo. Todos los cheques que no se han incluido en un archivo de pago positivo antes del final de esta fecha de cheque se incluyen en el archivo.

## <a name="view-the-results-of-positive-pay-file-generation"></a>Ver los resultados de la generación de archivos de pago positivo
Tras generar el archivo de pago positivo, puede ver los resultados en la página **Resumen de archivo de pago positivo**. Para ver los detalles de los cheques individuales, vaya a la página de detalles **Archivo de pago positivo**.

## <a name="confirm-a-positive-pay-file"></a>Confirmar un archivo de pago positivo
Después de que se hayan pagado los cheques que aparecen en un archivo de pago positivo, recibirá un número de confirmación del banco. A continuación puede confirmar el archivo de pago positivo. En la página **Resumen de archivo de pago positivo**, seleccione un archivo de pago positivo que tenga un estado **Creado** y, a continuación, seleccione la acción **Especificar confirmación**. Al confirmar un archivo de pago positivo, se registra el número de confirmación que ha recibido del banco.

## <a name="recall-a-positive-pay-file"></a>Recuperar un archivo de pago positivo
Si debe cambiar un archivo de pago positivo, puede recuperarlo. En la página **Resumen de archivo de pago positivo**, seleccione un archivo de pago positivo que tenga un estado **Creado** y, a continuación, seleccione la acción **Recuperar**. Para cada cheque del archivo de pago positivo, se restablece el campo que indica si el cheque se ha incluido en un archivo de pago positivo. A continuación puede crear un nuevo archivo de pago positivo que incluya el cheque que se ha recuperado.


El archivo XML resultante se descargará.
