---
title: Admita las llamadas con parámetros de los orígenes de datos de ER del tipo de campo calculado
description: Este artículo proporciona información sobre cómo usar el tipo de campo calculado para los orígenes de datos de ER.
author: NickSelin
ms.date: 01/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5a4eb70144957ecdbeba4246fb8c7cd6a20cb08c
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2022
ms.locfileid: "9108341"
---
# <a name="support-parameterized-calls-of-er-data-sources-of-the-calculated-field-type"></a>Admita las llamadas con parámetros de los orígenes de datos de ER del tipo de campo calculado

[!include [banner](../includes/banner.md)]

Este artículo explica cómo puede diseñar un origen de datos de informes electrónicos (ER) mediante el tipo **Campo calculado**. Este origen de datos puede contener una expresión del ER que, cuando se ejecuta, se puede controlar mediante los valores de los argumentos de parámetros que se configuran en un enlace que llama a este origen de datos. Al configurar llamadas con parámetros de este tipo de origen de datos, puede volver a usar un solo origen de datos en muchos enlaces, lo que reduce el número total de orígenes de datos que se deben configurar en distribuciones de modelos de ER o formatos de ER. También simplifica el componente de ER configurado, que reduce los costes de mantenimiento y el coste de uso de otros consumidores.

## <a name="prerequisites"></a>Requisitos previos
Para completar los ejemplos de este artículo, debe tener el acceso siguiente:

- Acceso a uno de estos roles:

    - Desarrollador de informes electrónicos
    - Consultor funcional de informes electrónicos
    - Administrador del sistema

- Acceso a la instancia de los Regulatory Configuration Services (RCS) que se han aprovisionado para el mismo arrendatario que finanzas y operaciones, para uno de los roles siguientes:

    - Desarrollador de informes electrónicos
    - Consultor funcional de informes electrónicos
    - Administrador del sistema

Debe descargar y también almacenar localmente los archivos siguientes.

| **Contenido**                           | **Nombre de archivo**                                        |
|---------------------------------------|------------------------------------------------------|
| Configuración del modelo datos de ER de ejemplo    | [Modelo para aprender llamadas con parámetros.versión.1.xml](https://download.microsoft.com/download/e/5/c/e5c0d3f9-1818-47c7-ae75-46efcbb1314f/Modeltolearnparameterizedcallsversion.1.xml)     |
| Configuración de metadatos de ER de ejemplo      | [Metadatos para aprender llamadas con parámetros.versión.1.xml](https://download.microsoft.com/download/8/3/a/83a910a5-bf65-4509-bec4-6737a81ecc45/Metadatatolearnparameterizedcalls.version.1.xml)  |
| Configuración del modelo de mapeado de ER de ejemplo | [Asignación para aprender llamadas con parámetros.versión.1.1.xml](https://download.microsoft.com/download/b/f/d/bfd8cbd8-0370-44d1-a1b1-66d021c580ca/Mappingtolearnparameterizedcalls.version.1.1.xml) |
| Configuración de formato de ER de ejemplo        | [Formato para aprender llamadas con parámetros.versión.1.1.xml](https://download.microsoft.com/download/8/1/d/81deb6d8-a768-4fcf-bbbe-8f84d2dac3eb/Formattolearnparameterizedcalls.version.1.1.xml)  |

## <a name="sign-in-to-your-rcs-instance"></a>Iniciar sesión en su instancia de RCS
En este ejemplo, creará una configuración para la empresa del ejemplo, Litware, Inc. First, en RCS, tiene que completar estos pasos, en el procedimiento [Crear proveedores de la configuración y marcarlos como activos](tasks/er-configuration-provider-mark-it-active-2016-11.md):

1. En el panel predeterminado, seleccione **Informes electrónicos**.
2. Seleccione **Configuraciones de informes**.
3. Importe las configuraciones descargadas al RCS en la siguiente secuencia: modelo de datos, metadatos, distribución de modelo, formato. Realice los pasos siguientes para cada configuración de ER:

    1. Seleccione **Intercambiar.**
    2. Seleccione **Cargar desde un archivo XML**.
    3. Seleccione **Examinar** y seleccione la configuración necesaria de ER en formato XML.
    4. Seleccione **Aceptar.**

## <a name="review-the-provided-er-solution"></a>Revise la solución de ER proporcionada

### <a name="review-model-mapping"></a>Revisión de la distribución del modelo

1. En el árbol de configuración, expanda el contenido del elemento **Modele para aprender llamadas con parámetros**.
2. Seleccione **Asignación para aprender llamadas con parámetros**.
3. Seleccione **Diseñador**.
4. Seleccione **Diseñador**.  
   
    Esta distribución del modelo de ER está diseñada para hacer lo siguiente:

    - Obtener la lista de códigos de impuestos (origen de datos **Impuestos**) que residen en la tabla **TaxTable**.
    - Obtener la lista de transacciones de impuestos (origen de datos **Impuestos**) que residen en la tabla **TaxTable**:
    
        - Agrupar la lista de transacciones capturadas (origen de datos **Gr**) por código de impuestos.
        - Calcular las transacciones agrupadas que siguen valores agregados por código de impuestos:

            - Sumar los valores de la base fiscal.
            - Sumar los valores de las tasas.
            - Sumar el valor mínimo del índice de impuestos.

    La distribución de modelo en esta configuración implementa el modelo de datos base de todos los formatos ER creados para este modelo y ejecutados en finanzas y operaciones. Como consecuencia, el contenido de los orígenes de datos **Impuesto** y **Gr** se expone para los formatos de ER como orígenes de datos abstractos.

    ![Página de diseñador de distribución de modelo que muestra los orígenes de datos Impuesto y Gr.](media/er-calculated-field-type-01.png)

5.  Cierre la página **Diseñador de distribución del modelo**.
6.  Cierre la página **Distribución del modelo**.

### <a name="review-format"></a>Formato de revisión

1. En el árbol de configuración, expanda el contenido del elemento **Modele para aprender llamadas con parámetros**.
2. Seleccione **Formato para aprender llamadas con parámetros**.
3. Seleccione **Diseñador**. Este formato de ER está diseñado para hacer lo siguiente:

    - Genere un extracto impositivo en formato XML.
    - Mostrar los siguientes niveles de impuestos en el extracto de impuestos: regular, reducido, y ninguno.
    - Actuales varois detalles en cada nivel de impuestos y tener un número distinto de detalles en cada nivel.

    ![Página de diseñador de formato.](media/er-calculated-field-type-02.png)

4. Seleccione **Asignación**.
5. Expanda las entradas **Modelo**, **Datos,** y **Resumen**. 

    El campo calculado **Model.Data.Summary.Level** contiene la expresión que devuelve el código del nivel de impuestos (**Regular**, **Reducido**, **Ninguno,** o **Otro**) como valor de texto para cualquier código de impuestos que se puede recuperar del origen de datos **Model.Data.Summary** en el tiempo de ejecución.

    ![La página del diseñador del formato que muestra los detalles del modelo de datos Model para aprender las llamadas con parámetros.](media/er-calculated-field-type-03.png)

6. Expanda **Model**.**Data2**.
7. Expanda **Model**.**Data2Summary2**.
   
    El origen de datos **Model**.**Data2.Summary2** está configurado para agrupar los detalles de transacción del origen de datos **Model.Data.Summary** por el nivel de impuestos (devuelto por el campo calculado **Model.Data.Summary.Level** ) y calcular las agregaciones.

    ![Página del diseñador del formato que muestra los detalles del origen de datos Model.Data2.Summary2.](media/er-calculated-field-type-04.png)

8. Revise los campos calculados **Model**.**Data2.Level1**, **Model**.**Data2.Level2**, y **Model**.**Data2.Level3.** Estos campos calculados se usan para filtrar la lista de registros de **Model**.**Data2.Summary2** y devolver solamente los registros que representan un nivel determinado de los impuestos.
9. Cierre la página **Diseñador de formato**.

## <a name="create-a-derived-format"></a>Crear un formato derivado
Puede mejorar el formato proporcionado agregando un campo calculado para filtrar el nivel impositivo requerido en lugar de utilizar los tres campos existentes: **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** y **Model**.**Data2.Level3**. El nivel necesario de impuestos se puede especificar en la ubicación donde se llamará a este nuevo campo calculado.

1. En el árbol de configuración, expanda el contenido del elemento **Modele para aprender llamadas con parámetros**.
2. Seleccione **Formato para aprender llamadas con parámetros**.
3. Seleccionar **Crear configuración**.
4. Seleccione **Derivar de nombre: Formato para aprender las llamadas con parámetros, Microsoft**.
5. En el campo **Nombre**, introduzca **Formato para aprender llamadas con parámetros (personalizado)**.
6. Seleccione **Crear configuración.**

## <a name="configure-a-parameterized-calculated-field-that-returns-a-list-of-records"></a>Configurar un campo calculado con parámetros que devuelve una lista de registros

### <a name="start-adding-a-new-calculated-field"></a>Empezar a agregar un nuevo campo calculado

1. Seleccione **Diseñador**.
2. Seleccione **Expandir o contraer/** para expandir todos los elementos de formato.
3. Seleccione **Asignación**.
4. Expanda el elemento **Model**.
5. Seleccione **Model.Data2**.
6. Seleccione **Agregar**.
7. Seleccione **Funciones\\Campo calculado**.
8. En el campo **Nombre**, especifique **Niveles**.
9. Seleccione **Editar fórmula**.

### <a name="define-a-parameter-for-adding-a-calculated-field"></a>Definir un parámetro para agregar un campo calculado

1. Seleccione **Parámetros**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre**, introduzca **Nivel impositivo**.
4. En el campo **Tipo**, seleccione **Cadena**.

    Solo los tipos de datos primitivos se pueden utilizar para especificar el tipo de argumento de parámetros. Por lo tanto, los tipos **Lista de registro**, **registro**, y **Enumeración** no se pueden usar con este propósito.

    El número máximo de parámetros que se pueden especificar para un solo campo calculado es 8.

    ![Lista de orígenes de datos de parámetros.](media/er-calculated-field-type-05.png)

5. Seleccione **Aceptar**.

Si agrega este parámetro, especifica la condición que debe existir en lugar de llamar a este campo calculado. Cuando llama a este campo calculado, debe especificar argumento del parámetro **Nivel impositivo** como valor con el formato **Cadena**.

   Asegúrese de definir parámetros solo para los campos calculados que residen en un contenedor ( **Lista de registros**, **registro**, o **Contenedor**).

   El parámetro configurado está disponible en la lista de orígenes de datos de este campo calculado. Puede agregar el parámetro a la expresión configurada seleccionando **Agregar origen de datos**.

   ![Campo del origen de datos.](media/er-calculated-field-type-06.png)

### <a name="define-an-expression-for-adding-a-calculated-field"></a>Definir una expresión para agregar un campo calculado

1. En el campo **Fórmula**, escriba: 

    **WHERE(\@.Summary2, \@.Summary2.grouped.Level =**
    
2. Seleccione el parámetro **Nivel impositivo** en la lista de orígenes de datos.
3. Seleccione **Agregar origen de datos**.
4. En el campo **Fórmula**, finalice la expresión como:  

    **WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**

5. Seleccione **Guardar**.

    ![Información del campo de origen de datos.](media/er-calculated-field-type-07.png)

6. Cierre la página **Diseñador de fórmula**.

### <a name="finish-adding-a-new-calculated-field"></a>Terminar de agregar un nuevo campo calculado

- Seleccione **Aceptar**.

En la página **Diseñador de formato**, el campo calculado configurado con parámetros **Niveles** requiere un argumento **Cadena**.

![Lista ampliada de niveles del campo calculado.](media/er-calculated-field-type-08.png)

### <a name="use-the-configured-calculated-field-for-binding-format-elements"></a>Use el campo calculado configurado para vincular elementos del formato

1. Seleccione **Model.Data2.Levels** para seleccionar el campo calculado configurado.
2. Seleccione el elemento de formato **Statement.Taxation.Regular**.
3. Seleccione **Enlazar**.
4. Seleccione **Sí** para confirmar la sustitución del origen de datos usado actualmente, **Level1**, para el nuevo origen de datos, **Niveles**, en todos los elementos del formato anidados del elemento del formato seleccionado.

    La vinculación aplicada se ha creado como una llamada del campo calculado con parámetros. De forma predeterminada, el nombre del elemento de formato vinculado se usa como argumento para el campo calculado con parámetros en las condiciones siguientes:

      - El campo calculado se configura para usar un único parámetro.
      - El tipo de datos de este parámetro se define como **Cadena**.

    Cuando el nombre del elemento de formato vinculado está en blanco, el nombre del origen de datos de este elemento se usa en el vínculo aplicado.

5. Seleccione el elemento de formato **Statement.Taxation.Reduced**.
6. Seleccione **Enlazar**.
7. Seleccione **Sí** para confirmar la sustitución del origen de datos usado actualmente, **Level2**, para el nuevo origen de datos, **Niveles**, en todos los elementos del formato anidados en el elemento del formato seleccionado.
8. Seleccione el elemento de formato **Statement.Taxation.None**.
9. Seleccione **Enlazar**.
10. Seleccione **Sí** para confirmar la sustitución del origen de datos usado actualmente, **Level3**, para el nuevo origen de datos, **Niveles**, en todos los elementos del formato anidados en el elemento del formato seleccionado.

   Cuando se especifica el argumento del campo calculado con parámetros para el elemento XML que representa el nivel de impuestos (por ejemplo, **Model.Data2.Levels ("Reduced")** como valor de texto), no es necesario hacer lo mismo para atributos XML anidados -sus vínculos heredarán automáticamente el valor del argumento definido en el nivel principal (**Model.Data2.Levels.aggregated.Base**, no **Model.Data2.Levels("Reduced").aggregated.Base**).

Las llamadas periódicas de cualquier campo calculado con parámetros no se admiten.

Puede seleccionar **Editar fórmula** y cambiar el argumento aplicado de forma predeterminada del campo calculado con parámetros del vínculo seleccionado. Si falta este argumento, puede producir errores en tiempo de ejecución — se informa a los usuarios sobre esta situación cuando se valida el formato actual.

![Notificación de aviso de validación.](media/er-calculated-field-type-10.png)

## <a name="configure-a-parameterized-calculated-field-to-return-a-record"></a>Configurar un campo calculado con parámetros para devolver un registro
Cuando un campo calculado con parámetros devuelve un registro, necesita admitir el vínculo de campos individuales de este registro para dar formato a elementos. En casos como éste no habrá vinculación principal que contenga el valor de un argumento para llamar a un campo calculado con parámetros —este valor debe definirse en la vinculación del campo de un único registro.

### <a name="start-adding-a-new-calculated-field"></a>Empezar a agregar un nuevo campo calculado

1. Seleccione **Model.Data2**.
2. Seleccione **Agregar**.
3. Seleccione **Funciones\\Campo calculado**.
4. En el campo **Nombre**, especifique **LevelRecord**.
5. Seleccione **Editar fórmula**.

### <a name="define-a-parameter-for-adding-a-calculated-field"></a>Definir un parámetro para agregar un campo calculado

1. Seleccione **Parámetros**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre**, introduzca **Nivel impositivo**.
4. En el campo **Tipo**, seleccione **Cadena**.
5. Seleccione **Aceptar**.

### <a name="define-an-expression-for-adding-a-calculated-field"></a>Definir una expresión para agregar un campo calculado

1. En el campo **Fórmula**, introduzca lo siguiente:  
    
    **FIRSTORNULL(\@.Levels(**

2. Seleccione el parámetro **Nivel impositivo**.
3. Seleccione **Agregar origen de datos**.
4. En el campo **Fórmula**, anexe **'Taxation Level'))** a lo que especificó en el paso 1 para finalizar la expresión a:  
    
    **FIRSTORNULL(\@.Levels('Taxation Level'))**

5. Seleccione **Guardar**.
6. Cierre la página **Diseñador de fórmula**.

### <a name="finish-adding-a-new-calculated-field"></a>Terminar de agregar un nuevo campo calculado

-   Seleccione **Aceptar**.

### <a name="use-the-configured-calculated-field-to-bind-format-elements"></a>Use el campo calculado configurado para vincular elementos del formato

1. Expanda **Model.Data2.LevelRecord** para seleccionar el campo calculado configurado.
2. Expanda el contenedor **Model.Data2.LevelRecord.aggregated** del campo calculado configurado.
3. Seleccione el campo **Model.Data2.LevelRecord.aggregated.Base**.
4. Seleccione el elemento de formato **Statement.Taxation.None**.
5. Seleccione **Desenlazar**.
6. Seleccione el elemento de formato **Statement.Taxation.None.Base**.
7. Seleccione **Enlazar**.
8. Seleccione **Editar fórmula**.
9. Cambie la expresión a **Model.Data2.LevelRecord("None").aggregated.Base**.

![Expresión actualizada.](media/er-calculated-field-type-11.png)

## <a name="remove-calculated-fields-that-are-not-used"></a>Quite los campos calculados que no se utilizan

1. Seleccione **Model.Data2.Level1**.
2. Seleccione **Eliminar**.
3. Seleccione **Model.Data2.Level2**.
4. Seleccione **Eliminar**.
5. Seleccione **Model.Data2.Level3**.
6. Seleccione **Eliminar**.
7. Seleccione **Guardar**.

  > [!NOTE]
  > Se reusó el mismo campo calculado **Model.Data2.Levels** varias veces en vínculos de formato. Es mucho más fácil utilizar y mantener un único campo calculado en lugar de hacerlo para varios campos similares.

8. Cierre la página **Diseñador de formato**.

## <a name="complete-adjusted-version-of-a-derived-format"></a>Completar la versión ajustada de un formato derivado

1. En la ficha desplegable **Versiones**, seleccione **Cambiar estado**.
2. Seleccione **Completar**.

## <a name="export-completed-version-of-a-derived-format"></a>Exportar la versión completada de un formato derivado

1. Seleccione el formato **Formato para aprender llamadas con parámetros (personalizado)** en el árbol de las configuraciones.
2. En la ficha desplegable **Versiones**, seleccione la versión 1.1.1 completa.
3. Seleccione **Intercambiar**.
4. Seleccione **Exportar como archivo XML**.
5. Almacene la configuración descargada localmente, en formato XML.

## <a name="test-er-formats"></a>Probar los formatos de ER 
Puede ejecutar los formatos de ER inicial y mejorado para asegurarse de que funcionan los campos calculados con parámetros configurados correctamente.

### <a name="import-er-configurations"></a>Importar configuraciones de ER
Puede importar las configuraciones revisadas de RCS mediante el repositorio de ER del tipo **RCS**. Si ya ha revisado los pasos en el tema, utilice el artículo [Importar configuraciones de informes electrónicos (ER) desde Regulatory Configuration Services (RCS)](rcs-download-configurations.md), use el repositorio de ER configurado para importar las configuraciones tratadas anteriormente en este artículo a su entorno. De lo contrario, siga estos pasos:

1. Seleccione la empresa **DEMF** y en el panel predeterminado, seleccione **Informes electrónicos**.
2. Seleccione **Configuraciones de informes**.
3. Importe las configuraciones desde el Centro de descarga de Microsoft en la siguiente secuencia: modelo de datos, distribución de modelo, formato. Realice los pasos siguientes para cada configuración de ER:

    1. Seleccione **Intercambiar.**
    2. Seleccione **Cargar desde un archivo XML**.
    3. Seleccione **Examinar** para seleccionar la configuración necesaria de ER en formato XML.
    4. Seleccione **Aceptar**.

4. Importe la versión 1.1.1 completada de RCS de formato **Formato para aprender llamadas con parámetros (personalizado)**:

    1. Seleccione **Intercambiar.**
    2. Seleccione **Cargar desde un archivo XML**.
    3. Seleccione **Examinar** para seleccionar el archivo almacenado localmente **Formato para aprender las llamadas con parámetros (personalizado)** en formato XML.
    4. Seleccione **Aceptar**.

### <a name="run-er-formats"></a>Ejecutar los formatos de ER

1. En el árbol de configuración, expanda el contenido del elemento **Modele para aprender llamadas con parámetros**.
2. Seleccione **Formato para aprender llamadas con parámetros**.
3. Seleccione **Ejecutar** en la cinta de opciones superior.
4. Guarde la salida generada localmente.
5. Seleccione **Formato para aprender llamadas con parámetros (personalizado)**.
6. Seleccione **Ejecutar** en la cinta de opciones superior.
7. Guarde la salida generada localmente. 
8. Compare el contenido de las salidas generadas.

## <a name="additional-resources"></a>Recursos adicionales

- [Diseñador de fórmulas en los informes electrónicos (ER)](general-electronic-reporting-formula-designer.md)
- [Mejorar el rendimiento de las soluciones de ER agregando orígenes de datos de CAMPO CALCULADO parametrizados](er-calculated-field-ds-performance.md)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

