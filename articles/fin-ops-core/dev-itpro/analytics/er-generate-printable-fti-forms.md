---
title: Generar formularios FTI imprimibles
description: Este tema explica cómo utilizar el marco de informes electrónicos (ER) para generar formularios de facturas de servicio (FTI) imprimibles como documentos de Microsoft Office.
author: NickSelin
manager: AnnBe
ms.date: 07/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 731b6a61bd78388f3db0a7007478e3a5e9629a49
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181436"
---
# <a name="generate-printable-fti-forms"></a>Generar formularios de FTI imprimibles

[!include[banner](../includes/banner.md)]

El marco de informes electrónicos (ER) le permite generar formularios de facturas de texto libre (FTI) imprimibles como documentos de Microsoft Office. Este tema proporciona información sobre cómo crear sus propias configuraciones, así como detalles de las plantillas de configuración disponibles.

## <a name="overview"></a>Información general

Además de la capacidad existente de generar formularios de FTI imprimibles mediante Microsoft SQL Server Reporting Services (SSRS), ahora puede utilizar el marco de ER. Puede administrar los formularios de FTI imprimibles en Microsoft Office Excel y Word. También puede modificar el diseño, el flujo de datos y el formato para satisfacer requisitos específicos sin realizar cambios en el código.

> [!NOTE]
> Si desea comenzar con una descripción general de las configuraciones de ER existentes para esta muestra de la solución de formularios de FTI imprimibles, puede ir directamente a la sección **Descargar ejemplos de configuraciones de ER para generar formularios de FTI imprimibles** más adelante en este tema.

## <a name="create-customized-configurations-for-fti-printable-forms"></a>Cree configuraciones personalizadas para formularios de FTI imprimibles
Como parte de su solución personalizada para formularios de FTI imprimibles, debe crear un conjunto de configuraciones de ER.

### <a name="configure-the-er-data-model"></a>Configurar el modelo de datos de ER
Su aplicación debe incluir la configuración del modelo de datos de ER que contiene un modelo de datos que describe el dominio empresarial de facturación del cliente. Como requisito, el nombre del modelo de datos debe ser **CustomersInvoicing**. Para obtener información acerca de cómo diseñar modelos de datos de ER, consulte [Diseñar un modelo de datos específico de dominio para informes electrónicos (ER)](tasks/er-design-domain-specific-data-model-2016-11.md).

### <a name="configure-the-er-model-mapping"></a>Configurar la asignación del modelo de ER
Su aplicación debe incluir la asignación del modelo de ER para el modelo de datos CustomersInvoicing. La asignación de modelo puede estar en la configuración del modelo de datos de ER o en la configuración de la asignación de modelo de ER. Sin embargo, el nombre del descriptor raíz del asignación de modelo debe ser **FreeTextInvoice**.

La asignación debe contener los orígenes de datos siguientes:

- Tipo de origen de datos: **Registros de tabla**

    - Este origen de datos se debe denominar **CustInvoiceJour**.
    - Debe hacer referencia a la tabla de aplicación CustInvoiceJour.
    - Se utiliza en el tiempo de ejecución para pasar desde la aplicación a la asignación de modelo de ER la lista de facturas que se han seleccionado para imprimir.

- Tipo de origen de datos: **Objeto**

    - Este origen de datos se debe denominar **PrintMgmtPrintSettingDetail**.
    - Debe hacer referencia a la clase de aplicación **PrintMgmtPrintSettingDetail**.
    - Se utiliza en el tiempo de ejecución para pasar desde la aplicación a la asignación de modelo de ER los detalles de la configuración de administración de impresión correspondiente al formato ER que se está ejecutando.

Los detalles de la integración de la aplicación con el marco de ER se pueden encontrar en la clase **ERPrintMgmtReportFormatSubscriber** (modelo de integración de la suite de aplicaciones de ER) en el código fuente de la aplicación.

Para obtener más información sobre el diseño de las asignaciones de modelo de ER, consulte [Definir la asignación de modelo y seleccionar los orígenes de datos para informes electrónicos (ER)](tasks/er-define-model-mapping-select-data-sources-2016-11.md).

### <a name="configure-the-er-format"></a>Configurar el formato de ER
En la instancia de la aplicación, debe tener la configuración de formato de ER que se utilizará para generar formularios de FTI. 

> [!NOTE]
> Esta configuración de formato debe crearse para el modelo de datos CustomersInvoicing y debe utilizar la asignación de modelo que tiene el descriptor raíz **FreeTextInvoice**.

Para obtener información sobre cómo configurar los formatos de ER, consulte [Crear una configuración de formato para informes electrónicos (ER)](tasks/er-format-configuration-2016-11.md). Para obtener información acerca de cómo diseñar formatos de ER para generar informes en formato OpenXML, consulte [Diseñar una configuración para generar informes en formato OpenXML para informes electrónicos (ER)](tasks/er-design-reports-openxml-2016-11.md).

## <a name="configure-print-management"></a>Configurar la administración de impresión
Para generar los formularios de FTI mediante el marco de ER, puede asignar los formatos de ER de la misma manera que se asignan los informes de SSRS. Para asociar el formato de ER con todas las FTI de clientes, vaya a **Clientes** \> **Configuración** \> **Formularios** \> **Configuración de formulario** \> **General** \> **Gestión de impresión** \> **Factura de servicios** \> **Original**. Para asociar el formato de ER con un cliente o una factura específica, siga estos pasos.

1. Vaya a **Clientes** \> **Facturas** \> **Todas las facturas de servicios**.
2. Seleccione la FTI a la que desea asociar el formato de ER y abra la página **Configuración de la gestión de impresiones**.
3. Seleccione el nivel de documento para especificar el ámbito de las facturas que se procesarán.
4. Seleccione el formato de ER para el nivel de documento especificado.

![Configuración de la gestión de impresiones](media/FTIbyGER-PMSetting.png)

> [!NOTE]
> Solo los formatos de ER que usan el descriptor raíz **FreeTextInvoice** del modelo de datos **CustomersInvoicing** aparecen en el campo **Búsqueda de formato de informe** para el formato seleccionado.

## <a name="generate-fti-forms"></a>Generar formularios de FTI
Los formularios de FTI se generan en el marco de ER de la misma manera que se generan los informes de SSRS.

Para generar los formularios de FTI, puede seleccionar facturas por intervalo o por selección. 

![Selección de facturas](media/FTIbyGER-InvoiceSelection.png)

![Vista previa de facturas](media/FTIbyGER-InvoiceExcelPreview.png)

Cuando se utilizan formatos de ER para imprimir formularios de FTI de este modo, se utilizan los destinos de archivo de ER predeterminados. No puede cambiar el destino. Para obtener más información sobre cómo configurar los destinos de ER para formatos de ER, consulte [Destinos de informes electrónicos](electronic-reporting-destinations.md).

También puede generar formularios de FTI al registrar una FTI, activando **Imprimir factura** y desactivando **Usar destinos de gestión de impresión**.

> [!NOTE]
> Cuando se utilizan formatos de ER para imprimir formularios de FTI de este modo, se utilizan los destinos de archivo de ER predeterminados. Puede cambiar el destino predeterminado en tiempo de ejecución si ya se ha configurado el destino. Para cambiar el destino, debe tener el privilegio de seguridad siguiente:
>
> - **Nombre:** ERFormatDestinationRuntimeMaintain
> - **Etiqueta:** Mantener destino de formato de informes electrónicos durante el tiempo de ejecución

![Destino de informes electrónicos](media/FTIbyGER-ERFileDestinationSetting.png)

![Destino de formato de informes electrónicos](media/FTIbyGER-ERFileDestinationUsage.png)

El marco de ER admite actualmente los siguientes destinos para documentos generados:

- **Archivo descargado**: los formularios generados se proporcionan como descargas que puede guardar mediante el explorador.
- **Pantalla**: Microsoft Office 365 Excel se usa para obtener una vista previa de los formularios de FTI generados en formato Excel.
- **Carpeta de SharePoint**: se almacenan los formularios generados según la configuración del marco de administración de documentos.
- **Archivo de la aplicación**: los formularios generados se almacenan como archivos adjuntos de los registros de ejecución de Microsoft Azure Storage.
- **Correo electrónico**: los formularios generados se envía como archivos adjuntos de correo electrónico.

> [!NOTE]
> No puede enviar los formularios de FTI que se generan directamente a la impresora, porque la impresión directa que utiliza el Agente de ruta de impresora de Dynamics no se admite actualmente.

## <a name="download-sample-er-configurations-to-generate-printable-fti-forms"></a>Descargar ejemplos de configuraciones de ER para generar formularios de FTI imprimibles
Puede descargar ejemplos de configuraciones de ER para utilizarlos como una plantilla de su solución de FTI. Las configuraciones se almacenan en la biblioteca de activos compartidos de Microsoft Dynamics Lifecycle Services (LCS). Las configuraciones incluyen:

- La configuración **Modelo de facturación del cliente** contiene el modelo de datos y la asignación de modelo necesarios.
- La configuración **Informe de FTI de cliente (GER)** contiene el formato de muestra.

> [!NOTE]
> Estas configuraciones se han creado como ejemplos para ayudar a clarificar los posibles escenarios. El futuro de estas configuraciones depende de los resultados de esta evaluación y de los comentarios que se reciban.

### <a name="features-that-are-implemented-in-the-sample-er-format"></a>Características que están implementadas en el formato de ER de ejemplo
En el ejemplo de configuración de formato de ER, se utiliza un archivo Excel como plantilla para generar formularios de FTI.

![Diseñador de formato](media/FTIbyGER-ERFormat.png)

Actualmente, este ejemplo de formato de ER admite las siguientes características para generar formularios de FTI:

- Los formularios de FTI se generan tanto para facturas originales que se han registrado como para las facturas originales que todavía no se han registrado. No se admiten las facturas y las notas de abono corregidas.
- Los formularios de FTI se generan en el idioma de la factura. El formato de los valores y las fechas en los formularios generados se basa en las opciones de la configuración regional del cliente del usuario.
- Las facturas generadas muestran notificaciones de no disponibilidad de datos si no hay líneas en las facturas que se procesan.
- Los encabezados de las facturas generadas se basan en el formato de papel que se ha seleccionado para el formulario de FTI en la página **Parámetros de clientes**. Los detalles de la empresa aparecen en el encabezado del formulario de factura generado solo si el formato de papel está en blanco.
- Los formularios de factura generados muestran los números de identificación fiscal de la empresa y del cliente cuando se ha seleccionado la opción apropiada para el formulario de FTI en la página **Parámetros de clientes**.
- Las secciones de líneas de factura y de totales de factura generados muestran los detalles monetarios de la factura predeterminada en la divisa de registro de la factura.
- La sección de totales de factura generados puede mostrar detalles monetarios en euros y en la divisa de registro de la factura cuando la opción **Imprimir importe en la divisa que representa al euro** está habilitada en la página **Parámetros de clientes**.
- Los formularios de factura generados muestran cualquier nota de factura de proceso que haya disponibles, según la configuración de la página **Parámetros de clientes**. Se incluyen notas tanto para toda la factura como para cada línea de factura.
- Los formularios de factura generados incluyen notas para el formulario de FTI del cliente y el idioma de procesamiento de factura cuando se han configurado en la lista de notas de formulario de AR.
- En función de la configuración de la gestión de impresión, las facturas generadas incluyen texto de pie de página personalizado cuando se ha configurado para el idioma de la factura, el formato de ER y el ámbito del documento de FTI.
- La sección de totales de los formularios de factura generados incluye cualquier información sobre descuento por pronto pago que esté disponible.
- La sección de multivencimientos de los formularios de factura generados incluye todos los detalles de multivencimientos que están disponibles.
- La sección de marcado de los formularios de factura generados incluye cualquier transacción de gastos que esté disponible.
- Los formularios de factura generados incluyen detalles de impuestos, según la configuración **Especificación de impuestos** en la página **Parámetros de clientes**. Esta sección puede mostrar los detalles de impuestos solo en la divisa de registro de factura o en la divisa de registro de factura y en la divisa de contabilidad de la empresa al mismo tiempo.
- Los formularios de factura generados muestran detalles de notificación de domiciliación. Por ejemplo, muestran cuándo se ha seleccionado para la factura el método de pago que tiene el id. de orden de domiciliación bancaria obligatorio, cuándo se registró la factura de procesamiento en euros y cuándo se definió el id. de orden de domiciliación bancaria para la factura.
- Las facturas generadas muestran cualquier detalle de pago por adelantado que esté disponible para las facturas registradas.
- Los formularios de factura generados se pueden enviar a un cliente de factura como un archivo adjunto de correo electrónico. Se debe configurar el destino del archivo de ER apropiado para el formato de ER que se está utilizando.

### <a name="countryregion-specific-features"></a>Funciones específicas de países o regiones 
Las siguientes características específicas de país o región se incluyen en el formato de ER de muestra para mostrar cómo se pueden tratar los requisitos específicos en las configuraciones de ER.

#### <a name="norway"></a>Noruega
El término Registro de empresa se pone en el encabezado del formulario de factura generado cuando la factura se procesa para una entidad jurídica que se configura de la siguiente manera:

- Se utiliza el contexto de país o región para Noruega.
- El parámetro **Imprimir Foretaksregisteret** está activo en los documentos de ventas.

#### <a name="spain"></a>España
El término **Régimen especial del criterio de caja** se pone en el encabezado del formulario de factura generado cuando la factura se procesa para una entidad jurídica que se configura de la siguiente manera:

- Se utiliza el contexto de país o región para España.
- El régimen especial para el método de contabilidad de efectivo se habilita en la fecha de procesamiento de la factura.

Cuando están disponibles los detalles del descuento por pronto pago, como el importe del descuento por pronto pago y el importe neto de la línea de factura, se presentan en la sección de totales de factura del formulario de factura generado cuando se ha procesado para una entidad jurídica que se configura de la siguiente manera:

- Se utiliza el contexto de país o región para España.
- **El descuento por pronto pago se aplica a la factura** está activado en la opción de la factura (**Parámetros de contabilidad general** \> **Sección de impuestos**).

#### <a name="italy"></a>Italia
La marca de descuento de los productos se incluye en las líneas de factura de la factura generada cuando se está procesando para una entidad jurídica que se ha configurado utilizando el contexto de país o región para Italia.

#### <a name="finland"></a>Finlandia
Además del formulario de factura generado, los resguardos de transferencia por giro bancario se pueden generar de la siguiente manera:

- Para la entidad jurídica que utiliza el contexto de país o región para Finlandia y que tiene al menos una cuenta bancaria marcada como **Cuenta de giros bancarios** y **Código de barras del banco**. 
- Para una factura marcada como necesaria para el archivo adjunto de pago asociado **Finlandés**.

![Resguardo del giro bancario](media/FTIbyGER-GiroSlip.PNG)

> [!NOTE]
> El modelo de formato de ER se ha configurado para generar opcionalmente los resguardos de transferencia por giro bancario en la hoja de cálculo independiente.

> [!NOTE]
> Primero debe instalar la fuente que se utiliza para generar el código de barras en el equipo local donde se obtendrá una vista previa del formulario de factura generado en formato Excel.

### <a name="use-the-sample-er-format-to-configure-email-destinations"></a>Usar el formato de ER de ejemplo para configurar los destinos de correo electrónico
Use los siguientes elementos del formato de ER de ejemplo para configurar los destinos de correo electrónico:

- Se puede acceder a la dirección de correo electrónico de un contacto de cliente a través de la siguiente expresión de ER: **model.InvoiceBase.Contact.ElectronicMail**.
- Al texto del asunto del mensaje de correo electrónico se puede acceder con la expresión de ER siguiente: **Emailing.TxtToUse.Subject**.
- Al texto del cuerpo del mensaje de correo electrónico se puede acceder con la expresión de ER siguiente: **Emailing.TxtToUse.Body**.

![Configuración de destino](media/FTIbyGER-ERFileDestinationSettingEmail.png)

El texto predeterminado del asunto y del cuerpo del mensaje de correo electrónico se define en el formato de ER de muestra. El idioma depende de las etiquetas del formato. Este texto predeterminado se utilizará para los mensajes de correo electrónico si no se ha añadido una plantilla de correo electrónico de organización personalizada que tenga el identificador **ERFTITMP** predefinido.

> [!NOTE]
> El identificador de plantilla de correo electrónico **ERFTITMP** se ha definido en el formato de ER de ejemplo. Se puede modificar según sea necesario en un nuevo formato de ER que se crea a partir de este formato de ejemplo.

Si se ha añadido la plantilla de correo electrónico de la organización que tiene el identificador **ERFTITMP** predefinido para la entidad jurídica para la que está procesando la factura, se utilizará la plantilla del asunto y del texto del cuerpo del correo electrónico para generar el correo electrónico. 

![Plantillas de correo electrónico de organización](media/FTIbyGER-EmailTemplate.png)

![Cargar plantilla de correo electrónico](media/FTIbyGER-EmailTemplateBody.png)

La expresión de ER **Emailing.TxtToUse.Subject** del formato de ER de ejemplo está configurada para reemplazar cualquier repetición del marcador de posición %1 por el identificador de factura de procesamiento.

La expresión **Emailing.TxtToUse.Body** del formato de muestra está configurada para las siguientes sustituciones para marcadores de posición:

- "%1" se reemplaza por el nombre de la persona de contacto del cliente.
- "%2" se reemplaza por el nombre de la empresa.
- "%3" se reemplaza por el nombre del cliente.
- "%4" se reemplaza por el nombre de la persona de contacto de la empresa.
- "%5" se reemplaza por el cargo de la persona de contacto de la empresa.
- "%6" se reemplaza por la dirección de correo electrónico de la persona de contacto de la empresa.

![Correo electrónico](media/FTIbyGER-Email.PNG)

## <a name="additional-resources"></a>Recursos adicionales
[Visión general de los informes electrónicos](general-electronic-reporting.md)
