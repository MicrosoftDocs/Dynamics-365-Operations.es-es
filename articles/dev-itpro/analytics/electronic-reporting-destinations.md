---
title: "Destinos de informes electrónicos"
description: "Puede configurar un destino para cada configuración de formato de informes electrónicos y su componente de salida (una carpeta o un archivo). A los usuarios que se le conceden los derechos de acceso adecuados también pueden modificar la configuración de destino en tiempo de ejecución. En este artículo se explica la administración de destinos de ER, los tipos de destinos que son compatibles y consideraciones de seguridad."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: fb7d0dc8b3ff9e8f1e4ade5cacfeed8f1a6871ab
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="electronic-reporting-destinations"></a>Destinos de informes electrónicos

[!include [banner](../includes/banner.md)]

Puede configurar un destino para cada configuración de formato de informes electrónicos y su componente de salida (una carpeta o un archivo). A los usuarios que se le conceden los derechos de acceso adecuados también pueden modificar la configuración de destino en tiempo de ejecución. En este artículo se explica la administración de destinos de ER, los tipos de destinos que son compatibles y consideraciones de seguridad.

Las configuraciones de formato de informes electrónicos (ER) suelen contener al menos un componente de salida: un archivo. Normalmente, las configuraciones contienen varios componentes de salida de archivo de diferentes tipos (por ejemplo, XML, TXT o XLSX) que se agrupan en una carpeta única o varias carpetas. La administración de destinos ER le permite preconfigurar lo que ocurre cuando se ejecuta cada componente. De forma predeterminada, cuando se ejecuta una configuración, se muestra un cuadro de diálogo que permite al usuario guardar o abrir el archivo. El mismo comportamiento también se usa al importar una configuración de ER y no configurar destinos específicos para ella. Después de que se cree un destino para un componente de salida principal, ese destino anula el comportamiento predeterminado y la carpeta o el archivo se envía según la configuración del destino.

## <a name="availability-and-general-prerequisites"></a>Disponibilidad y requisitos previos generales
La funcionalidad de los destinos de ER no está disponible en Microsoft Dynamics AX 7.0 (febrero de 2016). Por lo tanto, debe instalar la versión 1611 de Microsoft Dynamics 365 for Operations (noviembre de 2016) para utilizar todas las funciones que se describen en este tema. O bien, puede instalar uno de los siguientes requisitos previos. Sin embargo, tenga en cuenta que esta alternativa proporciona una experiencia de destino de ER más limitada.

-   Versión de la aplicación 7.0.1 de Microsoft Dynamics AX (mayo de 2016)
-   [Revisión de aplicación](https://fix.lcs.dynamics.com/issue/results/?q=3160213) de la administración de destinos de ER

Puede configurar destinos solo para configuraciones de ER que se han importado y para los formatos que están disponibles en la página **Configuraciones de informes electrónicos**.

## <a name="overview"></a>Visión general
La funcionalidad de administración de destinos de ER está disponible en **Administración de la organización** &gt; **Informes electrónicos**. En este caso, puede anular el comportamiento predeterminado para una configuración. Las configuraciones importadas no se muestran aquí hasta que no hace clic en **Nueva** y, a continuación, en el campo **Referencia** , seleccione una configuración para la que crear la configuración de destino.

[![Selección de una configuración en el campo Referencia](./media/ger-destinations-2-1611-1024x574.jpg)](./media/ger-destinations-2-1611.jpg) 

Después de haber creado una referencia, puede crear un destino de archivo para cada carpeta o para un archivo. 

[![Crear un archivo de destino](./media/ger-destinations-1611-1024x586.jpg)](./media/ger-destinations-1611.jpg)

> [!NOTE] 
> Puede crear un destino de archivo para cada componente de salida del mismo formato, como una carpeta o un archivo que está seleccionado en el campo **Nombre de archivo**. A continuación, puede habilitar y deshabilitar destinos individuales para el destino de archivo en el cuadro de diálogo **Configuración de destino**. El botón **Configuración** se utiliza para controlar todos los destinos para un destino de archivo seleccionado. En el cuadro de diálogo **Configuración de destino**, puede controlar por separado cada destino estableciendo la opción **Habilitado** para él.

[![Cuadro de diálogo Configuración de destino](./media/ger-destinations-settings-1611-1024x589.jpg)](./media/ger-destinations-settings-1611.jpg)

## <a name="destination-types"></a>Tipos de destino
Se admiten varios tipos de destinos. Puede deshabilitar o habilitar todos los tipos al mismo tiempo. De esta forma, puede no hacer nada o enviar el componente a todos los destinos configurados. Las secciones siguientes describen los destinos que se admiten.

### <a name="email-destination"></a>Destino de correo electrónico

Establezca **Habilitado** en **Sí** para enviar un archivo de salida por correo electrónico. Después de que se haya habilitado esta opción, puede especificar los destinatarios de correo electrónico y editar el asunto y el cuerpo del mensaje de correo electrónico. Puede configurar textos constantes para el asunto y el cuerpo de correo electrónico, o bien usar las fórmulas de ER dinámicamente para crear textos de correo electrónico. Puede configurar direcciones de correo electrónico para el ER de dos maneras. La configuración se puede completar de la misma manera en que la característica de gestión de impresión en Finance and Operations la completa. Como alternativa, puede resolver una dirección de correo electrónico mediante una referencia directa a la configuración del ER con una fórmula.

### <a name="email-address-types"></a>Tipos de direcciones de correo electrónico

Al hacer clic en **Editar** para el campo **Para** o **Cc**, se muestra el cuadro de diálogo **Correo electrónico para**. A continuación puede seleccionar el tipo de dirección de correo electrónico que se usará.

[![Cuadro de diálogo Correo electrónico para](./media/ger-destinations-email-1-1611-1024x588.jpg)](./media/ger-destinations-email-1-1611.jpg)

#### <a name="print-management"></a>Gestión de impresión

Si selecciona el tipo **Correo electrónico de administración de impresión**, puede especificar direcciones de correo electrónico fijas en el campo **Para**. Para utilizar direcciones de correo electrónico que no son fijas, debe seleccionar el tipo de origen de correo electrónico para un destino de archivo. Se admiten los siguientes valores: **Cliente**, **Proveedor**, **Cliente potencial**, **Contacto**, **Competidor**, **Trabajador**, **Candidato**, **Proveedor potencial** y **Proveedor no permitido**. Tras seleccionar un tipo de origen de correo electrónico, use el botón junto al campo **Cuenta de origen de correo electrónico** para abrir el formulario **Diseñador de fórmula**. Puede usar este formulario para vincular una fórmula que represente la cuenta de la parte seleccionada al destino de correo electrónico.

[![Configure el tipo de correo electrónico de la gestión de impresión](./media/ger-destinations-email-2-1611-1024x588.jpg)](./media/ger-destinations-email-2-1611.jpg) 

Tenga en cuenta que las fórmulas son específicas de la configuración de ER. En la **Fórmula**, especifique una referencia específica de documento para un tipo de parte de cliente o proveedor. En lugar de escribir, puede encontrar el nodo del origen de datos que represente la cuenta del cliente o proveedor y, a continuación, hacer clic en el botón **Agregar origen de datos** para actualizar la fórmula. Por ejemplo, si utiliza la configuración ISO 20022 Transferencia de crédito, el nodo que representa una cuenta de proveedor es **'$PaymentsForCoveringLetter".Creditor.Identification.SourceID**. De lo contrario, especifique cualquier valor de cadena, como **DE-001**, para guardar una fórmula.

[![Diseñador de fórmula](./media/ger_formuladesignerfordestination-1024x541.jpg)](./media/ger_formuladesignerfordestination.jpg)

En el cuadro de diálogo **Correo electrónico para**, haga clic en la papelera de reciclaje junto al campo **Cuenta de origen de correo electrónico** para eliminar de forma permanente la fórmula para la cuenta de origen del correo electrónico. Como alternativa, abra el diseñador de fórmula para cambiar una fórmula que se guardó anteriormente. Para asignar direcciones de correo electrónico, haga clic en **Editar** para abrir el cuadro de diálogo **Asignar direcciones de correo electrónico**.

[![Asignar direcciones de correo electrónico para un destino de correo electrónico](./media/ger-destinations-email-3-1611-1024x587.jpg)](./media/ger-destinations-email-3-1611.jpg)

#### <a name="configuration-email"></a>Correo electrónico de configuración

Use este tipo de correo electrónico si la configuración que utiliza tiene un nodo en los orígenes de datos que representa una dirección de correo electrónico. Puede usar orígenes de datos y funciones en el diseñador de fórmula para obtener una dirección de correo electrónico con formato correcto.

[![Asignar un origen de datos de direcciones de correo electrónico para un destino de correo electrónico](./media/ger-destinations-email-4-1611-1024x587.jpg)](./media/ger-destinations-email-4-1611.jpg) 

**Nota:** Un servidor de Protocolo simple de transferencia de correo (SMTP) se debe configurar y estar disponible. Puede especificar el servidor SMTP en Finance and Operations, en **Administración del sistema** &gt; **Configuración** &gt; **Correo electrónico** &gt; **Parámetros del correo electrónico**.

### <a name="archive-destination"></a>Destino de archivo

Puede utilizar esta opción para enviar la salida a una carpeta de Microsoft SharePoint o el Almacenamiento de Microsoft Azure. Establezca **Habilitada** en **Sí** para enviar la salida a un destino que se define por el tipo de documento seleccionado. Solo los tipos de documento donde el grupo se establece en **Archivo** están disponibles para su selección. Defina los tipos de documento en **Administración de la organización** &gt; **Administración de documentos** &gt; **Tipos de documento**. La configuración de destinos de ER es la misma que la configuración para el sistema de administración de documentos.

[![Página de tipos de documento](./media/ger_documenttypefile-1024x542.jpg)](./media/ger_documenttypefile.jpg) 

La ubicación determina dónde se guarda el archivo. Una vez que se habilite el destino de **Archivado**, los resultados de la ejecución de la configuración se pueden guardar en el archivo de trabajo. Puede ver los resultados en **Administración de organización** &gt; **Informes electrónicos** &gt; **Trabajos archivados de informes electrónicos**. **Nota:** Puede seleccionar un tipo de documento para el archivo de trabajo en Finance and Operations, en **Administración de organización** &gt; **Áreas de trabajo** &gt; **Informes electrónicos** &gt; **Parámetros de informes electrónicos**,

#### <a name="sharepoint"></a>SharePoint

Puede guardar un archivo en una carpeta de SharePoint designada. Defina el servidor predeterminado de SharePoint en **Gestión de la organización** &gt; **Gestión de documentos** &gt; **Parámetros de la gestión de documentos**, en la pestaña **SharePoint**. Tras configurar la carpeta de SharePoint, puede marcarla como la carpeta donde se guardará la salida de ER del tipo de documento. 

[![Selección de una carpeta de SharePoint](./media/ger_sharepointfolderselection-1024x543.jpg)](./media/ger_sharepointfolderselection.jpg) 

#### <a name="azure-storage"></a>Almacenamiento de Azure

Cuando se establece la ubicación del tipo de documento en **Directorio de archivo**, puede guardar un archivo en el Almacenamiento de Azure.

### <a name="file-destination"></a>Destino de archivo

Si establece **Habilitado** en **Sí** se abre un cuadro de diálogo para abrir o guardar cuando la configuración termina de ejecutarse.

### <a name="screen-destination"></a>Destino de la pantalla

Si establece **Habilitado** en **Sí**, se crea una vista previa de la salida. Puede ver algunos tipos de archivo, como XML, TXT o PDF, directamente en una ventana de explorador. Para otros tipos de archivo, como Microsoft Excel o Word, se usa el servicio de Microsoft Office Online.

### <a name="power-bi-destination"></a>Destino de Power BI

Establezca **Habilitado** en **Sí** para usar la configuración de ER para organizar la transferencia de datos de la instancia de Finance and Operations a los servicios de Microsoft Power BI. Los archivos transferidos se almacenan en una instancia de Microsoft SharePoint Server que debe configurarse para ese propósito. Para obtener más información, consulte [Usar una configuración electrónica de informes para proporcionar datos de Finance and Operations a Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md). **Sugerencia:** Para reemplazar el comportamiento predeterminado (es decir, el cuadro de diálogo para una configuración), puede crear una referencia de destino y un archivo de destino para el componente de salida principal y, a continuación, deshabilitar todos los destinos.

## <a name="security-considerations"></a>Consideraciones de seguridad
Se utilizan dos tipos de privilegios y deberes para destinos de ER. Un tipo controla la capacidad de mantener los destinos generales que están configurados para una entidad jurídica (es decir, controla el acceso a la página **Destinos de informes electrónicos** ). El otro tipo controla la capacidad de un usuario de aplicación para reemplazar, en tiempo de ejecución, los parámetros de destino que se configuran por un desarrollador de ER o consultor funcional de ER.

| Rol (nombre AOT)                     | Nombre de rol                                  | Aranceles (nombre AOT)                     | Nombre del derecho                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Desarrollador de informes electrónicos             | ERFormatDestinationConfigure        | Configurar destino de formato de informes electrónicos                |
| ERFunctionalConsultant              | Consultor funcional de informes electrónicos | ERFormatDestinationConfigure        | Configurar destino de formato de informes electrónicos                |
| PaymAccountsPayablePaymentsClerk    | Funcionario de pagos de proveedores            | ERFormatDestinationRuntimeConfigure | Configurar destino de formato de informes electrónicos durante el tiempo de ejecución |
| PaymAccountsReceivablePaymentsClerk | Funcionario de pagos de clientes         | ERFormatDestinationRuntimeConfigure | Configurar destino de formato de informes electrónicos durante el tiempo de ejecución |

> [!NOTE]
> Se utilizan dos privilegios en las tareas anteriores. Estos privilegios tienen los mismos nombres que los deberes correspondientes: **ERFormatDestinationConfigure** y **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes
### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>He importado configuraciones electrónicas y las veo en la página Configuraciones de informes electrónicos. Pero, ¿por qué no las veo en la página Destinos de informes electrónicos?

Asegúrese de hacer clic en **Nueva** y luego seleccione una configuración en el campo **Referencia**. En la página **Destinos de informes electrónicos**, solo puede ver las configuraciones para las que se han configurado los destinos.

### <a name="is-there-any-way-to-define-which-azure-storage-account-and-azure-blob-storage-are-used"></a>¿Hay alguna manera de definir qué cuentas de Azure Storage y Azure Blob Storage se utilizan?

N. º Se usa el Azure Blob Storage que está definido y se utiliza para el sistema de administración de documentos.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>¿Cuál es el propósito del destino de archivo en la configuración del destino? ¿Qué hace esa configuración?

El destino del **Archivo** se utiliza para controlar un cuadro de diálogo. Si habilita este destino o si no se ha definido ningún destino para una configuración, ve un cuadro de diálogo para guardar o abrir después de que se cree un archivo de salida.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>¿Puede dar un ejemplo de la fórmula que hace referencia a una cuenta de proveedor a la que puedo enviar correo electrónico?

La fórmula es específica de la configuración de ER. Por ejemplo, si utiliza la configuración de transferencia de crédito de ISO 20022, puede utilizar **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** o **model.Payments.Creditor.Identification.SourceID** para obtener una cuenta de proveedor asociada.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-group-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>Una de mis configuraciones de formato contiene varios archivos que se agrupan en una carpeta (por ejemplo, Carpeta1 contiene Archivo1, Archivo2 y Archivo3). ¿Cómo configuro los destinos para que Carpeta1.zip no se cree en absoluto, Archivo1 se envíe por correo electrónico, Archivo2 se envíe a SharePoint y pueda abrir Archivo3 inmediatamente después de que se ejecute la configuración?

El requisito previo es que el formato debe estar disponible en las configuraciones de ER. Si tiene su formato, abra la página **Destino de informes electrónicos** y cree una nueva referencia a esta configuración. A continuación, debe tener cuatro destinos de archivos, uno para cada componente de salida. Crear el primer destino de archivo, asígnele un nombre como **Carpeta** y seleccione un nombre de archivo que represente una carpeta en su configuración. A continuación, haga clic en **Configuración** y asegúrese de que todos los destinos están deshabilitados. Para este destino de archivo, no se creará la carpeta. De forma predeterminada, debido a las dependencias jerárquicas entre archivos y carpetas principales, los archivos se comportarán de la misma manera. En otras palabras, no se enviará a ningún lugar. Para anular ese comportamiento predeterminado, debe crear tres destinos de archivos más, uno para cada archivo. En la configuración de destino de cada uno, debe habilitar el destino al que se debe enviar el archivo.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos](general-electronic-reporting.md)




