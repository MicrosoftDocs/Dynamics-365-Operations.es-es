---
title: Configurar asignaciones de modelos de informes electrónicos dependientes del contexto del país
description: Este artículo explica cómo puede configurar asignaciones de modelo de ER de modo que dependen del contexto del país o región de la entidad jurídica que controla su uso.
author: NickSelin
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.2
ms.openlocfilehash: 771b14662638838ac1f39d85b19ac58a47352c79
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883886"
---
# <a name="configure-country-context-dependent-er-model-mappings"></a>Configurar las asignaciones del modelo de ER dependientes de contexto del país

[!include[banner](../includes/banner.md)]

Puede configurar las asignaciones de modelo de informes electrónicas (ER) de modo que implementen un modelo de datos de ER genérico, pero son específicas de Dynamics 365 Finance. Este artículo explica cómo diseñar varias asignaciones de modelos de ER para un modelo de datos de ER para controlar cómo se usan por los formatos de ER correspondientes que se ejecutan desde empresas con contextos diferente de país o región.

## <a name="prerequisites"></a>Requisitos previos

Para completar los ejemplos de este artículo, debe tener el acceso siguiente:

- Acceso a Finance para uno de los roles siguientes:
    - Desarrollador de informes electrónicos
    - Consultor funcional de informes electrónicos
    - Administrador del sistema

- Acceso a la instancia de los Regulatory Configuration Services (RCS) que se ha aprovisionado para el mismo que el arrendatario de Finance, para uno de los roles siguientes:
    - Desarrollador de informes electrónicos
    - Consultor funcional de informes electrónicos
    - Administrador del sistema

Algunos pasos de este artículo requieren la ejecución de un formato de ER. En algunos casos, la ejecución de un formato de ER se verá afectada por el contexto del país o región de la empresa en la que ha iniciado sesión actualmente. Puede ejecutar un formato de ER en la instancia de RCS actual si la empresa que tiene el contexto necesario de país o región está disponible en el RCS. Si no, debe cargar una versión completada de la asignación del modelo de ER y los parámetros de formato de ER que usan el modelo de datos de ER par su instancia de Finance y, después, ejecutar el formato de ER en dicha instancia de Finance. Para obtener más información sobre cómo importar las configuraciones que residen en RCS en una instancia de Finance, consulte [Importar configuraciones de RCS](rcs-download-configurations.md).

## <a name="single-model-mapping-case"></a>Caso de asignación de un único modelo

Siga los pasos en el [Apéndice 1](#appendix1) de este artículo para diseñar los componentes de ER requeridos. Ahora tiene la configuración del modelo de asignaciones **Asignación (general)** que contiene la asignación del modelo para la definición de **Punto de entrada 1**.

![Página de configuraciones de ER, formato para aprender la configuración de asignaciones.](./media/RCS-Context-specific-mapping-Tree.PNG)

### <a name="run-the-configured-format"></a>Ejecutar el formato configurado

1.  En la página **Configuraciones**, en la ficha desplegable **Versiones**, seleccione **Ejecutar**.
2.  Seleccione **Aceptar**.

Observe que el explorador web ofrece descargar el archivo de texto generado por el formato del ER ejecutado. Dado que este formato se configuró para usar la definición del **Punto de entrada 1**, y solo está disponible una sola asignación de modelo para el modelo base que contiene una asignación para esta definición, el formato de ER ejecutado usó la asignación de modelos **Asignación (general)** de la configuración **Asignación (general)** como origen de datos. Por lo tanto, el archivo descargado contiene el texto **Funcionalidad genérica 1**.

## <a name="multiple-shared-model-mappings-case"></a>Caso de asignaciones múltiples de modelos compartidos

Siga los pasos en el [Apéndice 2](#appendix2) de este artículo para diseñar los componentes de ER requeridos. Ahora tiene las configuraciones del modelo de asignaciones **Asignación (general)** y **Asignación (general), personalizada**, que cada una de ellas contiene la asignación del modelo para la definición de **Punto de entrada 1**.

![Página de configuraciones de ER, configuración personalizada de asignación general.](./media/RCS-Context-specific-mapping-TreeCustom.PNG)

### <a name="run-the-configured-format"></a>Ejecutar el formato configurado

1.  En la página **Configuraciones**, en el árbol de configuraciones, seleccione el elemento **Formato para aprender asignaciones**.
2.  En la ficha desplegable **Versiones**, seleccione **Ejecutar**.
3.  Seleccione **Aceptar**.

Observe que la ejecución del formato de ER seleccionado no se ha desarrollado correctamente. Un mensaje de error le informa de que existe más de una asignación de modelo para el modelo **Modelo para aprender asignaciones** y la definición del **Punto de entrada 1** en las configuraciones de asignación de modelos **Asignación (general)** y **Asignación (general), personalizada**. El mensaje que recomienda también que seleccione una de estas configuración como la configuración predeterminada.

![Página de configuraciones de ER con mensaje de error.](./media/RCS-Context-specific-mapping-FormatRunCustomFailed.PNG)

### <a name="define-a-default-mapping-configuration"></a>Definir una configuración predeterminada de asignación

Siga estos pasos para definir la configuración de la asignación de modelos **Asignación (general), personalizada** como la configuración predeterminada, para poder utilizar sus asignaciones como orígenes de datos para el formato de ER **Formato para aprender asignaciones**.

1.  En la página **Configuraciones**, en el árbol de configuraciones, seleccione el elemento **Asignación (general), personalizada**.
2.  Según se solicita, seleccione **Editar** para hacer que la página actual pase a estar lista para editar.
3.  Establezca la opción **Predeterminado para la asignación de modelo** a **Sí**.
4.  Seleccione **Guardar**.

![Página de configuraciones de ER, predeterminado para el control deslizante de asignación de modelos establecido en Sí.](./media/RCS-Context-specific-mapping-MappingsCustomDefault.PNG)

### <a name="run-the-configured-format"></a>Ejecutar el formato configurado

1.  En la página **Configuraciones**, en el árbol de configuraciones, seleccione el elemento **Formato para aprender asignaciones**.
2.  En la ficha desplegable **Versiones**, seleccione **Ejecutar**.
3.  Seleccione **Aceptar**.

Observe que la ejecución del formato de ER seleccionado se ha desarrollado correctamente. El explorador web ofrece descargar el archivo de texto generado por el formato del ER ejecutado. Dado que este formato se configuró para usar la definición del **Punto de entrada 1**, y la configuración de asignación de modelos **Asignación (general), personalizada** se seleccionó como la configuración predeterminado, el formato del ER ejecutado uso la asignación de modelos **Copia de asignación (general)** de la configuración **Asignación (general), personalizada** como origen de datos. Por lo tanto, el archivo descargado contiene el texto **Funcionalidad genérica 1 personalizada**.

> [!NOTE]
> Si cambia la empresa en la que ha iniciado sesión actualmente y ejecuta este formato de ER de nuevo, obtendrá el mismo contenido en el archivo generado, porque la configuración de la asignación de modelos del ER predeterminado no contiene restricciones dependientes de compañías.

## <a name="multiple-mixed-model-mappings-case"></a>Caso de asignaciones combinadas de modelos compartidos

Siga los pasos en el [Apéndice 3](#appendix3) de este artículo para diseñar los componentes de ER requeridos. Ahora tiene las configuraciones del modelo de asignaciones **Asignación (general)**, **Asignación (general), personalizada** y **Asignación de modelos de asignaciones (FR)** que contienen la asignación de modelos para la definición de **Punto de entrada 1**.

Observe que la versión 1 de la configuración de la asignación de modelos **Asignación (FR)** está configurada de modo que solo se aplique a los formatos de ER del modelo **Modelo para aprender asignaciones** que se ejecutan en las empresas con contexto de país o región francés.

![Página de configuraciones de ER, configuración de asignación de modelos (FR).](./media/RCS-Context-specific-mapping-TreeFR.PNG)

### <a name="run-the-configured-format"></a>Ejecutar el formato configurado

1.  Cambie la empresa a **FRSI**.
2.  En la página **Configuraciones**, en el árbol de configuraciones, seleccione el elemento **Formato para aprender asignaciones**.
3.  En la ficha desplegable **Versiones**, seleccione **Ejecutar**.
4.  Seleccione **Aceptar**.

Observe que la ejecución del formato de ER seleccionado se ha desarrollado correctamente. El explorador web ofrece descargar el archivo de texto generado por el formato del ER ejecutado. Dado que este formato se configuró para usar la definición del **Punto de entrada 1**, y la configuración de asignación de modelos **Asignación (general), personalizada** se seleccionó como la configuración predeterminado, el formato del ER ejecutado uso la asignación de modelos **Copia de asignación (general)** de la configuración **Asignación (general), personalizada** como origen de datos. Por lo tanto, el archivo descargado contiene el texto **Funcionalidad genérica 1 personalizada**.

### <a name="define-the-france-specific-mapping-configuration-as-the-default-configuration"></a>Definir la configuración de la asignación específica para Francia como la configuración predeterminada

Siga estos pasos para definir la configuración de la asignación de modelos personalizada la **Asignación (FR)** como la configuración predeterminada. Tenga en cuenta que, porque esta asignación sea específica para Francia, se considerará la asignación predeterminada entre todas las configuraciones de asignaciones de modelos que tienen el código de país **FR** especificado en el campo **Códigos de país o región ISO**.

1.  En la página **Configuraciones**, en el árbol de configuraciones, seleccione el elemento **Asignación (FR)**.
2.  Según se solicita, seleccione **Editar** para hacer que la página actual pase a estar lista para editar.
3.  Establezca la opción **Predeterminado para la asignación de modelo** a **Sí**.
4.  Seleccione **Guardar**.

![Página de configuraciones de ER, configuración de asignación (FR), predeterminado para el control deslizante de asignación de modelos establecido en Sí.](./media/RCS-Context-specific-mapping-TreeFRDefault.PNG)

### <a name="run-the-configured-format"></a>Ejecutar el formato configurado

1.  En la página **Configuraciones**, en el árbol de configuraciones, seleccione el elemento **Formato para aprender asignaciones**.
2.  En la ficha desplegable **Versiones**, seleccione **Ejecutar**.
3.  Seleccione **Aceptar**.

Observe que la ejecución del formato de ER seleccionado se ha desarrollado correctamente. El explorador web ofrece descargar el archivo de texto generado por el formato del ER ejecutado. Dado que este formato se configuró para usar la definición del **Punto de entrada 1**, y la configuración de asignación de modelos **Asignación (FR)** se seleccionó como la configuración predeterminado, el formato del ER ejecutado uso la asignación de modelos **Asignación (FR)** de la configuración **Asignación (FR)** como origen de datos. Por lo tanto, el archivo descargado contiene el texto **Funcionalidad FR 1**.

> [!NOTE]
> Si cambia la empresa en la que ha iniciado sesión actualmente y ejecuta este formato de ER de nuevo, el resultado dependerá del contexto de país o región de la empresa seleccionada.

## <a name="other-model-mapping-cases"></a>Otros casos de asignación de modelos

Como ha comprado, la selección de una asignación de modelo para la ejecución de un formato de ER funciona de la siguiente forma:

- Se especifica la definición de la asignación de modelos que usa un formato de ER (**Punto de entrada 1** en los ejemplos de este artículo).
- Todas las configuraciones de asignación que contienen una asignación con la definición especificada, y que satisfacen cualquier restricción de contexto de país o región que se hayan configurado, se podrían utilizar para ejecutar el formato de ER (**Asignación (general)**, **Asignación (general), personalizada** y **Asignación (FR)** en los ejemplos de este artículo).
- Cualquier asignación de modelo predeterminado con restricciones de contexto de país o región tiene la máxima prioridad de selección (**Asignación (FR)** en los ejemplos de este artículo).
- Cualquier asignación de modelo predeterminado que no tenga restricciones de contexto del país o región tiene la máxima prioridad de selección (**Asignación (general), personalizada** en los ejemplos de este artículo).
- Cualquier asignación de modelos con restricciones de contexto de país o región tiene prioridad más alta de selección que una asignación de modelos que no tenga restricciones de contexto de país o región.

La siguiente tabla ofrece información sobre los resultados de la selección de asignación de modelos para todos los casos posibles para parámetros de asignación de modelos:

- La columna 1 indica si la primera asignación de modelos que no tiene restricciones de contexto de país o región (por ejemplo, la asignación compartida **Asignación (general)**) se muestra y, si las tiene, si la opción **Predeterminado para la asignación de modelos** está establecida en **Sí** para ella.
- La columna 2 indica si la segunda asignación de modelos que no tiene restricciones de contexto de país o región (por ejemplo, la asignación compartida **Asignación (general), personalizada**) se muestra y, si las tiene, si la opción **Predeterminado para la asignación de modelos** está establecida en **Sí** para ella.
- La columna 3 indica si la primera asignación de modelos que tiene restricciones de contexto de país o región A (por ejemplo, la asignación específica para Francia **Asignación (FR)**) se muestra y, si las tiene, si la opción **Predeterminado para la asignación de modelos** está establecida en **Sí** para ella.
- La columna 4 indica si la segunda asignación de modelos que tiene restricciones de contexto de país o región A se muestra y, si las tiene, si la opción **Predeterminado para la asignación de modelos** está establecida en **Sí** para ella.
- La columna 5 muestra el resultado de una selección de asignación de modelos para la ejecución de un formato de ER bajo el control de una empresa que tienen contexto del país o región A.
- La columna 6 muestra el resultado de una selección de asignación de modelos para la ejecución de un formato de ER bajo el control de una empresa que tienen contexto del país o región B.

En la tabla, un signo más (+) indica la presencia de una configuración de asignación de modelos en la instancia actual del servicio Microsoft Azure que se usa para ejecutar un formato de ER (bien Finance o RCS).

| Caso | Asignación de modelos 1 sin el contexto de país o región (MM1) | Asignación de modelos 2 sin el contexto de país o región (MM2) | Asignación de modelos 1 con el contexto de país o región A (MM1A) | Asignación de modelos 2 con el contexto de país o región A (MM2A) | Ejecutar bajo el control de una empresa que tiene contexto del país o región A | Ejecutar bajo el control de una empresa que tiene contexto del país o región B |
|---------|---------|---------|---------|---------|---------------------------|----------------------------|
|         |     1   |     2   |    3    |    4    |           5               |            6               |
|     1   |         |         |         |         | Error (falta asignación)   | Error (falta asignación)    |
|     2   |     +   |         |         |         | MM1                       | MM1                        |
|     3   |     +   |     +   |         |         | Error (múltiples asignaciones) | Error (múltiples asignaciones)  |
|     4   |     +   |         |    +    |         | MM1A                      | MM1                        |
|     5   |     +   |         |    +    |    +    | Error (múltiples asignaciones) | MM1                        |
|     6   |     +   | predeterminada |    +    |    +    | MM2                       | MM2                        |
|     7   |     +   |         | predeterminada |         | MM1A                      | MM1                        |
|     8   |     +   |         | predeterminada |    +    | MM1A                      | MM1                        |
|     9   |     +   |         | predeterminada | predeterminada | Error (múltiples asignaciones) | MM1                        |
|    10   | predeterminada |         |         |         | MM1                       | MM1                        |
|    11   | predeterminada |    +    |         |         | MM1                       | MM1                        |
|    12   | predeterminada |         |    +    |         | MM1                       | MM1                        |
|    13   | predeterminada | predeterminada |         |         | Error (múltiples asignaciones) | Error (múltiples asignaciones)  |
|    14   | predeterminada |         | predeterminada |         | MM1A                      | MM1                        |
|    15   | predeterminada |         | predeterminada | predeterminada | MM1A                      | MM2A                       |
|    16   |         |         |    +    |    +    | MM1A                      | MM2A                       |
|    17   |         |         | predeterminada | predeterminada | MM1A                      | MM2A                       |

## <a name="learn-what-mapping-was-used-in-the-execution-of-an-er-format"></a>Sepa qué asignación se usó en la ejecución de un formato de ER

### <a name="configure-er-user-parameters"></a>Configurar los parámetros de usuario de ER

1.  En la página **Configuraciones**, en el panel de acciones, en la pestaña **CONFIGURACIONES**, seleccione **Parámetros de usuario**.
2.  Establezca la opción **Ejecutar en modo depuración** en **Sí**.
4.  Seleccione **Aceptar**.

### <a name="run-the-configured-format"></a>Ejecutar el formato configurado

1.  En la página **Configuraciones**, en el árbol de configuraciones, seleccione el elemento **Formato para aprender asignaciones**.
2.  En la ficha desplegable **Versiones**, seleccione **Ejecutar**.
3.  Seleccione **Aceptar**.

### <a name="review-the-er-debug-log"></a>Revise el registro de depuración de ER

1.  En el Panel de exploración, vaya a **Módulos \> Administración de la organización \> Informes electrónicos \> Configurar registro de depuración**.
2.  Seleccione el botón **Volver a cargar esta página**.

![Página de los registros de ejecución de ER.](./media/RCS-Context-specific-mapping-DebugLog.PNG)

Observe que se ha agregado un nuevo registro al registro de depuración de ER para el formato de ER ejecutado. Dado que el campo **Nivel** de este registro se establece en **Información**, el registro es informativo. Puesto que el campo del componente del formato está establecido en **Configuración de asignación**, el registro le informa sobre una asignación de modelos que se usó durante la ejecución del formato de ER **Formato para aprender asignaciones** (seleccionado en el campo **Nombre de configuración**). El contenido del campo **Texto generado** le informa de que se ha utilizado el componente de asignación **Asignación (FR)** que reside en la configuración de **Asignación (FR)** para ejecutar este informe.

## <a name="appendix-1"></a><a name="appendix1"></a> Apéndice 1

### <a name="configure-a-sample-data-model"></a>Configurar de un modelo de datos de ejemplo

Inicie sesión en su instancia de RCS.

En este ejemplo, creará una configuración para la empresa del ejemplo, Litware, Inc. Para completar estos pasos, primero tiene que completar, en RCS, los pasos en el procedimiento [Crear un proveedor de la configuración y marcarlo como activo](tasks/er-configuration-provider-mark-it-active-2016-11.md):

#### <a name="create-an-er-data-model-configuration"></a>Crear de nuevo modelo de configuración de datos de ER

1.  En el panel predeterminado, seleccione **Informes electrónicos**.
2.  Seleccione el título **Configuraciones de informes**.
3.  En la página **Configuraciones**, seleccione **Crear configuración**.
4.  En el cuadro de diálogo desplegable, en el campo **Nombre**, introduzca **Modelo para aprender asignaciones**.
5.  Seleccionar **Crear configuración**.
6.  Seleccione la ficha desplegable **Componentes de la configuración**.

Observe que la versión 1 del borrador de esta configuración del ER está lista para editarse. Esta versión contiene el componente del modelo de datos.

#### <a name="design-a-sample-data-model"></a>Diseñar un modelo de datos de ejemplo

1.  En la página **Configuraciones**, seleccione **Diseñador**.
2.  Seleccione **Nuevo**.
3.  En el cuadro de diálogo desplegable, en el campo **Nombre**, introduzca **Punto de entrada 1**.
4.  Seleccione **Agregar**.
5.  Seleccione **Nuevo**.
6.  En el cuadro de diálogo desplegable, en el campo **Nombre**, introduzca **Descripción de funcionalidad**.
7.  Seleccione **Agregar**.
8.  Seleccione **Nuevo**.
9.  En el cuadro de diálogo desplegable, en grupo de campos **Nuevo nodo**, seleccione **Raíz del modelo**.
10. En el campo **Nombre**, escriba **Punto de entrada 2**.
11. Seleccione **Punto de entrada 2**.
12. Seleccione **Agregar**.
13. Seleccione **Nuevo**.
14. En el cuadro de diálogo desplegable, en el campo **Nombre**, introduzca **Descripción de funcionalidad**.
15. Seleccione **Agregar**.

    ![Página de diseñador del modelo de datos de ER.](./media/RCS-Context-specific-mapping-Model.PNG)

16. Seleccione **Guardar**.
17. Cierre la página.

#### <a name="complete-the-modified-version-of-the-model-configuration"></a>Completar la versión modificada de la configuración de modelos

1.  En la página **Configuraciones**, en la ficha desplegable **Versiones**, seleccione **Cambiar estado**.

    > Cambie el estado de configuración del modelo diseñado de **Borrador** a **Completado**, para que se pueda usar para diseñar las asignaciones y los formatos de modelos requeridos.

2.  Seleccione **Completar**.
3.  Seleccione **Aceptar**.

Tenga en cuenta que la configuración que ha creado se guarda como versión completada 1.

### <a name="configure-a-sample-model-mapping"></a>Configurar de una asignación de modelos

#### <a name="create-an-er-model-mapping-configuration"></a>Crear una configuración de asignación de modelos ER

1.  En la página **Configuraciones**, seleccione **Crear configuración**.
2.  En el cuadro de diálogo desplegable, en el grupo del campo **Nuevo**, seleccione **Asignación de modelos basada en el modelo de datos Modelo para aprender asignaciones**.
3.  En el campo **Nombre**, introduzca **Asignación (general)**.
4.  En el campo **Definición del modelo de datos**, seleccione **Punto de entrada 1**.
5.  Seleccionar **Crear configuración**.

Observe que la versión 1 del borrador de esta configuración del ER está lista para editarse. Esta versión contiene el componente de la asignación de modelos.

#### <a name="design-a-sample-model-mapping"></a>Diseñar una asignación de modelos

1.  En la página **Configuraciones**, seleccione **Diseñador**.

    Observe que la asignación de modelos del tipo de dirección **Para modelo** se agregó automáticamente a este componente para la definición de **Punto de entrada 1**.
    
2.  Seleccione **Diseñador** para iniciar la edición de la asignación de modelos agregada.
3.  Seleccione **Editar** en la sección **Modelo de datos**.
4.  En el campo **Fórmula**, especifique **"Funcionalidad genérica 1"**.
5.  Seleccione **Guardar**.
6.  Cierre la página **Diseñador de fórmula**.

    ![Página del diseñador de asignaciones de modelos ER, definición del punto de entrada 1.](./media/RCS-Context-specific-mapping-Mapping1.PNG)

7.  Seleccione **Guardar**.
8.  Cierre la página **Diseñador de distribución del modelo**.
9.  Seleccione **Nuevo**.
10. En el campo **Definición**, seleccione **Punto de entrada 2**.
11. En el campo **Nombre**, introduzca **Asignación (general) 2**.
12. Seleccione **Diseñador**.
13. Seleccione **Editar** en la sección **Modelo de datos**.
14. En el campo **Fórmula**, especifique **"Funcionalidad genérica 2"**.
15. Seleccione **Guardar**.
16. Cierre la página **Diseñador de fórmula**.

    ![Página del diseñador de asignaciones de modelos ER, definición del punto de entrada 2.](./media/RCS-Context-specific-mapping-Mapping2.PNG)

17. Seleccione **Guardar**.
18. Cierre la página **Diseñador de distribución del modelo**.

    ![Página de asignaciones de modelos de ER con definiciones de puntos de entrada.](./media/RCS-Context-specific-mapping-Mappings.PNG)

19. Cierre la página **Distribuciones del modelo**.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>Completar la versión modificada de la configuración de asignación de modelos

1.  En la página **Configuraciones**, en la ficha desplegable **Versiones**, seleccione **Cambiar estado**.

    > Cambie el estado de configuración de la asignación de modelos de **Borrador** a **Completado**, para que se pueda usar por los formatos de ER.

2.  Seleccione **Completar**.
3.  Seleccione **Aceptar**.

Tenga en cuenta que la configuración que se ha creado se guarda como versión completada 1.

### <a name="configure-a-sample-format"></a>Configurar un formato de ejemplo

#### <a name="create-an-er-format-configuration"></a>Crear una configuración de formato de ER

1.  En la página **Configuraciones**, en el árbol de configuraciones, seleccione el elemento **Modelo para aprender asignaciones**.
2.  Seleccionar **Crear configuración**.
3.  En el cuadro de diálogo desplegable, en el grupo del campo **Nuevo**, seleccione **Formato basado en modelo de datos, Modelo para aprender asignaciones**.
4.  En el campo **Nombre**, introduzca **Formato para aprender asignaciones**.
5.  En el campo **Definición del modelo de datos**, seleccione **Punto de entrada 1**.
6.  Seleccionar **Crear configuración**.

Observe que la versión 1 del borrador de esta configuración del ER está lista para editarse. Esta versión contiene el componente del formato.

#### <a name="design-a-sample-format"></a>Diseñar un formato de ejemplo

1.  En la página **Configuraciones**, seleccione **Diseñador**.
2.  Seleccione **Agregar raíz**.
3.  En el grupo **Texto**, seleccione el elemento **Cadena**.
4.  Seleccione **Aceptar**.

#### <a name="bind-format-elements-to-a-data-source"></a>Vincule elementos de formato a un origen de datos

1.  En la página **Diseñador de formato**, en la pestaña **Asignación**, expanda el origen de datos del modelo.
2.  Seleccione el campo **Descripción de la funcionalidad**.
3.  Seleccione **Enlazar**.

    ![Página de diseñador de formato ER.](./media/RCS-Context-specific-mapping-Format.PNG)

4.  Seleccione **Guardar**.
5.  Cierre la página.

## <a name="appendix-2"></a><a name="appendix2"></a> Apéndice 2

### <a name="configure-a-sample-model-mapping-for-general-customization"></a>Configurar una asignación de modelos de ejemplo para personalización general

Es posible que desee personalizar una asignación de modelos que un proveedor de configuración (socio) le proporcionó, y luego usar la versión personalizada como origen de datos para los formatos de ER. En este caso, debe crear una configuración de asignación de modelos de ER personalizada para realizar los cambios necesarios en asignaciones de modelos existentes. Los procedimientos de este apéndice usan la asignación de modelos **Asignación (general)** como ejemplo.

#### <a name="create-an-er-model-mapping-configuration"></a>Crear una configuración de asignación de modelos ER

1.  En la página **Configuraciones**, en el árbol de configuraciones, seleccione el elemento **Asignación (general)**.
2.  Seleccionar **Crear configuración**.
3.  En el cuadro de diálogo desplegable, en el grupo de campos **Nuevo**, seleccione **Derivar del nombre: Asignación (general), Litware, Inc.**.
4.  En el campo **Nombre**, especifique **Asignación (general), personalizada**.
5.  Seleccionar **Crear configuración**.

Observe que la versión 1 del borrador de esta configuración del ER está lista para editarse.

#### <a name="design-a-sample-model-mapping"></a>Diseñar una asignación de modelos

1.  En la página **Configuraciones**, seleccione **Diseñador**.

    > Observe que las asignaciones de modelos de la configuración base se ha copiado automáticamente a esta configuración.

2.  Seleccione la asignación **Copia de asignación (general)**.
3.  Seleccione **Diseñador**.
4.  Seleccione **Editar** en la sección **Modelo de datos**.
5.  En el campo **Fórmula**, especifique **"Funcionalidad genérica 1 personalizada"**.
6.  Seleccione **Guardar**.
7.  Cierre la página.

    ![Página del diseñador de asignación de modelos de ER, fórmula personalizada de funcionalidad genérica 1.](./media/RCS-Context-specific-mapping-Mapping1Custom.PNG)

8.  Seleccione **Guardar**.
9.  Cierre la página.
10. Seleccione la asignación **Copia de asignación (general) 2**.
11. Seleccione **Diseñador**.
12. Seleccione **Editar** en la sección **Modelo de datos**.
13. En el campo **Fórmula**, especifique **"Funcionalidad genérica 2 personalizada"**.
14. Seleccione **Guardar**.
15. Cierre la página.

    ![Página del diseñador de asignación de modelos de ER, fórmula personalizada de funcionalidad genérica 2.](./media/RCS-Context-specific-mapping-Mapping2Custom.PNG)

16. Seleccione **Guardar**.
17. Cierre la página.

    ![Modelo de ER para la página de asignación de origen de datos para asignación de copia de asignación (general).](./media/RCS-Context-specific-mapping-MappingsCustom.PNG)

18. Cierre la página.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>Completar la versión modificada de la configuración de asignación de modelos

1.  En la página **Configuraciones**, en la ficha desplegable **Versiones**, seleccione **Cambiar estado**.

    > Cambie el estado de configuración de la asignación de modelos de **Borrador** a **Completado**, para que se pueda usar por los formatos de ER.

2.  Seleccione **Completar**.
3.  Seleccione **Aceptar**.

Tenga en cuenta que la configuración que se ha creado se guarda como versión completada 1.

## <a name="appendix-3"></a><a name="appendix3"></a> Apéndice 3

### <a name="configure-a-sample-model-mapping-for-countryregion-specific-customization"></a>Configurar una asignación de modelos de ejemplo para personalización específica para país o región

Para algunos formatos de ER, puede haber requisitos específicos del país o región para la preparación de datos. En este caso, puede administrar una configuración distinta para la asignación del modelo de ER y aislar la implementación de estos requisitos específicos de país o región de la implementación general. Los procedimientos de este apéndice usan el formato de ER **Formato para aprender asignaciones** y los requisitos específicos de Francés como ejemplo.

#### <a name="create-an-er-model-mapping-configuration"></a>Crear una configuración de asignación de modelos ER

En primer lugar, cree una nueva configuración de asignación de modelos de ER para implementar los requisitos específicos del país o región. Use la configuración de asignación de modelos de ER personalizada como base.

1.  En la página **Configuraciones**, en el árbol de configuraciones, seleccione el elemento **Asignación (general), personalizada**.
2.  Seleccionar **Crear configuración**.
3.  En el cuadro de diálogo desplegable, en el grupo de campos **Nuevo**, seleccione **Derivar del nombre: Asignación (general), personalizada**.
4.  En el campo **Nombre**, especifique **Asignación (FR)**.
5.  Seleccionar **Crear configuración**.

Observe que la versión 1 del borrador de esta configuración del ER está lista para editarse.

#### <a name="design-a-sample-model-mapping"></a>Diseñar una asignación de modelos

1.  En la página **Configuraciones**, seleccione **Diseñador**.

    > Observe que las asignaciones de modelos de la configuración base se ha copiado automáticamente a esta configuración.

2.  Seleccione la asignación **Copia de copia de asignación (general)**.
3.  Cambie el nombre a **Asignación (FR)**.
4.  Seleccione **Diseñador**.
5.  Seleccione **Editar** en la sección **Modelo de datos**.
6.  En el campo **Fórmula**, especifique **"Funcionalidad FR 1"**.
7.  Seleccione **Guardar**.
8.  Cierre la página.

    ![Página del diseñador de asignación de modelos de ER, fórmula de funcionalidad FR 1.](./media/RCS-Context-specific-mapping-Mapping1FR.PNG)

9.  Seleccione **Guardar**.
10. Cierre la página.
11. Seleccione la asignación **Copia de copia de asignación (general) 2**.
12. Cambie el nombre a **Asignación (FR) 2**.
13. Seleccione **Diseñador**.
14. Seleccione **Editar** en la sección **Modelo de datos**.
15. En el campo **Fórmula**, especifique **"Funcionalidad FR 2"**.
16. Seleccione **Guardar**.
17. Cierre la página.

    ![Página del diseñador de asignación de modelos de ER, fórmula de funcionalidad FR 2.](./media/RCS-Context-specific-mapping-Mapping2FR.PNG)

18. Seleccione **Guardar**.
19. Cierre la página.

    ![Modelo de ER para página de asignación de origen de datos.](./media/RCS-Context-specific-mapping-MappingsFR.PNG)

20. Cierre la página.

#### <a name="specify-countryregion-context-restrictions-for-use"></a>Especificar restricciones de contexto del país o región para su uso

1.  En la página **Configuraciones**, en la ficha desplegable **Códigos ISO de país o región**, seleccione **Nuevo**.
2.  En el campo **ISO**, seleccione **FR**.
3.  Seleccione **Guardar**.

Tenga en cuenta que debe iniciar sesión a una empresa específica en Finance para ejecutar un formato de ER. Por lo tanto, esta empresa puede considerarse como una parte que controla la ejecución del formato de ER y la selección de la asignación correcta de modelos de ER del modelo de datos de ER base. Si agrega el código de país **FR**, especifica que esta asignación de modelo está disponible para la selección por un formato de ER del modelo de datos base solo si ese formato se ejecuta bajo el control de una empresa que tenga contexto de país o región francés.

Puede agregar múltiples códigos de país o región para una única versión de la configuración de asignaciones de modelos de ER. De esta manera, las asignaciones de modelos que residen en dicha configuración de la asignación de modelos se pueden utilizar para un formato de ER que se ejecuta bajo el control de las empresas con un contextos diferente de país o región.

Tenga en cuenta que la lista de códigos de país región se especifica para cada versión de configuración de la asignación de modelos de ER y puede variar entre versiones.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>Completar la versión modificada de la configuración de asignación de modelos

1.  En la página **Configuraciones**, en la ficha desplegable **Versiones**, seleccione **Cambiar estado**.

    > Cambie el estado de configuración de la asignación de modelos de **Borrador** a **Completado**, para que se pueda usar por los formatos de ER.

2.  Seleccione **Completar**.
3.  Seleccione **Aceptar**.

Tenga en cuenta que la configuración que se ha creado se guarda como versión completada 1.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)

[Gestionar la asignación de modelos de ER en distintas configuraciones de ER](./tasks/er-manage-model-mapping-configurations-july-2017.md)

[Aplicar contexto del país o región](../lcs-solutions/apply-country-context.md)

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

#### <a name="i-configured-two-shared-er-model-mapping-configurations-in-rcs-and-marked-one-of-them-as-the-default-model-mapping-configuration-i-successfully-ran-an-er-format-that-was-created-for-the-same-base-er-data-model-configuration-to-test-model-mappings-i-then-imported-the-whole-er-solution-er-data-model-two-er-model-mapping-configurations-and-er-format-configuration-into-finance-why-do-i-receive-an-error-message-when-i-try-to-run-the-same-er-format-in-finance"></a>Configuré dos configuraciones compartidas de asignación de modelos de ER en RCS y maqué una de ellas como la configuración de la asignación de modelos predeterminada. Ejecuté correctamente un formato de ER que se creó para la misma configuración del modelo de datos de ER base, para probar asignaciones de modelos. A continuación, importé la solución completa de ER (modelo de datos de ER, dos configuraciones de asignación de modelos de ER y configuración del formato de ER) en Finance. ¿Por qué recibo un mensaje de error cuando intento ejecutar el mismo formato de ER en Finance?
El valor de la asignación del modelo predeterminado es específico del entorno. Se ha configurado en RCS, pero no se exporta a Finance. Para ejecutar correctamente este formato de ER, debe marcar una de las configuraciones de la asignación de modelos de ER como la configuración de la asignación de modelos predeterminada en Finance también.

#### <a name="i-configured-one-model-mapping-as-a-shared-model-mapping-and-completed-the-draft-version-of-it-i-then-added-a-new-model-mapping-configuration-for-same-data-model-and-configured-it-as-french-specific-why-is-the-shared-model-mapping-selected-when-i-run-an-er-format-even-though-this-er-format-uses-the-correct-root-definition-and-execution-is-done-under-the-control-of-the-company-that-has-french-countryregion-context"></a>Configuré una asignación de modelos como asignación de modelos compartidos y completé la versión de borrador de esta. Después agregué una configuración de la asignación de modelos nueva para el mismo modelo de datos y la configuré como específica para francés. ¿Por qué la asignación de modelos compartida se selecciona cuando ejecuto un formato de ER, aunque este formato de ER use la definición correcta de raíz y la ejecución se realiza bajo el control de la empresa con contexto del país o región francés?
Asegúrese de que la configuración de la asignación de modelos compartida no esté marcada como la configuración de la asignación de modelos predeterminada. Si no, tendrá una mayor prioridad durante la selección de la asignación. También asegúrese de que la configuración específica de francés de asignación de modelos se tendrán en cuenta cuando una asignación se selecciona durante la ejecución del formato de ER. Una configuración de la asignación del modelo de ER está disponible para su selección solo si al menos se cumple una de las siguientes condiciones:
- Al menos un versión de la configuración de la asignación de modelos de ER tiene su estado **Completado** o **Compartido**. En este caso, la versión que tiene el número de versión más alto se usará para la ejecución del formato de ER.
- La opción **Borrador de ejecución** para la configuración de la asignación de modelos de ER está activada. En este caso, la versión que el estado **Borrador** se usará para la ejecución del formato de ER.
> La opción **Ejecutar borrador** estará disponible en la página **Configuraciones** para cada configuración de asignación de modelos de ER cuando el parámetro de usuario de ER **Ejecutar valor** esté activado.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
