---
title: Personalizar la interfaz de ejecución de la planta de producción
description: Este tema explica cómo extender los formularios actuales o crear nuevos formularios y botones para la interfaz de ejecución de planta de producción.
author: johanhoffmann
ms.date: 05/04/2022
ms.topic: article
ms.search.form: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-11-08
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: ad5037442f27a5068b38613655591f1298808eac
ms.sourcegitcommit: 28537b32dbcdefb1359a90adc6781b73a2fd195e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712954"
---
# <a name="customize-the-production-floor-execution-interface"></a>Personalizar la interfaz de ejecución de la planta de producción

[!include [banner](../includes/banner.md)]

Los desarrolladores pueden extender los formularios actuales o crear sus propios formularios y botones para la interfaz de ejecución de planta de producción. Una vez que haya agregado el código para estos nuevos elementos, los administradores o gerentes de planta pueden agregarlos fácilmente a la interfaz utilizando los controles de configuración estándar.

Por ejemplo, estas son algunas de las posibles soluciones si se necesitan nuevas columnas en un formulario principal:

- Extienda el formulario `JmgProductionFloorExecutionMainGrid` y agregue los campos deseados.
- Cree un nuevo formulario y agréguelo como una nueva vista principal (pestaña).

## <a name="add-a-new-button-action"></a>Agregar un nuevo botón (acción)

Para agregar un nuevo botón (acción), siga estos pasos para crear una clase que implemente su acción personalizada.

1. Cree una nueva clase que se llame `<ExtensionPrefix>_JmgProductionFloorExecution<ActionName>Action`, donde:

    - `<ExtensionPrefix>` identifica de forma exclusiva su solución, normalmente mediante el nombre de su empresa.
    - `<ActionName>` es un nombre exclusivo para la clase. Por lo general, identifica el tipo de acción.

1. La nueva clase debe extender la clase `JmgProductionFloorExecutionAction`.
1. Reemplace todos los métodos necesarios.

Por ejemplo, mire el código de las siguientes clases:

- `JmgProductionFloorExecutionBreakAction`- Una clase para una acción simple que no necesita ningún registro.
- `JmgProductionFloorExecutionReportFeedbackAction`- Una clase que proporciona una funcionalidad más compleja.

Cuando haya terminado, el nuevo botón (acción) aparecerá automáticamente en la página **Pestañas de diseño** en Microsoft Dynamics 365 Supply Chain Management. Allí, usted (o un administrador o gerente de planta) puede agregarlo fácilmente a la barra de herramientas principal o secundaria, al igual que puede agregar los botones estándar. Para instrucciones, vea [Diseñar la interfaz de ejecución de la planta de producción](production-floor-execution-tabs.md).

## <a name="add-a-new-main-view"></a>Agregar una nueva vista principal

1. Cree un nuevo formulario que tenga los elementos y la funcionalidad deseados. Tenga en cuenta que este formulario es un formulario nuevo, no una extensión. Nombre el formulario `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`, donde:

    - `<ExtensionPrefix>` identifica de forma exclusiva su solución, normalmente mediante el nombre de su empresa.
    - `<FormName>` es un nombre exclusivo para el formulario.

1. Cree un elemento de menú que se llame `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>`.
1. Crea una extensión que se llame `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension`, donde el método `getMainMenuItemsList` se amplía agregando el nuevo elemento de menú a la lista. El código siguiente muestra un ejemplo.

    ```xpp
    [ExtensionOf(classStr(JmgProductionFloorExecutionMenuItemProvider))]
    public final class <ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>_Extension{
        static public List getMainMenuItemsList()
        {
            List menuItemList = next getMainMenuItemsList();
            menuItemList.addEnd(menuItemDisplayStr(<ExtensionPrefix>_JmgProductionFloorExecutionForm<FormName>));
            return menuItemList;
        }
    ```

Cuando haya terminado, la nueva vista principal aparecerá automáticamente en el cuadro combinado **Vista principal** en la página **Pestañas de diseño** en Supply Chain Management. Allí, usted (o un administrador o gerente de planta) puede agregarlo fácilmente a pestañas nuevas o existentes, al igual que puede agregar vistas principales estándar. Para instrucciones, vea [Diseñar la interfaz de ejecución de la planta de producción](production-floor-execution-tabs.md).

## <a name="add-a-details-view"></a>Agregar como vista de detalles

1. Cree un nuevo formulario que tenga los elementos y la funcionalidad deseados. Tenga en cuenta que este formulario es nuevo, no una extensión. Nombre el formulario `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`, donde: 

    - `<ExtensionPrefix>` identifica de forma exclusiva su solución, normalmente mediante el nombre de su empresa.
    - `<FormName>` es un nombre exclusivo para el formulario.

1. Cree un elemento de menú que se llame `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>Detail`.
1. Crea una extensión que se llame `<ExtensionPrefix>_JmgProductionFloorExecution<FormName>_Extension`, donde el método `getDetailsMenuItemList` se amplía agregando el nuevo elemento de menú a la lista.

Cuando haya terminado, la nueva vista de detalles aparecerá automáticamente en el cuadro combinado **Vista de detalles** en la página **Pestañas de diseño** en Supply Chain Management. Allí, usted (o un administrador o gerente de planta) puede agregarlo fácilmente a pestañas nuevas o existentes, al igual que puede agregar vistas de detalles estándar. Para instrucciones, vea [Diseñar la interfaz de ejecución de la planta de producción](production-floor-execution-tabs.md).

## <a name="add-a-numeric-keypad-to-a-form-or-dialog"></a>Agregar un teclado numérico a un formulario o cuadro de diálogo

El siguiente ejemplo muestra cómo agregar teclados numéricos a un formulario.

1. El número de controladores de teclado numérico que contiene cada formulario debe ser igual al número de teclados numéricos de ese formulario.

    ```xpp
    private JmgProductionFloorExecutionNumpadController   numpadController1;
    private JmgProductionFloorExecutionNumpadController   numpadController2;
    private JmgProductionFloorExecutionNumpadController   numpadController3;
    ```

1. Configure el comportamiento de cada controlador de teclado numérico y conecte cada controlador de teclado numérico a una parte del teclado numérico.

    ```xpp
    /// <summary>
    /// Initializes all numpad controllers, defines their behavior and connects them with numpad form parts.
    /// </summary>
    public void initializeNumpadController()
    {
        numpadController1 = new JmgProductionFloorExecutionNumpadController();
        numpadController1.getValueFromNumpadDelegate += eventhandler(this.setQuanityValueFromNumpad_1);
        QuantityNumpad1.getPartFormRun().setNumpadController(numpadController1);
    
        numpadController2 = new JmgProductionFloorExecutionNumpadController();
        numpadController2.parmNumpadEnabled(false);
        numpadController2.parmNumpadValue(333.56);
        numpadController2.getValueFromNumpadDelegate += eventhandler(this.setQuanityValueFromNumpad_2);
        QuantityNumpad2.getPartFormRun().setNumpadController(numpadController2);
    }
    ```

## <a name="use-a-numeric-keypad-as-a-pop-up-dialog"></a>Usa un teclado numérico como cuadro de diálogo emergente

El siguiente ejemplo muestra una forma de configurar un controlador de teclado numérico para un cuadro de diálogo emergente.

```xpp
private void setupNumpadController()
{
    numpadController = new JmgProductionFloorExecutionNumpadController();
    numpadController.parmShouldNumpadShowOkCancelButtons(true);
    numpadController.setNumpadValueToParentFormDelegate += eventhandler(this.setQtyValueFromNumpad);
}
```

El siguiente ejemplo muestra una forma de llamar al diálogo emergente de teclado numérico.

```xpp
Args args = new Args();
args.name(formstr(JmgProductionFloorExecutionNumpad));
args.menuItemName(menuItemDisplayStr(JmgProductionFloorExecutionNumpad));
args.caller(element);
Object formRun = classfactory.formRunClass(args);
formRun.init();
formRun.setNumpadController(numpadController);
numpadController.setValueToNumpad(333.56);
formRun.run();
```

## <a name="add-a-date-and-time-controls-to-a-form-or-dialog"></a>Agregar controles de fecha y hora a un formulario o cuadro de diálogo

Esta sección muestra cómo agregar controles de fecha y hora a un formulario o cuadro de diálogo. Los controles táctiles de fecha y hora permiten a los trabajadores especificar fechas y horas. Las siguientes capturas de pantalla muestran cómo suelen aparecer los controles en la página. El control de tiempo ofrece versiones de 12 y 24 horas; la versión que se muestra seguirá la preferencia establecida para la cuenta de usuario con la que se ejecuta la interfaz.

![Ejemplo de control de fecha](media/pfe-customize-date-control.png "Ejemplo de control de fecha")

![Ejemplo de control de tiempo con reloj de 12 horas.](media/pfe-customize-time-control-12h.png "Ejemplo de control de tiempo con reloj de 12 horas")

![Ejemplo de control de tiempo con reloj de 24 horas.](media/pfe-customize-time-control-24h.png "Ejemplo de control de tiempo con reloj de 24 horas")

El siguiente procedimiento muestra un ejemplo de cómo agregar controles de fecha y hora a un formulario.

1. Agregue un controlador al formulario para cada control de fecha y hora que debe contener el formulario. (El número de controladores debe ser igual al número de controles de fecha y hora en el formulario).

    ```xpp
    private JmgProductionFloorExecutionDateTimeController  dateFromController; 
    private JmgProductionFloorExecutionDateTimeController  dateToController; 
    private JmgProductionFloorExecutionDateTimeController  timeFromController; 
    private JmgProductionFloorExecutionDateTimeController  timeToController;
    ```

1. Declare las variables requeridas (de tipo `utcdatetime`).

    ```xpp
    private utcdatetime fromDateTime;
    private utcdatetime toDateTime;
    ```

1. Cree métodos en los que los controladores de fecha y hora actualicen la fecha y hora. En el ejemplo siguiente se muestra un método como este.

    ```xpp
    private void setFromDateTime(utcdatetime _value)
        {
            fromDateTime = _value;
        }
    ```

1. Configure el comportamiento de cada controlador de fecha y hora, y conecte cada controlador a una parte del formulario. El siguiente ejemplo muestra cómo configurar los datos para los controles de fecha y hora. Puede agregar un código similar para los controles de fecha y hora (no se muestra).

    ```xpp
    /// <summary>
    /// Initializes all date and time controllers, defines their behavior, and connects them with the form parts.
    /// </summary>
    private void initializeDateControlControllers()
    {
        dateFromController = new JmgProductionFloorExecutionDateTimeController();
        dateFromController.setDateControlValueToCallerFormDelegate += eventhandler(this.setFromDateTime);
        dateFromController.parmDateTimeValue(fromDateTime);
    
        timeFromController = new JmgProductionFloorExecutionDateTimeController();
        timeFromController.setDateControlValueToCallerFormDelegate += eventhandler(this.setFromDateTime);
        timeFromController.parmDateTimeValue(fromDateTime);
        
        DateFromFormPart.getPartFormRun().setDateControlController(dateFromController, timeFromController);
        TimeFromFormPart.getPartFormRun().setTimeControlController(timeFromController, dateFromController);
        
        ...

    }
    ```

    Si todo lo que necesita es un control de fecha, puede omitir la configuración del control de tiempo y, en su lugar, configurar el control de fecha como se muestra en el siguiente ejemplo:

    ```xpp
    {
        dateFromController = new JmgProductionFloorExecutionDateTimeController();
        dateFromController.setDateControlValueToCallerFormDelegate += eventhandler(this.setFromDateTime);
        dateFromController.parmDateTimeValue(fromDateTime);
    
        DateFromFormPart.getPartFormRun().setDateControlController(dateFromController, null);
    }
    ```

## <a name="additional-resources"></a>Recursos adicionales

- [Estilo de la interfaz de ejecución de la planta de producción](production-floor-execution-styles.md)
- [Diseñar la interfaz de ejecución de la planta de producción](production-floor-execution-tabs.md)
