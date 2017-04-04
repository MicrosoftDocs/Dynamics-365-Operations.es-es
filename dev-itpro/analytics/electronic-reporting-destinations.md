---
title: "Destinos de informes electrónicos"
description: "Puede configurar un destino para cada configuración de formato de informes electrónicos y su componente de salida (una carpeta o un archivo). A los usuarios que se le conceden los derechos de acceso adecuados también pueden modificar la configuración de destino en tiempo de ejecución. En este artículo se explica la administración de destinos de ER, los tipos de destinos que son compatibles y consideraciones de seguridad."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DocuType, ERSolutionTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: d38d05fe445bf0326d408038dff84ccf8c0ff64c
ms.lasthandoff: 03/31/2017


---

# <a name="electronic-reporting-destinations"></a>Destinos de informes electrónicos

Puede configurar un destino para cada configuración de formato de informes electrónicos y su componente de salida (una carpeta o un archivo). A los usuarios que se le conceden los derechos de acceso adecuados también pueden modificar la configuración de destino en tiempo de ejecución. En este artículo se explica la administración de destinos de ER, los tipos de destinos que son compatibles y consideraciones de seguridad.

Las configuraciones de formato de informes electrónicos (ER) suelen contener al menos un componente de salida: un archivo. Normalmente, las configuraciones contienen varios componentes de salida de archivo de diferentes tipos (por ejemplo, XML, TXT o XLSX) que se agrupan en una carpeta única o varias carpetas. La administración de destinos ER le permite preconfigurar lo que ocurre cuando se ejecuta cada componente. De forma predeterminada, al ejecutar una configuración, aparece un cuadro de diálogo que permite al usuario guardar o abrir el archivo. El mismo comportamiento también se usa al importar una configuración de ER y no configurar destinos específicos para ella. Después de que se cree un destino para un componente de salida principal, ese destino anula el comportamiento predeterminado y la carpeta o el archivo se envía según la configuración del destino.

## <a name="availability-and-general-prerequisites"></a>Disponibilidad y requisitos previos generales
La funcionalidad de los objetivos de ER no está disponible en Microsoft Dynamics 365 para la liberación de las operaciones (7.0). febrero de 2016 Por lo tanto, debe instalar Microsoft Dynamics 365 para las operaciones (noviembre de 2016 lanzamiento) para utilizar todas las funciones que se describen en este tema. Como alternativa, puede instalar uno de los siguientes requisitos previos. Sin embargo, tenga en cuenta que este la alternativa proporciona una experiencia limitada más de destino de ER.

-   Microsoft Dynamics 365 para la versión de aplicación 7.0.1 de las operaciones (mayo de 2016)
-   [Revisión de aplicación](https://fix.lcs.dynamics.com/issue/results/?q=3160213) de la administración de destinos de ER

Puede configurar destinos solo para configuraciones de ER que se han importado y para los formatos que están disponibles en la página **Configuraciones de informes electrónicos**.

## <a name="overview"></a>Visión general
La funcionalidad de gestión de destino de ER está disponible en ** Administración de organización ** &gt; ** el informe de errores ** electrónico. En este caso, puede anular el comportamiento predeterminado para una configuración. Las configuraciones importadas no se muestran aquí hasta que no hace clic en **Nueva** y, a continuación, en el campo **Referencia** , seleccione una configuración para la que crear la configuración de destino.

[![que selecciona una configuración en el campo Referencia (]. /media/ger-destinations-2-1611-1024x574.jpg])(. /media/ger-destinations-2-1611.jpg) 

Una vez que haya creado una referencia, puede crear un objetivo del archivo para cada carpeta, o para un archivo. 

[![que crea un destino del archivo (]. /media/ger-destinations-1611-1024x586.jpg])(. /media/ger-destinations-1611.jpg)

**Nota:** Puede crear un destino de archivo para cada componente de salida del mismo formato, como una carpeta o un archivo que está seleccionado en el campo **Nombre de archivo**. A continuación habilitar y deshabilitar los destinos individuales para el destino del archivo en ** los valores de destino ** el cuadro de diálogo. El botón **Configuración** se utiliza para controlar todos los destinos para un destino de archivo seleccionado. En el cuadro de diálogo **Configuración de destino**, puede controlar por separado cada destino estableciendo la opción **Habilitado** para él.

[cuadro de diálogo de los valores de destino![] (. /media/ger-destinations-settings-1611-1024x589.jpg])(. /media/ger-destinations-settings-1611.jpg)

## <a name="destination-types"></a>Tipos de destino
Se admiten varios tipos de destinos. Puede deshabilitar o habilitar todos los tipos al mismo tiempo. De esta forma, puede no hacer nada o enviar el componente a todos los destinos configurados. Las secciones siguientes describen los destinos que se admiten.

### <a name="email-destination"></a>Destino de correo electrónico

Establezca **Habilitado **en **Sí** para enviar un archivo de salida por correo electrónico. Después de que se habilite esta opción, puede especificar los destinatarios de correo electrónico, y edita el asunto y el cuerpo de correo electrónico. Puede configurar los textos constantes para el asunto y el cuerpo de correo electrónico, o bien usar las fórmulas de ER dinámicamente para crear textos de correo electrónico. Puede configurar direcciones de correo electrónico para el ER de dos maneras. La configuración se puede completar de la misma manera que la característica de gestión de impresión a Dynamics 365 para las operaciones la completa. Como alternativa, puede resolver una dirección de correo electrónico mediante una referencia directa a la configuración del ER con una fórmula.

### <a name="email-address-types"></a>Tipos de la dirección de correo electrónico

Al hacer clic en ** edición ** para ** ** o ** Cc ** campo, ** correo electrónico ** el cuadro de diálogo. A continuación puede seleccionar el tipo de dirección de correo electrónico que se usará.

[correo electrónico![al cuadro de diálogo] (. /media/ger-destinations-email-1-1611-1024x588.jpg])(. /media/ger-destinations-email-1-1611.jpg)

#### <a name="print-management"></a>Gestión de impresión

Si selecciona ** correo electrónico de la gestión de impresión ** el tipo, puede especificar las direcciones de correo electrónico fijas en ** ** al campo. Para utilizar direcciones de correo electrónico que no se modifican, debe seleccionar el tipo de origen de correo electrónico para un destino del archivo. Se admiten los siguientes valores: ** Cliente **, ** ** proveedor, cliente potencial ** **, ** ** contacto, ** competidor **, ** ** trabajador, ** ** candidato, ** ** proveedor potencial, y ** proveedor no permitido **. Tras seleccionar un tipo de origen de correo electrónico, use el botón junto a ** cuenta de origen de correo electrónico ** campo para abrir ** diseñador de fórmula ** el formulario. Puede usar este formulario para vincular una fórmula que represente la cuenta de la parte seleccionada al destino de correo electrónico.

[![configura el tipo de correo electrónico de la gestión de impresión] (. /media/ger-destinations-email-2-1611-1024x588.jpg])(. /media/ger-destinations-email-2-1611.jpg) 

Tenga en cuenta que las fórmulas son específicas de la configuración de ER. En la **Fórmula**, especifique una referencia específica de documento para un tipo de parte de cliente o proveedor. En lugar de escribir, puede encontrar el nodo del origen de datos que represente la cuenta del cliente o proveedor y, a continuación, hacer clic en el botón **Agregar origen de datos** para actualizar la fórmula. Por ejemplo, si utiliza la configuración ISO 20022 Transferencia de crédito, el nodo que representa una cuenta de proveedor es **'$PaymentsForCoveringLetter".Creditor.Identification.SourceID**. De lo contrario, especifique cualquier valor de cadena, como **DE-001**, para guardar una fórmula.

[![Formula designer](./media/ger_formuladesignerfordestination-1024x541.jpg)](./media/ger_formuladesignerfordestination.jpg)

En ** correo electrónico ** el cuadro de diálogo, haga clic en la papelera de reciclaje junto a ** cuenta de origen de correo electrónico ** del campo para eliminar de forma permanente la fórmula para la cuenta de origen del correo electrónico. Como alternativa, abra el diseñador de fórmula para cambiar una fórmula que se guardada anteriormente. Para asignar a direcciones de correo electrónico, haga clic en ** edición ** para abrir ** las direcciones de correo electrónico de la asignación ** el cuadro de diálogo.

[direcciones de correo electrónico de la asignación![para un destino de correo electrónico (]. /media/ger-destinations-email-3-1611-1024x587.jpg])(. /media/ger-destinations-email-3-1611.jpg)

#### <a name="configuration-email"></a>Correo electrónico de configuración

Usa este tipo de correo electrónico si la configuración que utiliza tiene un nodo en los orígenes de datos que representa una dirección de correo electrónico. Puede usar orígenes de datos y funciones en el diseñador de fórmula para obtener una dirección de correo electrónico con formato correctamente.

[![que asigna un origen de datos de la dirección de correo electrónico para un destino de correo electrónico (]. /media/ger-destinations-email-4-1611-1024x587.jpg])(. /media/ger-destinations-email-4-1611.jpg) 

**Nota:** Un servidor de Protocolo simple de transferencia de correo (SMTP) se debe configurar y estar disponible. Puede especificar al servidor SMTP en Dynamics 365 para las operaciones, en ** Administración del sistema ** &gt; ** la configuración ** &gt; ** correo electrónico ** &gt; ** los parámetros de correo electrónico **.

### <a name="archive-destination"></a>Destino de archivo

Puede utilizar esta opción para enviar la salida a una carpeta de Microsoft SharePoint o el Almacenamiento de Microsoft Azure. Establezca **Habilitada** en **Sí **para enviar la salida a un destino que se define por el tipo de documento seleccionado. Solo los tipos de documento donde el grupo se establece en **Archivo** están disponibles para su selección. Defina tipos de documento en ** Administración de organización ** &gt; ** la gestión de documentos ** &gt; ** los tipos de documento **. La configuración de destinos de ER es la misma que la configuración para el sistema de administración de documentos.

[página de tipos de documentos![] (. /media/ger_documenttypefile-1024x542.jpg])(. /media/ger_documenttypefile.jpg) 

La ubicación determina dónde se guarda el archivo. Una vez que ** archivo ** se habilite el destino, los resultados de la ejecución de la configuración se pueden guardar en el archivo de trabajo. Puede ver los resultados en ** Administración de organización ** &gt; ** el informe de errores electrónico ** &gt; ** los trabajos almacenados informe de errores ** electrónico. ** Nota: ** Puede seleccionar un tipo de documento para el trabajo almacenado en Dynamics 365 para las operaciones, en ** Administración de organización ** &gt; ** las áreas de trabajo ** &gt; ** informe de errores electrónico ** &gt; ** los parámetros electrónicos de informes **.

#### <a name="sharepoint"></a>SharePoint

Puede guardar un archivo en una carpeta de SharePoint designada. Defina el servidor predeterminado de SharePoint ** en Administración de organización ** &gt; ** la gestión de documentos ** &gt; ** los formularios document management parameters **, en SharePoint ** ** la ficha. Tras configurar la carpeta de SharePoint, puede marcarlo como carpeta donde se guardará la producción de ER para el tipo de documento. 

[![que selecciona una carpeta de SharePoint (]. /media/ger_sharepointfolderselection-1024x543.jpg])(. /media/ger_sharepointfolderselection.jpg) 

#### <a name="azure-storage"></a>Almacenamiento de Azure

Cuando se establece la ubicación del tipo de documento en **Directorio de archivo**, puede guardar un archivo en el Almacenamiento de Azure.

### <a name="file-destination"></a>Destino de archivo

Si establece ** habilitado ** ** Sí **, un cuadro de diálogo Abrir o Guardar se produce cuando la configuración ha terminado de ejecutar.

### <a name="screen-destination"></a>Destino de la pantalla

Si establece ** habilitado ** ** Sí **, una vista previa de salida crean. Puede ver algunos tipos de archivo, como XML, TXT, o PDF, directamente en una ventana de explorador. Para otros tipos de archivo, se usará por Microsoft Excel o Word, el servicio de Microsoft Office Online.

### <a name="power-bi-destination"></a>Destino de Power BI

Conjunto ** habilitado ** ** Sí ** para utilizar la configuración del ER para organizar la transferencia de datos de la instancia de Dynamics 365 para las operaciones a los servicios de Power BI de Microsoft. Los archivos transferir se almacenan en una instancia del servidor de Microsoft SharePoint que se debe configurar para ese propósito. Para obtener más información, consulte [use una configuración electrónica de informes para proporcionar el BI de la potencia con datos de las Dynamics 365 para las operaciones general-electronic-reporting-report-configuration-get-data-powerbi.md] (). **Sugerencia:** Para reemplazar el comportamiento predeterminado (es decir, el cuadro de diálogo para una configuración), puede crear una referencia de destino y un archivo de destino para el componente de salida principal y, a continuación, deshabilitar todos los destinos.

## <a name="security-considerations"></a>Consideraciones de seguridad
Se utilizan dos tipos de privilegios y deberes para destinos de ER. Los controles escritos uno la capacidad de mantener los destinos totales que se configuran para una entidad jurídica (es decir, controla el acceso ** los destinos electrónicos de informes ** a la página). El otro tipo controla la capacidad de un usuario de aplicación para reemplazar, en tiempo de ejecución, los parámetros de destino que se configuran por un desarrollador de ER o consultor funcional de ER.

| Rol (nombre AOT)                     | Nombre de rol                                  | Aranceles (nombre AOT)                     | Nombre del derecho                                                        |
|-------------------------------------|--------------------------------------------|-------------------------------------|------------------------------------------------------------------|
| ERDeveloper                         | Desarrollador de informes electrónicos             | ERFormatDestinationConfigure        | Configurar destino de formato de informes electrónicos                |
| ERFunctionalConsultant              | Consultor funcional de informes electrónicos | ERFormatDestinationConfigure        | Configurar destino de formato de informes electrónicos                |
| PaymAccountsPayablePaymentsClerk    | Funcionario de pagos de proveedores            | ERFormatDestinationRuntimeConfigure | Configurar destino de formato de informes electrónicos durante el tiempo de ejecución |
| PaymAccountsReceivablePaymentsClerk | Funcionario de pagos de clientes         | ERFormatDestinationRuntimeConfigure | Configurar destino de formato de informes electrónicos durante el tiempo de ejecución |

**Nota:** Se utilizan dos privilegios en las tareas anteriores. Estos privilegios tienen los mismos nombres que los deberes correspondientes: **ERFormatDestinationConfigure** y **ERFormatDestinationRuntimeConfigure**.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes
### <a name="i-have-imported-electronic-configurations-and-i-see-them-on-the-electronic-reporting-configurations-page-but-why-dont-i-see-them-on-the-electronic-reporting-destinations-page"></a>He importado configuraciones electrónicas y las veo en la página Configuraciones de informes electrónicos. ¿Pero por qué no los consulto en la página electrónica de los objetivos de informes?

Asegúrese de hacer clic en ** nuevo ** y seleccione una configuración en ** referencia ** el campo. En la página **Destinos de informes electrónicos**, solo puede ver las configuraciones para las que se han configurado los destinos.

### <a name="is-there-any-way-to-define-which-azure-storage-account-and-azure-blob-storage-are-used"></a>¿Hay forma de definir qué se utiliza cuenta Azure Storage Azure Storage y almacenamiento Azure Blob?

N. º Se utiliza el almacenamiento Azure Blob Azure Blob predeterminado definido y se utiliza para el sistema de gestión de documentos.

### <a name="what-is-the-purpose-of-the-file-destination-in-the-destination-settings-what-does-that-setting-do"></a>¿Qué es el propósito de destino de archivo en los valores de destino? ¿Qué hace esa configuración?

El destino del **Archivo** se utiliza para controlar un cuadro de diálogo. Si se activa el destino, o si no se define un destino para una configuración, verá un cuadro de diálogo Abrir o Guardar después de que se cree un archivo de salida.

### <a name="can-you-give-an-example-of-the-formula-that-refers-to-a-vendor-account-that-i-can-send-email-to"></a>¿Puede dar un ejemplo de la fórmula que hace referencia a una cuenta de proveedor a la que puedo enviar correo electrónico?

La fórmula es específica de la configuración de ER. Por ejemplo, si utiliza la configuración de transferencia de crédito de ISO 20022, puede utilizar **'$PaymentsForCoveringLetter'.Creditor.Identification.SourceID** o **model.Payments.Creditor.Identification.SourceID** para obtener una cuenta de proveedor asociada.

### <a name="one-of-my-format-configurations-contains-multiple-files-that-are-group-into-one-folder-for-example-folder1-contains-file1-file2-and-file3-how-do-i-set-up-destinations-so-that-folder1zip-isnt-created-at-all-file1-is-sent-by-email-file2-is-sent-to-sharepoint-and-i-can-open-file3-immediately-after-the-configuration-is-run"></a>Una de mis configuraciones de formato contiene varios archivos que se agrupan en una carpeta (por ejemplo, Carpeta1 contiene Archivo1, Archivo2 y Archivo3). ¿Cómo configuro los destinos para que Carpeta1.zip no se cree en absoluto, Archivo1 se envíe por correo electrónico, Archivo2 se envíe a SharePoint y pueda abrir Archivo3 inmediatamente después de que se ejecute la configuración?

El requisito previo es que su formato debe estar disponible en las configuraciones de ER. Si tiene su formato, abra la página **Destino de informes electrónicos** y cree una nueva referencia a esta configuración. A continuación, debe tener cuatro destinos de archivos, uno para cada componente de salida. Crear el primer destino de archivo, asígnele un nombre como **Carpeta**y seleccione un nombre de archivo que represente una carpeta en su configuración. A continuación, haga clic en **Configuración**y asegúrese de que todos los destinos están deshabilitados. Para este destino de archivo, no se creará la carpeta. De forma predeterminada, debido a las dependencias jerárquicas entre archivos y carpetas principales, los archivos se comportarán de la misma manera. En otras palabras, no se enviará a ningún lugar. Para anular ese comportamiento predeterminado, debe crear tres destinos de archivos más, uno para cada archivo. En la configuración de destino de cada uno, debe habilitar el destino al que se debe enviar el archivo.

# <a name="see-also"></a>Consulte también

[Visión general de los informes electrónicos](general-electronic-reporting.md)


