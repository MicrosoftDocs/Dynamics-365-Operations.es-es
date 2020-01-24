---
title: Visión general de los informes electrónicos (ER)
description: Este tema proporciona una visión general de la herramienta de informes electrónicos (ER). Incluye información sobre conceptos clave, escenarios compatibles con ER y una lista con los formatos diseñados y publicados como parte de la solución.
author: NickSelin
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7cd3e2ac729bdb3ecc8e7bfacb060e433b185f09
ms.sourcegitcommit: 3a06d3b38d9de2afc22839e5a794829405068024
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2020
ms.locfileid: "2933941"
---
# <a name="electronic-reporting-er-overview"></a>Visión general de los informes electrónicos (ER)

[!include [banner](../includes/banner.md)]

Este tema proporciona una visión general de la herramienta de informes electrónicos (ER). Incluye información sobre conceptos clave, escenarios compatibles con ER y una lista con los formatos diseñados y publicados como parte de la solución.

Los informes electrónicos (ER) son una herramienta que puede utilizar para configurar formatos de entrada y de salida para documentos electrónicos en función de requisitos legales de diversos países o regiones. ER le permite administrar estos formatos durante su ciclo de vida. Por ejemplo, puede adoptar nuevos requerimientos normativos y puede generar documentos empresariales en el formato requerido para intercambiar información electrónicamente con organismos gubernamentales, bancos y otras partes.

El motor de ER está dirigido a usuarios empresariales en lugar de desarrolladores. Dado que configura formatos, en lugar de código, los procesos de creación y ajuste de formatos para documentos electrónicos son más rápidos y sencillos.

ER admite actualmente los formatos de hoja de cálculo de texto, XML, documento Microsoft Word y OPENXML. Sin embargo, una interfaz de extensión proporciona compatibilidad con formatos adicionales.

## <a name="capabilities"></a>Capacidades
El motor de ER tiene las siguientes capacidades:

- Representa una sola herramienta compartida para informes electrónicos en diferentes ámbitos y reemplaza más de 20 distintos motores que hacen algún tipo de informe electrónico para Finance and Operations.
- Aísla el formato de un informe de la implementación actual. En otras palabras, el formato es aplicable para diferentes versiones.
- Admite la creación de un formato personalizado que se basa en un formato original. También incluye capacidades para actualizar automáticamente el formato personalizado cuando se producen cambios en el formato original porque se introducen requisitos de localización y personalización.
- Se convierte en la herramienta estándar principal para la ayuda de los requisitos de localización en los informes electrónicos, tanto para Microsoft como para los socios de MS.
- Admite la capacidad de distribuir formatos a los socios y los clientes a través de Microsoft Dynamics Lifecycle Services (LCS).

## <a name="key-concepts"></a>Conceptos clave
### <a name="components"></a>Componentes

ER es compatible con dos tipos de componentes: **Modelo de datos** y **Formato**.

#### <a name="data-model-and-model-mapping-components"></a>Componentes de modelos de datos y de asignación de modelos

Un componente de modelo de datos es una representación abstracta de una estructura de datos. Se usa para describir un área de dominio empresarial específico con los detalles suficientes para cumplir los requisitos de creación de informes para dicho dominio. Un componente del modelo de datos consta de las siguientes partes:

- <a name="DataModelComponent"></a>Un modelo de datos como un conjunto de entidades específicas de empresa de dominio y una definición jerárquicamente estructurada de las relaciones entre esas entidades.
- <a name="ModelMappingComponent"></a>Una asignación de modelo que vincula orígenes de datos seleccionados de la aplicación a elementos individuales de un modelo de datos que especifica, en tiempo de ejecución, el flujo de datos y las reglas de población de datos empresariales a un componente del modelo de datos.

Una entidad de negocio de un modelo de datos se representa como un contenedor (registro). Las propiedades de la entidad empresarial se representan como elementos de datos (campos). Cada elemento de datos tiene un nombre, ficha, descripción y valor únicos. El valor de cada elemento de datos se puede diseñar para que se reconozca como cadena, entero, real, fecha, enumeración, booleano, etc. Además, puede ser otro registro o lista de registros.

Un único componente del modelo de datos puede contener varias jerarquías de entidades empresariales de dominio específicas. También contiene asignaciones de modelo que admiten un flujo de datos de informes específico en el tiempo de ejecución. Las jerarquías se distinguen por un único registro que se ha seleccionado como raíz para la asignación de modelo Por ejemplo, el modelo de datos del área de dominio de pago puede admitir las asignaciones siguientes:

- Empresa \> Proveedor \> Transacciones de pago del dominio de proveedores
- Cliente \> Empresa \> transacciones de pago del dominio de clientes

Tenga en cuenta que las entidades empresariales como las transacciones de empres y de pago se diseñan una vez. Asignaciones diferentes, a continuación, vuelven a utilizarlas.

Una asignación de modelo que admite documentos electrónicos salientes tiene las siguientes capacidades:

- Puede utilizar distintos tipos de datos como orígenes de datos para un modelo de datos. Por ejemplo, puede utilizar tablas, entidades de datos, métodos o enumeraciones.
- Admite parámetros de entrada de usuario que se pueden definir como orígenes de datos para un modelo de datos cuando algunos datos se deben especificar en el tiempo de ejecución.
- Admite la transformación de los datos en los grupos necesarios. También permite, filtrar, clasificar y sumar datos y anexar campos lógicos calculados que están diseñados con las fórmulas que se asemejan las fórmulas de Microsoft Excel. Para obtener más información, consulte [Diseñador de fórmulas en los informes electrónicos (ER)](general-electronic-reporting-formula-designer.md).


Una asignación de modelo que admite documentos electrónicos entrantes tiene las siguientes capacidades:

- Puede utilizar distintos elementos de datos actualizables como objetivos. Estos elementos de datos incluyen tablas, entidades de datos y vistas. Los datos se pueden actualizar con los datos de los documentos electrónicos entrantes. Se pueden utilizar diversos objetivos en una sola asignación de modelo.
- Admite parámetros de entrada de usuario que se pueden definir como orígenes de datos para un modelo de datos cuando algunos datos se deben especificar en el tiempo de ejecución.

Un componente de modelo de datos está diseñado para cada dominio del negocio que se debe usar como origen de datos unificado para creación de informes y que aísla los informes de la implementación física de los orígenes de datos. Representa conceptos y funcionalidades de dominio de negocio específicos en un formulario que hace que el diseño inicial del formato y el mantenimiento posterior sean más eficientes.

#### <a name="FormatComponentOutbound"></a>Componentes del formato para los documentos electrónicos salientes

Un componente de formato es el esquema de la salida de informes que se generará en el momento de la ejecución. Un esquema consta de los siguientes elementos:

- Un formato que define la estructura y el contenido del documento electrónico saliente que se genera en tiempo de ejecución.
- Orígenes de datos como un conjunto de parámetros de entrada del usuario y un modelo determinado de los datos de dominio que usa la asignación de modelo seleccionado.
- Una asignación de formato como un conjunto de vinculaciones de los orígenes de datos de formato que tienen elementos individuales de formato que especifican, en tiempo de ejecución, el flujo de datos y las reglas de generación de salida de formato.
- Una validación del formato como un conjunto de reglas configurables que controlan la generación de informes en el tiempo de ejecución en función de contexto de ejecución. Por ejemplo, puede haber una regla que detenga la generación de los pagos de proveedor y produzca una excepción cuando falten los atributos específicos del proveedor seleccionado, por ejemplo el número de cuenta bancaria.

Un componente de formato admite las siguientes funciones:

- Creación de salida de informes como archivos individuales en diversos formatos, como por ejemplo, texto, XML, documentos de Microsoft Word u hojas de cálculo.
- Creación de varios archivos por separado y encapsulación de esos archivos en archivos zip.

Un componente de formato le permite adjuntar archivos específicos que se pueden usar en la salida de informes:

- Libros de Excel que contienen una hoja de cálculo que se puede usar como plantilla para salida en el formato de hoja de cálculo de OPENXML
- Los archivos de word que contienen un documento que se puede usar como plantilla para salida en el formato de documento de Microsoft Word
- Otros archivos que se pueden incorporar en la salida de formato como archivos predefinidos

La ilustración siguiente muestra fluyen los datos para estos formatos.

[![Flujo de datos para componentes de formato saliente](./media/ER-overview-02.png)](./media/ER-overview-02.png)

Para ejecutar una sola configuración de formato ER y generar un documento electrónico salientes, debe identificar la asignación de la configuración del formato.

#### <a name="FormatComponentInbound"></a>Componentes del formato para los documentos electrónicos entrantes
Un componente de formato es el esquema del documento entrante que se importa en tiempo de ejecución. Un esquema consta de los siguientes elementos:

- Un formato que define la estructura y el contenido del documento electrónico de entrada que contiene datos que se importan en tiempo de ejecución. Un componente de formato se usa analizar un documento entrante en distintos formatos, como texto y XML.
- Una asignación de formato que vincula elementos individuales de formato a elementos de un modelo de datos específico de dominio. En tiempo de ejecución, los elementos en el modelo de datos especifican el flujo de datos y las reglas para importar datos desde un documento de entrada y después almacenar los datos en un modelo de datos.
- Una validación del formato como un conjunto de reglas configurables que controlan la importación de datos en el tiempo de ejecución en función de contexto de ejecución. Por ejemplo, puede haber una regla que detenga la importación de datos de un extracto bancario que tenga pagos de proveedor y produzca una excepción cuando falte un atributo específico del proveedor seleccionado, por ejemplo el código de identificación del proveedor.

La ilustración siguiente muestra fluyen los datos para estos formatos.

[![Flujo de datos para componentes de formato entrante](./media/ER-overview-03.png)](./media/ER-overview-03.png)

Para ejecutar una única configuración del formato de ER para importar datos desde un documento electrónico entrante, debe identificar la asignación deseada de una configuración del formato, así como el punto de la integración de una asignación de modelo. Puede usar la misma asignación y destinos de modelos así como los formatos diferentes para el tipo distinto de documentos de entrada.

#### <a name="component-versioning"></a>Control de versiones de componentes

El control de versiones se admite para componentes de ER. El flujo de trabajo siguiente se proporciona para gestionar cambios en los componentes de ER:

1. La versión que se creó originalmente se marca como una versión **Borrador**. Esta versión se puede editar y está disponible para ejecuciones de prueba.
2. La versión **Borrador** puede convertirse en una versión **Completado**. Esta versión se puede utilizar en procesos de informes locales.
3. La versión **Completado** puede convertirse en una versión **Compartido**. Esta versión se publica en LCS y puede utilizarse en procesos globales de informes.
4. La versión **Compartido** puede convertirse en una versión **Interrumpida**. Esta versión se puede eliminar a continuación.

Las versiones que tienen el estado **Completado** o **Compartido** están disponibles para otro intercambio de datos. En un componente que tiene estos estados se pueden realizar las siguientes acciones:

- El componente se puede serializar en formato XML y exportar como archivo en formato XML.
- El componente puede volver a serializar desde un archivo XML e importar en la aplicación como una nueva versión de un componente de ER.

#### <a name="component-date-effectivity"></a>Eficacia de la fecha del componente

Las versiones del componente de ER tienen fecha de vigencia. Puede establecer fecha **Vigente desde** para que un componente de ER especifique la fecha en la que el componente se hace efectivo para procesos de informes. La fecha de sesión de la aplicación se usa para definir si un componente es válido para la ejecución. Si hay más de una versión válida para una fecha concreta, la última versión se usa para procesos de informes.

#### <a name="component-access"></a>Acceso del componente

El acceso a los componentes del formato de ER depende de la configuración del código de país o región ISO. Cuando esta opción está en blanco para una versión seleccionada de una configuración de formato, se puede obtener acceso a un componente de formato desde cualquier empresa en tiempo de ejecución. Cuando esta configuración contiene códigos de país o región ISO, un componente de formato solo está disponible desde las empresas que tienen una dirección principal que está definida para uno de los códigos de país o región ISO de un componente de formato.

Diferentes versiones de un componente de formato de datos pueden tener distintos ajustes de los códigos de país o región ISO.

#### <a name="Configuration"></a>Configuración

Una configuración de ER es el contenedor de un componente concreto de ER. Dicho componente puede ser un componente del modelo de datos o un componente del formato. Una configuración puede incluir diferentes versiones de un componente de ER. Cada configuración se marca como perteneciente a un proveedor específico de configuración. La versión **Borrador** de un componente de una configuración se puede editar cuando se ha seleccionado el propietario de la configuración como proveedor activo en la configuración de ER de la aplicación.

Cada configuración de modelo contiene un componente de modelo de datos. Una nueva configuración de formato se puede derivar de una configuración de modelo de datos específico. En la configuración de árbol, la configuración de formato que se crea aparece como un elemento secundario de la configuración del modelo de datos original.

La configuración de formato que se crea contiene un componente formato. El componente modelo de datos de la configuración del modelo original se inserta automáticamente en el componente formato de la configuración creada de formato secundario como origen de datos predeterminado.

Una configuración de ER se comparte en las empresas de la aplicación.

#### <a name="Provider"></a>Proveedor

El proveedor de ER es la identificación de parte que se usa para indicar el autor (propietario) de cada configuración de ER. ER le permite administrar la lista de proveedores de configuración. Las configuraciones del formato que se liberan para documentos electrónicos como parte de la solución de Finance and Operations se marcan como propiedad del proveedor de configuración **Microsoft**.

Para obtener información sobre cómo registrar un nuevo proveedor de ER, reproduzca la guía de la tarea, **ER Creación de un proveedor de configuraciones y marcarlo como activo** (parte del proceso empresarial **7.5.4.3 Adquirir y desarrollar los componentes del servicio o la solución de TI (10677)**).

#### <a name="Repository"></a>Repositorio

Un repositorio de ER guarda las configuraciones de ER. Los tipos de repositorios de ER siguientes son compatibles: 

- Biblioteca compartida LCS
- Proyecto LCS
- Sistema de archivo
- Regulatory Configuration Services (RCS)
- Recursos de operaciones


Un repositorio **Biblioteca compartida LCS** proporciona acceso a la lista de configuraciones dentro de la biblioteca de activos compartidos en Lifecycle Services (LCS). Este tipo de repositorio de ER se puede registrar solo para el proveedor de Microsoft. En la biblioteca compartida LCS del activo puede importar las últimas versiones de las configuraciones de ER en la instancia actual.

Un repositorio del **proyecto de LCS** proporciona acceso a la lista de configuraciones de un proyecto de LCS específico (biblioteca de los activos del proyecto de LCS) que se seleccionó en la etapa de registro del repositorio. ER le permite cargar las configuraciones compartidas de la instancia actual a un repositorio específico del **Proyecto LCS**. También puede importar configuraciones de un repositorio del **Proyecto LCS** en la instancia de Finance and Operations actual.

Un repositorio de **Sistema de archivos** proporciona acceso a la lista de configuraciones que están ubicadas como archivos XML en la carpeta específica del sistema de archivos local del equipo en el que se aloja el servicio AOS. La carpeta necesaria se selecciona en la etapa de registro de repositorio. Puede importar configuraciones de un repositorio del **sistema de archivos** en la instancia actual. 

Tenga en cuenta que este tipo de repositorio es accesible en los entornos siguientes:

- Los entornos hospedados en la nube implementados para fines de desarrollo (que contienen los modelos de prueba de suites)
- Entornos implementados localmente

Para obtener más información, consulte [Importar configuraciones de informes electrónicos (ER)](./electronic-reporting-import-ger-configurations.md).

Un repositorio de **instancia RCS** proporciona acceso a la lista de configuraciones de una instancia RCS específica que se seleccionó en la etapa de registro del repositorio. ER le permite importar configuraciones completadas o compartidas desde la instancia de RCS seleccionada a la instancia actual para que pueda usarlas en los informes electrónicos.

Para más información, consulte [Importar configuraciones de informes electrónicos (ER) de Regulatory Configuration Services (RCS)](./rcs-download-configurations.md).

Un repositorio de **Recursos de Operations** proporciona acceso a la lista de configuraciones que libera Microsoft, como el proveedor de configuración de ER, como parte inicial de la solución de la aplicación. Estas configuraciones se pueden importar a la instancia actual y usar para los informes electrónicos o realizar tareas de guía de muestra. También se pueden utilizar para localizaciones y personalizaciones adicionales. Tenga en cuenta que las últimas versiones proporcionados por las configuraciones de Microsoft ER deben importarse de la biblioteca de activos compartidos de LCS usando el repositorio ER correspondiente.

Los repositorios necesarios del **Proyecto LCS**, **Sistema de archivos** y **Servicios de configuración reglamentaria (RCS)** se pueden registrar de manera individual para cada proveedor de configuración de la instancia actual. Cada repositorio se puede dedicar a un proveedor de configuración específico.

## <a name="supported-scenarios"></a>Escenarios admitidos
### <a name="building-a-data-model"></a>Creación de un modelo de datos

ER proporciona un diseñador de modelo que puede usar para crear un modelo de datos para un dominio concreto de negocio. Todas las entidades específicas de empresa de dominio y las relaciones entre ellas se pueden presentar en un modelo de datos como una estructura jerárquica. 

Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **CE Diseñar el modelo de datos específico de dominio** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**).

### <a name="translating-data-model-content"></a>Traducción del contenido del modelo de datos

El contenido del modelo de datos (etiquetas y descripciones) se puede traducir a otros idiomas admitidos por las aplicaciones. Desea traducir el contenido del modelo de datos por las siguientes razones:

- En tiempo de diseño, para que el contenido sea más inteligible para los diseñadores de formato que hablan otros idiomas que utilizarán un modelo de datos para la asignación de datos de los componentes de formato.
- En tiempo de ejecución, para hacer el contenido más sencillo con anuncios y ayudas de los parámetros de tiempo de ejecución, así como mensajes configurados de validación (errores y advertencias), en el idioma que prefiere el usuario registrado actualmente.

### <a name="configuring-data-model-mappings-for-outgoing-documents"></a>Configurar asignaciones del modelo de datos para los documentos de salida

ER proporciona un diseñador de asignación de modelos que permite a los usuarios asignar modelos de datos que se han diseñado para orígenes de datos de la aplicación específicos. En función de la asignación, los datos se importarán en tiempo de ejecución desde los orígenes de datos seleccionados en el modelo de datos. El modelo de datos se usa como un origen de datos abstracto de los formatos de ER que generan los documentos electrónicos salientes. 

Para familiarizarse con los detalles de este escenario, reproduzca las guías de tareas **CE Definir asignación del modelo y seleccionar orígenes de datos** y **CE Asignar modelo de datos a los orígenes de datos seleccionados** (parte del proceso de negocio **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**).

### <a name="configuring-data-model-mappings-for-incoming-documents"></a>Configurar asignaciones del modelo de datos para los documentos de entrada
ER proporciona un diseñador de asignación de modelos que permite a los usuarios asignar modelos de datos que se han diseñado para destinos específicos. Por ejemplo, los modelos de datos se pueden asignar para los componentes de datos que se puede actualizar (tablas, entidades de datos y vistas). En función de la asignación, los datos se actualizarán en tiempo de ejecución con los datos del modelo de datos. Como almacenamiento abstracto del formato de ER, el modelo de datos se rellena con los datos que se importan de un documento electrónico entrante. 

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Almacenar un componente modelo diseñado como una configuración del modelo

ER puede almacenar un modelo de datos diseñado, junto con las asignaciones de datos asociadas, como una configuración del modelo de la instancia actual. En la siguiente ilustración se muestra un ejemplo de este tipo de configuración de modelo de datos (la configuración del modelo de pago).

Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **CE Asignar modelo de datos a los orígenes de datos seleccionados** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**).

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Creación de un formato que usa un modelo de datos como base

ER admite un diseñador de formato que puede usar para crear el formato de un documento electrónico para un dominio empresarial seleccionando el componente modelo como base. El mismo diseñador del formato de ER le permite asignar un formato que crea a la asignación del modelo de datos de un dominio seleccionado como origen de datos. 

Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **CE Diseñar el formato específico de dominio** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Creación de una configuración para generar documentos electrónicos en formato de hoja de cálculo OPENXML

El diseñador de formato de ER se puede utilizar para generar un documento electrónico en formato de hoja de cálculo OPENXML. 

Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **Crear una configuración ER para generar informes en formato OPENXML** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**). Como parte del paso de la guía de la tarea para importar una plantilla, utilice [Plantilla de informe de pago (SampleVendPaymWsReport.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202) el archivo de Excel como plantilla.

### <a name="building-a-configuration-to-generate-electronic-documents-in-a-word-document-format"></a>Creación de una configuración para generar documentos electrónicos en formato documento de Word.
El diseñador de formato de ER se puede utilizar para generar un documento electrónico en formato de documento de Word. En la siguiente ilustración se muestra un ejemplo de este tipo de formato. Tenga en cuenta que este formato reutiliza la configuración actual de ER que diseñó originalmente para generar la salida de informes en formato de OPENXML.

Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas Diseñar una configuración ER para generar informes en formato de Microsoft WORD (parte del proceso empresarial 7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)). Como parte del paso de la guía de tareas para importar una plantilla, use los archivos de Word siguientes como plantillas para el formato de ER:

- [Plantilla de informe de pago (SampleVendPaymDocReport.docx)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Plantilla enlazada de pago (SampleVendPaymDocReportBounded.docx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="building-a-configuration-to-import-data-from-incoming-electronic-documents"></a>Generar una configuración para importar datos desde documentos electrónicos entrantes
El diseñador del formato de ER se puede utilizar para describir un documento electrónico que se planifica para la importación de datos en formato XML o de texto. El formato diseñado se usa para analizar un documento de entrada. El diseñador de la asignación de formato de ER se puede utilizar para definir el enlazado de los elementos del formato diseñado para el modelo de datos. 

Para familiarizarse con los detalles de este escenario, reproduzca la guía Crear configuraciones de ER requeridas para importar datos desde una guía de tareas de archivo externo (parte del proceso empresarial 7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)). Use archivos siguientes para reproducir este manual:

- [Configuración del modelo de datos de ER (1099model.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Configuración del formato de ER (1099format.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Ejemplo de documento de entrada en formato XML (1099entries.xml)](https://go.microsoft.com/fwlink/?linkid=845202)
- [Ejemplo de libro para administrar datos del documento de entrada (1099entries.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Almacenar un componente diseñado del formato en una configuración del formato

ER puede almacenar un formato diseñado junto con las asignaciones configuradas de los datos como una configuración del formato de la instancia actual. La ilustración anterior muestra un ejemplo de este tipo de configuración de formato (**BACS (Reino Unido)**, que es un elemento secundario de la configuración de **Modelo de pago**). Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **CE Diseñar el formato específico de dominio** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**).

### <a name="configuring-finance-to-start-to-use-a-created-format-internally"></a>Configurar Finance para comenzar a usar un formato creado internamente

La aplicación se puede configurar para empezar a usar un formato creado para generar informes electrónicos. La referencia a la configuración creada de formato se debe definir en la configuración de un determinado dominio. Por ejemplo, para empezar a utilizar una configuración de formato de ER para pagos electrónicos a proveedores en formato BACS, se debe hacer referencia a la configuración de formato en métodos específicos de pago.

Para familiarizarse bien con los detalles de este escenario, reproduzca la guía de tareas **ER Usar formato para generar documentos electrónicos para pagos** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**).

## <a name="handling-er-components"></a>Tratamiento de componentes de ER
### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Publicación de un componente de ER en LCS para ofrecerlo externamente (localización)

El propietario de un componente (modelo o formato) que se ha creado puede usar ER para publicar la versión completada del componente en LCS. Se requiere Un repositorio del tipo **Proyecto de LCS** para el proveedor actual de la configuración de ER. Cuando cambie el estado de la versión completada de un componente de **COMPLETADO** a **COMPARTIDO**, esa versión se publica en el LCS. Cuando haya publicado un componente a LCS, el propietario de ese componente pasa a ser un proveedor de servicio para admitir el componente. Por ejemplo, si el componente del formato está diseñado para generar un documento electrónico legalmente necesario (por ejemplo, de acuerdo con una situación de localización), se supone que el formato se mantendrá compatible con los cambios legislativos y que el proveedor emitirá nuevas versiones del componente siempre surjan nuevos requisitos legislativos. Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **ER Cargar una configuración en Lifecycle Services** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importar el componente de ER de LCS para utilizarlo internamente

ER le permite importar componentes de ER desde LCS en la instancia actual. Se requiere un repositorio del tipo **Proyecto de LCS**. Si se ha importado un componente de ER de LCS a la instancia actual, el propietario de la instancia se convierte en un consumidor del servicio ofrecido por el propietario (autor) del componente importado. Por ejemplo, si un componente del formato está diseñado para generar un documento electrónico específico desde la aplicación en un formato específico del país o región (situación de localización), se supone que el consumidor del servicio podrá obtener actualizaciones que se realizan a ese formato, para mantenerlo compatible con los requisitos legislativos. Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **ER Importar una configuración de Lifecycle Services** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Creación de un formato que selecciona otro formato como base (personalización)

ER le permite crear (deriva) un nuevo componente de la versión actual de un componente (base) que se importó de LCS. Por ejemplo, si un usuario desea derivar un nuevo formato para implementar algunos requisitos especiales para un documento electrónico (como un campo adicional o una descripción amplia) para admitir un escenario de personalización. Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **ER Actualizar formato adoptando una nueva versión base del mismo** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**) .

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Actualizar un formato que selecciona una versión nueva del formato base (rebase)

ER le permite adoptar automáticamente los cambios de la última versión del componente de la base de la versión actual del borrador de componentes derivados. Este proceso se conoce como *reorganización*. Por ejemplo, un cambio normativo nuevo que se ha introducido en la última versión del formato que se importó desde LCS se puede combinar automáticamente en la versión personalizada de este formato del documento electrónico. Los cambios que no se pueden combinar automáticamente se consideran conflictos. Estos conflictos se presentan para la resolución manual de la herramienta del diseñador para el componente apropiado. Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **ER Actualizar formato adoptando una nueva versión base del mismo** (parte del proceso empresarial **7.5.5.3 Adquirir/Desarrollar componente cambiado de solución/servicios de la TI (10683)**).

## <a name="list-of-er-configurations-that-are-delivered-in-the-finance-application"></a>Lista de configuraciones ER que se entregan en la solución de la aplicación

| Configuraciones del modelo de datos específicos de dominio: título | Dominio                | Configuraciones de formato dependientes del modelo de datos: título | Descripción                                                        |
|--------------------------------------------------|-----------------------|---------------------------------------------------|--------------------------------------------------------------------|
| Modelo de archivo de auditoría                                 | Auditoría financiera       |                                                   |                                                                    |
|                                                  |                       | Archivo de auditoría (NL)                                   | Formato de archivo de auditoría para Países Bajos                                  |
| Modelo BAS                                        | Informe de impuestos         |                                                   |                                                                    |
|                                                  |                       | BAS (AU)                                          | Formato BAS para Australia                                           |
| Modelo del esquema del sector de la construcción               | Informe de impuestos         |                                                   |                                                                    |
|                                                  |                       | Devolución mensual CIS (Reino Unido)                           | Formato de devolución mensual CIS para el Reino Unido                   |
| Modelo de la carta de cobro                          | Facturas electrónicas  |                                                   |                                                                    |
|                                                  |                       | Carta de cobro OIOUBL (DK)                     | Formato de carta de cobro OIOUBL para Dinamarca                        |
| Modelo electrónico de cuenta contable (MX)          | Informe de impuestos         |                                                   |                                                                    |
|                                                  |                       | Libro mayor auxiliar XML (MX)                         | Formato de transacciones de contabilidad auxiliar por cuenta para México |
|                                                  |                       | Plan de cuentas XML (MX)                         | Formato de informe de plan de cuentas para México                          |
|                                                  |                       | Diarios XML (MX)                                 | Formato de informe de transacciones de diario para México                      |
|                                                  |                       | Saldo de comprobación XML (MX)                            | Formato de informe de saldo de comprobación para México                             |
| Modelo Elster                                     | Informe de impuestos         |                                                   |                                                                    |
|                                                  |                       | Elster (DE)                                       | Formato de Elster para Alemania                                          |
| Modelo de lista de ventas de la UE                              | Informes comerciales       |                                                   |                                                                    |
|                                                  |                       | Lista de ventas de la UE (DE)                                | Formato TXT de lista de ventas de la UE para Alemania                               |
|                                                  |                       | Lista de ventas de la UE (DK)                                | Formato TXT de lista de ventas de la UE para Dinamarca                               |
|                                                  |                       | Lista de ventas de la UE (FR)                                | Formato XML de lista de ventas de la UE para Francia                                |
|                                                  |                       | Lista de ventas de la UE (NL)                                | Formato XML de lista de ventas de la UE para Países Bajos                           |
|                                                  |                       | TXT de lista de ventas de la UE (UK)                            | Formato TXT de lista de ventas de la UE para el Reino Unido                    |
|                                                  |                       | XML de lista de ventas de la UE (UK)                            | Formato XML de lista de ventas de la UE para el Reino Unido                    |
|                                                  |                       | Informe de lista de ventas de la UE por columnas                   | Informe de lista de ventas de la UE por columnas                                    |
|                                                  |                       | Informe de lista de ventas de la UE por filas                      | Informe de lista de ventas de la UE por filas                                       |
| Modelo de contabilidad FEC (FR)                        | Informe de impuestos         |                                                   |                                                                    |
|                                                  |                       | XML de datos contables FEC (FR)                      | Formato XML de exportación de datos contables FEC para Francia                   |
| Archivo de auditoría alemán                                | Auditoría financiera       |                                                   |                                                                    |
|                                                  |                       | Salida de archivo de auditoría alemán                          | Salida de archivo de auditoría para Alemania y Austria                          |
| Modelo intrastat                                  | Informes comerciales       |                                                   |                                                                    |
|                                                  |                       | Intrastat (DE)                                    | Formato de intrastat para Alemania                                       |
|                                                  |                       | Intrastat (DK)                                    | Formato de intrastat para Dinamarca                                       |
|                                                  |                       | INTRACOM intrastat (FR)                           | Formato INTRACOM intrastat para Francia                               |
|                                                  |                       | SAISUNIC intrastat (FR)                           | Formato SAISUNIC intrastat para Francia                               |
|                                                  |                       | Intrastat (NL)                                    | Formato de intrastat para Países bajos                               |
|                                                  |                       | Intrastat (UK)                                    | Formato de intrastat para el Reino Unido                            |
|                                                  |                       | Informe intrastat                                  | Informe de control Excel de intrastat                                     |
| Modelo de factura de cliente                           | Facturas electrónicas  |                                                   |                                                                    |
|                                                  |                       | Nota de abono de proyecto OIOUBL (DK)                   | Formato de nota de abono de proyecto OIOUBL para Dinamarca                      |
|                                                  |                       | Factura del proyecto OIOUBL (DK)                       | Formato de factura de proyecto OIOUBL para Dinamarca                          |
|                                                  |                       | Nota de abono de ventas OIOUBL (DK)                     | Formato de nota de abono de ventas OIOUBL para Dinamarca                        |
|                                                  |                       | Factura de ventas OIOUBL (DK)                         | Formato de factura de ventas OIOUBL para Dinamarca                            |
| Modelo de declaración OB                             | Informe de impuestos         |                                                   |                                                                    |
|                                                  |                       | Declaración OB (NL)                               | Formato de declaración OB para Países Bajos                          |
| Modelo de pago                                    | Pagos              |                                                   |                                                                    |
|                                                  |                       | Betalingsservice (DK)                             | Formato de pago de Betalingsservice para Dinamarca                        |
|                                                  |                       | Envío de letra de cambio (FR)                  | Formato de envío de letra de cambio para Francia                      |
|                                                  |                       | BTL91 (NL)                                        | Formato de pago de proveedor BTL91 para Países Bajos                    |
|                                                  |                       | Prelevements CFONB (FR)                           | Formato de pago de adeudo directo CFONB para Francia                       |
|                                                  |                       | Virements CFONB (FR)                              | Formato de pago de proveedor nacional CFONB para Francia                    |
|                                                  |                       | Proveedor de Nordea (DK)                                | Formato de pago de proveedor de Nordea Corporate Netbank para Dinamarca         |
|                                                  |                       | Servicio de crédito directo ANZ (AU)                    | Formato para el servicio de crédito directo ANZ para Australia                 |
|                                                  |                       | Servicio de crédito directo CBA (AU)                    | Formato para el servicio de crédito directo CBA para Australia                 |
|                                                  |                       | Servicio de crédito directo NAB (AU)                    | Formato para el servicio de crédito directo NAB para Australia                 |
|                                                  |                       | Servicio de crédito directo STG (AU)                    | Formato para el servicio de crédito directo STG para Australia                 |
|                                                  |                       | Sistema de entrada directa WBC (AU)                      | Formato para el sistema de entrada directa WBC para Australia                   |
|                                                  |                       | DirectLink (NZ)                                   | Formato para DirectLink para Nueva Zelanda                              |
|                                                  |                       | Archivo de pago JBA (JP)                             | Formato de pago JBA para Japón                                       |
|                                                  |                       | Transferencia de crédito ISO20022                          | Formato de transferencia de crédito SEPA para Europa                             |
|                                                  |                       | Transferencia de crédito ISO20022 (FR)                     | Formato de transferencia de crédito SEPA para Francia                             |
|                                                  |                       | Transferencia de crédito ISO20022 (DE)                     | Formato de transferencia de crédito SEPA para Alemania                            |
|                                                  |                       | Transferencia de crédito ISO20022 (NL)                     | Formato de transferencia de crédito SEPA para Países Bajos                    |
|                                                  |                       | Domiciliación bancaria ISO20022                             | Formato de adeudo directo SEPA para Europa                                |
|                                                  |                       | Domiciliación bancaria ISO20022 (FR)                        | Formato de adeudo directo SEPA para Francia                                |
|                                                  |                       | Domiciliación bancaria ISO20022 (DE)                        | Formato de adeudo directo SEPA para Alemania                               |
|                                                  |                       | Domiciliación bancaria ISO20022 (NL)                        | Formato de adeudo directo SEPA para Países Bajos                       |
|                                                  |                       | BACS (UK)                                         | Formato de pago de proveedor BACS para el Reino Unido                  |
| Gasto invertido                                   | Informe de impuestos         |                                                   |                                                                    |
|                                                  |                       | Lista de ventas de gastos invertidos                         | Formato de lista de ventas de gastos invertidos                                   |
| Modelo de integración XBRL neerlandés                     | Informes de XBRL        |                                                   |                                                                    |
|                                                  |                       | XBRL Semansys (NL)                                | Formato de exportación XBRL Semansys para Países Bajos                    |
| Modelo GAF (MY)                                   | Auditoría financiera       |                                                   |                                                                    |
|                                                  |                       | Archivo GAF (MY)                                     | Formato de GAF para Malasia                                         |
| Informe de vencimientos de proveedores (CN)                         | Análisis de datos de proveedores |                                                   |                                                                    |
|                                                  |                       | Formato del informe de vencimiento de proveedores (CN)                   | Formato del informe de vencimiento de proveedores para China                               |
| Modelo de declaración de factura de proveedor                 | Análisis de datos de proveedores |                                                   |                                                                    |
|                                                  |                       | Declaración de factura de proveedor (IS)                   | Formato de declaración de factura de proveedor para Islandia                      |
|                                                  |                       | Informe de declaración de facturas de proveedor (IS)            | Informe de declaración de factura de proveedor para Islandia                      |

## <a name="additional-resources"></a>Recursos adicionales

- [Crear configuraciones de informes electrónicos (ER)](electronic-reporting-configuration.md)
- [Administrar el ciclo de vida de las configuraciones de la notificación electrónica (ER)](general-electronic-reporting-manage-configuration-lifecycle.md)
