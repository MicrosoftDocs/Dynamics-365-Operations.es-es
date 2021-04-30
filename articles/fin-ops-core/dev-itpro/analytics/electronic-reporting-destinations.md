---
title: Destinos de informes electrónicos (ER)
description: Este tema proporciona información sobre la administración de los destinos de informes electrónicos, los tipos de destinos admitidos y las consideraciones de seguridad.
author: nselin
ms.date: 02/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: fe0c3bc94359c7e6a3eb2476b8096a8a2339ee9d
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893613"
---
# <a name="electronic-reporting-er-destinations"></a>Destinos de informes electrónicos (ER)

[!include [banner](../includes/banner.md)]

Puede configurar un destino para cada configuración de formato de informes electrónicos y su componente de salida (una carpeta o un archivo). Los usuarios que tienen derechos de acceso adecuados también pueden modificar la configuración de destino en tiempo de ejecución. En este tema se explica la administración de destinos de ER, los tipos de destinos que son compatibles y consideraciones de seguridad.

Las configuraciones de formato ER suelen contener al menos un componente de salida: un archivo. Normalmente, las configuraciones contienen varios componentes de salida de archivo de diferentes tipos (por ejemplo, XML, TXT, XLSX, DOCX, o PDF) que se agrupan en una carpeta única o varias carpetas. La administración de destinos ER le permite preconfigurar lo que ocurre cuando se ejecuta cada componente. De forma predeterminada, cuando se ejecuta una configuración, se muestra un cuadro de diálogo que le permite guardar o abrir el archivo. El mismo comportamiento también se da al importar una configuración de ER y no configurar destinos específicos para ella. Después de que se cree un destino para un componente de salida principal, ese destino anula el comportamiento predeterminado y la carpeta o el archivo se envía según la configuración del destino.

## <a name="availability-and-general-prerequisites"></a>Disponibilidad y requisitos previos generales

La funcionalidad de los destinos de ER no está disponible en Microsoft Dynamics AX 7.0 (febrero de 2016). Por lo tanto, debe instalar Microsoft Dynamics 365 for Operations versión 1611 (noviembre de 2016) o posterior para usar los siguientes tipos de destino:

- [Correo electrónico](er-destination-type-email.md)
- [Archivar](er-destination-type-archive.md)
- [Archivo](er-destination-type-file.md)
- [Pantalla](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)

O bien, puede instalar uno de los siguientes requisitos previos. Sin embargo, tenga en cuenta que estas alternativas proporcionan una experiencia de destino de ER más limitada.

- Versión de aplicación Microsoft Dynamics AX 7.0.1 (mayo de 2016)
- [Revisión electrónica de la aplicación de administración de destinos de informes](https://fix.lcs.dynamics.com/issue/results/?q=3160213)

También hay un tipo de destino de [Impresión](er-destination-type-print.md). Para usarlo, debe instalar Microsoft Dynamics 365 Finance versión 10.0.9 (abril de 2020).

## <a name="overview"></a>Visión general

Puede configurar destinos solo para configuraciones de ER que se han [importado](general-electronic-reporting.md#importing-an-er-component-from-lcs-to-use-it-internally) en la instancia de Finance actual y para los formatos que están disponibles en la página **Configuraciones de informes electrónicos**. La funcionalidad de administración de destinos de ER está disponible en **Administración de la organización** \> **Informes electrónicos** \> **Destino de informes electrónicos**.

### <a name="default-behavior"></a>Comportamiento predeterminado

El comportamiento predeterminado para una configuración de formato ER depende del tipo de ejecución que especifique cuando se inicia un formato ER.

En el cuadro de diálogo **Informe Intrastat**, en la ficha desplegable **Ejecutar en segundo plano**, si configura la opción de **Procesamiento por lotes** en **No**, un formato ER se ejecuta inmediatamente en modo interactivo. Cuando esta ejecución se completa con éxito, un documento resultante generado está disponible para descargar.

Si configura la opción **Procesamiento por lotes** en **Sí**, se ejecuta un formato ER en modo [lote](../sysadmin/batch-processing-overview.md). Se crea el trabajo por lotes adecuado, en función de los parámetros que especifique en la pestaña **Ejecutar en segundo plano** del cuadro de diálogo **Parámetros ER**.

> [!NOTE]
> La descripción del trabajo le informa sobre la ejecución de una asignación de formato de informes electrónicos. También contiene el nombre del componente de informes electrónicos que se ejecuta.

[![Ejecución de un formato ER](./media/ER_Destinations-RunInBatchMode.png)](./media/ER_Destinations-RunInBatchMode.png)

Puede encontrar información sobre este trabajo en varios lugares:

- Vaya a **Común** \> **Consultas** \> **Trabajos por lotes** \> **Mis trabajos por lotes** para verificar el estado del trabajo programado.
- Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Trabajos de informes electrónicos** para verificar el estado del trabajo programado y los resultados de ejecución del trabajo completado. Cuando la ejecución del trabajo se complete con éxito, seleccione **Mostrar archivos** en la página **Trabajos de informes electrónicos** para obtener un documento resultante generado.

    > [!NOTE]
    > Este documento se almacena como un archivo adjunto del registro de trabajo actual y se controla mediante el marco de referencia [Gestión de documentos](../../fin-ops/organization-administration/configure-document-management.md). El [tipo de Documento](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types) que se utiliza para almacenar artefactos ER de este tipo se configura en los [Parámetros ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

- En la página **Trabajos de informes electrónicos**, seleccione **Mostrar archivos** para ver la lista de errores y advertencias que se generaron durante la ejecución del trabajo.

    [![Revisión de la lista de trabajos de ER](./media/ER_Destinations-ReviewERJobs.png)](./media/ER_Destinations-ReviewERJobs.png)

### <a name="user-configured-behavior"></a>Comportamiento configurado por el usuario

En la página **Destino de informes electrónicos**, puede anular el comportamiento predeterminado para una configuración. Las configuraciones importadas no se muestran en esta página hasta que se selecciona **Nueva** y, a continuación, en el campo **Referencia** , selecciona una configuración para la que crear la configuración de destino.

[![Selección de una configuración en el campo Referencia](./media/ER_Destinations-SelectFormat.png)](./media/ER_Destinations-SelectFormat.png)

Después de crear una referencia, puede crear un destino de archivo para cada **Carpeta** o **Archivo** componente de salida del formato ER referenciado.

[![Crear un archivo de destino](./media/ER_Destinations-ConfigureElementDestination.png)](./media/ER_Destinations-ConfigureElementDestination.png)

A continuación, en el cuadro de diálogo **Configuración de destino**, puede habilitar y deshabilitar destinos individuales para el destino de archivo. El botón **Configuración** se utiliza para controlar todos los destinos para un destino de archivo seleccionado. En el cuadro de diálogo **Configuración de destino**, puede controlar por separado cada destino estableciendo la opción **Habilitado** para él.

En las versiones de Finance **previas a la 10.0.9**, se puede crear **un destino de archivo** para cada componente de salida del mismo formato, como una carpeta o un archivo que está seleccionado en el campo **Nombre de archivo**. Sin embargo, en la **versión 10.0.9 y posterior**, puede crear **múltiples destinos de archivos** para cada componente de salida del mismo formato.

Por ejemplo, puede usar esta capacidad para configurar destinos de archivo para un componente de archivo que se usa para generar un documento saliente en formato Excel. Un destino ([Archivo](er-destination-type-archive.md)) se puede configurar para almacenar el archivo Excel original en el archivo de trabajos de ER y otro destino ([Correo electrónico](er-destination-type-email.md)) puede configurarse para simultáneamente [convertir](#OutputConversionToPDF) el archivo de Excel a formato PDF y enviar el archivo PDF por correo electrónico.

[![Configurar múltiples destinos para un elemento de formato único](./media/ER_Destinations-SampleDestinations.png)](./media/ER_Destinations-SampleDestinations.png)

Cuando ejecuta un formato de informes electrónicos, siempre se ejecutan todos los destinos que se configuraron para los componentes del formato. Además, en las **versiones 10.0.17 y posteriores** de Finance, la funcionalidad de destinos de informes electrónicos se ha mejorado y ahora le permite configurar diferentes conjuntos de destinos para un solo formato de informes electrónicos. Esta configuración marca cada conjunto como configurado para una acción de usuario en particular. La API de informes electrónicos se ha [ampliado](er-apis-app10-0-17.md) para que se pueda proporcionar una acción que el usuario realiza mediante la ejecución de un formato de informes electrónicos. El código de acción que se proporciona se pasa a los destinos de informes electrónicos. Puede ejecutar diferentes destinos de un formato de informes electrónicos según el código de acción proporcionado. Para obtener más información, consulte [Configurar destinos de informes electrónicos que dependen de acciones](er-action-dependent-destinations.md).

## <a name="destination-types"></a>Tipos de destino

Los siguientes destinos son actualmente compatibles con los formatos ER. Puede deshabilitar o habilitar todos los tipos al mismo tiempo. De esta forma, puede no hacer nada o enviar el componente a todos los destinos configurados.

- [Correo electrónico](er-destination-type-email.md)
- [Archivar](er-destination-type-archive.md)
- [Archivo](er-destination-type-file.md)
- [Pantalla](er-destination-type-screen.md)
- [Power BI](er-destination-type-powerbi.md)
- [Imprimir](er-destination-type-print.md)

## <a name="applicability"></a>Aplicabilidad

Puede configurar destinos solo para configuraciones de ER que se han importado y para los formatos que están disponibles en la página **Configuraciones de informes electrónicos**.

> [!NOTE]
> Los destinos configurados son específicos de la empresa. Si planea usar un formato ER en diferentes compañías de la instancia actual de Finance, debe configurar destinos para ese formato ER para cada una de esas compañías.

Cuando configura destinos de archivo para un formato seleccionado, los configura para todo el formato.

[![Vínculo de configuración](./media/ER_Destinations-ConfigurationLink.png)](./media/ER_Destinations-ConfigurationLink.png)

Al mismo tiempo, puede tener múltiples [versiones](general-electronic-reporting.md#component-versioning) del formato que se ha importado a la instancia actual de Finance. Puede verlas si selecciona el vínculo **Configuración** que se ofrece cuando selecciona el **Referencia** campo.

[![Versiones de configuración](./media/ER_Destinations-ConfigurationVersions.png)](./media/ER_Destinations-ConfigurationVersions.png)

De forma predeterminada, los destinos configurados se aplican solo cuando ejecuta una versión en formato ER que tiene un estado de **Terminado** o **Compartido**. Sin embargo, a veces debe usar destinos configurados cuando se ejecuta la versión de borrador de un formato ER. Por ejemplo, modifica una versión borrador de su formato y desea utilizar destinos configurados para probar cómo se entregará la salida generada. Siga estos pasos para aplicar destinos para un formato ER cuando se ejecute la versión de borrador.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
3. Establezca la opción **Usar destinos para el estado de borrador** en **Sí**.

[![Opción Usar destinos para el estado de borrador](./media/ER_Destinations-UserSetting1.png)](./media/ER_Destinations-UserSetting1.png)

Para utilizar la versión borrador de un formato ER, debe marcar el formato ER en consecuencia.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
3. Establezca la opción **Ejecutar valor** en **Sí**.

[![Opción Ejecutar valor](./media/ER_Destinations-UserSetting2.png)](./media/ER_Destinations-UserSetting2.png)

Después de completar esta configuración, la opción **Ejecutar borrador** está disponible para los formatos ER que modifique. Establezca esta opción en **Sí** para comenzar a usar la versión borrador del formato cuando se ejecute el formato.

[![Opción Ejecutar borrador](./media/ER_Destinations-FormatSetting.png)](./media/ER_Destinations-FormatSetting.png)

## <a name="destination-failure-handling"></a><a name="DestinationFailure"></a>Control de errores de destino

Por lo general, un formato ER se ejecuta dentro del alcance de un proceso de negocio específico. Sin embargo, la entrega de un documento saliente que se genera durante la ejecución de un formato ER a veces debe considerarse parte de ese proceso comercial. En este caso, si la entrega de un documento saliente generado a un destino configurado no tiene éxito, la ejecución del proceso comercial debe cancelarse. Para configurar el destino ER adecuado, seleccione la opción **Detener el procesamiento en caso de error**.

Por ejemplo, configura el procesamiento de pagos del proveedor para que el formato ER **Transferencia de crédito ISO20022** se ejecute para generar el archivo de pago y los documentos complementarios (por ejemplo, la carta de presentación y el informe de control). Si un pago se considera procesado con éxito solo si la carta de presentación se entrega con éxito por correo electrónico, debe seleccionar la casilla **Detener el procesamiento en caso de error** para el componente **CoveringLetter** en el destino de archivo apropiado, como se muestra en la siguiente ilustración. En este caso, el estado del pago seleccionado para procesamiento se cambiará de **Ninguno** a **Enviado** solo cuando la carta de presentación que se genera sea aceptada con éxito para su entrega por un proveedor de correo electrónico configurado en la instancia de Finance.

[![Configurar el control de procesos para los errores de destino del archivo](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)](./media/ER_Destinations-StopProcessingAtDestinationFailure.png)

Si desactiva la casilla **Detener el procesamiento en caso de error** para el componente **CoveringLetter** en el destino, un pago se considera procesado con éxito aunque la carta de presentación no se entregue con éxito por correo electrónico. El estado del pago cambiará de **Ninguno** a **Enviado** incluso si la carta de presentación no se puede enviar porque, por ejemplo, falta la dirección de correo electrónico del destinatario o del remitente o es incorrecta.

## <a name="output-conversion-to-pdf"></a><a name="OutputConversionToPDF"></a>Conversión de salida a PDF

Puede usar la opción de conversión de PDF para convertir la salida en formato de Microsoft Office (Excel/Word) a formato PDF.

### <a name="make-pdf-conversion-available"></a>Hacer que la conversión de PDF esté disponible

Para que la opción de conversión de PDF esté disponible en la instancia de Finance actual, abra el espacio de trabajo **Gestión de funciones** y active la función **Convertir documentos salientes de informes electrónicos de formatos de Microsoft Office a PDF**.

[![Activar la función de conversión de PDF de documentos salientes en Administración de características](./media/ER_Destinations-EnablePdfConversionFeature.png)](./media/ER_Destinations-EnablePdfConversionFeature.png)

### <a name="applicability"></a>Aplicabilidad

La opción de conversión de PDF solo se puede activar para los componentes de archivo que se utilizan para generar salidas en formato de Office (Excel o Word) (**archivo Excel**). Cuando esta opción está activada, la salida que se genera en formato de Office se convierte automáticamente a formato PDF. En versiones de Finance **antes de la versión 10.0.18**, puede activar esta opción solo para los componentes del tipo **Excel\\Archivo** que se utilizan para generar resultados en formato [Excel](er-fillable-excel.md) o [Word](er-design-configuration-word.md). Sin embargo, en la **versión 10.0.18 y posteriores**, también puede activar esta opción para los componentes del tipo **Común\\Archivo**.

> [!NOTE]
> Preste atención al mensaje de advertencia que recibe cuando activa la opción de conversión de PDF para un componente ER del tipo **Común\\Archivo**. Este mensaje le informa que no hay forma de garantizar, en el momento del diseño, que el componente de archivo seleccionado expondrá el contenido en formato PDF o el contenido convertible en PDF en tiempo de ejecución. Por lo tanto, debe activar la opción solo si está seguro de que el componente de archivo seleccionado se configuró para exponer el contenido en formato PDF o el contenido convertible en PDF en tiempo de ejecución.
> 
> Si activa la opción de conversión de PDF para un componente del tipo **Excel\\Archivo**, si ese componente expone contenido en un formato que no sea PDF, y si el contenido expuesto no se puede convertir a formato PDF, se producirá una excepción en tiempo de ejecución. El mensaje que recibe le informa de que el contenido generado no se puede convertir a formato PDF.

### <a name="limitations"></a>Limitaciones

La opción de conversión de PDF solo está disponible para implementaciones en la nube.

El documento en PDF producido está limitado a una longitud máxima de 300 páginas.

En la **versión 10.0.9** de Finance, solo se admite la orientación de página horizontal en el documento PDF que se produce a partir de una salida de Excel. En la **versión 10.0.10 (mayo de 2020) y posteriores**, puede [especificar la orientación de la página](#SelectPdfPageOrientation) del documento PDF que se produce a partir de una salida de Excel mientras configura un destino de informes electrónicos.

Solo se usan las fuentes comunes del sistema operativo Windows para la conversión de una salida que no contiene fuentes incrustadas.

### <a name="use-the-pdf-conversion-option"></a>Usar la opción de conversión de PDF

Para activar la conversión de PDF para un destino de archivo, seleccione la casilla **Convertir a PDF**.

[![Activar la conversión de PDF para un destino de archivo](./media/ER_Destinations-TurnOnPDFConversion.png)](./media/ER_Destinations-TurnOnPDFConversion.png)

### <a name=""></a><a name="SelectPdfPageOrientation">Seleccione una orientación de página para la conversión de PDF</a>

Si genera una configuración de informes electrónicos en formato Excel y desea convertirla a formato PDF, puede especificar la orientación de la página del documento en PDF. Cuando selecciona la casilla de verificación **Convertir a PDF** para activar la conversión de PDF para un destino de archivo que produce un archivo de salida en formato Excel, el campo **Orientación de la página** está disponible en la ficha desplegable **Configuración de conversión de PDF**. En el campo **Orientación de la página**, seleccione la orientación preferida.

[![Seleccionando una orientación de página para la conversión de PDF](./media/ER_Destinations-SelectPDFConversionPageOrientation.png)](./media/ER_Destinations-SelectPDFConversionPageOrientation.png)

> [!NOTE]
> Para tener la opción de seleccionar la orientación de la página PDF, debe instalar la versión 10.0.10 de Finance o posteriores.
>
> La orientación de página seleccionada se aplica a todas las configuraciones de ER que se generan en formato Excel y luego se convierten a formato PDF.
>
> Si una configuración de informes electrónicos en formato Word se convierte a formato PDF, se toma la orientación de página del documento en Word para el documento en PDF.

## <a name="security-considerations"></a>Consideraciones de seguridad

Se utilizan dos tipos de privilegios y deberes para destinos de ER. Un tipo controla la capacidad general de un usuario de mantener los destinos que están configurados para una entidad jurídica (es decir, controla el acceso a la página **Destinos de informes electrónicos**). El otro tipo controla la capacidad de un usuario de aplicación para reemplazar, en tiempo de ejecución, los parámetros de destino que un desarrollador de ER o consultor funcional de ER han configurado.

| Rol (nombre AOT)                     | Nombre de rol                                  | Aranceles (nombre AOT)                     | Nombre de arancel                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Desarrollador de informes electrónicos             | ERFormatDestinationConfigure        | Configurar destino de formato de informes electrónicos                |
| ERFunctionalConsultant              | Consultor funcional de informes electrónicos | ERFormatDestinationConfigure        | Configurar destino de formato de informes electrónicos                |
| PaymAccountsPayablePaymentsClerk    | Funcionario de pagos de proveedores            | ERFormatDestinationRuntimeConfigure | Configurar destino de formato de informes electrónicos durante el tiempo de ejecución |
| PaymAccountsReceivablePaymentsClerk | Funcionario de pagos de clientes         | ERFormatDestinationRuntimeConfigure | Configurar destino de formato de informes electrónicos durante el tiempo de ejecución |

> [!NOTE]
> Se utilizan dos privilegios en las tareas anteriores. Estos privilegios tienen los mismos nombres que los deberes correspondientes: **ERFormatDestinationConfigure** y **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>He importado configuraciones electrónicas y las veo en la página Configuraciones de informes electrónicos. Pero, ¿por qué no las veo en la página Destinos de informes electrónicos?

Asegúrese de seleccionar **Nueva** y luego seleccione una configuración en el campo **Referencia**. La página **Destinos de informes electrónicos**, solo muestra las configuraciones para las que se han configurado los destinos.

### <a name="is-there-any-way-to-define-which-microsoft-azure-storage-account-and-azure-blob-storage-are-used"></a>¿Hay alguna manera de definir qué cuentas de Microsoft Azure Storage y Azure Blob Storage se utilizan?

N. º Se usa el Microsoft Azure Blob Storage que está definido y se utiliza para el sistema de administración de documentos.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>¿Cuál es el propósito del destino de archivo en la configuración del destino? ¿Qué hace esa configuración?

El destino **Archivo** se utiliza para controlar un cuadro de diálogo de su navegador web cuando ejecuta un informe electrónico en modo interactivo. Si habilita este destino o si no se ha definido ningún destino para una configuración, aparece un cuadro de diálogo para guardar o abrir en su navegador web después de que se cree un archivo de salida.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>¿Puede dar un ejemplo de la fórmula que hace referencia a una cuenta de proveedor a la que puedo enviar correo electrónico?

La fórmula es específica de la configuración de ER. Por ejemplo, si utiliza la configuración de transferencia de crédito de ISO 20022, puede utilizar **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** o **model.Payments.Creditor.Identification.SourceID** para obtener una cuenta de proveedor asociada.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-grouped-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>Una de mis configuraciones de formato contiene varios archivos que se agrupan en una carpeta (por ejemplo, Carpeta1 contiene Archivo1, Archivo2 y Archivo3). ¿Cómo configuro los destinos para que Carpeta1.zip no se cree en absoluto, Archivo1 se envíe por correo electrónico, Archivo2 se envíe a SharePoint y pueda abrir Archivo3 inmediatamente después de que se ejecute la configuración?

Su formato debe estar disponible primero en configuraciones de ER. Si se cumple este requisito previo, abra la página **Destino de informes electrónicos** y cree una nueva referencia a la configuración. A continuación, debe tener cuatro destinos de archivos, uno para cada componente de salida. Crear el primer destino de archivo, asígnele un nombre como **Carpeta** y seleccione un nombre de archivo que represente una carpeta en su configuración. A continuación, seleccione **Configuración** y asegúrese de que todos los destinos están deshabilitados. Para este destino de archivo, no se creará la carpeta. De forma predeterminada, debido a las dependencias jerárquicas entre archivos y carpetas principales, los archivos se comportarán de la misma manera. En otras palabras, no se enviará a ningún lugar. Para anular ese comportamiento predeterminado, debe crear tres destinos de archivos más, uno para cada archivo. En la configuración de destino de cada uno, debe habilitar el destino al que se debe enviar el archivo.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)

[Configurar destinos de informes electrónicos dependientes de acciones](er-action-dependent-destinations.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]