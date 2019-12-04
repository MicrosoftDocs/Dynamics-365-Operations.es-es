---
title: Implementar campos personalizados para la aplicación móvil de Microsoft Dynamics 365 Project Timesheet en iOS y Android
description: Este tema proporciona los patrones comunes para usar extensiones para implementar campos personalizados.
author: KimANelson
manager: AnnBe
ms.date: 05/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: 10.0.3
ms.search.validFrom: 2019-05-29
ms.openlocfilehash: c0c578ca44919671b67daeea51a9ec7687f755c9
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773654"
---
# <a name="implement-custom-fields-for-the-microsoft-dynamics-365-project-timesheet-mobile-app-on-ios-and-android"></a>Implementar campos personalizados para la aplicación móvil de Microsoft Dynamics 365 Project Timesheet en iOS y Android

[!include [banner](../includes/banner.md)]

Este tema proporciona los patrones comunes para usar extensiones para implementar campos personalizados. Se cubren los siguientes temas:

- Los distintos tipos de datos que el marco de campos personalizados admite
- Cómo mostrar campos de sólo lectura o editables en entradas de hoja de horas y guardar valores proporcionados por el usuario en la base de datos
- Cómo mostrar campos de sólo lectura en el encabezado de la hoja de horas
- Cómo integrar la otra lógica de negocios personalizada para especificar los valores predeterminados en los campos y emitir la validación adicional

## <a name="audience"></a>Audiencia

Este tema se ha creado para los desarrolladores que están integrando sus campos personalizados en la aplicación móvil Microsoft Dynamics 365 Project Timesheet que está disponible para Apple iOS y Google Android. Se asume que el lector está familiarizado con el desarrollo en X++ y la funcionalidad de la hoja de horas de proyecto.

## <a name="data-contract--tstimesheetcustomfield-x-class"></a>Contrato de datos – Clase de X++ TSTimesheetCustomField

La clase **TSTimesheetCustomField** es la clase de contrato de datos de X++ que representa información sobre un campo personalizado para la funcionalidad de la hoja de horas. Las listas de los objetos de campos personalizados se aplican en el contrato de datos de TSTimesheetDetails y el contrato de datos de TSTimesheetEntry para mostrar campos personalizados en la aplicación móvil.

- **TSTimesheetDetails** - El contrato de encabezado de hoja de horas.
- **TSTimesheetEntry** - El contrato de la transacción de la hoja de horas. Grupos de estos objetos con la misma información de proyecto y valor **timesheetLineRecId** constituyen una línea.

### <a name="fieldbasetype-types"></a>fieldBaseType (tipos)

La propiedad **FieldBaseType** en el objeto **TsTimesheetCustom** determina el tipo de campo que aparece en la aplicación. Los valores **Tipos** siguientes se admiten.

| Tipos de valor | Tipo              | Notas |
|-------------|-------------------|-------|
| 0           | Cadena (y Enum) | El campo aparece como campo de texto. |
| 1           | Entero           | El valor se muestra como número sin decimales. |
| 2           | Real              | El valor se muestra como número que tiene decimales.<p>Para mostrar el valor real como divisa en la aplicación, use la propiedad **fieldExtenededType**. Puede utilizar la propiedad **numberOfDecimals** para establecer el número de decimales que se muestran.</p> |
| 3           | Fecha              | Los formatos de fecha son determinados por la configuración **Fecha, horas y formato de número** del usuario que se especifica en **Idioma y preferencia del país/región** en **Opciones de usuario**. |
| 4           | Booleano           | |
| 15          | GUID              | |
| 16          | Int64             | |

- Si la propiedad **stringOptions** no se proporciona en el objeto **TSTimesheetCustomField**, un campo de texto libre se proporciona al usuario.

    La propiedad **stringLength** se puede usar para establecer la longitud máxima de la cadena que los usuarios pueden especificar.

- Si la propiedad **stringOptions** se proporciona en el objeto **TSTimesheetCustomField**, estos elementos de la lista son los únicos valores que los usuarios pueden seleccionar mediante los botones de opción (botones de opción).

    En este caso, el campo de la cadena puede actuar como valor de la enumeración con el fin de entrada de usuario. Para guardar la configuración a la base de datos como enumeración, asigne manualmente el valor de la cadena de nuevo al valor de la enumeración antes de guardar a la base de datos mediante cadena de mando (consulte “Usar la cadena de mando de la clase de TSTimesheetEntryService para guardar una entrada de hoja de horas de la aplicación de nuevo la sección es la base de datos” más adelante en este tema para un ejemplo).

### <a name="fieldextendedtype-tscustomfieldextendedtype"></a>fieldExtendedType (TSCustomFieldExtendedType)

Puede usar esta propiedad para dar formato a valores reales como divisas. Este enfoque es aplicable si el valor **fieldBaseType** es **Real**.

- **TSCustomFieldExtendedType: Ninguno** - No se aplica ningún formato.
- **TSCustomFieldExtendedType::Divisa** - Da formato el valor como divisa.

    Cuando el formato de la divisa está activo, el campo **stringValue** puede ser correcto utilizado el código de divisa que se debe mostrar en la aplicación. El valor es un valor de sólo lectura.

    El campo **realValue** contiene el importe de dinero que se debe guardar en la base de datos.

### <a name="fieldsection-tscustomfieldsection"></a>fieldSection (TSCustomFieldSection)

Puede usar esta propiedad para especificar dónde el campo personalizado debe aparecer en la aplicación.

- **TSCustomFieldSection::Encabezado** - El campo aparecerá en la sección **Ver más detalles** en la aplicación. Estos campos son siempre de sólo lectura.
- **TSCustomFieldSection::Línea** - El campo aparecerá después de todos los campos línea del componente estándar en entradas de la hoja de horas. Estos campos pueden ser editables o de sólo lectura.

### <a name="fieldname-fieldnameshort"></a>fieldName (FieldNameShort)

Esta propiedad identifica el campo cuando los valores que la aplicación proporciona se guardan de nuevo a la base de datos.

### <a name="tablename-tablenameshort"></a>tableName (TableNameShort)

Esta propiedad identifica el campo cuando los valores que la aplicación proporciona se guardan de nuevo a la base de datos.

### <a name="iseditable-noyes"></a>isEditable (NoYes)

Establezca esta propiedad en **Sí** para especificar que el campo en la sección de la entrada de hoja de horas debe ser editables los usuarios. Establezca la propiedad en **No** para crear el campo de sólo lectura.

### <a name="ismandatory-noyes"></a>isMandatory (NoYes)

Establezca esta propiedad en **Sí** para especificar que el campo en la sección de la entrada de hoja de horas debe ser obligatorio.

### <a name="label-str"></a>label (str)

Esta propiedad especifica la etiqueta que se muestra junto al campo en la aplicación.

### <a name="stringoptions-list-of-strings"></a>stringOptions (lista de cadenas)

Esta propiedad solo es aplicable si **fieldBaseType** se establece en **Cadena**. Si se establece **stringOptions**, los valores de cadena disponibles para la selección mediante los botones de opción (botones de opción) son especificados por las cadenas en la lista. Si no se proporciona ninguna cadena, se permite introducir texto libre en el campo cadena (consulte “Usar la cadena de mando de la clase de TSTimesheetEntryService para guardar una entrada de hoja de horas de la aplicación de nuevo la sección es la base de datos” más adelante en este tema para un ejemplo).

### <a name="stringlength-int"></a>stringLength (int)

Esta propiedad especifica la longitud máxima para un campo cadena. Solo es aplicable si **fieldBaseType** se establece en **Cadena**.

### <a name="numberofdecimals-int"></a>numberOfDecimals (int)

Esta propiedad especifica el número de decimales que se muestran para un campo real. Solo es aplicable si **fieldBaseType** se establece en **Real**.

### <a name="ordersequence-int"></a>orderSequence (int)

Esta propiedad controla el orden en que los campos personalizados se muestran en la aplicación cuando se especifica más de un campo personalizado. Los campos que tienen números menores se muestran primero.

### <a name="booleanvalue-boolean"></a>booleanValue (booleano)

Para los campos de tipo **Booleano**, esta propiedad pasa el valor booleano del campo entre el servidor y la aplicación.

### <a name="guidvalue-guid"></a>guidValue (guid)

Para los campos de tipo **GUID**, esta propiedad pasa el valor identificador único global (GUID) del campo entre el servidor y la aplicación.

### <a name="int64value-int64"></a>int64Value (int64)

Para los campos de tipo **Int64**, esta propiedad pasa el valor int64 del campo entre el servidor y la aplicación.

### <a name="intvalue-int"></a>intValue (int)

Para los campos de tipo **Int**, esta propiedad pasa el valor int del campo entre el servidor y la aplicación.

### <a name="realvalue-real"></a>realValue (real)

Para los campos de tipo **Real**, esta propiedad pasa el valor real del campo entre el servidor y la aplicación.

### <a name="stringvalue-str"></a>stringValue (str)

Para los campos de tipo **Cadena**, esta propiedad pasa el valor cadena del campo entre el servidor y la aplicación. También se usa para los campos del tipo **Real** que se aplican el formato como divisa. Para estos campos, la propiedad se usa para pasar el código de divisa a la aplicación.

### <a name="datevalue-date"></a>dateValue (fecha)

Para los campos de tipo **Fecha**, esta propiedad pasa el valor fecha del campo entre el servidor y la aplicación.

## <a name="show-and-save-a-custom-field-in-the-timesheet-entry-section"></a>Muestra y guardar un campo personalizado en la sección de la entrada de hoja de horas

Abajo aparece una captura de pantalla de la aplicación móvil de una creación de la entrada de hoja de horas. Muestra los campos del componente estándar y un campo personalizado en la sección “Entrada de tiempo” llamado "Cadena de prueba" con un valor de enumeración "Segunda opción" ya establecido.

![Campo personalizado de la cadena de prueba en la aplicación](media/timesheet-entry.jpg)



Abajo aparece una captura de pantalla de la aplicación móvil del usuario que selecciona una de las opciones de la enumeración disponibles para el campo personalizado "Cadena de prueba".  Las dos opciones son “Primera opción “y “Segunda opción” y aparecen como botones de opción. La segunda opción está seleccionada actualmente.

![Botones de opción (botones de opción) para el campo personalizado de la cadena de la prueba](media/enum-option.jpg)



### <a name="extend-the-tstimesheetline-table-so-that-it-has-a-custom-field"></a>Extiende la tabla de TSTimesheetLine de modo que tiene un campo personalizado

En situaciones habituales, es probable que los datos de un campo personalizado en la sección de la entrada de hoja de horas son se guarden en la tabla de TSTimesheetLine. Sin embargo, otras tablas se pueden usar si los datos se pueden recuperar según un registro de TSTimesheetTrans que se proporcione, o si no tiene contexto de registro determinado (por ejemplo, si el campo está establecido como de sólo lectura en los parámetros de proyecto).

Tenga en cuenta que los campos personalizados no tienen que tener ningún registros de la base de datos de respaldo. Pueden ser generados dinámicamente en función de la lógica de X++. Este enfoque puede ser útil en escenarios de sólo lectura (consulte “Usar la cadena de mando de la clase de TSTimesheetDetails, el método de buildCustomFieldListForHeader para completar la sección de los detalles de la hoja de horas” para un ejemplo de los valores de forma dinámica generados de campos personalizados.)

Abajo aparece una captura de pantalla Visual Studio del árbol de objetos de aplicación (AOT). Muestra una extensión de la tabla de TSTimesheetLine con el campo de TestLineString agregado como campo personalizado.

![Cadena de la línea](media/b6756b4a3fc5298093327a088a7710fd.png)

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-timesheet-entry-section"></a>Cadena de mando del método de buildCustomFieldList de la clase de TSTimesheetSettings para mostrar un campo en la sección de la entrada de hoja de horas

Este código controla los valores de visualización del campo de la aplicación. Por ejemplo, controla el tipo de campo, la etiqueta, si el campo es obligatorio y en qué sección el campo aparece.

El siguiente ejemplo muestra entradas de un campo de la cadena en el tiempo. Este campo tiene dos opciones, **Primera opción** y **Segunda opción**, que están disponibles mediante los botones de opción (botones de opción). El campo de la aplicación está asociado al campo **TestLineString** que se agrega a la tabla de TSTimesheetLine.

Tega en cuenta el uso del método **TSTimesheetCustomField::(newFromMetatdata)** para simplificar la inicialización de las propiedades del campo personalizado: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength** y **numberOfDecimals**. También puede definir los parámetros manualmente, como prefiera.

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('Second option');
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforentry-method-of-the-tstimesheetentry-class-to-enter-values-in-a-timesheet-entry"></a>Cadena de mando del método de buildCustomFieldListForEntry de la clase de TSTimesheetEntry para introducir valores en la entrada de hoja de horas

El método **buildCustomFieldListForEntry** se utiliza para especificar los valores en las líneas de hoja de horas guardadas en la aplicación móvil. Toma un registro de TSTimesheetTrans como parámetro. Los campos de ese registro se pueden usar para completar el valor del campo personalizado en la aplicación.

```
...
[ExtensionOf(classStr(TsTimesheetEntry))]
final class TsTimesheetEntry_Extension
{
    protected List buildCustomFieldListForEntry(TSTimesheetTrans _tsTimesheetTrans)
    {
        List customFieldList = next buildCustomFieldListForEntry(_tsTimesheetTrans);
        TSTimesheetLine tsTimesheetLine = _tsTimesheetTrans.timesheetLine();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        tsTimesheetCustomField.parmStringValue(tsTimesheetLine.TestLineString);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('second option;);
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-tstimesheetentryservice-class-to-save-a-timesheet-entry-from-the-app-back-to-the-database"></a>Usar la cadena de mando de la clase de TSTimesheetEntryService para guardar una entrada de hoja de horas de la aplicación de nuevo a la base de datos

Para guardar un campo personalizado de nuevo a la base de datos en uso habitual, debe extender varios métodos:

- El método **el timesheetLineNeedsUpdating** se usa para determinar si el usuario de la aplicación ha cambiado registro de la línea y se debe guardar en la base de datos. Si el rendimiento no es una preocupación, este método puede ser simplificado de modo que devuelva siempre **verdadero**.
- Los métodos **populateTimesheetLineFromEntryDuringCreate** y **populateTimesheetLineFromEntryDuringUpdate** se pueden ampliar de modo que especifiquen valores en el registro de base de datos de TSTimesheetLine de registro de contrato de datos de TSTimesheetEntry que se proporciona. En el ejemplo siguiente, note cómo la asignación entre el campo de base de datos y el campo de entrada se hace manualmente mediante código X++.
- El método **populateTimesheetWeekFromEntry** también se puede extender si el campo personalizado asignado al objeto **TSTimesheetEntry** debe escribir de nuevo a la tabla de base de datos de TSTimesheetLineweek.

> [!NOTE]
> El siguiente ejemplo guarda el **firstOption** o el valor **secondOption** que el usuario selecciona a la base de datos como valor de cadena sin formato. Si el campo de base de datos es un campo del tipo **Enum**, estos valores pueden asignarse manualmente a un valor de enumeración y luego guardar un campo de la enumeración en la tabla de base de datos.

```
...
[ExtensionOf(classStr(TSTimesheetEntryService))]
final class TSTimesheetEntryService_Extension
{
    protected boolean timesheetLineNeedsUpdating(TSTimesheetLine _tsTimesheetLine,
    TsTimesheetEntry _tsTimesheetEntry)
    {
        boolean ret = next timesheetLineNeedsUpdating(_tsTimesheetLine,
        _tsTimesheetEntry);
        if (!ret)
        {
            */ Loop through custom fields to see if value needs updating*/
            ListEnumerator enumerator =  _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    */ If Custom field value for TestLineString field has changed, We need to update the timesheet line.*/
                    if (_tsTimesheetLine.TestLineString != customField.parmStringValue())
                    {
                        ret = true;
                    }
                }
            }
        }
        return ret;
    }
    protected void populateTimesheetLineFromEntryDuringCreate(TSTimesheetLine
    _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
    {
        next populateTimesheetLineFromEntryDuringCreate(_tsTimesheetLine,
        _tsTimesheetEntry);
        this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
        _tsTimesheetEntry);
        }
        protected void populateTimesheetLineFromEntryDuringUpdate(TSTimesheetLine
        \_tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            next populateTimesheetLineFromEntryDuringUpdate(_tsTimesheetLine,
            _tsTimesheetEntry);
            this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
            _tsTimesheetEntry);
        }
        private void populateTimesheetLineFromCustomFields(TSTimesheetLine
        _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            ListEnumerator enumerator =
            _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    _tsTimesheetLine.TestLineString = customField.parmStringValue();
                }
            }
        }
    }
...
```

## <a name="show-a-custom-field-in-the-timesheet-header-section"></a>Muestra un campo personalizado en la sección del encabezado de hoja de horas

Abajo aparece una captura de pantalla de la aplicación de un usuario viendo una hoja de horas. El botón de “Más información” se ha seleccionado en la esquina superior derecha para mostrar la opción “Ver más detalles".  

![Comando Ver más detalles](media/show-more.png)

Abajo aparece una captura de pantalla de la aplicación mostrando la sección "Más" de una hoja de horas. Un campo personalizado denominado “Tasa de utilización de esta hoja de horas (campo personalizado calculado)” se ha agregado a la sección de encabezado de hoja de horas. Un valor de sólo lectura de “0,667 " se establece en el campo personalizado.

![Sección Más](media/more-section.jpg)

### <a name="extend-the-tstimesheettable-table-so-that-it-has-a-custom-field"></a>Extiende la tabla de TSTimesheetTable de modo que tiene un campo personalizado

En situaciones habituales, es probable que los datos de un campo personalizado en la sección del encabezado de hoja de horas se extraigan de la tabla TSTimesheetHeader. Sin embargo, otras tablas se pueden usar si los datos se pueden recuperar según un registro de TSTimesheetTable que se proporcione, o si no tiene contexto de registro determinado (por ejemplo, si el campo está establecido como de sólo lectura en los parámetros de proyecto).

Tenga en cuenta que los campos personalizados no tienen que tener ningún registros de la base de datos de respaldo. Pueden ser generados dinámicamente en función de la lógica de X++. El siguiente ejemplo muestra este planteamiento.

Los campos de la sección de encabezado son siempre de sólo lectura en la aplicación.

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-header-section"></a>Usar la cadena de mando del método de buildCustomFieldList de la clase de TSTimesheetSettings para mostrar un campo en la sección del encabezado.

Este código controla los valores de visualización del campo de la aplicación. Por ejemplo, controla el tipo de campo, la etiqueta, si el campo es obligatorio y en qué sección el campo aparece.

El ejemplo siguiente muestra un valor calculado en la sección de encabezado en la aplicación.

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforheader-method-of-the-tstimesheetdetails-class-to-fill-in-timesheet-details"></a>Cadena de mando del método de buildCustomFieldListForHeader de la clase de TSTimesheetDetails para rellenar los detalles de la hoja de horas

El método **buildCustomFieldListForHeader** se utiliza para rellenar los valores del encabezado en la hoja de horas en la aplicación móvil. Toma un registro de TSTimesheetTable como parámetro. Los campos de ese registro se pueden usar para completar el valor del campo personalizado en la aplicación. El siguiente ejemplo no lee ningún valor de la base de datos. En su lugar, usa lógica X++ para generar un valor calculado que se muestre en la aplicación.


```
...
[ExtensionOf(classStr(TSTimesheetDetails))]
final class TSTimesheetDetails_Extension
{
    protected List buildCustomFieldListForHeader(TSTimesheetTable
    _tsTimesheetTable)
    {
        List customFieldList = next buildCustomFieldListForHeader(_tsTimesheetTable);
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        real utilizationRate = 0;
        if (_tsTimesheetTable.totalHours() != 0)
        {
            utilizationRate = _tsTimesheetTable.totalHoursBillable() /
            _tsTimesheetTable.totalHours();
        }
        tsTimesheetCustomField.parmRealValue(utilizationRate);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

## <a name="other-configurabilityextensibility-opportunities"></a>Otras oportunidades de la flexibilidad de configuración o la extensibilidad

### <a name="adding-additional-validation-for-the-app"></a>Agregar una validación adicional para la aplicación

La lógica existente para la funcionalidad de la hoja de horas en el nivel de la base de datos aún funcionará como esperado. Para suspender la finalización de guardar o enviar operaciones y mostrar un mensaje de error específico, puede agregar **error de captura (“mensaje para el usuario”)** al código mediante una extensión de la cadena de mando. Aquí tiene tres ejemplos de métodos de extensión útiles:

- Si **validateWrite** en la tabla de TSTimesheetLine devuelve **falso** durante una operación de guardado para una línea de hoja de horas, un mensaje de error se muestra en la aplicación móvil.
- Si **validateSubmit** en la tabla de TSTimesheetTable devuelve **falso** durante el envío de una hoja de horas en la aplicación, un mensaje de error se muestra al usuario.
- La lógica que complete campos (por ejemplo, **Propiedad de línea**) durante el método **inserción** en la tabla de TSTimesheetLine se ejecutará de todas formas.

### <a name="hiding-and-marking-out-of-box-fields-as-read-only-via-configuration"></a>Ocultar y marcar componente estándar como los campos de sólo lectura a través de la configuración

De los parámetros de proyecto, puede crear campos del componente estándar de sólo lectura o ocultarán en la aplicación móvil. Establezca las opciones de la sección **Hojas de horas móviles** en la pestaña **Hoja de horas** de la página **Gestión de proyectos y contabilidad**.

![Parámetros del proyecto](media/5753b8ecccd1d8bb2b002dd538b3f762.png)

### <a name="changing-the-activities-that-are-available-for-selection-via-extensions"></a>Cambiando las actividades disponibles para la selección a través de extensiones

Las actividades disponibles para la selección de un proyecto se completan a través de los métodos **(getActivitiesForProject)** y **(getActivityQuery)** en la clase **TsTimesheetProjectService**. Puede usar la cadena de mando para cambiar este comportamiento para coincidir con su escenario empresarial para las actividades que están disponibles para la selección para un proyecto específico.

### <a name="entering-a-default-project-category-on-timesheet-entries"></a>Especificación de una categoría de proyecto predeterminada en entradas de la hoja de horas

Escribir una categoría de proyecto predeterminada en entradas de la hoja de horas tiene lugar a tres niveles. Puede usar la cadena de mando para ampliar el comportamiento en cualquiera de estos niveles para lograr el comportamiento deseado. Se usa la siguiente jerarquía:

1. La aplicación intenta poner la categoría predeterminada del recurso del proyecto. Esta categoría predeterminada se establece en los métodos **getCurrentUserResource** y **getDelegatedResourcesForCurrentUser** en la clase **TSTimesheetSettingsService**.
2. Si la categoría predeterminada no se proporciona en el nivel del recurso del proyecto, la aplicación intentará extraerlo de la actividad de proyecto. Esta categoría predeterminada se configura en el método **getActivitiesForProject** en la clase **TSTimesheetProjectService**.
3. Si la categoría predeterminada no se proporciona en el nivel de actividad del proyecto, la categoría predeterminada se tomará de los parámetros del proyecto. Esta categoría predeterminada se configura en el método **getProjectDetailsbyRule** en la clase **TSTimesheetProjectService**.
