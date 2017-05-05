---
title: "Visión general de los informes electrónicos"
description: "Este artículo proporciona una visión general de la herramienta de informes electrónicos (ER). Incluye información sobre conceptos clave, escenarios compatibles con ER y una lista con los formatos diseñados y publicados como parte de la solución."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.region: global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: b3e8174d07c9b9fd4210486c369c640fe07c49eb
ms.lasthandoff: 03/31/2017


---

# <a name="electronic-reporting-overview"></a>Visión general de los informes electrónicos

[!include[banner](../includes/banner.md)]


Este artículo proporciona una visión general de la herramienta de informes electrónicos (ER). Incluye información sobre conceptos clave, escenarios compatibles con ER y una lista con los formatos diseñados y publicados como parte de la solución.

Los informes electrónicos son una herramienta que puede utilizar para configurar formatos para documentos electrónicos en función de requisitos legales de diversos países o regiones. ER le permite administrar estos formatos durante su ciclo de vida. Por ejemplo, puede adoptar nuevos requerimientos normativos y puede generar documentos empresariales en el formato requerido para intercambiar información electrónicamente con organismos gubernamentales, bancos y otras partes. El motor de ER está dirigido a usuarios empresariales en lugar de desarrolladores. Dado que configura formatos, no código, los procesos de creación y ajuste de formatos para documentos electrónicos son más rápidos y sencillos. ER admite actualmente los formatos de hoja de cálculo de texto, XML y OPENXML. Sin embargo, una interfaz de extensión proporciona compatibilidad con más formatos.

## <a name="capabilities"></a>Capacidades
El motor de ER tiene las siguientes capacidades:

-   Representa una sola herramienta común para realizar informes electrónicos en diferentes ámbitos y reemplaza a más de 20 motores distintos que hacen algún tipo de informe electrónico para Microsoft Dynamics 365 for Operations.
-   Aísla el formato de informe de la implementación actual de Dynamics 365 for Operations. (En otras palabras, el formato es aplicable para diferentes versiones de Dynamics 365 for Operations).
-   Admite la creación de un formato personalizado que se basa en un formato original. Incluye capacidades para actualizar automáticamente el formato personalizado cuando se producen cambios en el formato original porque se introducen requisitos de localización y personalización.
-   Se convierte en la herramienta estándar principal para la ayuda de los requisitos de localización en los informes electrónicos, tanto para Microsoft como para los socios de MS.
-   Admite la capacidad de distribuir formatos a los socios y los clientes a través de Microsoft Dynamics Lifecycle Services (LCS).

## <a name="concepts"></a>Conceptos
### <a name="components"></a>Componentes

ER es compatible con dos tipos de componentes: **Modelo de datos **y **Formato**.

#### <a name="data-model-components"></a>Componentes de modelo de datos

Un componente de modelo de datos es una representación abstracta de una estructura de datos y se utiliza para describir una área de dominio empresarial concreta con bastantes detalles para cumplir los requisitos de informes para ese dominio. Un componente del modelo de datos consta de las siguientes partes:

-   Un modelo de datos como un conjunto de entidades específicas de empresa de dominio y una definición jerárquicamente estructurada de las relaciones entre esas entidades
-   Una asignación de modelo que vincula orígenes de datos seleccionados de Dynamics 365 for Operations a elementos individuales de un modelo de datos que especifica, en tiempo de ejecución, el flujo de datos y las reglas de población de datos empresariales a un componente del modelo de datos.

Una entidad de negocio de un modelo de datos se representa como un contenedor (registro). Las propiedades de la entidad empresarial se representan como elementos de datos (campos). Cada elemento de datos tiene un nombre, ficha, descripción y valor únicos. El valor de cada elemento de datos se puede diseñar para que se reconozca como cadena, entero, real, fecha, tipo enumeración, booleano, etc. Además, puede ser otro registro o lista de registros. Un único componente del modelo de datos puede contener varias jerarquías de entidades específicas de la empresa de dominio y también asignaciones de modelo que admiten un flujo de datos específico del informe concreto en tiempo de ejecución. Las jerarquías se distinguen por un único registro que se ha seleccionado como raíz para la asignación de modelo Por ejemplo, el modelo de datos del área de dominio de pago puede admitir las asignaciones siguientes:

-   Empresa -&gt; Proveedor -&gt; Transacciones de pago del dominio de proveedores
-   Cliente -&gt; Empresa -&gt; transacciones de pago del dominio de clientes

Tenga en cuenta que las entidades empresariales (por ejemplo, las transacciones de pago y empresa) se diseñan una vez. Asignaciones diferentes, a continuación, vuelven a utilizarlas. Una asignación de modelo tiene las siguientes capacidades:

-   Puede utilizar distintos tipos de datos de Dynamics 365 for Operations como orígenes de datos para un modelo de datos. Por ejemplo, puede utilizar tablas, entidades de datos, métodos o enumeraciones.
-   Admite parámetros de entrada de usuario que se pueden definir como orígenes de datos para un modelo de datos cuando algunos datos se deben especificar en el tiempo de ejecución.
-   Admite la transformación de datos de Dynamics 365 for Operations en grupos requeridos, el filtrado, la ordenación y la suma de datos, además de la anexión con campos calculados lógicos que están diseñados a través de fórmulas del tipo de Microsoft Excel (para obtener más detalles, consulte [Diseñador de fórmulas en los informes electrónicos](general-electronic-reporting-formula-designer.md)).

[![Editor de fórmulas de tipo Excel](./media/pic-formula-1024x615.png)](./media/pic-formula.png) Un componente de modelo de datos está diseñado para cada dominio empresarial que debe usarse como origen de datos unificado para notificaciones que aíslan las notificaciones de la implementación física de los orígenes de datos de Dynamics 365 for Operations, y representa conceptos y funcionalidades específicos de la empresa de dominio en un formulario que hace que el diseño inicial de los formatos de las notificaciones y el mantenimiento posterior sean más eficientes.

#### <a name="format-components"></a>Componentes de formato

Un componente de formato es el esquema de la salida de informes que se generará en el momento de la ejecución. Un esquema consta de los siguientes elementos:

-   Un formato que define la estructura y el contenido del documento de informes electrónicos que se genera en tiempo de ejecución
-   Orígenes de datos como un conjunto de parámetros de entrada del usuario y un modelo determinado de los datos de dominio que usa la asignación de modelo seleccionado
-   Una asignación de formato como un conjunto de vinculaciones de los orígenes de datos de formato que tienen elementos individuales de formato que especifican, en tiempo de ejecución, el flujo de datos y las reglas de generación de salida de formato
-   Una validación de formato como un conjunto de reglas configurables que controlan la generación de informes en tiempo de ejecución, en función del contexto de ejecución (por ejemplo, una regla que detiene la generación de la salida de los pagos de un proveedor y genera una excepción cuando faltan atributos específicos del proveedor seleccionado, como el número de la cuenta bancaria).

Un componente de formato admite las siguientes funciones:

-   Creación de salida de informes como archivos individuales en diversos formatos: texto, XML u hoja de cálculo
-   Creación de varios archivos por separado y también encapsulación de esos archivos en archivos zip

Un componente de formato proporciona la capacidad de adjuntar archivos específicos que se pueden usar en la salida de informes

-   Libros de Excel que contienen una hoja de cálculo que se puede usar como plantilla para salida en el formato de hoja de cálculo de OPENXML
-   Otros archivos que se pueden incorporar en la salida de formato como archivos predefinidos

#### <a name="component-versioning"></a>Control de versiones de componentes

El control de versiones se admite para componentes de ER. El flujo de trabajo siguiente se proporciona para gestionar cambios en los componentes de ER:

-   La versión que se creó originalmente se marca como una versión **BORRADOR**. Esta versión se puede editar y está disponible para ejecuciones de prueba.
-   La versión **BORRADOR** puede convertirse en una versión **COMPLETADO**. Esta versión se puede utilizar en procesos de informes locales.
-   La versión **COMPLETADO** puede convertirse en una versión **COMPARTIDO**. Esta versión se publica en LCS y puede utilizarse en procesos globales de informes.
-   La versión **COMPARTIDO** puede convertirse en una versión **INTERRUMPIDA**. Esta versión se puede eliminar a continuación.

Las versiones que tienen el estado** COMPLETADO** o **COMPARTIDO** están disponibles para otro intercambio de datos. En un componente que tiene estos estados se pueden realizar las siguientes acciones:

-   Se pueden serializar en formato XML y exportar desde Dynamics 365 for Operations como archivo en formato XML.
-   Se pueden volver a serializar desde un archivo XML e importar en Dynamics 365 for Operations como una nueva versión de un componente de ER.

#### <a name="component-date-effectivity"></a>Eficacia de la fecha del componente

Las versiones del componente de ER tienen fecha de vigencia. La fecha** Vigente desde **se puede definir para que un componente de ER especifique la fecha en la que el componente se hace efectivo para procesos de informes. La fecha de sesión de Microsoft Dynamics 365 for Operations se usa para definir si un componente es válido para la ejecución. Si hay más de una versión válida para una fecha concreta, la última versión se usa para procesos de informes.

#### <a name="component-access"></a>Acceso del componente

El acceso a los componentes del formato de ER depende de la configuración del código de país o región ISO. Cuando esta opción está en blanco para una versión seleccionada de una configuración de formato, se puede obtener acceso a un componente de formato desde cualquier empresa de Dynamics 365 for Operations en tiempo de ejecución. Cuando esta configuración contiene códigos de país o región ISO, un componente de formato está disponible solo desde las empresas de Dynamics 365 for Operations que tienen una dirección principal que está definida para uno de los códigos de país o región ISO de un componente de formato. Diferentes versiones de un componente de formato de datos pueden tener distintos ajustes de los códigos de país o región ISO.

#### <a name="configuration"></a>Configuración

Una configuración de ER es la envoltura de un componente concreto de ER: **Modelo de datos **o **Formato**. Una configuración puede incluir diferentes versiones de un componente concreto de ER. Cada configuración se marca como perteneciente a un proveedor concreto de configuración. La versión **BORRADOR** de un componente de una configuración se puede editar cuando se ha seleccionado el propietario de la configuración como proveedor activo en la configuración de ER de Dynamics 365 for Operations. Cada configuración de modelo contiene un componente de **Modelo de datos**. Una nueva configuración de formato se puede originar (derivar) de una configuración de modelo de datos específico. La configuración de formato que se crea se presentará en el árbol de configuración como un elemento secundario de la configuración del modelo de datos original. La configuración de formato que se crea contiene un componente **Formato **. El componente **Modelo de datos** de la configuración del modelo original se inserta automáticamente en el componente **Formato **de la configuración creada de formato secundario como origen de datos predeterminado. Una configuración de ER se comparte en las empresas de Dynamics 365 for Operations.

#### <a name="provider"></a>Proveedor

El proveedor de ER es la identificación de parte que se usa para indicar el autor (propietario) de cada configuración de ER. ER le permite administrar la lista de proveedores de configuración. Las configuraciones del formato que se liberan para documentos electrónicos como parte de la solución de Dynamics 365 for Operations se marcan como propiedad del proveedor de configuración **Microsoft**.

#### <a name="repository"></a>Repositorio

Un repositorio de ER guarda las configuraciones de ER. Los tipos de repositorios de ER siguientes son compatibles actualmente: **Recursos de Operations** y **Proyecto LCS**. Un repositorio de **Recursos de Operations** proporciona acceso a la lista de configuraciones que libera Microsoft como parte de la solución Dynamics 365 for Operations como un proveedor de configuración de ER. Esas configuraciones se pueden importar a la instancia actual de Dynamics 365 for Operations y usar para los informes electrónicos. También se pueden utilizar para localizaciones/personalizaciones adicionales. Un repositorio del **proyecto de LCS **proporciona acceso a la lista de configuraciones de un proyecto de LCS específico (biblioteca de los activos del proyecto de LCS) que se seleccionó en la etapa de registro del repositorio. ER le permite cargar las configuraciones compartidas de la instancia de Dynamics 365 for Operations actual a un repositorio concreto del **Proyecto LCS**. También puede importar configuraciones de un repositorio concreto del **Proyecto LCS** en la instancia de Dynamics 365 for Operations actual. Los repositorios necesarios del **Proyecto LCS** se pueden registrar de manera individual para cada proveedor de la configuración de la instancia actual de Dynamics 365 for Operations. Cada repositorio se puede dedicar a un proveedor de configuración específico.

## <a name="supported-scenarios"></a>Escenarios admitidos
### <a name="building-a-data-model"></a>Creación de un modelo de datos

ER proporciona un diseñador de modelo que puede usar para crear un modelo de datos para un dominio concreto de negocio. Todas las entidades específicas de empresa de dominio y las relaciones entre ellas se pueden presentar en un modelo de datos como una estructura jerárquica. En la siguiente ilustración se muestra un ejemplo de este tipo de modelo de datos (el modelo de datos de dominio de pago). [![Ejemplo de un modelo de datos](./media/pic-data-model-1024x550.png)](./media/pic-data-model.png) Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **ER Diseñar el modelo de datos específico de dominio** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677**)).

### <a name="translating-data-model-content"></a>Traducción del contenido del modelo de datos

El contenido del modelo de datos (etiquetas y descripciones) se puede traducir a otros idiomas admitidos por Dynamics 365 for Operations. Desea traducir el contenido del modelo de datos por las siguientes razones:

-   En tiempo de diseño, para que el contenido sea más inteligible para los diseñadores de formato que hablan otros idiomas que utilizarán un modelo de datos para la asignación de datos de los componentes de formato
-   En tiempo de ejecución, para hacer el contenido más sencillo con anuncios y ayudas de los parámetros de tiempo de ejecución, así como mensajes configurados de validación (errores y advertencias), en el idioma que prefiere el usuario registrado actualmente en Dynamics 365 for Operations

La ilustración siguiente muestra un ejemplo de cómo se puede traducir el contenido del modelo de datos del inglés al japonés. [![Contenido del modelo de datos en inglés](./media/pic-translate-en-1024x495.png)](./media/pic-translate-en.png) [![Contenido del modelo de datos traducido al japonés](./media/pic-translate-ja-1024x495.png)](./media/pic-translate-ja.png)

### <a name="configuring-data-model-mappings"></a>Configuración de asignación de modelo de datos

ER proporciona un diseñador de asignación de modelos que permite a los usuarios asignar modelos de datos que se han diseñado para orígenes de datos de Dynamics 365 for Operations específicos. La ilustración siguiente muestra un ejemplo de este tipo de asignación de modelo de datos (**Transferencia de crédito SEPA** asignación del modelo de datos de dominio de pago). [![Ejemplo de asignación de modelos de datos ](./media/pic-model-mapping-1024x551.png)](./media/pic-model-mapping.png) Para familiarizarse con los detalles de este escenario, reproduzca las guías de tareas **ER Definir asignación del modelo y seleccionar orígenes de datos** y **ER Asignar modelo de datos a los orígenes de datos seleccionados** (parte del proceso de negocio **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**).

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Almacenar un componente modelo diseñado como una configuración del modelo

ER puede almacenar un modelo de datos diseñado junto con las asignaciones de datos asociadas como una configuración del modelo de la instancia actual de Dynamics 365 for Operations. En la siguiente ilustración se muestra un ejemplo de este tipo de configuración de modelo de datos (la configuración del modelo de pago). [![Ejemplo de una configuración de modelo de datos ](./media/pic-model-configuration-1024x585.png)](./media/pic-model-configuration.png) Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **ER Asignar modelo de datos a orígenes de datos seleccionados** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677**)).

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Creación de un formato que usa un modelo de datos como base

ER admite un diseñador de formato que puede usar para crear el formato de un documento electrónico determinado para un dominio empresarial seleccionando el componente modelo como base. El mismo diseñador del formato de ER le permite asignar un formato que crea a la asignación del modelo de datos de un dominio seleccionado como origen de datos. En la siguiente ilustración se muestra un ejemplo de este tipo de formato (la configuración de formato que admite el formato de pago **BACS** para el Reino Unido). [![Ejemplo de un formato que tiene un modelo de datos como base](./media/pic-format-1024x690.png)](./media/pic-format.png) Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **ER Diseñar el formato específico de dominio** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677**)).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Creación de una configuración para generar documentos electrónicos en formato de hoja de cálculo OPENXML

El diseñador de formato de ER se puede utilizar para generar un documento electrónico concreto en formato de hoja de cálculo OPENXML. La ilustración siguiente muestra un ejemplo de este tipo de formato (una configuración de formato para generar la hoja de cálculo OPENXML con los detalles de un diario de pago seleccionado):[![Imagen-ER-formato- Excel](./media/pic-er-format-excel.jpg)](./media/pic-er-format-excel.jpg) Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **ER Crear una configuración para informes en formato de OPENXML** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**). Utilice el archivo Excel al que se hace referencia a continuación como una plantilla del formato ER de diseño para completar el paso de importación de una plantilla de formato de esta guía de tareas: [Plantilla de informe de pago (SampleVendPaymWsReport.xlsx)](https://go.microsoft.com/fwlink/?linkid=845202)

### <a name="storing-a-designed-format-component-in-a-format-configuration"></a>Almacenar un componente diseñado del formato en una configuración del formato

ER puede almacenar un formato diseñado junto con las asignaciones configuradas de los datos como una configuración del formato de la instancia actual de Dynamics 365 for Operations. La ilustración anterior muestra un ejemplo de este tipo de configuración de formato (**BACS (Reino Unido)**, que es un elemento secundario de la configuración de **Modelo de pago**). Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **CE Diseñar el formato específico de dominio** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**).

### <a name="configuring-dynamics-365-for-operations-to-start-to-use-a-created-format-internally"></a>Configuración de Dynamics 365 for Operations para comenzar a usar un formato creado internamente

Dynamics 365 for Operations se puede configurar para empezar a usar un formato creado para generar informes electrónicos. La referencia a la configuración creada de formato se debe definir en la configuración de un determinado dominio. Por ejemplo, para empezar a utilizar una configuración de formato de ER para pagos electrónicos a proveedores en formato BACS, se debe hacer referencia a la configuración de formato en métodos específicos de pago, como se muestra en las siguientes ilustraciones: 

[![Configuración de formato BACS (Reino Unido)](media/ger-bacs-uk-format-configuration.png) 

[![Referencia al formato BACS (Reino Unido) en un método de pago](media/ger-bacs-uk-format-method.png) 

Para familiarizarse bien con los detalles de este escenario, reproduzca la guía de tareas **ER Usar formato para generar documentos electrónicos para pagos** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**).

## <a name="handling-er-components"></a>Tratamiento de componentes de ER
### <a name="publishing-an-er-component-in-lcs-to-offer-it-externally-localization"></a>Publicación de un componente de ER en LCS para ofrecerlo externamente (localización)

El propietario de un componente (modelo o formato) que se ha creado puede usar ER para publicar la versión completada del componente en LCS. Se requiere Un repositorio del tipo **Proyecto de LCS **para el proveedor actual de la configuración de ER. Cuando cambie el estado de la versión completada de un componente de **COMPLETADO** a **COMPARTIDO**, esa versión se publica en el LCS. Cuando haya publicado un componente a LCS, el propietario de ese componente pasa a ser un proveedor de servicio para admitir el componente. Por ejemplo, si el componente del formato está diseñado para generar un documento electrónico legalmente necesario (por ejemplo, de acuerdo con una situación de localización), se supone que el formato se mantendrá compatible con los cambios legislativos y que el proveedor emitirá nuevas versiones del componente siempre surjan nuevos requisitos legislativos. Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **ER Cargar una configuración en Lifecycle Services** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**).

### <a name="importing-an-er-component-from-lcs-to-use-it-internally"></a>Importar el componente de ER de LCS para utilizarlo internamente

ER le permite importar componentes de ER desde LCS en la instancia actual de Dynamics 365 for Operations. Se requiere un repositorio del tipo **Proyecto de LCS**. Si se ha importado un componente de ER de LCS a la instancia actual de Dynamics 365 for Operations, el propietario de la instancia se convierte en un consumidor del servicio ofrecido por el propietario (autor) del componente importado. Por ejemplo, si un componente del formato está diseñado para generar un documento electrónico específico desde Dynamics 365 for Operations en un formato específico del país o región (situación de localización), se supone que el consumidor del servicio podrá obtener actualizaciones que se realizan a ese formato, para mantenerlo compatible con los requisitos legislativos. Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **ER Importar una configuración de Lifecycle Services** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**).

### <a name="building-a-format-selecting-another-format-as-a-base-customization"></a>Creación de un formato que selecciona otro formato como base (personalización)

ER le permite crear (deriva) un nuevo componente de la versión actual de un componente (base) que se importó de LCS. Por ejemplo, si un usuario desea derivar un nuevo formato para implementar algunos requisitos especiales para un documento electrónico (como un campo adicional o una descripción amplia) para admitir un escenario de personalización. Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **ER Actualizar formato adoptando una nueva versión base del mismo** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**) .

### <a name="upgrading-a-format-selecting-a-new-version-of-base-format-rebase"></a>Actualizar un formato que selecciona una versión nueva del formato base (rebase)

ER le permite adoptar automáticamente los cambios de la última versión del componente de la base de la versión actual del borrador de componentes derivados. Este proceso se conoce como *reorganización*. Por ejemplo, un cambio normativo nuevo que se ha introducido en la última versión del formato que se importó desde LCS se puede combinar automáticamente en la versión personalizada de este formato del documento electrónico. Los cambios que no se pueden combinar automáticamente se consideran conflictos. Estos conflictos se presentan para la resolución manual de la herramienta del diseñador para el componente apropiado. Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **ER Actualizar formato adoptando una nueva versión base del mismo** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**) .

## <a name="list-of-er-configurations-that-are-delivered-in-the-dynamics-365-for-operations-solution"></a>Lista de configuraciones ER que se entregan en la solución de Dynamics 365 for Operations
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



<a name="see-also"></a>Consulte también
--------

[Requisitos de localización: crear una configuración de informes electrónicos](electronic-reporting-configuration.md)

[Administrar el ciclo de vida de las configuraciones de la notificación electrónica](general-electronic-reporting-manage-configuration-lifecycle.md)




