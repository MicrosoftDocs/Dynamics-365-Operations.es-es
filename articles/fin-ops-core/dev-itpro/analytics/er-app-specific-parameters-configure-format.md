---
title: Configurar formatos de informes electrónicos para usar parámetros especificados por entidad jurídica
description: En este artículo se explica cómo puede configurar formatos de informes electrónicos (ER) para usar parámetros que se especifican por entidad jurídica.
author: kfend
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.custom: ''
ms.assetid: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
ms.openlocfilehash: b81c9c8fd1639b9af53c8e15a041c00db8c19752
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292688"
---
# <a name="configure-er-formats-to-use-parameters-that-are-specified-per-legal-entity"></a>Configurar formatos de ER para usar parámetros que se especifican por entidad jurídica

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>Visión general

En muchos de los formatos de informes electrónicos (ER) que diseñará, debe filtrar los datos mediante un conjunto de valores que son específicos para cada entidad jurídica de su instancia (por ejemplo, un conjunto de códigos de impuestos para filtrar transacciones de impuestos). Actualmente, cuando el filtrado de este tipo se configura en un formato de ER, los valores que dependan de la entidad jurídica (por ejemplo, los códigos de impuestos) se usan en expresiones del formato de ER para especificar reglas de filtrado de datos. Por lo tanto, el formato de ER se convierte en específico de la entidad jurídica y, para generar los informes necesarios, debe crear copias derivadas del formato de ER original para cada entidad jurídica en la que tenga que ejecutar el formato de ER. Cada formato de ER derivado debe editarse para que incorpore valores específicos de la entidad jurídica, reorganizarse cada vez que se actualice la versión original (base), exportarse desde un entorno de prueba e importarse a un entorno de producción cuando deba implementarse para uso de producción, etc. Por lo tanto, el mantenimiento de este tipo de solución de ER configurada es complejo y largo por varios motivos:

-   Cuantas más entidades jurídicas haya, más configuraciones de formato de ER deberán mantenerse.
-   El mantenimiento de configuraciones de ER requiere que los usuarios empresariales tengan conocimiento de ER.

La característica de parámetros específicos de la aplicación de ER permite a los usuarios avanzados configurar el filtrado de datos en un formato de ER de modo que se base en un conjunto de reglas abstractas. Este conjunto de reglas se puede configurar para utilizar los orígenes de datos disponibles en un formato de ER. Los usuarios empresariales pueden especificar reglas reales más allá del marco de ER mediante la interfaz de usuario (UI) que se genera automáticamente en función de la configuración del formato de ER correspondiente y de los datos de la entidad jurídica actual a los que accederán los orígenes de datos del formato de ER. El conjunto de reglas que se especifica para un formato de ER puede exportarse desde la entidad jurídica actual de la instancia de Dynamics 365 Finance (Finance). Posteriormente, se pude importar en otra entidad jurídica de la misma instancia de Finance o en una instancia diferente como un conjunto de reglas para el mismo formato de ER.

## <a name="prerequisites"></a>Requisitos previos

Para completar los ejemplos de este artículo, debe tener acceso a la instancia de los Regulatory Configuration Services (RCS) que se ha aprovisionado para el mismo que el inquilino que Finance para uno de los siguientes roles:

- Desarrollador de informes electrónicos
- Consultor funcional de informes electrónicos
- Administrador del sistema

Le recomendamos que complete los pasos del artículo [Admitir llamadas con parámetros de orígenes de datos de ER DE tipo CAMPO CALCULADO](er-calculated-field-type.md). Si ya ha completado estos pasos, puede omitir los pasos en la sección **Importar configuraciones de ER en RCS** que sigue a continuación.

## <a name="import-er-configurations-into-rcs"></a>Importar configuraciones de ER en RCS

Descargue y almacene localmente las siguientes configuraciones de ER.

| **Descripción del contenido**                        | **Nombre de archivo**                                        |
|------------------------------------------------|------------------------------------------------------|
| Archivo de configuración del **modelo datos de ER** de ejemplo    | [Modelo para aprender llamadas con parámetros.versión.1.xml](https://download.microsoft.com/download/2/d/b/2db913a0-3622-494e-91a2-97fc494af9b9/Modeltolearnparameterizedcalls.version.1.xml)     |
| Archivo de configuración de **metadatos de ER** de ejemplo      | [Metadatos para aprender llamadas con parámetros.versión.1.xml](https://download.microsoft.com/download/1/b/3/1b343968-5a47-4000-b5a8-6487698ef4c0/Metadatatolearnparameterizedcalls.version.1.xml)  |
| Archivo de configuración de **asignación de modelo de ER** de ejemplo | [Asignación para aprender llamadas con parámetros.versión.1.1.xml](https://download.microsoft.com/download/8/6/6/866e0ab6-2e05-4d98-9d52-d2da2038f6e4/Mappingtolearnparameterizedcalls.version.1.1.xml) |
| Configuración de **formato de ER** de ejemplo             | [Formato para aprender llamadas con parámetros.versión.1.1.xml](https://download.microsoft.com/download/e/3/9/e392eadc-b9b4-4834-95c3-b8066dd00b9c/Formattolearnparameterizedcalls.version.1.1.xml)  |

A continuación, inicie sesión en su instancia de RCS.

En este ejemplo, creará una configuración para la empresa de muestra Litware, Inc. Antes de poder completar este procedimiento, debe completar los pasos del artículo [Creación y activación de un proveedor de configuraciones](tasks/er-configuration-provider-mark-it-active-2016-11.md).

1.  En el panel predeterminado, seleccione **Informes electrónicos**.
2.  Seleccione **Configuraciones de informes**.
3.  Importe las configuraciones de ER que descargó previamente al RCS en el siguiente orden: modelo de datos, metadatos, distribución de modelo y formato. Para cada configuración de ER, siga estos pasos:

    1.  Seleccione **Intercambiar**.
    2.  Seleccione **Cargar desde un archivo XML**.
    3.  Seleccione **Examinar** para seleccionar el archivo para la configuración necesaria de ER en formato XML.
    4.  Seleccione **Aceptar**.

## <a name="review-the-er-solution-that-is-provided"></a>Revisar la solución de ER que se proporciona

1.  En el árbol de configuración, expanda el contenido del elemento **Modelo para aprender llamadas con parámetros**.
2.  Seleccione el elemento **Formato para aprender llamadas con parámetros**.
3.  Seleccione **Diseñador**.
4.  Seleccione **Expandir/Contraer**.

    El formato de ER **Formato para aprender llamadas con parámetros** está diseñado para generar una declaración de impuestos en formato XML que presenta varios niveles de impuestos (normal, reducido y ninguno). Cada nivel tiene un número distinto de detalles.

    ![Múltiples niveles de formato ER, formato para aprender llamadas parametrizadas.](./media/RCS-AppSpecParms-ReviewFormat.PNG)

5.  En la pestaña **Asignación**, expanda los elementos **Modelo**, **Datos** y **Resumen**.

    El origen de datos **Model.Data.Summary** devuelve la lista de transacciones de impuestos. Estas transacciones se resumen por un código de impuesto. Para este origen de datos, el campo calculado **Model.Data.Summary.Level** se ha configurado para devolver el código para el nivel impositivo de cada registro resumido. Para cualquier código de impuestos que se puede recuperar del origen de datos **Model.Data.Summary** en el tiempo de ejecución, el campo calculado devuelve el código del nivel impositivo (**Normal**, **Reducido**, **Ninguno** u **Otro**) como valor de texto. El campo calculado **Model.Data.Summary.Level** se utiliza para filtrar registros del origen de datos **Model.Data.Summary** e introducir los datos filtrados en cada elemento XML que represente el nivel impositivo mediante el uso de los campos **Model.Data2.Level1**, **Model.Data2.Level2** y **Model.Data2.Level3**.

    ![El origen de datos Model.Data.Summary enumera la lista de transacciones de impuestos.](./media/RCS-AppSpecParms-ReviewFormat-Data2Fld.PNG)

    El campo calculado **Model.Data.Summary.Level** se ha configurado para que contenga una expresión de ER. Los códigos de impuestos (**VAT19**, **InVAT19**, **VAT7**, **InVAT7**, **THIRD** e **InVAT0**) están codificados en esta configuración. Por lo tanto, este formato de ER depende de la entidad jurídica en la que se configuraron estos códigos de impuestos.

    ![El campo calculado Model.Data.Summary.Level con códigos de impuestos codificados.](./media/RCS-AppSpecParms-ReviewFormat-LevelFld.PNG)

    Para admitir a un conjunto diferente de códigos de impuestos para cada entidad jurídica, debe seguir estos pasos:

    - Crear una versión derivada del formato de ER para cada entidad jurídica.
    - Actualice los códigos de impuestos en el campo calculado **Model.Data.Summary.Level**, en función de la configuración de la entidad jurídica.

6.  Cierre la página **Diseñador de formato**.

## <a name="create-a-derived-format"></a>Crear un formato derivado

A continuación, utilizará la característica de parámetros específicos de la aplicación de ER para admitir un conjunto diferente de códigos de impuestos para cada entidad jurídica en un único formato de ER.

1.  En el árbol de configuración, expanda el contenido del elemento **Modelo para aprender llamadas con parámetros**.
2.  Seleccione el elemento **Formato para aprender llamadas con parámetros**.
3.  Seleccionar **Crear configuración**.
4.  Seleccione la opción **Derivar de nombre: Formato para aprender las llamadas con parámetros, Microsoft**.
5.  En el campo **Nombre**, introduzca **Formato para aprender a buscar datos de LE**.
6.  Seleccionar **Crear configuración**.

## <a name="configure-a-derived-format"></a>Configurar un formato derivado

### <a name="add-a-format-enumeration"></a>Agregar una enumeración de formato

A continuación, agregará una nueva enumeración de formato de ER. Los valores de esta enumeración de formato se presentarán a los usuarios empresariales, que especificarán conjuntos de códigos de impuestos que dependen de la entidad jurídica para los distintos niveles impositivos que se usan en el formato de ER.

1.  Seleccione **Diseñador**.
2.  Seleccione **Enumeraciones de formato**.
3.  Seleccione **Agregar**.
4.  En el campo **Nombre**, introduzca **Lista de niveles impositivos**.
5.  Seleccione **Guardar**.
6.  En la pestaña **Aplicar formato a valores de enumeración**, seleccione **Agregar**.
7.  En el campo **Nombre**, introduzca **Impuesto normal**.
8.  Seleccione de nuevo **Agregar**.
9.  En el campo **Nombre**, introduzca **Impuesto reducido**.
10. Seleccione de nuevo **Agregar**.
11. En el campo **Nombre**, introduzca **Ningún impuesto**.
12. Seleccione de nuevo **Agregar**.
13. En el campo **Nombre**, introduzca **Otro**.

    ![Nuevo registro en la página Enumeraciones de formato.](./media/RCS-AppSpecParms-ConfigureFormat-Enum.PNG)

    Puesto que los usuarios empresariales pueden usar distintos idiomas para especificar conjuntos de códigos de impuestos que dependen de la entidad jurídica, le recomendamos que traduzca los valores de esta enumeración a los idiomas que se configuren como los idiomas preferidos de esos usuarios en Finance.

14. Seleccione el registro **Ningún impuesto**.
15. Haga clic en el campo **Etiqueta**.
16. Seleccione **Traducir**.
17. En el panel **Traducción de texto**, en el campo **Id. de etiqueta**, introduzca **LBL_LEVELENUM_NO**.
18. En el campo **Texto en el idioma predeterminado**, introduzca **Ningún impuesto**.
19. En el campo **Idioma**, seleccione **DE**.
20. En el campo **Texto traducido**, escriba **keine Besteuerung**.
21. Seleccione **Traducir**.

    ![La traducción de texto se desliza hacia afuera.](./media/RCS-AppSpecParms-ConfigureFormat-EnumTranslate.PNG)

22. Seleccione **Guardar**.
23. Cierre la página **Enumeraciones de formato**.

### <a name="add-a-new-lookup-data-source"></a>Agregar un nuevo origen de datos de la búsqueda

A continuación, agregará un nuevo origen de datos para especificar cómo los usuarios empresariales especificarán reglas que dependen de la entidad jurídica para reconocer el nivel impositivo correcto para cada cada registro de transacción resumido.

1.  En la pestaña **Asignación**, seleccione **Agregar**.
2.  Seleccione **Enumeración de formato\Búsqueda**.

    Acaba de identificar que cada regla que los usuarios empresariales especifiquen para el reconocimiento del nivel impositivo devolverá un valor de una enumeración de formato de ER. Tenga en cuenta que se puede acceder al tipo de origen de datos **Búsqueda** en los bloques **Modelo de datos** y **Dynamics 365 for Operations**, además del bloque **Enumeración de formato**. Por lo tanto, las enumeraciones de modelo de datos de ER y las enumeraciones de aplicación se pueden usar para especificar el tipo de valores que se devuelve para orígenes de datos de ese tipo. Para aprender más sobre el **Buscar** fuentes de datos, ver [Configure las fuentes de datos de búsqueda para utilizar la función de parámetros específicos de la aplicación de ER](er-lookup-data-sources.md).
    
3.  En el campo **Nombre**, especifique **Selector**.
4.  En el campo **Enumeración de formato**, seleccione **Lista de niveles impositivos**.

    Ha especificado que, para cada regla que se especifique en este origen de datos, un usuario empresarial debe seleccionar uno de los valores de la enumeración de formato **Lista de niveles impositivos** como un valor devuelto.
    
5.  Seleccione **Editar búsqueda**.
6.  Seleccione **Columnas**.
7.  Expanda el elemento **Model**.
8.  Expanda el elemento **Datos**.
9.  Expanda el elemento **Impuesto**.
10. Seleccione el elemento **Model.Data.Tax.Code**.
11. Seleccione el botón **Agregar** (la flecha derecha).

    ![Las columnas se deslizan hacia afuera.](./media/RCS-AppSpecParms-ConfigureFormat-Lookup1.PNG)

    Acaba de especificar que, para cada regla que se especifique en este origen de datos para el reconocimiento del nivel impositivo, un usuario empresarial debe seleccionar uno de los códigos de impuestos como una condición. La lista de códigos de impuestos que el usuario empresarial pueden seleccionar será devuelta por el origen de datos **Model.Data.Tax**. Puesto que este origen de datos contiene el campo **Nombre**, el nombre del código de impuestos se mostrará para cada valor de código de impuestos en la búsqueda que se presenta al usuario empresarial.
    
12. Seleccione **Aceptar**.

    ![Página del diseñador de búsquedas.](./media/RCS-AppSpecParms-ConfigureFormat-Lookup2.PNG)

    Los usuarios empresariales pueden agregar varias reglas como registros de este origen de datos. Cada registro se enumerará mediante un código de línea. Las reglas se evaluarán en orden de incremento del número de líneas.

    Puesto que seleccionó el campo **Código de impuesto** como una condición para las reglas de este origen de datos de la búsqueda, y dado que **Código de impuesto** está configurado como un campo del tipo de datos **Cadena**, cada regla se evaluará en tiempo de ejecución comparando el código de impuestos que se pasa al origen de datos con el código de impuestos que se define en este registro del origen de datos.

    Cuando se encuentra una regla que cumple la condición configurada, este origen de datos devuelve el valor de búsqueda de la regla que se define en el campo **Resultado de la búsqueda**. Si no se encuentra ninguna regla, se genera una excepción para notificar al usuario que el origen de datos actual no puede devolver un valor correcto.

13. Seleccione **Guardar**.
14. Cierre la página **Diseñador de búsqueda**.
15. Seleccione **Aceptar**.

    Tenga en cuenta que agregó un nuevo origen de datos que devolverá el nivel impositivo como el valor de la enumeración de formato **Lista de niveles impositivos** para cualquier código de impuestos que se pase al origen de datos como el argumento del parámetro **Código** del tipo de datos **Cadena**.
    
    ![Formatear la página del diseñador con un nuevo origen de datos.](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld.PNG)

    La evaluación de reglas configuradas depende del tipo de datos de los campos que se han seleccionado para definir condiciones de dichas reglas. Cuando seleccione un campo que está configurado como un campo del tipo de datos **Numérico** o **Fecha**, los criterios diferirán de los criterios que se describieron anteriormente para el tipo de datos **Cadena**. Para los campos **Numérico** y **Fecha**, la regla debe especificarse como un intervalo de valores. La condición de la regla se considerará cumplida cuando un valor que se pasa al origen de datos esté en el intervalo configurado.
    
    En la siguiente ilustración se muestra un ejemplo de este tipo de configuración. Además del campo **Model.Data.Tax.Code** del tipo de datos **Cadena**, el campo **Model.Tax.Summary.Base** del tipo de datos **Real** se usa para especificar condiciones para un origen de datos de la búsqueda.
    
    ![Página del diseñador de búsquedas con columnas adicionales.](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld2.PNG)

    Puesto que los campos **Model.Data.Tax.Code** y **Model.Tax.Summary.Base** se seleccionan para este origen de datos de la búsqueda, cada regla de este origen de datos se configurará de la siguiente manera:
    
    -   En la lista que se presenta, el valor de la enumeración de formato **Lista de niveles impositivos** debe seleccionarse como valor devuelto.
    -   El código de impuestos debe especificarse como condición de esta regla. Solo se aplican los códigos de impuestos que son proporcionados por el origen de datos **Model.Data.Tax**.
    -   Los valores mínimo y máximo del importe base de impuestos deben introducirse como condiciones de esta regla.

    Así es cómo cada regla de este origen de datos se evaluará en tiempo de ejecución:
    -   ¿El código del tipo de datos **Cadena** que se pasó a este origen de datos es igual al código de impuestos de una regla?
    -   ¿El valor del tipo de datos **Real** que se pasó a este origen de datos se encuentra entre los valores mínimos y máximos específicos?

    Una regla se considerará aplicable cuando se cumplan las dos condiciones.

### <a name="translate-the-label-of-the-lookup-data-source-that-was-added"></a>Traducir la etiqueta del origen de datos de la búsqueda que se agregó

Puesto que los usuarios empresariales pueden usar distintos idiomas para especificar conjuntos de códigos de impuestos que dependen de la entidad jurídica, le recomendamos que traduzca la etiqueta de cualquier origen de datos de la búsqueda que agregue, de modo que se presente en el idioma preferido de cada usuario en la página correspondiente.

1.  Seleccione el origen de datos **Model.Data.Selector**.
2.  Seleccione **Editar**.
3.  Haga clic en el campo **Etiqueta**.
4.  Seleccione **Traducir**.
5.  En el panel **Traducción de texto**, en el campo **Id. de etiqueta**, introduzca **LBL_SELECTOR_DS**.
6.  En el campo **Texto en el idioma predeterminado**, especifique **Seleccionar nivel impositivo por código de impuesto**.
7.  En el campo **Idioma**, seleccione **DE**.
8.  En el campo **Texto traducido**, escriba **Steuerebene für Steuerkennzeichen auswählen**.
9.  Seleccione **Traducir**.
10. Seleccione **Aceptar**.

    ![Las propiedades del origen de datos se deslizan hacia afuera.](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFldTranslate.PNG)

### <a name="add-a-new-field-to-consume-the-configured-lookup"></a>Agregar un nuevo campo para consumir la búsqueda configurada

1.  Expanda el elemento **Model.Data**.
2.  Seleccione el elemento **Model.Data.Summary**.
3.  Seleccione **Agregar**.
4.  Seleccione **Funciones/Campo calculado**.
5.  En el campo **Nombre**, introduzca **LevelByLookup**.
6.  Seleccione **Editar fórmula**.
7.  En el **campo Fórmula**, introduzca **Model.Selector(Model.Data.Summary.Code)**.
8.  Seleccione **Guardar**.

    ![Agregar Model.Selector(Model.Data.Summary.Code) a la página del diseñador de fórmulas.](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld.PNG)

9.  Cierre la página **Editor de la fórmula**.
10. Seleccione **Aceptar**.

    ![Formatear la página del diseñador con una nueva fórmula agregada.](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld2.PNG)

    Tenga en cuenta que el campo calculado **LevelByLookup** que agregó devolverá el nivel impositivo como el valor de la enumeración de formato **Lista de niveles impositivos** para cada registro de transacciones de impuestos resumido. El código de impuestos del registro pasará al origen de datos de la búsqueda **Model.Selector** y el conjunto de reglas para este origen de datos se utilizará para seleccionar el nivel impositivo correcto.

### <a name="add-a-new-format-enumeration-based-data-source"></a>Agregar un nuevo origen de datos basado en enumeración de formato

A continuación, agregará un nuevo origen de datos que hace referencia a la enumeración de formato que agregó antes. Los valores de este origen de datos se usarán más adelante en una expresión de formato de ER.

1.  Seleccione **Agregar raíz**.
2.  Seleccione **Enumeraciones de formato\Enumeración**.
3.  En el campo **Nombre**, introduzca **TaxationLevel**.
4.  En el campo **Enumeración de formato**, seleccione **Lista de niveles impositivos**.
5.  Seleccione **Guardar**.

### <a name="modify-an-existing-field-to-start-to-use-the-lookup"></a>Modificar un campo existente para empezar a usar la búsqueda

A continuación, modificará el campo calculado existente para que utilice el origen de datos configurado de la búsqueda para devolver el valor del nivel impositivo correcto, en función del código de impuestos.

1.  Seleccione el elemento **Model.Data.Summary.Level**.
2.  Seleccione **Editar**.
3.  Seleccione **Editar fórmula**.

    Tenga en cuenta que la expresión actual del campo **Model.Data.Summary.Level** incluye los siguientes códigos de impuestos codificados:
    
    CASE (@.Code, "VAT19", "Normal", "InVAT19", "Normal", "VAT7", "Reducido", "InVAT7", "Reducido", "THIRD", "Ninguno", "InVAT0", "Ninguno", "Otro")

4.  En el campo **Fórmula**, introduzca **CASE(@.LevelByLookup, TaxationLevel.'Regular taxation', "Normal", TaxationLevel.'Reduced taxation', "Reducido", TaxationLevel.'No taxation', "Ninguno", "Otro")**.

    ![Página de diseñador de operación de ER.](./media/RCS-AppSpecParms-ConfigureFormat-ChangeLookupFld.PNG)
    
    Tenga en cuenta que la expresión del campo **Model.Data.Summary.Level** ahora devolverá el nivel impositivo, en función del código de impuestos del registro actual y el conjunto de reglas que un usuario empresarial configura en el origen de datos de la búsqueda **Model.Data.Selector**.
    
5.  Seleccione **Guardar**.
6.  Cierre la página **Diseñador de fórmula**.
7.  Seleccione **Aceptar**.
8.  Seleccione **Guardar**.
9.  Cierre la página **Diseñador de formato**.

## <a name="complete-the-draft-version-of-a-derived-format"></a>Completar la versión de borrador de un formato derivado

1.  En la ficha desplegable **Versiones**, seleccione **Cambiar estado**.
2.  Seleccione **Completar**.
3.  Seleccione **Aceptar**.

## <a name="export-completed-version-of-modified-format"></a>Exportar versión completada de formato modificado

1.  En el árbol de configuraciones, seleccione el elemento **Formato para aprender a buscar datos de LE**.
2.  En la ficha desplegable **Versiones**, seleccione el registro que tenga estado de **Completado**.
3.  Seleccione **Intercambiar**.
4.  Seleccione **Exportar como archivo XML**.
5.  Seleccione **Aceptar**.
6.  El explorador web descarga un archivo **Formato para aprender a buscar datos de LE.xml**. Almacene este archivo localmente.

Repita los pasos de esta sección para los elementos principales del formato **Formato para aprender a buscar datos de LE** y almacene los siguientes archivos localmente:

-   Formato para aprender llamadas con parámetros.xml
-   Asignación para aprender llamadas con parámetros.xml
-   Modelo para aprender llamadas con parámetros.xml

Para aprender a usar el formato de ER **Formato para aprender a buscar datos de LE** configurado para configurar conjuntos de impuestos que dependen de la entidad jurídica para filtrar transacciones de impuestos por distintos niveles impositivos, complete los pasos del artículo [Configurar los parámetros de un formato de ER por entidad jurídica](er-app-specific-parameters-set-up.md).

## <a name="additional-resources"></a>Recursos adicionales

[Diseñador de fórmulas en los informes electrónicos](general-electronic-reporting-formula-designer.md)

[Configurar los parámetros de un formato de informes electrónicos por entidad jurídica](er-app-specific-parameters-set-up.md)

[Configurar las fuentes de datos de Búsqueda para utilizar la característica de parámetros específicos de la aplicación de ER](er-lookup-data-sources.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
