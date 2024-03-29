---
title: Visión general de los informes electrónicos (ER)
description: Este artículo proporciona una visión general de la herramienta de informes electrónicos. Describe conceptos clave, escenarios compatibles y formatos que forman parte de la solución.
author: kfend
ms.date: 11/02/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58941,  ""intro-internal
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.form: ERWorkspace
ms.openlocfilehash: e94846dd565abb6de2c1f07532d285e28307e9a2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269703"
---
# <a name="electronic-reporting-er-overview"></a>Visión general de los informes electrónicos (ER)

[!include [banner](../includes/banner.md)]

Este artículo proporciona una visión general de la herramienta de informes electrónicos (ER). Incluye información sobre conceptos clave, escenarios compatibles con ER y una lista con los formatos diseñados y publicados como parte de la solución.

ER es una herramienta configurable que le ayuda a crear y mantener informes y pagos electrónicos regulatorios. Se basa en los siguientes tres conceptos:

- Configuración en lugar de codificación:

    - La configuración la puede realizar un usuario empresarial y no requiere un desarrollador.
    - El modelo de datos se define en términos comerciales.
    - Los editores visuales se utilizan para crear todos los componentes de la configuración de ER.
    - El idioma que se usa para la transformación de datos se asemeja al idioma que se usa en Microsoft Excel.

- Una configuración para múltiples versiones de Dynamics 365 Finance:

    - Administre un modelo de datos específico de dominio que se define en términos comerciales.
    - Aísle los detalles de la versión de la aplicación en asignaciones de modelos de datos dependientes de la versión.
    - Mantenga una configuración de formato para múltiples lanzamientos de la versión actual, según el modelo de datos.

- Actualización fácil o automática:

    - Compatibilidad con el control de versiones de configuraciones de ER.
    - La biblioteca de Microsoft Dynamics Lifecycle Services (LCS) Assets se puede utilizar como repositorio de configuraciones de ER para el intercambio de versiones.
    - Las localizaciones que se basan en configuraciones ER originales se pueden introducir como versiones secundarias.
    - Se proporciona un árbol de configuración de ER como una herramienta que ayuda a controlar las dependencias de las versiones.
    - Las diferencias en la localización o la configuración delta se registran para permitir la actualización automática a una nueva versión de la configuración ER original.
    - Es fácil resolver manualmente los conflictos que se descubren durante la actualización automática de las versiones de localización.

ER le permite definir estructuras en formato electrónico y, a continuación, describir cómo deben rellenarse mediante datos y algoritmos. Puede utilizar un lenguaje de fórmulas que se parezca al lenguaje de Excel para la transformación de datos. Para hacer que la asignación de la base de datos al formato sea más manejable, reutilizable e independiente de los cambios de formato, se introduce un concepto de modelo de datos intermedio. Este concepto permite ocultar los detalles de implementación de la asignación de formato y permite reutilizar un único modelo de datos para asignaciones de múltiples formatos.

Puede usar ER para configurar formatos de entrada y de salida para documentos electrónicos en función de requisitos legales de diversos países y regiones. ER le permite administrar estos formatos durante su ciclo de vida. Por ejemplo, puede adoptar nuevos requerimientos normativos y puede generar documentos empresariales en el formato requerido para intercambiar información electrónicamente con organismos gubernamentales, bancos y otras partes.

El motor de ER está dirigido a usuarios empresariales en lugar de desarrolladores. Dado que configura formatos, en lugar de código, los procesos de creación y ajuste de formatos para documentos electrónicos son más rápidos y sencillos.

ER admite actualmente los formatos de hoja de cálculo de TEXTO, XML, JSON, PDF, Microsoft Word, Microsoft Excel y OPENXML.

## <a name="capabilities"></a>Capacidades

El motor de ER tiene las siguientes capacidades:

- Representa una sola herramienta compartida para informes electrónicos en diferentes ámbitos y reemplaza más de 20 distintos motores que hacen algún tipo de informe electrónico de finanzas y operaciones.
- Aísla el formato de un informe de la implementación actual. En otras palabras, el formato es aplicable para diferentes versiones.
- Admite la creación de un formato personalizado que se basa en un formato original. También incluye capacidades para actualizar automáticamente el formato personalizado cuando se producen cambios en el formato original porque se introducen requisitos de localización y personalización.
- Se convierte en la herramienta estándar principal para la ayuda de los requisitos de localización en los informes electrónicos, tanto para Microsoft como para los socios de MS.
- Admite la capacidad de distribuir formatos a los socios y los clientes a través de Microsoft Dynamics Lifecycle Services (LCS).

## <a name="key-concepts"></a>Conceptos clave

### <a name="main-data-flow"></a>Flujo de datos principal

[![Flujo de datos principal de ER](./media/ger-main-data-flow.jpg)](./media/ger-main-data-flow.jpg)

### <a name="component"></a>Componente

ER admiten los siguientes tipos de componentes:

- Modelo de datos
- Asignación de modelos
- Formato
- Metadatos

Para obtener más información, consulte [Informes de componentes electrónicos](er-overview-components.md).

### <a name="configuration"></a><a name="Configuration"></a>Configuración

Una configuración de ER es el contenedor de un componente concreto de ER. Dicho componente puede ser un componente del modelo de datos o un componente del formato. Una configuración puede incluir diferentes versiones de un componente de ER. Cada configuración se marca como perteneciente a un proveedor específico de configuración. La versión **Borrador** de un componente de una configuración se puede editar cuando se ha seleccionado el propietario de la configuración como proveedor activo en la configuración de ER de la aplicación.

Cada configuración de modelo contiene un componente de modelo de datos. Una nueva configuración de formato se puede derivar de una configuración de modelo de datos específico. En la configuración de árbol, la configuración de formato que se crea aparece como un elemento secundario de la configuración del modelo de datos original.

La configuración de formato que se crea contiene un componente formato. El componente modelo de datos de la configuración del modelo original se inserta automáticamente en el componente formato de la configuración creada de formato secundario como origen de datos predeterminado.

Una configuración de ER se comparte en las empresas de la aplicación.

### <a name="provider"></a><a name="Provider"></a>Proveedor

El proveedor de ER es la identificación de parte que se usa para indicar el autor (propietario) de cada configuración de ER. ER le permite administrar la lista de proveedores de configuración. Las configuraciones del formato que se liberan para documentos electrónicos como parte de la solución de finanzas y operaciones se marcan como propiedad del proveedor de configuración **Microsoft**.

Para obtener información sobre cómo registrar un nuevo proveedor de ER, reproduzca la guía de la tarea, **ER Creación de un proveedor de configuraciones y marcarlo como activo** (parte del proceso empresarial **7.5.4.3 Adquirir y desarrollar los componentes del servicio o la solución de TI (10677)**).

### <a name="repository"></a><a name="Repository"></a>Repositorio

Un repositorio de ER guarda las configuraciones de ER. Los tipos de repositorios de ER siguientes son compatibles: 

- Biblioteca compartida LCS
- Proyecto LCS
- Sistema de archivos
- RCS
- Recursos de Operations
- Repositorio Global

Un repositorio **Biblioteca compartida LCS** proporciona acceso a la lista de configuraciones dentro de la biblioteca de activos compartidos en Lifecycle Services (LCS). Este tipo de repositorio de ER se puede registrar solo para el proveedor de Microsoft. En la biblioteca compartida LCS del activo puede importar las últimas versiones de las configuraciones de ER en la instancia actual.

Un repositorio del **proyecto LCS** proporciona acceso a la lista de configuraciones de un proyecto LCS específico (biblioteca de activos del proyecto LCS) que se seleccionó al registrarse el repositorio. ER le permite cargar las configuraciones compartidas de la instancia actual a un repositorio específico del **Proyecto LCS**. También puede importar configuraciones desde un repositorio de **proyecto LCS** en la instancia actual de sus aplicaciones de finanzas y operaciones.

Un repositorio de **Sistema de archivos** proporciona acceso a la lista de configuraciones que están ubicadas como archivos XML en la carpeta específica del sistema de archivos local del equipo en el que se aloja el servicio AOS. La carpeta necesaria se selecciona en la etapa de registro de repositorio. Puede importar configuraciones de un repositorio del **sistema de archivos** en la instancia actual. 

Tenga en cuenta que este tipo de repositorio es accesible en los entornos siguientes:

- Los entornos hospedados en la nube implementados para fines de desarrollo (que contienen los modelos de prueba de suites)
- Entornos implementados localmente

Para obtener más información, consulte [Importar configuraciones de informes electrónicos (ER)](./electronic-reporting-import-ger-configurations.md).

Un repositorio **RCS** proporciona acceso a la lista de configuraciones de una instancia específica del [servicio de configuración](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration) que se seleccionó en la etapa de registro del repositorio. ER le permite importar configuraciones completadas o compartidas desde la instancia de RCS seleccionada a la instancia actual para que pueda usarlas en los informes electrónicos.

Para obtener más información, consulte [Importar configuraciones de informes electrónicos (ER) desde RCS](./rcs-download-configurations.md).

Un **repositorio global** proporciona acceso a la lista de configuraciones del repositorio global en el [servicio de configuración](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration). Este tipo de repositorio de ER se puede registrar solo para el proveedor de Microsoft. Desde el repositorio global, puede importar las últimas versiones de las configuraciones de ER en la instancia actual.

Para más información, consulte [Importar configuraciones de informes electrónicos (ER) del repositorio Global del servicio de configuración](./er-download-configurations-global-repo.md).

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

ER proporciona un diseñador de asignación de modelos que permite a los usuarios asignar modelos de datos que se han diseñado para orígenes de datos de la aplicación específicos. En característica de la asignación, los datos se importarán en tiempo de ejecución desde los orígenes de datos seleccionados en el modelo de datos. El modelo de datos se usa como un origen de datos abstracto de los formatos de ER que generan los documentos electrónicos salientes. 

Para familiarizarse con los detalles de este escenario, reproduzca las guías de tareas **CE Definir asignación del modelo y seleccionar orígenes de datos** y **CE Asignar modelo de datos a los orígenes de datos seleccionados** (parte del proceso de negocio **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**).

### <a name="configuring-data-model-mappings-for-incoming-documents"></a>Configurar asignaciones del modelo de datos para los documentos de entrada

ER proporciona un diseñador de asignación de modelos que permite a los usuarios asignar modelos de datos que se han diseñado para destinos específicos. Por ejemplo, los modelos de datos se pueden asignar para los componentes de datos que se puede actualizar (tablas, entidades de datos y vistas). En característica de la asignación, los datos se actualizarán en tiempo de ejecución con los datos del modelo de datos. Como almacenamiento abstracto del formato de ER, el modelo de datos se rellena con los datos que se importan de un documento electrónico entrante. 

### <a name="storing-a-designed-model-component-as-a-model-configuration"></a>Almacenar un componente modelo diseñado como una configuración del modelo

ER puede almacenar un modelo de datos diseñado, junto con las asignaciones de datos asociadas, como una configuración del modelo de la instancia actual. En la siguiente ilustración se muestra un ejemplo de este tipo de configuración de modelo de datos (la configuración del modelo de pago).

Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **CE Asignar modelo de datos a los orígenes de datos seleccionados** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**).

### <a name="building-a-format-that-uses-a-data-model-as-a-base"></a>Creación de un formato que usa un modelo de datos como base

ER admite un diseñador de formato que puede usar para crear el formato de un documento electrónico para un dominio empresarial seleccionando el componente modelo como base. El mismo diseñador del formato de ER le permite asignar un formato que crea a la asignación del modelo de datos de un dominio seleccionado como origen de datos. 

Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **CE Diseñar el formato específico de dominio** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**).

### <a name="building-a-configuration-to-generate-electronic-documents-in-openxml-worksheet-format"></a>Creación de una configuración para generar documentos electrónicos en formato de hoja de cálculo OPENXML

El diseñador de formato de ER se puede utilizar para generar un documento electrónico en formato de hoja de cálculo OPENXML. 

Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas **Crear una configuración ER para generar informes en formato OPENXML** (parte del proceso empresarial **7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)**). Como parte del paso de la guía de la tarea para importar una plantilla, utilice [Plantilla de informe de pago (SampleVendPaymWsReport.xlsx)](https://download.microsoft.com/download/3/f/0/3f0658b2-042c-43cf-a776-0f4c7f7cfe4e/SampleVendPaymWsReport.xlsx) el archivo de Excel como plantilla.

### <a name="building-a-configuration-to-generate-electronic-documents-in-a-word-document-format"></a>Creación de una configuración para generar documentos electrónicos en formato documento de Word.

El diseñador de formato de ER se puede utilizar para generar un documento electrónico en formato de documento de Word. En la siguiente ilustración se muestra un ejemplo de este tipo de formato. Tenga en cuenta que este formato reutiliza la configuración actual de ER que diseñó originalmente para generar la salida de informes en formato de OPENXML.

Para familiarizarse con los detalles de este escenario, reproduzca la guía de tareas Diseñar una configuración ER para generar informes en formato de Microsoft WORD (parte del proceso empresarial 7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)). Como parte del paso de la guía de tareas para importar una plantilla, use los archivos de Word siguientes como plantillas para el formato de ER:

- [Plantilla de informe de pago (SampleVendPaymDocReport.docx)](https://download.microsoft.com/download/0/d/e/0de5a87c-95fc-4dfa-958f-285cb28b5b2b/SampleVendPaymDocReport.docx)
- [Plantilla enlazada de pago (SampleVendPaymDocReportBounded.docx)](https://download.microsoft.com/download/a/1/2/a126cb43-6281-4f7b-bde0-25e03ff9bc1e/SampleVendPaymDocReportBounded.docx)

### <a name="building-a-configuration-to-import-data-from-incoming-electronic-documents"></a>Generar una configuración para importar datos desde documentos electrónicos entrantes

El diseñador del formato de ER se puede utilizar para describir un documento electrónico que se planifica para la importación de datos en formato XML o de texto. El formato diseñado se usa para analizar un documento de entrada. El diseñador de la asignación de formato de ER se puede utilizar para definir el enlazado de los elementos del formato diseñado para el modelo de datos. 

Para familiarizarse con los detalles de este escenario, reproduzca la guía Crear configuraciones de ER requeridas para importar datos desde una guía de tareas de archivo externo (parte del proceso empresarial 7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)). Use archivos siguientes para reproducir este manual:

- [Configuración del modelo de datos de ER (1099model.xml)](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml)
- [Configuración del formato de ER (1099format.xml)](https://download.microsoft.com/download/e/8/7/e87154b0-b53f-431f-8e1e-0b7f7c9805a9/1099format.xml)
- [Ejemplo de documento de entrada en formato XML (1099entries.xml)](https://download.microsoft.com/download/4/0/3/403a4958-df24-476a-b8b0-6843a9fa7f89/1099entries.xml)
- [Ejemplo de libro para administrar datos del documento de entrada (1099entries.xlsx)](https://download.microsoft.com/download/6/0/0/6001abab-a331-48db-a939-41851fb0f5d0/1099entries.xlsx)

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

## <a name="list-of-er-configurations-that-have-been-released-in-finance"></a><a name="list-of-configurations"></a>Lista de configuraciones de ER que se han lanzado en Finance

La lista de las configuraciones de informes electrónicos para Finance se actualiza constantemente. Abra el [Repositorio global](er-download-configurations-global-repo.md) para revisar la lista de configuraciones de informes electrónicos que son compatibles actualmente. En la ficha desplegable **Detalles de discontinuación** puede revisar la información sobre las configuraciones que se han discontinuado o que ya no se mantienen. 

![Contenido del repositorio global en la página de configuración del repositorio.](./media/er-overview-03.gif)

## <a name="additional-resources"></a>Recursos adicionales

- [Componentes de los informes electrónicos](er-overview-components.md)
- [Crear configuraciones de informes electrónicos (ER)](electronic-reporting-configuration.md)
- [Administrar el ciclo de vida de las configuraciones de la notificación electrónica (ER)](general-electronic-reporting-manage-configuration-lifecycle.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

