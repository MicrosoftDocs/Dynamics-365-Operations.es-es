---
title: Diseñar una nueva solución de informes electrónicos para imprimir un informe personalizado
description: En este tema se explica cómo diseñar una solución de informes electrónicos (ER) para imprimir un informe personalizado.
author: NickSelin
manager: AnnBe
ms.date: 08/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERParameters, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, EROperationDesigner, ERVendorTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c5bbfae36fb15437f2baadc66663cbfdb28691e8
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562620"
---
# <a name="design-a-new-er-solution-to-print-a-custom-report"></a>Diseñar una nueva solución de informes electrónicos para imprimir un informe personalizado

[!include[banner](../includes/banner.md)]

Los siguientes pasos explican cómo un usuario con el rol de Administrador del sistema, Desarrollador de informes electrónicos o Consultor funcional de informes electrónicos puede configurar los parámetros del marco de ER, diseñar las configuraciones de ER necesarias para una nueva solución de ER con el fin de acceder a los datos de un dominio comercial concreto, y generar un informe personalizado con formato de Microsoft Office. Estos pasos se pueden llevar a cabo en la empresa **USMF**.

- [Configurar el marco ER](#ConfigureFramework)

    - [Configurar los parámetros de ER](#ConfigureParameters)
    - [Activar un proveedor de configuración de ER](#ActivateProvider)

        - [Revise la lista de proveedores de configuración de ER](#ReviewProvidersList)
        - [Añada una nueva configuración para el proveedor de ER](#AddProvider)
        - [Activar un proveedor de configuración de ER](#ActivateAddedProvider)

- [Diseñar un modelo de datos específico de dominio](#DesignModel)

    - [Importar una nueva configuración de modelo de datos](#ImportDataModel)
    - [Creación de un nuevo modelo de configuración de datos](#DesignDataModel)

        - [Asignar un nombre al modelo de datos](#NameDataModel)
        - [Agregar campos de modelo de datos](#FieldsEntry)
        - [Completar el diseño del modelo de datos](#CompleteDataModel)

- [Diseñar una asignación de modelo para el modelo de datos configurado](#DesignMapping)

    - [Importar una nueva configuración de asignación de modelo](#ImportModelMapping)
    - [Crear una nueva configuración de asignación de modelo](#CreateModelMapping)

        - [Diseñar un nuevo componente de asignación de modelo](#DesignMappingComponent)
        - [Agregar orígenes de datos para acceder a las tablas de la aplicación](#AddMmDataSource1)
        - [Agregar orígenes de datos para acceder a las enumeraciones de la aplicación](#AddMmDataSource2)
        - [Agregar etiquetas de ER para generar un informe en un idioma específico](#AddMmLabels)
        - [Agregar un origen de datos para transformar los resultados de comparar valores de enumeración con un valor de texto](#AddMmDataSource3)
        - [Enlazar orígenes de datos a campos de modelo de datos](#AddMmBindings1)
        - [Completar el diseño de la asignación del modelo](#CompleteModelMapping)

- [Diseñar una plantilla para un informe personalizado](#DesignReportTemplate)
- [Diseñar un formato](#DesignFormat)

    - [Importar una configuración de formato diseñado](#FormatImport)
    - [Creación de una configuración de formato nueva](#FormatCreate)

        - [Importar una plantilla de informe](#ImportReportTemplate)
        - [Configurar un formato](#ConfigureFormat)
        - [Definir el enlace de datos para un título de informe](#DefineFormatBindings)
        - [Revisar el origen de datos del modelo](#ReviewModelDataSource)
        - [Enlazar elementos de formato a campos de origen de datos](#BindFormatElements)

    - [Ejecutar un formato diseñado a partir de un informe electrónico](#RunFormatFromER)

- [Ajustar un formato diseñado](#TuneFormat)

    - [Modificar un formato para cambiar el nombre de un documento generado](#ModifyToChangeName)
    - [Modificar un formato para cambiar el orden de las preguntas](#ModifyToOrder)
    - [Ejecutar un formato modificado a partir de un informe electrónico](#RunFormatFromER2)
    - [Completar el diseño del formato](#CompleteFormat)

- [Desarrollar artefactos de aplicación para llamar al informe diseñado](#DevelopCustomCode)

    - [Modificación de código de origen](#ModifySourceCode)

        - [Agregar una clase de contrato de datos](#DataContractClass)
        - [Agregar una clase de generador de interfaz de usuario](#UIBuilderClass)
        - [Agregar una clase de proveedor de datos](#DataProviderClass)
        - [Agregar un archivo de etiquetas](#LabelsFile)
        - [Agregar una clase de servicio de informes](#ServiceClass)
        - [Agregar una clase de controlador de informes](#ControllerClass)
        - [Agregar un elemento de menú](#MenuItem)
        - [Agregar un elemento de menú a un menú](#Menu)
        - [Crear un proyecto de Visual Studio](#BuildVSProject)

    - [Ejecutar un formato desde la aplicación](#RunFormatFromApp)

- [Ajustar una solución de informes electrónicos diseñada](#TuneSolution)

    - [Modificar una asignación de modelo](#ModifyModelMapping)

        - [Agregar orígenes de datos para acceder al objeto de contrato de datos](#AddDataSource1)
        - [Agregar un origen de datos para acceder a registros de asignación de formato de informe electrónico](#AddDataSource2)
        - [Agregar un origen de datos para acceder a un registro de asignación de formato de un formato de informe electrónico en ejecución](#AddDataSource3)
        - [Introducir en el modelo de datos el nombre del formato de informe electrónico en ejecución](#AddBinding)
        - [Completar el diseño de la asignación del modelo](#CompleteModelMapping2)

    - [Modificar un formato](#ModifyFormat)

        - [Agregar un nuevo elemento de formato](#AddFormatElement)
        - [Enlazar el elemento de formato agregado](#BindAddedFormatElement)
        - [Completar el diseño del formato](#CompleteFormat2)

    - [Ejecutar un formato desde la aplicación](#RunFormatFromApp2)
    - [Ejecutar un formato a partir de un informe electrónico](#RunFormatFromER3)
    - [Configurar un destino de formato para una vista previa en pantalla](#ConfigureDestination)
    - [Ejecutar un formato desde la aplicación para obtener una vista previa como un documento PDF](#RunFormatFromApp3)

- [Recursos adicionales](#References)

En este ejemplo, va a crear una nueva solución de informes electrónicos para el módulo [Cuestionario](https://docs.microsoft.com/dynamics365/human-resources/hr-learning-questionnaires). Esta nueva solución de informes electrónicos le permite diseñar un informe utilizando una hoja de cálculo de Microsoft Excel como plantilla. A continuación, puede generar el informe de **Cuestionario** con formato Excel o PDF, y generar el informe de SQL Server Reporting Services (SSRS) existente. También puede modificar el nuevo informe posteriormente, a petición. No se requiere codificación.

1. Para ejecutar el informe existente, vaya a **Cuestionario** \> **Diseño** \> **Informe de cuestionarios**.

    ![Seleccionar el elemento de menú Informe de cuestionarios en el módulo Cuestionario para ejecutar el informe de SSRS existente](./media/er-quick-start1-application-menu-origin.png)

2. En el cuadro de diálogo **Informe de cuestionarios**, especifique los criterios de selección. Aplique un filtro para que el informe solo incluya el cuestionario **SBCCrsExam**.

    ![Especificar los criterios de selección en el cuadro de diálogo Informe de cuestionarios](./media/er-quick-start1-ssrs-report-dialog.png)

La siguiente ilustración muestra la versión generada del informe de SSRS para el cuestionario **SBCCrsExam**.

![Informe de SSRS generado](./media/er-quick-start1-ssrs-report.png)

## <a name="configure-the-er-framework"></a><a name="ConfigureFramework"></a>Configurar el marco ER

Como usuario en el rol de Desarrollador de informes electrónicos, debe configurar el conjunto mínimo de parámetros de ER antes de comenzar a usar el marco de ER para diseñar su nueva solución de ER.

### <a name="configure-er-parameters"></a><a name="ConfigureParameters"></a>Configurar los parámetros de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En el área de trabajo de **Informes electrónicos**, seleccione **Parámetros de informes electrónicos**.
3. En la página **Parámetros de informes electrónicos**, en la pestaña **General**, establezca la opción **Habilitar modo de diseño** en **Sí**.
4. En la pestaña **Adjuntos**, establezca los parámetros siguientes:

    - Establezca el campo **Configuraciones** en **Archivo** para la empresa **USMF**.
    - Establezca los campos **Archivo de trabajo**, **Temporal**, **Base** y **Otros** en **Archivo**.

Para obtener más información sobre cómo configurar los parámetros de ER, consulte [Configurar el marco de ER](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a name="ActivateProvider"></a>Activar un proveedor de configuración de ER

Cada configuración de ER está marcada como propiedad de un proveedor de configuración de ER. Por lo tanto, debe activar un proveedor de configuración de ER en el espacio de trabajo **Informes electrónicos** antes de comenzar a agregar o editar configuraciones de ER.

> [!NOTE]
> Solo el propietario de una configuración de ER puede editarla. Por lo tanto, antes de poder editar una configuración de ER, se debe activar el proveedor de configuración ER apropiado en el espacio de trabajo **Informes electrónicos**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a name="ReviewProvidersList"></a>Revise la lista de proveedores de configuración de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En el espacio de trabajo **Informes electrónicos**, en la sección **Vínculos relacionados**, seleccione **Proveedores de configuración**.
3. En la página **Proveedores de configuración**, cada registro de proveedor de configuración tiene un nombre y una dirección URL únicos. Revise el contenido de esta página. Si un registro para **Litware, Inc.** (`https://www.litware.com`) ya existe, omita el siguiente procedimiento, [Agregar un nuevo proveedor de configuración de ER](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a name="AddProvider"></a>Añada una nueva configuración para el proveedor de ER

1. En la página **Proveedores de configuración**, seleccione **Nuevo**.
2. En el campo **Nombre**, introduzca **Litware, Inc.**
3. En el campo **Dirección de Internet**, introduzca `https://www.litware.com`.
4. Seleccione **Guardar**.

#### <a name="activate-an-er-configuration-provider"></a><a name="ActivateAddedProvider"></a>Activar un proveedor de configuración de ER

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En el espacio de trabajo **Informes electrónicos**, seleccione el proveedor de configuración **Litware, Inc.**
3. Seleccione **Definir como activo**.

Para obtener más información sobre proveedores de configuración de ER, consulte [Crear proveedores de la configuración y marcarlos como activos](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="design-a-domain-specific-data-model"></a><a name="DesignModel"></a>Diseñar un modelo de datos específico del dominio

Debe crear una nueva configuración de ER que contenga un componente de [modelo de datos](general-electronic-reporting.md#data-model-and-model-mapping-components) para el dominio empresarial **Cuestionario**. Este modelo de datos se utilizará más tarde como origen de datos al diseñar un formato de ER para generar informe **Cuestionario**.

Al completar los pasos de la sección [Importar una nueva configuración de modelo de datos](#ImportDataModel) puede importar el modelo de datos necesario desde el archivo XML suministrado. Como alternativa, puede completar los pasos de la sección [Crear una nueva configuración de modelo de datos](#DesignDataModel) para diseñar este modelo de datos desde cero.

### <a name="import-a-new-data-model-configuration"></a><a name="ImportDataModel"></a>Importar una nueva configuración de modelo de datos

1. Descargue el archivo [Questionnaires model.version.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) y guárdelo en su equipo local.
2. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
3. En el espacio de trabajo **Informes electrónico**, seleccione **Configuraciones de informes**.
4. En el panel Acción, seleccione **Exchange** \> **Cargar del archivo XML**.
5. Seleccione **Examinar** y, a continuación, busque y seleccione el archivo **Questionnaires model.version.1.xml**.
6. Seleccione **Aceptar** para importar la configuración.

Para continuar, omita el siguiente procedimiento, [Crear una nueva configuración de modelo de datos](#DesignDataModel).

### <a name="create-a-new-data-model-configuration"></a><a name="DesignDataModel"></a>Creación de un nuevo modelo de configuración de datos

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En el espacio de trabajo **Informes electrónico**, seleccione **Configuraciones de informes**.
3. Seleccionar **Crear configuración**.
4. En el cuadro de diálogo desplegable, en el campo **Nombre**, escriba **Modelo de cuestionario**.
5. Seleccione **Crear configuración** para crear la configuración.

#### <a name="name-the-data-model"></a><a name="NameDataModel"></a>Asignar un nombre al modelo de datos

1. En la página **Configuraciones**, en el árbol de configuración, seleccione **Modelo de cuestionario**.
2. Seleccione **Diseñador**.
3. En la página **Diseñador de modelo de datos**, en la ficha desplegable **General**, en el campo **Nombre**, escriba <a name="DataModeName"></a>**Cuestionarios**.

#### <a name="add-new-data-model-fields"></a><a name="FieldsEntry"></a>Agregar nuevos campos de modelo de datos

1. En la página **Diseñador de modelo de datos**, seleccione **Nuevo**.
2. En el cuadro de diálogo desplegable para agregar un nodo de modelo de datos, siga estos pasos:

    1. Seleccione **Raíz del modelo** como tipo del nuevo nodo.
    2. En el campo **Nombre**, especifique <a name="RootDefinitionName"></a>**Root**.
    3. Seleccione **Agregar** para agregar el nuevo nodo.

    Este descriptor raíz se utilizará para proporcionar datos para el informe de **Questionnaire**. Un solo modelo de datos puede tener varios descriptores. Cada descriptor se puede especificar para un solo formato de informes electrónicos, a fin de identificar los datos que se requieren para generar el informe.

3. Vuelva a seleccionar **Nuevo** y, a continuación, en el cuadro de diálogo desplegable para agregar un nodo de modelo de datos, siga estos pasos:

    1. Seleccione **Secundario de un nodo activo** como tipo del nuevo nodo.
    2. En el campo **Nombre**, especifique **CompanyName**.
    3. En el campo **Tipo de artículo**, seleccione **Cadena**.
    4. Seleccione **Agregar** para agregar el nuevo campo.

    Este campo es obligatorio para pasar el nombre de la empresa actual a un informe ER que consume este modelo de datos como origen de datos.

4. Vuelva a seleccionar **Nuevo** y, a continuación, en el cuadro de diálogo desplegable para agregar un nodo de modelo de datos, siga estos pasos:

    1. Seleccione **Secundario de un nodo activo** como tipo del nuevo nodo.
    2. En el campo **Nombre**, especifique **Questionnaire**.
    3. En el campo **Tipo de artículo**, seleccione **Lista de registros**.
    4. Seleccione **Agregar** para agregar el nuevo campo.

    Este campo se usará para pasar la lista de cuestionarios a un informe ER que consume este modelo de datos como origen de datos.

5. Seleccione el nodo **Questionnaire**.
6. Siga agregando de la misma manera los campos obligatorios del modelo de datos editable, hasta que haya completado la siguiente estructura del modelo de datos.

    | Ruta de acceso de campo                                                    | Tipo de datos   | Designación de campo/valor devuelto |
    |---------------------------------------------------------------|-------------|----------------------------------|
    | Root                                                          |             | El punto de referencia para solicitar los datos del cuestionario. |
    | Root\\CompanyName                                             | Cadena      | El nombre de la empresa actual. |
    | Root\\ExecutionContext                                        | Registro      | Detalles de ejecución del formato. |
    | Root\\ExecutionContext\\FormatName                            | Cadena      | Nombre del formato ER que se está ejecutando. |
    | Root\\Questionnaire                                           | Lista de registros | La lista de cuestionarios |
    | Root\\Questionnaire\\Active                                   | Cadena      | El estado del mensaje de cuestionario actual. |
    | Root\\Questionnaire\\Code                                     | Cadena      | El código del cuestionario actual. |
    | Root\\Questionnaire\\Description                              | Cadena      | La descripción del cuestionario actual. |
    | Root\\Questionnaire\\QuestionnaireType                        | Cadena      | El tipo del cuestionario actual. |
    | Root\\Questionnaire\\QuestionOrder                            | Cadena      | El orden numérico del cuestionario actual. |
    | Root\\Questionnaire\\ResultsGroup                             | Grabar      | Los parámetros de resultados del cuestionario actual. |
    | Root\\Questionnaire\\ResultsGroup\\Code                       | Cadena      | El código de identificación del grupo de resultados actual. |
    | Root\\Questionnaire\\ResultsGroup\\Description                | Cadena      | La descripción del grupo de resultados actual. |
    | Root\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints          | Real        | El número máximo de puntos que se pueden ganar. |
    | Root\\Questionnaire\\Question                                 | Lista de registros | La lista de preguntas del cuestionario actual. |
    | Root\\Questionnaire\\Question\\CollectionSequenceNumber       | Entero     | El número de secuencia de la colección de respuestas actual. |
    | Root\\Questionnaire\\Question\\Id                             | Cadena      | El código de identificación de la pregunta actual. |
    | Root\\Questionnaire\\Question\\MustBeCompleted                | Cadena      | Una marca que indica si se debe responder a la pregunta actual. |
    | Root\\Questionnaire\\Question\\PrimaryQuestion                | Cadena      | Una marca que indica si la pregunta actual es principal. |
    | Root\\Questionnaire\\Question\\SequenceNumber                 | Entero     | El número de secuencia de la pregunta actual. |
    | Root\\Questionnaire\\Question\\Text                           | Cadena      | El texto de la pregunta actual. |
    | Root\\Questionnaire\\Question\\Answer                         | Lista de registros | La lista de respuestas de la pregunta actual. |
    | Root\\Questionnaire\\Question\\Answer\\CorrectAnswer          | Cadena      | Una marca que indica si la respuesta actual es correcta. |
    | Root\\Questionnaire\\Question\\Answer\\Points                 | Real        | Los puntos que se obtienen cuando se selecciona la respuesta actual. |
    | Root\\Questionnaire\\Question\\Answer\\SequenceNumber         | Entero     | El número de secuencia de la respuesta actual. |
    | Root\\Questionnaire\\Question\\Answer\\Text                   | Cadena      | El texto de la respuesta actual. |

    La siguiente ilustración muestra el modelo de datos editable completado en la página **Diseñador de modelo de datos**.

    ![Modelo de datos configurado en el diseñador de modelo de datos de ER](./media/er-quick-start1-model2.png)

7. Guarde los cambios.
8. Cierre la página **Diseñador de modelo de datos**.

#### <a name="complete-the-design-of-the-data-model"></a><a name="CompleteDataModel"></a>Completar el diseño del modelo de datos

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuración, seleccione **Modelo de cuestionario**.
3. En la ficha desplegable **Versiones**, seleccione la versión de configuración que tenga un estado de **Borrador**.
4. Seleccione **Cambiar estado** \> **Completada**.

El estado de la versión 1 de esta configuración cambia de **Borrador** a **Completada**. La versión 1 ya no se puede cambiar. Esta versión contiene el modelo de datos configurado y se puede utilizar como la base de otras configuraciones de informes electrónicos. Se crea la versión 2 de esta configuración y tiene un estado de **Borrador**. Puede editar esta versión para ajustar el modelo de datos **Questionnaire**.

![Versiones de la configuración de ER editable en la página Configuraciones](./media/er-quick-start1-model-configuration.png)

Para obtener más información sobre el control de versiones para configuraciones de ER, consulte [Visión general de los informes electrónicos (ER)](general-electronic-reporting.md#component-versioning).

> [!NOTE]
> El modelo de datos configurado es su representación abstracta del dominio empresarial **Questionnaire** y no contiene relaciones con artefactos específicos de Microsoft Dynamics 365 Finance.

## <a name="design-a-model-mapping-for-the-configured-data-model"></a><a name="DesignMapping"></a>Diseñar una asignación de modelo para el modelo de datos configurado

Como usuario con el rol de Desarrollador de informes electrónicos, debe crear una nueva configuración de ER que contenga un componente de [asignación de modelo](general-electronic-reporting.md#data-model-and-model-mapping-components) para el modelo de datos **Questionnaire**. Dado que este componente implementa el modelo de datos configurado para Finance, es específico de Finance. Debe configurar el componente de asignación del modelo para especificar los objetos de la aplicación que hay que usar para completar el modelo de datos configurado con los datos de la aplicación en tiempo de ejecución. Para completar esta tarea, debe conocer los detalles de implementación de la estructura de datos del dominio empresarial **Questionnaire** en Finance.

Al completar los pasos de la sección [Importar una nueva configuración de asignación de modelo de datos](#ImportModelMapping) puede importar la configuración de asignación de modelo necesaria desde el archivo XML suministrado. Como alternativa, puede completar los pasos de la sección [Crear una nueva configuración de asignación de modelo de datos](#CreateModelMapping) para diseñar esta asignación de modelo desde cero.

### <a name="import-a-new-model-mapping-configuration"></a><a name="ImportModelMapping"></a>Importar una nueva configuración de asignación de modelo

1. Descargue el archivo [Questionnaires mapping.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) y guárdelo en su equipo local.
2. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
3. En el espacio de trabajo **Informes electrónico**, seleccione **Configuraciones de informes**.
4. En el panel Acción, seleccione **Exchange** \> **Cargar del archivo XML**.
5. Seleccione **Examinar** y, a continuación, busque y seleccione el archivo **Questionnaires mapping.version.1.1.xml**.
6. Seleccione **Aceptar** para importar la configuración.

Para continuar, omita el siguiente procedimiento, [Crear una nueva configuración de asignación de modelo](#CreateModelMapping).

### <a name="create-a-new-model-mapping-configuration"></a><a name="CreateModelMapping"></a>Crear una nueva configuración de asignación de modelo

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuración, seleccione **Modelo de cuestionario**.
3. Seleccionar **Crear configuración**.
4. En el cuadro de diálogo desplegable, siga estos pasos:

    1. En el campo **Nuevo**, seleccione **Asignación de modelo según el modelo de datos Questionnaires**.
    2. En el campo **Nombre**, escriba **Asignación de cuestionario**.
    3. En el campo **Definición del modelo de datos**, seleccione la definición **Root**.
    4. Seleccione **Crear configuración** para crear la configuración.

#### <a name="design-a-new-model-mapping-component"></a><a name="DesignMappingComponent"></a>Diseñar un nuevo componente de asignación de modelo

1. En la página **Configuraciones**, en el árbol de configuración, seleccione **Asignación de cuestionario**.
2. Seleccione **Diseñador** para abrir la lista de asignaciones.
3. Seleccione la asignación **Asignación de cuestionarios** que se agregó automáticamente para la definición **Root**
4. Seleccione **Diseñador** para empezar a configurar la asignación seleccionada.

Se agrega automáticamente una nueva asignación para la definición **Root**. Esta asignación tiene la dirección **Para modelo**. Por lo tanto, esta asignación se puede usar para rellenar un modelo de datos con los datos necesarios.

#### <a name="add-data-sources-to-access-application-tables"></a><a name="AddMmDataSource1"></a>Agregar orígenes de datos para acceder a las tablas de la aplicación

Debe configurar los orígenes de datos para acceder a las tablas de la aplicación que contienen los detalles del cuestionario.

1. En la página **Diseñador de asignación de modelo**, en el panel **Tipos de origen de datos**, seleccione **Dynamics 365 for Operations\\Registros de tabla**.
2. Agregue un nuevo origen de datos que se utilizará para acceder a la tabla KMCollection, donde cada registro representa un solo cuestionario:

    1. En el panel **Orígenes de datos**, seleccione **Agregar raíz**.
    2. En el cuadro de diálogo, en el campo **Nombre**, escriba **Questionnaire**.
    3. En el campo **Tabla**, escriba **KMCollection**.
    4. Establezca la opción **Pedir consulta** en **Sí**. Puede especificar en tiempo de ejecución opciones de [filtrado](../../fin-ops/get-started/advanced-filtering-query-options.md) para esta tabla en el cuadro de diálogo de consulta del sistema.
    5. Seleccione **Aceptar** para agregar el nuevo origen de datos.

3. En el panel **Tipos de origen de datos**, seleccione **Dynamics 365 for Operations\\Registros de tabla**.
4. Agregue un nuevo origen de datos que se utilizará para acceder a la tabla KMQuestion, donde cada registro representa una sola pregunta en un cuestionario:

    1. En el panel **Orígenes de datos**, seleccione **Agregar raíz**.
    2. En el cuadro de diálogo, en el campo **Nombre**, escriba **Pregunta**.
    3. En el campo **Tabla**, escriba **KMQuestion**.
    4. Seleccione **Aceptar** para agregar el nuevo origen de datos.

5. En el panel **Tipos de origen de datos**, seleccione **Dynamics 365 for Operations\\Registros de tabla**.
6. Agregue una nueva prueba de origen de datos que se utilizará para acceder a la tabla KMAnswer, donde cada registro representa una sola respuesta a una pregunta en un cuestionario:

    1. En el panel **Orígenes de datos**, seleccione **Agregar raíz**.
    2. En el campo **Nombre**, especifique **Respuesta**.
    3. En el campo **Tabla**, escriba **KMAnswer**.
    4. Seleccione **Aceptar** para agregar el nuevo origen de datos.

7. En el panel **Tipos de origen de datos**, seleccione **Funciones\\Campo calculado**.
8. Agregue un nuevo campo calculado que se utilizará para acceder a un registro de la tabla KMQuestionResultGroup desde cada registro de la tabla principal KMCollection:

    1. En el panel **Orígenes de datos**, seleccione **Cuestionario**.
    2. Seleccione **Agregar**.
    3. En el cuadro de diálogo, en el campo **Nombre**, escriba **\$ResultGroup**.
    4. Seleccione **Editar fórmula**.
    5. En el [Editor de fórmulas ER](general-electronic-reporting-formula-designer.md), en el campo **Fórmula**, escriba **FIRSTORNULL(\@ .'\<Relations'.KMQuestionResultGroup)** para usar la [ruta](er-formula-language.md#paths) de la relación uno a varios entre las tablas KMCollection y KMQuestionResultGroup.
    6. Seleccione **Guardar** y cierre el editor de fórmulas.
    7. Seleccione **Aceptar** para agregar el nuevo campo calculado.

9. En el panel **Tipos de origen de datos**, seleccione **Funciones\\Campo calculado**.
10. Agregue un nuevo campo calculado que se utilizará para acceder a registros de preguntas de la tabla KMQuestion desde cada registro de la tabla principal KMCollectionQuestion:

    1. En el panel **Orígenes de datos**, seleccione **Cuestionario**.
    2. Amplíe el nodo **\<Relations**, que contiene relaciones de uno a varios de la tabla KMCollection.
    3. Seleccione la tabla **KMCollectionQuestion** relacionado y, a continuación, seleccione **Agregar**.
    4. En el cuadro de diálogo, en el campo **Nombre**, escriba **\$Question**.
    5. Seleccione **Editar fórmula**.
    6. En el editor de fórmulas, en el campo **Fórmula**, escriba **FIRSTORNULL (FILTER(Question, Question.kmQuestionId = \@ .kmQuestionId))** para devolver los registros de preguntas correspondientes de la tabla KMQuestion.
    7. Seleccione **Guardar** y cierre el editor de fórmulas.
    8. Seleccione **Aceptar** para agregar el nuevo campo calculado.

11. En el panel **Tipos de origen de datos**, seleccione **Funciones\\Campo calculado**.
12. Agregue un nuevo campo calculado que se utilizará para acceder a registros de respuesta de la tabla KMAnswer desde cada registro de la tabla principal KMQuestion:

    1. En el panel **Orígenes de datos**, seleccione **Questionnaire.\<Relations.KMCollectionQuestion.\$Question** y, a continuación, seleccione **Agregar**.
    2. En el cuadro de diálogo, en el campo **Nombre**, escriba **\$Answer**.
    3. Seleccione **Editar fórmula**.
    4. En el editor de fórmulas, en el campo **Fórmula**, escriba **FILTER (Answer,Answer.kmAnswerCollectionId = \@ .kmAnswerCollectionId)** para devolver los registros de respuesta correspondientes de la tabla KMAnswer.
    5. Seleccione **Guardar** y cierre el editor de fórmulas.
    6. Seleccione **Aceptar** para agregar el nuevo campo calculado.

13. En el panel **Tipos de origen de datos**, seleccione **Dynamics 365 for Operations\\Tabla**.
14. Agregue un nuevo origen de datos que se utilizará para acceder a los métodos de la tabla CompanyInfo. Tenga en cuenta que el método **find()** de esta tabla devuelve un registro que representa una empresa de la instancia de Finance actual en cuyo contexto se llama a esta asignación.

    1. En el panel **Orígenes de datos**, seleccione **Agregar raíz**.
    2. En el cuadro de diálogo, en el campo **Nombre**, escriba **CompanyInfo**.
    3. En el campo **Tabla**, escriba **CompanyInfo**.
    4. Seleccione **Aceptar** para agregar el nuevo origen de datos.

#### <a name="add-data-sources-to-access-application-enumerations"></a><a name="AddMmDataSource2"></a>Agregar orígenes de datos para acceder a las enumeraciones de la aplicación

Debe configurar los orígenes de datos para acceder a las enumeraciones de la aplicación y comparar sus valores con los valores de los campos de tipo **Enumeración** en las tablas de la aplicación. Debe utilizar el resultado de la comparación para completar los campos correspondientes del modelo de datos.

1. En la página **Diseñador de asignación de modelo**, en el panel **Tipos de origen de datos**, seleccione **Dynamics 365 for Operations\\Enumeración**.
2. Agregue un nuevo origen de datos que se utilizará para acceder a los valores de la enumeración **EnumAppNoYes**.

    1. En el panel **Orígenes de datos**, seleccione **Agregar raíz**.
    2. En el cuadro de diálogo, en el campo **Nombre**, escriba **EnumAppNoYes**.
    3. En el campo **Enumeración**, introduzca **NoYes**.
    4. Seleccione **Aceptar** para agregar el nuevo origen de datos.

3. En el panel **Tipos de origen de datos**, seleccione **Dynamics 365 for Operations\\Enumeración**.
4. Agregue un nuevo origen de datos que se utilizará para acceder a los valores de la enumeración **KMCollectionQuestionMode**.

    1. En el panel **Orígenes de datos**, seleccione **Agregar raíz**.
    2. En el cuadro de diálogo, en el campo **Nombre**, introduzca **EnumAppQuestionOrder**.
    3. En el campo **Enumeración**, introduzca **KMCollectionQuestionMode**.
    4. Seleccione **Aceptar** para agregar el nuevo origen de datos.

#### <a name="add-er-labels-to-generate-a-report-in-a-specified-language"></a><a name="AddMmLabels"></a>Agregar etiquetas de informes electrónicos para generar un informe en un idioma específico

Puede agregar etiquetas de ER para configurar algunos de sus orígenes de datos de forma que devuelvan valores que dependen del idioma definido en el contexto de la llamada de asignación del modelo.

1. En la página **Diseñador de asignación de modelo**, en el panel **Orígenes de datos**, seleccione **Respuesta** y después seleccione **Editar**.
2. Active el campo **Etiqueta**.
3. Seleccione **Traducir**.
4. En el cuadro de diálogo **Traducción de texto**, siga estos pasos:

    1. En el campo **Id. de etiqueta**, introduzca **PositiveAnswer**.
    2. En el campo **Texto en el idioma predeterminado**, introduzca **Yes**.
    3. Seleccione **Traducir**.
    4. En el campo **Id. de etiqueta**, introduzca **NegativeAnswer**.
    5. En el campo **Texto en el idioma predeterminado**, introduzca **No**.
    6. Seleccione **Traducir**.

5. Cierra el cuadro de diálogo **Traducción de texto**.
6. Seleccione **Cancelar**.

![Agregar etiquetas de ER para la asignación del modelo editable](./media/er-quick-start1-adding-labels.png)

Ha introducido etiquetas de ER solo para el idioma predeterminado. Para obtener información sobre cómo las etiquetas de ER se pueden traducir a otros idiomas, consulte [Diseñar informes multilingües](er-design-multilingual-reports.md).

#### <a name="add-a-data-source-to-transform-the-results-of-comparing-enumeration-values-to-a-text-value"></a><a name="AddMmDataSource3"></a>Agregar un origen de datos para transformar los resultados de comparar valores de enumeración con un valor de texto

Dado que debe transformar los resultados de la comparación entre los valores de enumeración y los valores de texto varias veces para los orígenes de diferencias, es una buena idea configurar esta lógica como un único origen de datos. Sin embargo, para que este origen de datos sea reutilizable, debe configurarlo como un origen de datos parametrizado. Para obtener más información, consulte [Admitir llamadas parametrizadas de orígenes de datos de informes electrónicos del tipo de campo calculado](er-calculated-field-type.md).

1. En la página **Diseñador de asignación de modelo**, en el panel **Tipos de origen de datos**, seleccione **General\\Contenedor vacío**.
2. Agregar un nuevo origen de datos de contenedor:

    1. En el panel **Orígenes de datos**, seleccione **Agregar raíz**.
    2. En el cuadro de diálogo, en el campo **Nombre**, escriba **Ayudante**.
    3. Seleccione **Aceptar** para agregar el nuevo origen de datos de contenedor.

3. En el panel **Tipos de origen de datos**, seleccione **Funciones\\Campo calculado**.
4. Agregar un nuevo origen de datos:

    1. En el panel **Orígenes de datos**, seleccione **Ayudante**.
    2. Seleccione **Agregar**.
    3. En el cuadro de diálogo, en el campo **Nombre**, introduzca **NoYesEnumToString**.
    4. Seleccione **Editar fórmula**.
    5. En el editor de fórmulas, seleccione **Parámetros**.
    6. Siga estos pasos para especificar parámetros para la expresión configurada:

        1. Seleccione **Nuevo**.
        2. En el cuadro de diálogo, en el campo **Nombre**, escriba **Argumento**.
        3. En el campo **Tipo**, seleccione el tipo de datos **Booleano**.
        4. Seleccione **Aceptar**.

    7. En el campo **Fórmula**, introduzca **IF (Argumento = true, \@"GER\_LABEL:PositiveAnswer ", \@"GER\_LABEL:NegativeAnswer")** para devolver el texto de la etiqueta de ER adecuada, según el idioma del contexto de ejecución y el valor del parámetro especificado.
    8. Seleccione **Guardar** y cierre el editor de fórmulas.
    9. Seleccione **Aceptar** para agregar el nuevo origen de datos.

![Asignación de datos configurada en el diseñador de asignación de modelo de ER](./media/er-quick-start1-added-data-sources.png)

#### <a name="bind-data-sources-to-data-model-fields"></a><a name="AddMmBindings1"></a>Enlazar orígenes de datos a campos de modelo de datos

Debe enlaza los orígenes de datos configurados a los campos del modelo de datos para especificar cómo se completará el modelo de datos con los datos de la aplicación en tiempo de ejecución.

1. En la página **Diseñador de asignación de modelo**, en el panel **Modelo de datos**, seleccione **CompanyName**.
2. En el panel **Orígenes de datos**, expanda **CompanyInfo** y después siga estos pasos:

    1. Expanda el nodo **CompanyInfo.find()** que representa el método **find()** de la tabla CompanyInfo.
    2. Seleccione **CompanyInfo.find().Name**.
    3. Seleccione **Enlazar** para completar el nombre de la empresa en la que se llama la asignación de modelo configurada en el contexto de tiempo de ejecución.

3. En el panel **Modelo de datos**, seleccione **Cuestionario**.
4. En el panel **Orígenes de datos**, seleccione **Cuestionario** y, a continuación, seleccione **Enlazar** para rellenar los registros de cuestionario.
5. En el panel **Modelo de datos**, expanda **Cuestionario** y después siga estos pasos:

    1. En el panel **Modelo de datos**, seleccione **Activo**.
    2. En el panel **Modelo de datos**, seleccione **Editar**.
    3. En el campo **Fórmula**, introduzca **Helper.NoYesEnumToString (\@.Active = EnumAppNoYes.Yes)** para completar el resultado dependiente del texto y del idioma de la comparación entre los valores de enumeración.

6. Continúe enlazando orígenes de datos a campos del modelo de datos de la misma manera hasta que obtenga el siguiente resultado.

    | Ruta de acceso de campo                                              | Tipo de datos   | Acción | Expresión de enlace |
    |---------------------------------------------------------|-------------|--------|--------------------|
    | CompanyName                                             | Cadena      | Enlazar   | CompanyInfo.'find()'.Name |
    | Cuestionarios                                           | Lista de registros | Enlazar   | Cuestionarios |
    | Questionnaire\\Active                                   | Cadena      | Editar   | Helper.NoYesEnumToString(\@.active = EnumAppNoYes.Yes) |
    | Questionnaire\\Code                                     | Cadena      | Enlazar   | \@.kmCollectionId |
    | Questionnaire\\Description                              | Cadena      | Enlazar   | \@.Description |
    | Questionnaire\\QuestionnaireType                        | Cadena      | Enlazar   | \@.'&gt;Relations'.kmCollectionTypeId.Description |
    | Questionnaire\\QuestionOrder                            | Cadena      | Editar   | CASE (\@.questionMode,<br>EnumAppQuestionOrder.Conditional, "Condicional",<br>EnumAppQuestionOrder.Random, "Aleatorio (porcentaje en cuestionario)",<br>EnumAppQuestionOrder.RandomGroup, "Aleatorio (porcentaje en grupos de resultados)",<br>EnumAppQuestionOrder.Sequence, "Secuencial",<br>"") |
    | Questionnaire\\ResultsGroup                             | Grabar      |        | |
    | Questionnaire\\ResultsGroup\\Code                       | Cadena      | Enlazar   | \@.'\$ResultGroup'.kmQuestionResultGroupId |
    | Questionnaire\\ResultsGroup\\Description                | Cadena      | Enlazar   | \@.'\$ResultGroup'.description |
    | Questionnaire\\ResultsGroup\\MaxNumberOfPoints          | Real        | Enlazar   | \@.'\$ResultGroup'.maxPoint |
    | Questionnaire\\Question                                 | Lista de registros | Enlazar   | \@.'&lt;Relations'.KMCollectionQuestion |
    | Questionnaire\\Question\\CollectionSequenceNumber       | Entero     | Enlazar   | \@.answerCollectionSequenceNumber |
    | Questionnaire\\Question\\Id                             | Cadena      | Enlazar   | \@.kmQuestionId |
    | Questionnaire\\Question\\MustBeCompleted                | Cadena      | Editar   | Helper.NoYesEnumToString(\@.mandatory = EnumAppNoYes.Yes) |
    | Questionnaire\\Question\\PrimaryQuestion                | Cadena      | Enlazar   | \@.parentQuestionId |
    | Questionnaire\\Question\\SequenceNumber                 | Entero     | Enlazar   | \@.SequenceNumber |
    | Questionnaire\\Question\\Text                           | Cadena      | Enlazar   | \@.'\$Question'.text |
    | Questionnaire\\Question\\Answer                         | Lista de registros | Enlazar   | \@.'\$Question'.'\$Answer' |
    | Questionnaire\\Question\\Answer\\CorrectAnswer          | Cadena      | Editar   | Helper.NoYesEnumToString(\@.correctAnswer = EnumAppNoYes.Yes) |
    | Questionnaire\\Question\\Answer\\Points                 | Real        | Enlazar   | \@.point |
    | Questionnaire\\Question\\Answer\\SequenceNumber         | Entero     | Enlazar   | \@.sequenceNumber |
    | Questionnaire\\Question\\Answer\\Text                   | Cadena      | Enlazar   | \@.text |

    La siguiente ilustración muestra el estado final de la asignación del modelo configurado en la página **Diseñador de asignación de modelo**.

    ![Asignación de datos totalmente configurada en el diseñador de asignación de modelo de ER](./media/er-quick-start1-mapping2.png)

7. Guarde los cambios.
8. Cierre la página **Diseñador de distribución del modelo**.

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping"></a>Completar el diseño de la asignación del modelo

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuración, seleccione **Asignación de cuestionario**.
3. En la ficha desplegable **Versiones**, seleccione la versión de configuración que tenga un estado de **Borrador**.
4. Seleccione **Cambiar estado** \> **Completada**.

El estado de la versión 1.1 de esta configuración cambia de **Borrador** a **Completada**. La versión 1.1 ya no se puede cambiar. Esta versión contiene la asignación de modelo configurada y se puede utilizar como la base de otras configuraciones de informes electrónicos. Se crea la versión 1.2 de esta configuración y tiene un estado de **Borrador**. Puede editar esta versión para ajustar la configuración **Asignación de cuestionario**.

![Versiones de la configuración de ER editable en la página Configuraciones](./media/er-quick-start1-mapping-configuration.png)

> [!NOTE]
> La asignación de modelo configurada es su implementación específica de Finance del modelo de datos abstracto que representa el dominio empresarial **Cuestionario**.

## <a name="design-a-template-for-a-custom-report"></a><a name="DesignReportTemplate"></a>Diseñar una plantilla para un informe personalizado

El marco de ER usa plantillas de documento predefinidas para generar informes con formatos de Microsoft Office (libros de Excel o documentos de Word). Mientras se genera el informe requerido, se rellena una plantilla con los datos necesario de acuerdo con el flujo de datos configurado. Por lo tanto, primero debe diseñar una plantilla para su informe personalizado. Esta plantilla debe diseñarse como un libro de Excel, cuya estructura representa el diseño de un informe personalizado. Debe asignar nombre a todos los elementos de Excel que planea completar con los datos requeridos.

1. Descargue el archivo [Questionnaires report template.xslx](https://go.microsoft.com/fwlink/?linkid=851448) y guárdelo en su equipo local.
2. Abra el archivo en Excel y revise la estructura del libro.

Como muestra la siguiente ilustración, la plantilla descargada ha sido diseñada para imprimir cuestionarios específicos que presentan las preguntas de un cuestionario junto con las respuestas adecuadas.

![Plantilla de Excel para imprimir cuestionarios específicos](./media/er-quick-start1-template-layout.png)

Se han agregado nombres de Excel a esta plantilla para completar los detalles del cuestionario. Puede utilizar el Administrador de nombres para revisar los nombres de Excel.

![Uso del Administrador de nombres para revisar los nombres de Excel en la plantilla de Excel proporcionada](./media/er-quick-start1-template-names.png)

Se han agregado etiquetas de informe como texto fijo en el idioma inglés. Puede reemplazar las etiquetas del informe con nuevos nombres de Excel que rellenen las etiquetas con texto dependiente del idioma con las [etiquetas](#AddMmLabels) de formato de ER, como lo hizo para las expresiones dependientes del idioma en la asignación de modelo configurada. En este caso, las etiquetas de ER deben agregarse con el formato de ER editable.

Como muestra la siguiente ilustración, se ha especificado el encabezado del informe personalizado para permitir que Excel realice la paginación.

![Encabezado de informe personalizado en la plantilla de Excel suministrada](./media/er-quick-start1-template-header.png)

## <a name="design-a-format"></a><a name="DesignFormat"></a>Diseñar un formato

Como usuario con el rol de Consultor funcional de informes electrónicos, debe crear una nueva configuración de ER que contenga un componente de [formato](general-electronic-reporting.md#FormatComponentOutbound). Debe configurar el componente de formato para especificar cómo debe rellenarse una plantilla de informe con los datos necesarios en tiempo de ejecución.

Al completar los pasos de la sección [Importar una configuración de formato diseñado](#FormatImport), puede importar el formato necesario desde el archivo XML suministrado. Como alternativa, puede completar los pasos de la sección [Crear una nueva configuración de formato](#FormatCreate) para diseñar este formato desde cero.

### <a name="import-a-designed-format-configuration"></a><a name="FormatImport"></a>Importar una configuración de formato diseñado

1. Descargue el archivo [Questionnaires format.version.1.1.xml](https://go.microsoft.com/fwlink/?linkid=851448) y guárdelo en su equipo local.
2. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
3. En el espacio de trabajo **Informes electrónico**, seleccione **Configuraciones de informes**.
4. En el panel de acciones, seleccione **Exchange** \> **Cargar desde un archivo XML**.
5. Seleccione **Examinar** y, a continuación, busque y seleccione el archivo **Questionnaires format.version.1.1.xml**.
6. Seleccione **Aceptar** para importar la configuración.

Para continuar, omita el siguiente procedimiento, [Crear una nueva configuración de formato](#FormatCreate).

### <a name="create-a-new-format-configuration"></a><a name="FormatCreate"></a>Creación de una configuración de formato nueva
 
1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuración, seleccione **Modelo de cuestionario**.
3. Seleccionar **Crear configuración**.
4. En el cuadro de diálogo desplegable, siga estos pasos:

    1. En el campo **Nuevo**, seleccione **Formato basado en cuestionarios de modelo de datos**.
    2. En el campo **Nombre**, escriba **Informe de cuestionario**.
    3. En el campo **Versión del modelo de datos**, seleccione **1**.

        > [!NOTE]
        > - Si selecciona una versión específica del modelo de datos base, la estructura de la versión correspondiente del modelo de datos se le presentará como la estructura del origen de datos **Modelo** con el formato creado.
        > - Este campo se puede dejar en blanco. En ese caso, la estructura de la versión **Borrador** del modelo de datos se le presentará como la estructura del origen de datos **Modelo** con el formato creado. Después puede ajustar el modelo y ver inmediatamente estos ajustes en el formato. Este enfoque puede mejorar la eficiencia del diseño de la solución de ER al configurar su modelo de datos, la asignación del modelo y el formato simultáneamente.
        > - Si selecciona una versión específica del modelo de datos base, puede pasar a usar la versión **Borrador** cuando empiece a editar un formato.

    4. En el campo **Definición del modelo de datos**, seleccione la definición **Root**.

5. Seleccione **Crear configuración** para crear la configuración.

#### <a name="import-a-report-template"></a><a name="ImportReportTemplate"></a>Importar una plantilla de informe

1. En la página **Configuraciones**, en el árbol de configuración, seleccione **Informe de cuestionario**.
2. Seleccione **Diseñador** para empezar a configurar un formato personalizado.
3. En la página **Diseñador de formato**, en el panel de acciones, seleccione **Importar** \> **Importar desde Excel**.
4. En el cuadro de diálogo, siga estos pasos:

    1. Seleccione **Agregar plantilla**.
    2. Busque y seleccione el archivo **Questionnaires report template.xslx** guardado localmente y, a continuación, seleccione **Abrir**.
    3. Seleccione **Aceptar** para importar la plantilla.

    ![Importar una plantilla de informe](./media/er-quick-start1-template-import.png)

El elemento de formato **Excel\\File** se agrega automáticamente al formato editable como elemento raíz. Además, el elemento de formato **Excel\\Range** o el elemento de formato **Excel\\Cell** se agregan automáticamente para cada nombre de Excel reconocido de la plantilla importada. El formato **Excel\\Header** con el elemento **String** anidado se agrega automáticamente para reflejar la configuración del encabezado de la plantilla importada.

![Estructura de formato que incluye automáticamente los elementos agregados en el diseñador de operaciones de ER](./media/er-quick-start1-template-import2.png)

#### <a name="configure-a-format"></a><a name="ConfigureFormat"></a>Configurar un formato

1. En la página **Diseñador de formato**, en el árbol de formato, seleccione el elemento raíz **Excel**.
2. En la pestaña **Formato** del lado derecho de la página, en el campo **Nombre**, introduzca <a name="AddFormatRootElement"></a>**Informe**.
3. En el campo **Preferencia de idioma**, seleccione **Preferencia del usuario** para ejecutar el informe en el idioma preferido del usuario.
4. En el campo **Preferencias culturales**, seleccione **Preferencia del usuario** para ejecutar el informe en la cultura preferida del usuario.

    Para obtener información sobre cómo especificar los contextos de idioma y cultura para un proceso de ER, consulte [Diseñar informes multilingües](er-design-multilingual-reports.md).

    ![Configurar las opciones de idioma y cultura para el informe diseñado en el diseñador de operaciones de ER](./media/er-quick-start1-template-format-structure1.png)

5. En el árbol de formato, expanda el nodo raíz y luego seleccione **ResultsGroup**.
6. En la pestaña **Formato**, en el campo **Dirección de replicación**, seleccione **Sin replicación**, ya que no espera tener varios grupos de resultados para un solo cuestionario.

    ![Definición de la dirección de replicación para los elementos de formato de rango en el diseñador de operaciones de ER](./media/er-quick-start1-template-format-structure2.png)

7. Seleccione **Guardar**.

#### <a name="define-the-data-binding-for-a-report-title"></a><a name="DefineFormatBindings"></a>Definir el enlace de datos para un título de informe

Debe especificar un enlace de datos para un elemento de formato que se utiliza para rellenar el título de un informe generado.

1. En la página **Diseñador de formato**, en la pestaña **Asignación** de la derecha, seleccione el elemento **Report\\ReportTitle**.
2. Seleccione **Editar fórmula**.
3. En el editor de fórmulas, seleccione **Traducir**.
4. En el cuadro de diálogo **Traducción de texto**, siga estos pasos:

    1. En el campo **Id. de etiqueta**, introduzca **ReportTitle**.
    2. En el campo **Texto en el idioma predeterminado**, introduzca **Informe de cuestionarios**.
    3. Seleccione **Traducir** y, a continuación, seleccione **Guardar**.
    4. Seleccione **Traducir** para cerrar el cuadro de diálogo **Traducción de texto**.

5. Cierre el editor de fórmulas.

    ![Configurar el enlace para completar el título de un informe generado](./media/er-quick-start1-add-report-title-label.png)

Puede utilizar esta técnica para hacer que todas las demás etiquetas de la plantilla actual dependan del idioma. Para obtener más información sobre cómo se pueden traducir las etiquetas agregadas de una única configuración de ER a todos los idiomas ofrecidos, consulte [Diseñar informes multilingües](er-design-multilingual-reports.md).

#### <a name="review-model-data-source"></a><a name="ReviewModelDataSource"></a>Revisar el origen de datos del modelo

1. En la página **Diseñador de formato**, en la pestaña **Asignación**, seleccione el origen de datos de <a name="ModelDSName"></a>**modelo**, que representa el modelo de datos base de este formato de ER.
2. Seleccione **Editar**.
3. Revise la información en el cuadro de diálogo **Propiedades del origen de datos**. Este origen de datos representa la versión 1 del componente del modelo de datos **Cuestionarios** que reside en la configuración de ER **Modelo de cuestionarios**.

![Propiedades del origen de datos de modelo en el diseñador de operaciones de ER](./media/er-quick-start1-model-data-source.png)

#### <a name="bind-format-elements-to-data-source-fields"></a><a name="BindFormatElements"></a>Enlazar elementos de formato a campos de origen de datos

Para especificar cómo se rellena una plantilla en tiempo de ejecución, debe vincular cada elemento de formato asociado con un nombre de Excel apropiado a un solo campo del origen de datos de este formato.

1. En la página **Diseñador de formato**, en el árbol de formato, seleccione el elemento de formato **Report\\CompanyName**.
2. En la pestaña **Asignación**, seleccione el campo de origen de datos **model.CompanyName** de tipo **Cadena**.
3. Seleccione **Enlazar** para introducir un nombre de empresa en una plantilla.
4. En el árbol de formato, seleccione el elemento **Report\\Questionnaire**.
5. En la pestaña **Asignación**, seleccione el campo de origen de datos **model.Questionnaire** de tipo **Lista de registros**.
6. Seleccione **Enlazar**.
7. Seleccione **Mostrar detalles** para ver más detalles de los elementos de formato.

    El elemento de formato de rango **Cuestionario** está configurado como replicado verticalmente. Cuando se enlaza a un origen de datos de tipo **Lista de registros**, el rango de **Cuestionario** apropiado de la plantilla de Excel se repite para cada registro del origen de datos enlazado.
 
    ![Enlazar el elemento de formato de rango de Cuestionario a los orígenes de datos de tipo lista de registros adecuados en el diseñador de operaciones de ER](./media/er-quick-start1-bindings1.png)

    Como el rango **Cuestionario** de la plantilla de Excel se define entre las filas 5 y 14, estas filas se repiten para cada cuestionario incluido en el informe.

    ![Filas de la plantilla de Excel que se repetirán en un informe generado para cada registro de los orígenes de datos de tipo lista de registros](./media/er-quick-start1-template-questionnaire-range.png)

8. Configure enlaces similares para los elementos de formato restantes, como se describe en la siguiente tabla.

    > [!NOTE]
    > En esta tabla, la información de la columna "Ruta del origen de datos" supone que la característica de ER [ruta relativa](relative-path-data-bindings-er-models-format.md) está activada.

    | Aplicar formato a ruta de elemento                                      | Ruta de origen de datos |
    |----------------------------------------------------------|------------------|
    | Excel\\ReportTitle                                       | **\@"GER\_LABEL:ReportTitle"** |
    | Excel\\CompanyName                                       | **model.CompanyName** |
    | Excel\\Questionnaire                                     | **model.Questionnaire** |
    | Excel\\Questionnaire\\Active                             | **\@.Active**, donde **\@** es **model.Questionnaire** |
    | Excel\\Questionnaire\\Code                               | **\@.Code** |
    | Excel\\Questionnaire\\Description                        | **\@.Description** |
    | Excel\\Questionnaire\\QuestionnaireType                  | **\@.QuestionnaireType** |
    | Excel\\Questionnaire\\QuestionOrder                      | **\@.QuestionOrder** |
    | Excel\\Questionnaire\\ResultsGroup\\Code\_               | **\@.ResultsGroup.Code** |
    | Excel\\Questionnaire\\ResultsGroup\\Description\_        | **\@.ResultsGroup.Description** |
    | Excel\\Questionnaire\\ResultsGroup\\MaxNumberOfPoints    | **\@.ResultsGroup.MaxNumberOfPoint** |
    | Excel\\Questionnaire\\Question                           | **\@.Question** |
    | Excel\\Questionnaire\\Question\\CollectionSequenceNumber | **\@.CollectionSequenceNumber**, donde **\@** es **model.Questionnaire.Question** |
    | Excel\\Questionnaire\\Question\\Id                       | **\@.Id** |
    | Excel\\Questionnaire\\Question\\MustBeCompleted          | **\@.MustBeCompleted** |
    | Excel\\Questionnaire\\Question\\PrimaryQuestion          | **\@.PrimaryQuestion** |
    | Excel\\Questionnaire\\Question\\SequenceNumber           | **\@.SequenceNumber** |
    | Excel\\Questionnaire\\Question\\Text                     | **\@.Text** |
    | Excel\\Questionnaire\\Question\\Answer                   | **\@.Answer** |
    | Excel\\Questionnaire\\Question\\Answer\\CorrectAnswer    | **\@.CorrectAnswer**, donde **\@** es **model.Questionnaire.Answer** |
    | Excel\\Questionnaire\\Question\\Answer\\Points           | **\@.Points** |
    | Excel\\Questionnaire\\Question\\Answer\\Text             | **\@.Text** |

9. Cuando haya terminado, haga clic en **Guardar**.

La siguiente ilustración muestra el estado final de los enlaces de datos configurados en la página **Diseñador de formato**.

![Enlaces de datos configurados en el diseñador de operaciones de ER](./media/er-quick-start1-bindings2.png)

> [!IMPORTANT]
> Toda la colección de orígenes de datos y enlaces especificados representa un componente de asignación de formato del formato configurado. Se llama a esta asignación de formato cuando se ejecuta el formato configurado para la generación de informes.

### <a name="run-a-designed-format-from-er"></a><a name="RunFormatFromER"></a>Ejecutar un formato diseñado a partir de un informe electrónico

Ahora puede ejecutar un formato diseñado con fines de prueba desde la página **Configuraciones**.

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuración**, en el árbol de configuración, expanda **Modelo de cuestionario** y seleccione **Informe de cuestionario**.
3. Seleccione **Diseñador** para la versión de formato que tiene el estado **Borrador**.
4. En la página **Diseñador de formato**, seleccione **Ejecutar**.
5. En el cuadro de diálogo **Parámetros de ER**, en la ficha desplegable **Registros para incluir**, configure la opción de filtrado de forma que solo se incluya el cuestionario **SBCCrsExam**.
6. Seleccione **Aceptar** para confirmar la opción de filtrado.
7. Seleccione **Aceptar** para ejecutar el informe.
8. Revise el informe generado.

De forma [predeterminada](electronic-reporting-destinations.md#default-behavior), se entrega un informe generado como un archivo de Excel que se puede descargar. Las siguientes ilustraciones muestran dos páginas del informe generado con formato Excel.

![Ejemplo de informe generado con formato Excel, página 1](./media/er-quick-start1-report1a.png)

![Ejemplo de informe generado con formato Excel, página 2](./media/er-quick-start1-report1b.png)

## <a name="tune-a-designed-format"></a><a name="TuneFormat"></a>Ajustar un formato diseñado

### <a name="modify-a-format-to-change-the-name-of-a-generated-document"></a><a name="ModifyToChangeName"></a>Modificar un formato para cambiar el nombre de un documento generado

De forma predeterminada, a un documento generado se le asigna como nombre el alias del usuario actual. Al modificar el formato, puede cambiar este comportamiento para que un documento generado reciba un nombre según su lógica personalizada. Por ejemplo, el nombre de un documento generado puede basarse en la fecha y hora de la sesión actual, y en el título del informe.

1. En la página **Diseñador de formato**, seleccione el elemento raíz **Report** .
2. En la pestaña **Asignación**, seleccione **Editar nombre de archivo**.
3. En el campo **Fórmula**, introduzca **CONCATENATE (\@"GER\_LABEL:ReportTitle", " - ", DATETIMEFORMAT(SESSIONNOW(), "yyyy-MM-dd hh-mm-ss"))**.
4. Seleccione **Guardar** y cierre el editor de fórmulas.
5. Seleccione **Guardar**.

### <a name="modify-a-format-to-change-the-order-of-questions"></a><a name="ModifyToOrder"></a>Modificar un formato para cambiar el orden de las preguntas

Las preguntas no están ordenadas correctamente en un informe generado. Puede cambiar el orden modificando el formato.

1. En la página **Diseñador de formato**, seleccione el elemento raíz **Report** .
2. En la pestaña **Asignación**, en el árbol de formato, expanda **Report\\Questionnaire\\Question**.

    ![Elemento de formato de pregunta del tipo Rango el diseñador de operaciones de ER](./media/er-quick-start1-bindings3.png)

3. En la pestaña **Asignación**, seleccione **model.Questionnaire**.
4. Seleccione **Agregar** \> **Functions\\Calculated field** y, a continuación, en el campo **Nombre**, introduzca **OrderedQuestions**.
5. Seleccione **Editar fórmula**.
6. En el editor de fórmulas, en el campo **Fórmula**, introduzca **ORDERBY (model.Questionnaire.Question, model.Questionnaire.Question.SequenceNumber)** para ordenar la lista de preguntas del cuestionario actual por el número de orden de la secuencia.
7. Seleccione **Guardar** y cierre el editor de fórmulas.
8. Seleccione **Aceptar** para completar la entrada de un nuevo campo calculado.
9. En la pestaña **Asignación**, seleccione **model.Questionnaire.OrderedQuestions**.
10. En el árbol de formato, seleccione **Excel\\Questionnaire\\Question**.
11. Seleccione **Enlazar** y, a continuación, confirme que la ruta **model.Questionnaire.Questions** actual se reemplaza por la nueva ruta **model.Questionnaire.OrderedQuestions** en todos los enlaces de elementos anidados.
12. Seleccione **Guardar**.

![Vincular el elemento de formato de pregunta al origen de datos OrderedQuestions configurado en el diseñador de operaciones de ER](./media/er-quick-start1-bindings4.png)

### <a name="run-a-modified-format-from-er"></a><a name="RunFormatFromER2"></a>Ejecutar un formato modificado a partir de un informe electrónico

Ahora puede ejecutar un formato modificado con fines de prueba desde el marco de ER.

1. En la página **Diseñador de formato**, seleccione **Ejecutar**.
2. En el cuadro de diálogo **Parámetros de ER**, en la ficha desplegable **Registros para incluir**, configure la opción de filtrado de forma que solo se incluya el cuestionario **SBCCrsExam**.
3. Seleccione **Aceptar** para confirmar la opción de filtrado.
4. Seleccione **Aceptar** para ejecutar el informe.
5. Revise el informe generado.

La siguiente ilustración muestra un informe generado en formato Excel donde las preguntas están correctamente ordenadas.

![Informe generado en formato Excel que tiene preguntas ordenadas correctamente](./media/er-quick-start1-report2.png)

### <a name="complete-the-format-design"></a><a name="CompleteFormat"></a>Completar el diseño del formato

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuración, expanda **Modelo de cuestionario** y seleccione **Informe de cuestionario**.
3. En la ficha desplegable **Versiones**, seleccione la versión de configuración que tenga un estado de **Borrador**.
4. Seleccione **Cambiar estado** \> **Completada**.

El estado de la versión 1.1 de esta configuración cambia de **Borrador** a **Completada**. La versión 1.1 ya no se puede cambiar. Esta versión contiene el formato configurado y se puede utilizar para imprimir su informe personalizado. Se crea la versión 1.2 de esta configuración y tiene un estado de **Borrador**. Puede editar esta versión con el fin de ajustar el formato del informe **Questionnaire**.

![Versiones de la configuración de ER editable en la página Configuraciones](./media/er-quick-start1-format-configuration.png)

> [!NOTE]
> El formato configurado es su diseño del informe **Questionnaire** y no contiene ninguna relación con los artefactos específicos de Finance.

## <a name="develop-application-artefacts-to-call-the-designed-report"></a><a name="DevelopCustomCode"></a>Desarrollar artefactos de aplicación para llamar al informe diseñado

Como usuario con el rol de administrador del sistema, debe desarrollar una nueva lógica para que el formato de ER configurado se pueda llamar desde la interfaz de usuario de la aplicación para generar su informe personalizado. Actualmente, ER no ofrece ninguna capacidad para configurar este tipo de lógica. Por lo tanto, se requiere algún trabajo de ingeniería. 

Para desarrollar la nueva lógica debe implementar una topología que permita la compilación continua. Para obtener más información, consulte [Implementar topologías que admiten la automatización continua de la compilación y la prueba](../perf-test/continuous-build-test-automation.md). También debe tener acceso al entorno de desarrollo para esta topología. Para obtener más información sobre la API de ER disponible, consulte [API del marco de ER](er-apis-app73.md).

### <a name="modify-source-code"></a><a name="ModifySourceCode"></a>Modificación de código de origen

#### <a name="add-a-data-contract-class"></a><a name="DataContractClass"></a>Agregar una clase de contrato de datos

Agregue la nueva clase **QuestionnairesErReportContract** a su proyecto de Microsoft Visual Studio y escriba el código que especifique el contrato de datos que se debe utilizar para ejecutar el formato de ER configurado.

```xpp
/// <summary>
///     This class is the data contract class for the <c>QuestionnairesErReportDP</c> class.
/// </summary>
/// <remarks>
///    This is the data contract class for the Questionnaires ER report.
/// </remarks>
[
    DataContractAttribute,
    SysOperationContractProcessingAttribute(classStr(QuestionnairesErReportUIBuilder))
    ]
    public class QuestionnairesErReportContract extends ERFormatMappingRunBaseContract implements SysOperationValidatable
{
    ERFormatMappingId formatMapping;

    /// <summary>
    ///    Validates the report parameters.
    /// </summary>
    /// <returns>
    ///    true if no errors; otherwise, false.
    /// </returns>
    public boolean validate()
    {
        boolean ret = true;
        if (!formatMapping)
        {
            ret = checkFailed(strFmt("@SYS26332", new SysDictType(extendedTypeNum(ERFormatMappingId)).label()));
        }
        return ret;
    }
    [
        DataMemberAttribute('FormatMapping'),
        SysOperationLabelAttribute(literalstr("@ElectronicReporting:FormatMapping")),
        SysOperationHelpTextAttribute(literalstr("@ElectronicReporting:FormatMapping"))
    ]
    public ERFormatMappingId parmFormatMapping(ERFormatMappingId _formatMapping = formatMapping)
    {
        formatMapping = _formatMapping;
        return formatMapping;
    }
}
```

#### <a name="add-a-ui-builder-class"></a><a name="UIBuilderClass"></a>Agregar una clase de generador de interfaz de usuario

Agregue la nueva clase **QuestionnairesErReportUIBuilder** a su proyecto de Visual Studio y escriba el código necesario para generar un cuadro de diálogo en tiempo de ejecución que se utilizará para buscar el id. de asignación del formato de ER que hay que ejecutar. El código suministrado solo busca formatos de ER que contienen un origen de datos de tipo **Modelo de datos** que hace referencia al modelo de datos **[Questionnaires](#DataModeName)** a través de la definición de **[Root](#RootDefinitionName)**.

> [!NOTE]
> Como alternativa, puede utilizar puntos de integración de ER para filtrar formatos de ER. Para obtener más información, consulte [API para mostrar una búsqueda de asignación de formato](er-apis-app10-0-11.md#api-to-show-a-format-mapping-lookup).

```xpp
/// <summary>
/// The UIBuilder class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportUIBuilder extends SysOperationAutomaticUIBuilder
{
    public const str ERQuestionnairesModel = 'Questionnaires';
    public const str ERQuestionnairesDataContainer = 'Root';

    /// <summary>
    /// Action after build of the dialog UI.
    /// </summary>
    public void postBuild()
    {
        DialogField formatMapping;
        super();
        formatMapping = this.bindInfo().getDialogField(this.dataContractObject(),
            methodStr(QuestionnairesErReportContract, parmFormatMapping));
        formatMapping.registerOverrideMethod(
            methodStr(FormReferenceControl, lookupReference),
            methodStr(QuestionnairesErReportUIBuilder, formatMappingLookup),
            this);
    }

    /// <summary>
    /// Performs the lookup form for format mapping.
    /// </summary>
    /// <param name="_referenceGroupControl">
    /// The control to perform lookup form.
    /// </param>
    public void formatMappingLookup(FormReferenceControl _referenceGroupControl)
    {
        ERObjectsFactory::createFormatMappingTableLookupForControlAndModel(
            _referenceGroupControl,
            ERQuestionnairesModel,
            ERQuestionnairesDataContainer).performFormLookup();
    }
}
```

#### <a name="add-a-data-provider-class"></a><a name="DataProviderClass"></a>Agregar una clase de proveedor de datos

Agregue la nueva clase **QuestionnairesErReportDP** a su proyecto de Visual Studio y escriba el código para introducir el proveedor de datos que se debe utilizar para ejecutar el formato de ER configurado. El código suministrado solo incluye el contrato de datos para este proveedor de datos.

```xpp
/// <summary>
/// Data provider class for Questionnaires ER report.
/// </summary>
public class QuestionnairesErReportDP
{
    QuestionnairesErReportContract contract;
    public static QuestionnairesErReportDP construct()
    {
        QuestionnairesErReportDP  dataProvider;
        dataProvider = new QuestionnairesErReportDP();
        return dataProvider;
    }
}
```

#### <a name="add-a-labels-file"></a><a name="LabelsFile"></a>Agregar un archivo de etiquetas

Agregue el nuevo archivo de etiquetas **QuestionnairesErReportLabels\_en-US** a su proyecto de Visual Studio y especifique las siguientes etiquetas para nuevos recursos de interfaz de usuario:

- La etiqueta **\@QuestionnairesReport** para un nuevo elemento de menú que contiene el siguiente texto en inglés de EE.UU. (en-US): **Questionnaires report (powered by ER)**
- La etiqueta **\@QuestionnairesReportBatchJobDescription** para un título de trabajo por lotes si un formato de ER seleccionado está programado para su ejecución como trabajo por lotes

#### <a name="add-a-report-service-class"></a><a name="ServiceClass"></a>Agregar una clase de servicio de informes

Agregue la nueva clase **QuestionnairesErReportService** a su proyecto de Visual Studio y escribe el código necesario para llamar a un formato de ER, identificarlo mediante un id. de asignación y proporcionar un contrato de datos como parámetro.

```xpp
using Microsoft.Dynamics365.LocalizationFramework;
/// <summary>
/// The electronic reporting service class for Questionnaires ER report
/// </summary>
class QuestionnairesErReportService extends SysOperationServiceBase
{
    public const str ERModelDataSourceName = 'model';
    public const str DefaultExportedFileName = 'Questionnaires report';
    public const str ParametersDataSourceName = 'RunTimeParameters';

    /// <summary>
    /// Generates report by using Electronic reporting framework
    /// </summary>
    /// <param name = "_contract">The Questionnaires report contract</param>
    public void generateReportByGER(QuestionnairesErReportContract _contract)
    {
        ERFormatMappingId formatMappingId;
        QuestionnairesErReportDP  dataProvider;
        dataProvider = QuestionnairesErReportDP::construct();
        formatMappingId = _contract.parmFormatMapping();
        if (formatMappingId)
        {
            try
            {
                ERIModelDefinitionParamsAction parameters = new ERModelDefinitionParamsUIActionComposite()
                    .add(new ERModelDefinitionObjectParameterAction(ERModelDataSourceName, ParametersDataSourceName, _contract, true));

                // Call ER to generate the report.
                ERIFormatMappingRun formatMappingRun = ERObjectsFactory::createFormatMappingRunByFormatMappingId(formatMappingId, DefaultExportedFileName);
                if (formatMappingRun.parmShowPromptDialog(true))
                {
                    formatMappingRun.withParameter(parameters);
                    formatMappingRun.withFileDestination(_contract.getFileDestination());
                    formatMappingRun.run();
                }
            }
            catch
            {
                // An error occurred while exporting data.
                error("@SYP4861341");
            }
        }
        else
        {
            // There is no data available.
            info("@SYS300117");
        }
    }
}
```

Cuando tiene que utilizar un formato de ER que ejecuta datos de aplicaciones, debe configurar un origen de datos de tipo **Modelo de datos** con la asignación de formato. Este origen de datos se refiere a una parte concreta del modelo de datos especificado mediante el uso de una única definición de raíz. Cuando se ejecuta el formato de ER, llama a este origen de datos para acceder a la asignación del modelo de ER apropiado que está configurado para una definición de modelo y raíz determinada.

Toda la información que pueda preparar en el código fuente y almacenar como parte del contrato de datos se puede pasar al formato de ER en ejecución mediante una asignación de modelo de ER de este tipo. En la asignación del modelo de ER, debe configurar un origen de datos de tipo **Objeto** que haga referencia a la clase **[QuestionnairesErReportContract](#DataContractClass)**. Para identificar una asignación de modelo, debe especificar un origen de datos que llame a esta asignación de modelo. En el código suministrado, este origen de datos se especifica con la constante **ERModelDataSourceName** que tiene el valor de **[modelo](#ModelDSName)**. Para identificar qué origen de datos se utiliza para exponer el contrato de datos en la asignación de modelo, debe especificar un nombre de origen de datos. En el código suministrado, este nombre se especifica con la constante **ParametersDataSourceName** que tiene el valor <a name="DataContractDSName"></a>**RunTimeParameters**.

> [!NOTE]
> En un entorno nuevo, es posible que tenga que actualizar los metadatos de ER para que este tipo de clase esté disponible en el diseñador de asignación de modelo de ER. Para obtener más información, consulte [Configurar el marco de informes electrónicos (ER)](electronic-reporting-er-configure-parameters.md#frequently-asked-questions).

#### <a name="add-a-report-controller-class"></a><a name="ControllerClass"></a>Agregar una clase de controlador de informes

Agregue la nueva clase **QuestionnairesErReportController** a tu proyecto de Visual Studio y escriba código para ejecutar un formato de ER en modo sincrónico o en modo por lotes (como prefiera) en el cuadro de diálogo que se crea en base a la lógica de la clase **QuestionnairesErReportUIBuilder**.

```xpp
/// <summary>
/// The controller for Questionnaires ER report
/// </summary>
class QuestionnairesErReportController extends ERFormatMappingRunBaseController
{
    /// <summary>
    /// The main entrance of the controller
    /// </summary>
    /// <param name = "args">The arguments</param>
    public static void main(Args args)
    {
        QuestionnairesErReportController operation;
        operation = new QuestionnairesErReportController(
            classStr(QuestionnairesErReportService),
            methodStr(QuestionnairesErReportService, generateReportByGER),
            SysOperationExecutionMode::Synchronous);
        operation.startOperation();
    }

    /// <summary>
    /// Gets caption of the dialog.
    /// </summary>
    /// <returns>Caption of the dialog</returns>
    public ClassDescription defaultCaption()
    {
        ClassDescription batchDescription;
        batchDescription = "Questionnaires report (powered by ER)";
        return batchDescription;
    }
}
```

#### <a name="add-a-menu-item"></a><a name="MenuItem"></a>Agregar un elemento de menú

Agregue el nuevo elemento de menú **QuestionnairesErReport** a su proyecto de Visual Studio. En la propiedad **Objeto**, este elemento de menú se refiere a la clase **QuestionnairesErReportController** y se usa para especificar un permiso de usuario para seleccionar y ejecutar un formato de ER. En la propiedad **Etiqueta**, este elemento de menú se refiere a la etiqueta **\@QuestionnairesReport** que creó anteriormente, para que se presente el texto correcto en la interfaz de usuario de la aplicación.

#### <a name="add-a-menu-item-to-a-menu"></a><a name="Menu"></a>Agregar un elemento de menú a un menú

Agregue el menú **KM** existente a su proyecto de Visual Studio. Debe agregar un nuevo elemento **QuestionnairesErReport** de tipo **Salida** a este menú. Este elemento debe hacer referencia al elemento de menú **QuestionnairesErReport** descrito en la sección anterior.

#### <a name="build-a-visual-studio-project"></a><a name="BuildVSProject"></a>Compilar un proyecto de Visual Studio

Cree su proyecto para hacer que un nuevo elemento de menú esté disponible para los usuarios.

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp"></a>Ejecutar un formato desde la aplicación

1. Vaya a **Cuestionario** \> **Diseño** \> **Questionnaires report (powered by ER)**.

    ![Seleccionar el elemento de menú Questionnaires report (powered by ER) en el módulo Questionnaire para ejecutar el formato de ER configurado](./media/er-quick-start1-application-menu-modified.png)

2. En el cuadro de diálogo, en el campo **Asignación de formato**, seleccione **Informe de cuestionarios**.
3. Seleccione **Aceptar**.
4. En el cuadro de diálogo **Parámetros de informe electrónico**, en la ficha desplegable **Registros que incluir**, configure la opción de filtrado de forma que solo se incluya el cuestionario **SBCCrsExam**.
5. Seleccione **Aceptar** para confirmar la opción de filtrado.
6. Seleccione **Aceptar** para ejecutar el informe.

    ![Especificar los criterios de selección en el cuadro de diálogo Informe electrónico](./media/er-quick-start1-report-run-dialog-page.png)

7. Revise el informe generado.

## <a name="tune-a-designed-er-solution"></a><a name="TuneSolution"></a>Ajustar una solución de informes electrónicos diseñada

Puede modificar la solución de ER configurada para que utilice la clase de proveedor de datos que desarrolló con el fin de acceder a los detalles del formato de ER en ejecución y para que introduzca el nombre de este formato de ER en un informe generado.

### <a name="modify-a-model-mapping"></a><a name="ModifyModelMapping"></a>Modificar una asignación de modelo

#### <a name="add-data-sources-to-access-a-data-contract-object"></a><a name="AddDataSource1"></a>Agregar orígenes de datos para acceder al objeto de contrato de datos

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuración, expanda **Modelo de cuestionario** y seleccione **Asignación de cuestionario**.
3. Seleccione **Diseñador** para abrir la página **Asignación de modelo a origen de datos**.
4. Seleccione **Diseñador** para abrir la asignación seleccionada en el diseñador de asignación de modelo.
5. En la página **Diseñador de asignación de modelo**, en el panel **Tipos de origen de datos**, seleccione **Dynamics 365 for Operations\\Objeto**.
6. En el panel **Orígenes de datos**, seleccione **Agregar raíz**.
7. En el cuadro de diálogo, en el campo **Nombre**, introduzca **[RunTimeParameters](#DataContractDSName)**, como se define en el código fuente de la clase **QuestionnairesErReportService**.
8. En el campo **Clase**, introduzca **[QuestionnairesErReportContract](#DataContractClass)**, que se programó anteriormente.
9. Seleccione **Aceptar**.
10. Expanda **RunTimeParameters**.

El origen de datos agregado proporciona información sobre el id. de registro de la asignación de formato de ER en ejecución.

![Origen de datos agregado en el diseñador de asignación de modelo de ER](./media/er-quick-start1-mapping3.png)

#### <a name="add-a-data-source-to-access-er-format-mapping-records"></a><a name="AddDataSource2"></a>Agregar un origen de datos para acceder a registros de asignación de formato de informe electrónico

Para continuar, edite la asignación del modelo seleccionado agregando un origen de datos para acceder a los registros de asignación de formato de ER.

1. En la página **Diseñador de asignación de modelo**, en el panel **Tipos de origen de datos**, seleccione **Dynamics 365 for Operations\\Registros de tabla**.
2. En el panel **Orígenes de datos**, seleccione **Agregar raíz**.
3. En el cuadro de diálogo, en el campo **Nombre**, escriba **ER1**.
4. En el campo **Tabla**, escriba **ERFormatMappingTable**.
5. Seleccione **Aceptar**.

#### <a name="add-a-data-source-to-access-a-format-mapping-record-of-a-running-er-format"></a><a name="AddDataSource3"></a>Agregar un origen de datos para acceder a un registro de asignación de formato de un formato de informe electrónico en ejecución

Para continuar, edite la asignación del modelo seleccionado agregando un origen de datos para acceder al registro de asignación de formato del formato de ER en ejecución.

1. En la página **Diseñador de asignación de modelo**, en el panel **Tipos de origen de datos**, seleccione **Functions\\Calculated field**.
2. En el panel **Orígenes de datos**, seleccione **Agregar raíz**.
3. En el cuadro de diálogo, en el campo **Nombre**, escriba **ER2**.
4. Seleccione **Editar fórmula**.
5. En el editor de fórmulas, en el campo **Fórmula**, introduzca **FIRSTORNULL (FILTER(ER1, ER1.RecId = RunTimeParameters.parmFormatMapping))**.
6. Seleccione **Guardar** y cierre el editor de fórmulas.
7. Seleccione **Aceptar**.

#### <a name="enter-the-name-of-the-running-er-format-in-the-data-model"></a><a name="AddBinding"></a>Introducir en el modelo de datos el nombre del formato de informe electrónico en ejecución

Para continuar, edite la asignación del modelo seleccionado de forma que se introduzca el nombre del formato de ER en ejecución en el modelo de datos.

1. En la página **Diseñador de asignación de modelo**, en el panel **Modelo de datos**, expanda **ExecutionContext** y después seleccione **ExecutionContext\\FormatName**.
2. En el panel **Modelo de datos**, seleccione **Editar** para configurar un enlace de datos para el campo del modelo de datos seleccionado.
3. En el editor de fórmulas, en el campo **Fórmula**, introduzca **FIRSTORNULL (ER2.'\>Relations'.Format).Name**.
4. Seleccione **Guardar** y cierre el editor de fórmulas.

Como utilizó el campo **FormatName**, ahora la asignación de modelo configurada expone el nombre de un formato de ER que llama a esta asignación de modelo durante la ejecución.

![Enlazar el campo del modelo de datos al método del origen de datos agregado en el diseñador de asignación de modelo de ER](./media/er-quick-start1-mapping4.png)

#### <a name="complete-the-design-of-the-model-mapping"></a><a name="CompleteModelMapping2"></a>Completar el diseño de la asignación del modelo

1. En la página **Diseñador de asignación de modelo**, seleccione **Guardar**.
2. Cierre la página.
3. Cierre la página de asignaciones de modelo.
4. En la página **Configuraciones**, en el árbol de configuración, asegúrese de que la configuración **Asignación de cuestionario** sigue seleccionada. A continuación, en la ficha desplegable **Versiones**, seleccione la versión de configuración que tiene el estado **Borrador**.
5. Seleccione **Cambiar estado** \> **Completada**.

El estado de la versión 1.2 de esta configuración cambia de **Borrador** a **Completada**. La versión 1.2 ya no se puede cambiar. Esta versión contiene la asignación de modelo configurada y se puede utilizar como la base de otras configuraciones de informes electrónicos. Se crea la versión 1.3 de esta configuración y tiene un estado de **Borrador**. Puede editar esta versión para ajustar la asignación de modelo **Questionnaire**.

### <a name="modify-a-format"></a><a name="ModifyFormat"></a>Modificar un formato

Puede modificar el formato de ER configurado de forma que su nombre se muestre en el pie de página de un informe que se genera cuando se ejecuta el formato de ER.

#### <a name="add-a-new-format-element"></a><a name="AddFormatElement"></a>Agregar un nuevo elemento de formato

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuración, expanda **Modelo de cuestionario** y seleccione **Informe de cuestionario**.
3. Seleccione **Diseñador**.
4. En la página **Diseñador de formato**, seleccione el elemento raíz **Report** .
5. Seleccione **Agregar** para agregar un nuevo elemento de formato anidado para el elemento raíz **Report** seleccionado.
6. Seleccione **Excel\\Footer**.
7. En el campo **Nombre**, especifique **Footer**.
8. Seleccione **Report\Footer** y seleccione **Agregar**.
9. Seleccione **Text\\String**.

#### <a name="bind-the-added-format-element"></a><a name="BindAddedFormatElement"></a>Enlazar el elemento de formato agregado

1. En la página **Diseñador de formato**, en la pestaña **Asignación**, para el elemento **Footer\\String** activo, seleccione **Editar fórmula**.
2. En el editor de fórmulas, en el campo **Fórmula**, introduzca **CONCATENATE ("\&C\&10", FORMAT("Generated by'\%1' ER solution", model.ExecutionContext.FormatName))**
3. Seleccione **Guardar** y cierre el editor de fórmulas.
4. Seleccione **Guardar**.

Ahora el formato configurado se ha modificado para que se introduzca su nombre en el pie de página de un informe generado mediante el elemento **Footer\\String**.

![Agregar el elemento de formato de pie de página al formato configurado en el diseñador de operaciones de ER](./media/er-quick-start1-template-format-structure3.png)

#### <a name="complete-the-format-design"></a><a name="CompleteFormat2"></a>Completar el diseño del formato

1. Cierre la página **Diseñador de formato**.
2. En la página **Configuraciones**, en el árbol de configuración, asegúrese de que la configuración **Informe de cuestionario** sigue seleccionada. A continuación, en la ficha desplegable **Versiones**, seleccione la versión de configuración que tiene el estado **Borrador**.
3. Seleccione **Cambiar estado** \> **Completada**.

El estado de la versión 1.2 de esta configuración cambia de **Borrador** a **Completada**. La versión 1.2 ya no se puede cambiar. Esta versión contiene el formato configurado y se puede utilizar como la base de otras configuraciones de informes electrónicos. Se crea la versión 1.3 de esta configuración y tiene un estado de **Borrador**. Puede editar esta versión para ajustar el informe **Questionnaire**.

### <a name="run-a-format-from-the-application"></a><a name="RunFormatFromApp2"></a>Ejecutar un formato desde la aplicación

1. Vaya a **Cuestionario** \> **Diseño** \> **Questionnaires report (powered by ER)**.
2. En el cuadro de diálogo, en el campo **Asignación de formato**, seleccione **Informe de cuestionarios**.
3. Seleccione **Aceptar**.
4. En el cuadro de diálogo **Parámetros de ER**, en la ficha desplegable **Registros para incluir**, configure la opción de filtrado de forma que solo se incluya el cuestionario **SBCCrsExam**.
5. Seleccione **Aceptar** para confirmar la opción de filtrado.
6. Seleccione **Aceptar** para ejecutar el informe.
7. Revise el informe generado con formato Excel.

Observe que el pie de página del informe generado contiene el nombre del formato de ER que se utilizó para generarlo.

![Informe generado con formato Excel](./media/er-quick-start1-report4.png)

### <a name="run-a-format-from-er"></a><a name="RunFormatFromER3"></a>Ejecutar un formato a partir de un informe electrónico

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2. En la página **Configuraciones**, en el árbol de configuración, expanda **Modelo de cuestionario** y seleccione **Informe de cuestionario**.
3. En el panel de acciones, haga clic en **Ejecutar**.
4. En el cuadro de diálogo **Parámetros de informe electrónico**, en la ficha desplegable **Registros que incluir**, configure la opción de filtrado de forma que solo se incluya el cuestionario **SBCCrsExam**.
5. Seleccione **Aceptar** para confirmar la opción de filtrado.
6. Seleccione **Aceptar** para ejecutar el informe.
7. Revise el informe generado con formato Excel.

Tenga en cuenta que el pie de página del informe generado no contiene el nombre del formato de ER que se utilizó para generarlo, ya que el objeto del contrato de datos no se pasó a la asignación de modelo en ejecución cuando lo llamó el formato de ER que se ejecutó desde ER.

### <a name="configure-a-format-destination-for-on-screen-preview"></a><a name="ConfigureDestination"></a>Configurar un destino de formato para una vista previa en pantalla

1. Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Destino de informes electrónicos**.
2. En la página **Destino de informes electrónicos**, agregue un registro de destino para el formato de ER **Informe de cuestionario** configurado.
3. En la ficha desplegable **Destino de archivo**, configure el [destino](er-destination-type-screen.md) de **Pantalla** para el componente de formato **Report** que se ha [agregado](#AddFormatRootElement) como el elemento raíz del formato de ER **Informe de cuestionario** configurado.
4. En la ficha desplegable **Configuración de conversión de PDF**, configure el destino para convertir un informe al [formato PDF](electronic-reporting-destinations.md#OutputConversionToPDF) que usa la orientación de página **Horizontal**.

![Configurar el destino de pantalla personalizado para el formato de ER en la página de destino de informes electrónicos](./media/er-quick-start1-destination.png)

### <a name="run-a-format-from-the-application-to-preview-it-as-a-pdf-document"></a><a name="RunFormatFromApp3"></a>Ejecutar un formato desde la aplicación para obtener una vista previa como un documento PDF

1. Vaya a **Cuestionario** \> **Diseño** \> **Questionnaires report (powered by ER)**.
2. En el cuadro de diálogo, en el campo **Asignación de formato**, seleccione **Informe de cuestionarios**.
3. Seleccione **Aceptar**.
4. En el cuadro de diálogo **Parámetros de informe electrónico**, en la ficha desplegable **Registros que incluir**, configure la opción de filtrado de forma que solo se incluya el cuestionario **SBCCrsExam**.
5. Seleccione **Aceptar** para confirmar la opción de filtrado.

    En la ficha desplegable **Destinos**, observe que el campo **Salida** está establecido en **Pantalla**. Si desea cambiar el destino configurado, seleccione **Cambiar**.

    ![Cuadro de diálogo de tiempo de ejecución de informe de ER en el que puede cambiar el destino configurado](./media/er-quick-start1-run-settings.png)

6. Seleccione **Aceptar** para ejecutar el informe.
7. Revise el informe generado con formato PDF.

    ![Vista previa en pantalla del informe generado con formato PDF](./media/er-quick-start1-preview-PDF.png)

## <a name="additional-resources"></a><a name="References"></a>Recursos adicionales

- [Visión general de los informes electrónicos](general-electronic-reporting.md)
- [Idioma de fórmulas en los informes electrónicos](er-formula-language.md)
- [Diseñar informes multilingües](er-design-multilingual-reports.md)
- [API de marco de informes electrónicos](er-apis-app73.md)
- [Función CASE](er-functions-logical-case.md)
- [Función CONCATENATE](er-functions-text-concatenate.md)
- [Función DATETIMEFORMAT](er-functions-datetime-datetimeformat.md)
- [Función FILTER](er-functions-list-filter.md)
- [Función FIRSTORNULL](er-functions-list-firstornull.md)
- [Función FORMAT](er-functions-text-format.md)
- [Función IF](er-functions-logical-if.md)
- [Función ORDERBY](er-functions-list-orderby.md)
- [Función SESSIONNOW](er-functions-datetime-sessionnow.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]