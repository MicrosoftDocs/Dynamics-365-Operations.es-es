---
title: Diseñar la interfaz de ejecución de la planta de producción
description: El tema explica cómo configurar los controles de formulario para que se les apliquen los estilos de ejecución predeterminados del piso de producción.
author: johanhoffmann
ms.date: 11/08/2021
ms.topic: article
ms.search.form: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: ef39dc6414f0afdadd4a4b5a41e1fb1fe60e4974
ms.sourcegitcommit: bc9e75c38e192664cde226ed3a94df5a0b304369
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2021
ms.locfileid: "7790899"
---
# <a name="style-the-production-floor-execution-interface"></a>Diseñar la interfaz de ejecución de la planta de producción

[!include [banner](../includes/banner.md)]

El tema explica cómo configurar los controles de formulario para que se les apliquen los estilos de ejecución predeterminados del piso de producción.

## <a name="forms-and-dialogs"></a>Formularios y diálogos

Los estilos se pueden aplicar a un formulario o cuadro de diálogo solo si se cumplen los siguientes requisitos:

- Si el formulario debe parecerse al formulario de progreso del informe existente, el nombre de su formulario o cuadro de diálogo debe comenzar con `JmgProductionFloorExecutionCustomInputDialog`.
- El formulario o cuadro de diálogo puede contener una parte de formulario detallada. Para aplicarle estilos, el nombre de la parte del formulario de detalle debe comenzar con `JmgProductionFloorExecutionCustomDetailsDialog`.
- Si el formulario o cuadro de diálogo debe tener una vista simple, entonces el nombre de la vista simple debe comenzar con `JmgProductionFloorExecutionCustomDialog`. Ejemplos de formularios que tienen una vista simple incluyen el formulario de inicio y el formulario de actividad indirecta.
- Todos los controles del cuadro de diálogo deben configurarse como se describe en este tema.

> [!IMPORTANT]
> Las características mencionadas en los dos primeros puntos de esta lista requieren la versión 10.0.19 o posterior de Supply Chain Management.

Los estilos se pueden aplicar al botón **Aceptar** de un cuadro de diálogo solo si se cumplen los siguientes requisitos:

- El botón está contenido en un grupo de formularios.
- El nombre del grupo comienza con `OkButtonGroup`.

Los estilos se pueden aplicar al botón **Cancelar** de un cuadro de diálogo solo si se cumplen los siguientes requisitos:

- El botón está contenido en un grupo de formularios.
- El nombre del grupo comienza con `CancelButtonGroup`.

### <a name="header"></a>Encabezado

La siguiente ilustración muestra un encabezado de formulario o diálogo típico.

![Encabezado de formulario o diálogo típico.](media/pfe-styles-header.png "Encabezado de formulario o diálogo típico")

En Visual Studio, los encabezados se crean utilizando una estructura como la que se muestra en la siguiente ilustración.

![Estructura de código típica para crear un encabezado.](media/pfe-styles-header-code-structure.png "Estructura de código típica para crear un encabezado")

Para agregar texto a su encabezado, use código como el siguiente ejemplo.

```xpp
private void setCaption()
{
    HeaderFieldWithSeparatorText1.text("Report Progress");
    HeaderFieldWithSeparatorText2.text(ProdId);

    …

    HeaderFieldText.text(OprNum);
}
```

Cuando escriba su código de encabezado, aplique las siguientes reglas:

- El nombre del grupo principal debe ser `TableRowHeaderGroup`.
- Cada bloque de texto (separado por viñetas) debe comenzar con `HeaderFieldWithSeparatorText`.
- El nombre del último texto debe comenzar con `HeaderFieldText`.
- `CaptionImage` se puede omitir.

### <a name="progress-indicator"></a>Indicador de progreso

Puede incluir un indicador de progreso, que se muestra a la derecha del encabezado. La siguiente ilustración muestra un indicador de progreso.

![Indicador de progreso típico.](media/pfe-styles-header-progress.png "Indicador de progreso típico")

Para mostrar el indicador de progreso, el campo de texto debe tener el nombre `ShowProgress`.

## <a name="grid"></a>Cuadrícula

Los estilos se aplican automáticamente. No se requiere ninguna configuración específica.

La cuadrícula debe tener un estilo `TabularView`, y el método `run()` en el formulario personalizado debe sobrescribirse, porque aún no se admite una nueva cuadrícula. Agregue el código siguiente.

```xpp
public void run()
{
    super();
    // To opt out a page from the new grid
    this.forceLegacyGrid();
}
```

Para actualizar los datos en una vista principal, es posible que desee utilizar algo como `this.parmParentForm().updateLayout();` en un método `click` de su acción. (Por ejemplo, mire la clase `JmgProductionFloorExecutionReportFeedbackAction`.) No tiene más que asegurarse de que `parmDataSource` está establecido en el método `init` de su nuevo formulario (`formCaller.parmDataSource(this.dataSource(1));`). Por ejemplo, mire el formulario `JmgProductionFloorExecutionMainGrid`.

## <a name="card-view"></a>Vista de tarjeta

Los estilos se pueden aplicar controles de vista de tarjeta solo si se cumplen los siguientes requisitos:

- Cada vista de tarjeta está contenida en un grupo de formularios.
- El nombre del grupo comienza con `CardGroup` (por ejemplo, `CardGroupJobsView`).

La siguiente ilustración muestra una vista de tarjeta que no tiene controles en su interior.

![Vista de carta sin elementos.](media/pfe-styles-empty-card.png)

Las siguientes ilustraciones muestran vistas de tarjeta que tienen controles en su interior.

![Tarjeta con elementos que muestran Hz.](media/pfe-styles-elements.png)

![Tarjeta con elementos para una solicitud de mantenimiento.](media/pfe-styles-elements-maintenance.png)

## <a name="business-card"></a>Tarjeta de visita

Los estilos se pueden aplicar a controles de tarjeta de visita solo si se cumplen los siguientes requisitos:

- Cada tarjeta de visita está contenida en un grupo de formularios.
- El nombre del grupo comienza con `BusinessCardGroup` (por ejemplo, `BusinessCardGroupJobsList`).

Configure las siguientes propiedades en la tarjeta de presentación:

- **Estilo:** *list*
- **Estilo extendido:** *cardList*
- **Selección múltiple:** *No*
- **Mostrar etiquetas de columna:** *No*

![Tarjeta de visita.](media/pfe-styles-business-card.png)

## <a name="radio-button"></a>Botón de opción

Los estilos se pueden aplicar a botones de opción solo si se cumplen los siguientes requisitos:

- Cada botón de opción está contenido en un grupo de formularios.
- El nombre del grupo comienza con `RadioTextBelow` o `RadioTextRight`, dependiendo de dónde desee que aparezca el texto.

Configure las siguientes propiedades en el botón de opción:

- **Botón de alternancia:** *Comprobar*
- **Valor de alternancia:** *Activado* si se debe seleccionar el botón de radio; de lo contrario, *Desactivado*

La siguiente ilustración muestra un ejemplo en el que el texto aparece debajo de los botones de opción.

![Botones de radio con texto debajo.](media/pfe-styles-radio-text-below.png)

La siguiente ilustración muestra un ejemplo en el que el texto aparece a la derecha de los botones de opción.

![Botones de radio con texto a la derecha.](media/pfe-styles-radio-text-right.png)

### <a name="radio-buttons-in-internet-explorer"></a>Botones de radio en Internet Explorer

Los estilos de botones de opción no se admiten en Internet Explorer. La ilustración siguiente muestra el aspecto de los botones de opción como en Internet Explorer.

![Botones de radio en Internet Explorer.](media/pfe-styles-browser.png)

## <a name="buttons"></a>Botones

Los estilos se pueden aplicar a botones solo si se cumplen los siguientes requisitos:

- Cada grupo de botones está contenido en un grupo de formularios. Todos los botones del grupo tendrán el mismo estilo.
- No hay requisitos sobre el nombre del grupo.

Configure las siguientes propiedades en los botones:

- **Pantalla de botones:** *TextWithImageLeft*
- **Imagen normal:** esta propiedad no puede estar en blanco. Por ejemplo, use *CoffeeScript*.
- **Texto:** esta propiedad no puede estar en blanco. Por ejemplo, use *Iniciar pausa*.
- **Ancho:** *Auto* o *SizeToContent*
- **Alto:** *Auto* o *SizeToContent*

### <a name="primary-button"></a>Botón principal

Los estilos se pueden aplicar a un botón principal solo si se cumplen los siguientes requisitos:

- El botón está contenido en un grupo de formularios.
- El nombre del grupo comienza con `DefaultButtonGroup` o `PrimaryButtonGroup` (por ejemplo, `DefaultButtonGroup10`).

![Botón principal.](media/pfe-styles-first.png)

### <a name="secondary-button"></a>Botón secundario

Los estilos se pueden aplicar a un botón secundario solo si se cumplen los siguientes requisitos:

- El botón está contenido en un grupo de formularios.
- El grupo se llama **Panel derecho** o el nombre del grupo comienza con `SecondaryButtonGroup`.

![Botón secundario.](media/pfe-styles-second.png)

### <a name="third-group-button"></a>Botón de tercer grupo

Los estilos se pueden aplicar a un botón de tercer grupo solo si se cumplen los siguientes requisitos:

- El botón está contenido en un grupo de formularios.
- El grupo se llama **Panel izquierdo** o el nombre del grupo comienza con `ThirdButtonGroup`.

![Botón de tercer grupo.](media/pfe-styles-third.png)

### <a name="fourth-group-button"></a>Botón del cuarto grupo

Los estilos se pueden aplicar a un botón de cuarto grupo solo si se cumplen los siguientes requisitos:

- El botón está contenido en un grupo de formularios.
- El nombre del grupo comienza con `FourthButtonGroup`.

Configure las siguientes propiedades en el botón:

- **Pantalla de botones:** *TextOnly*
- **Imagen normal:** esta propiedad debe estar en blanco.
- **Texto:** esta propiedad no puede estar en blanco. Por ejemplo, use *Ver* o *Editar*.
- **Ancho:** *Auto*
- **Alto:** *Auto*

![Botón del cuarto grupo.](media/pfe-styles-fourth.png)

### <a name="flat-button"></a>Botón plano

Los estilos se pueden aplicar a un botón plano solo si se cumplen los siguientes requisitos:

- El botón está contenido en un grupo de formularios.
- El nombre del grupo comienza con `FlatButtonGroup`.

Configure las siguientes propiedades en el botón:

- **Pantalla de botones:** *ImageOnly*
- **Imagen normal:** esta propiedad no puede estar en blanco. Por ejemplo, use *CoffeeScript*.
- **Texto:** esta propiedad debe estar en blanco.
- **Ancho:** *Auto* o *SizeToContent*
- **Alto:** *Auto* o *SizeToContent*

![Botón plano.](media/pfe-styles-flat-button.png)

### <a name="continue-button"></a>Botón Continuar

Los estilos se pueden aplicar a un botón continuar solo si se cumplen los siguientes requisitos:

- El botón está contenido en un grupo de formularios.
- El nombre del grupo comienza con `ContinueButtonGroup`.

Configure las siguientes propiedades en el botón:

- **Pantalla de botones:** *ImageOnly*
- **Imagen normal:** *Hacia adelante*
- **Texto:** esta propiedad debe estar en blanco.
- **Ancho:** *Auto* o *SizeToContent*
- **Alto:** *Auto* o *SizeToContent*

![Botón Continuar.](media/pfe-styles-continue-button.png)

## <a name="combo-box"></a>Cuadro combinado

Un cuadro combinado es una combinación de tres controles: un control de entrada, un botón que borra el control de entrada y un botón que ejecuta una búsqueda.

Los estilos se pueden aplicar a un cuadro combinado solo si se cumplen los siguientes requisitos:

- El cuadro combinado está contenido en un grupo de formularios.
- El nombre del grupo comienza con `Combobox`.
- Dentro del grupo, el primer control es un control `AxFormStringControl`. Este control muestra el valor actual y es donde el usuario ingresa el valor requerido.
- El segundo control es un control `CommonButton` y su nombre comienza con `ClearButton`. Este botón debe contener código que utilice la propiedad `enable` para mostrar u ocultar el botón. Por ejemplo, para mostrar u ocultar el botón **Borrar** mientras el usuario escribe información en el control de entrada, puede utilizar el siguiente código.

    ```xpp
    public void textChange()
    {
        super();
        ClearButtonSerial.enabled(this.text()? true : false);
    }
    ```

    Debería tener un método en el que los datos se establezcan en el control de entrada. Habilite el botón **Borrar** en ese método. He aquí un ejemplo.

    ```xpp
    public void setSerialId(str _serialId)
    {
        JmgTmpJobBundleProdFeedback.InventSerial = _serialId;
        ClearButtonSerial.enabled(_serialId? true : false);

        if (_serialId)
        {
            this.addSerialNumber();
        }
    }
    ```

    Utilice el siguiente código para el método `clicked` del botón **Borrar**.

    ```xpp
    public void clicked()
    {
        element.setSerialId('');
        InventSerialId.setFocus(); // set focus back to the input box
    }
    ```

    Establecer el valor del control de entrada, `AxFormStringControl`, cuando el formulario se inicializa mediante el método `init`. Si el valor no está en blanco, habilite el botón **Borrar**. Si el valor está en blanco, deshabilite el botón **Borrar**.

- El tercer control es un control `CommonButton` y su nombre comienza con `SearchButton`.

La siguiente ilustración muestra dos controles de cuadro combinado. El cuadro combinado de la izquierda tiene un cuadro de texto vacío y el botón **Borrar** está desactivado. El cuadro combinado de la derecha tiene texto en el cuadro de texto y el botón **Borrar** está activado.

![Cuadros combinados con y sin botón Borrar.](media/pfe-styles-combo.png)

## <a name="quick-filter"></a>Filtro rápido

El control de filtro rápido agrega un campo de búsqueda a la página. Puede aplicar estilos a un filtro rápido siempre que se cumplan los siguientes requisitos:

- El filtro rápido está contenido en un grupo de formularios.
- El nombre del grupo comienza con `SearchInputGroup`.
- Dentro del grupo, el primer control es un control `QuickFilter`. (Este control es donde el usuario ingresa la cadena de búsqueda.)
- El segundo control es un `FormStaticTextControl` que se llama `NumberOfResults`. (Este control es opcional. Si está incluido, muestra la cantidad de artículos encontrados.)
- El tercer control es un control `CommonButton` y su nombre comienza con `ClearButton`.

La siguiente ilustración muestra dos controles de filtro rápido. El filtro rápido de la izquierda tiene un filtro rápido vacío y el número de resultados no es visible. El filtro rápido de la derecha contiene una cadena de búsqueda y muestra el número de resultados.

![Ejemplos de un control de filtro rápido con y sin una cadena de búsqueda.](media/pfe-styles-quick-filter.png "Ejemplos de un control de filtro rápido con y sin una cadena de búsqueda")

## <a name="center-align-elements-on-a-tab"></a>Alinear elementos al centro en una pestaña

Para alinear elementos en el centro de una pestaña, el nombre del grupo debe comenzar con `TabContentGroup` y el grupo debe tener las siguientes propiedades:

- **Modo de ancho:** `SizeToAvailable`
- **Modo de altura:** `SizeToAvailable`

## <a name="align-a-grid-detail-part-and-quick-filter"></a>Alinear una cuadrícula, una parte de detalle y un filtro rápido

Para organizar una cuadrícula personalizada, una parte de detalle y un filtro rápido de modo que se parezcan al diseño estándar, tenga en cuenta los siguientes puntos cuando los coloque juntos:

- Si la cuadrícula tiene un filtro rápido, tanto la cuadrícula como el filtro rápido deben estar dentro del grupo que tiene un nombre que comienza con `GridGroup`.
- Para aplicarle estilos a una parte de detalle, el nombre del grupo debe comenzar con `DetailInformationGroup`,

La siguiente ilustración muestra una cuadrícula típica que incluye un filtro rápido y una parte de detalle a la derecha.

![Cuadrícula típica que incluye un filtro rápido y una parte de detalle.](media/pfe-styles-align-grid.png "Cuadrícula típica que incluye un filtro rápido y una parte de detalle")

En Visual Studio, se pueden crear una cuadrícula, una parte de detalle y un filtro rápido utilizando una estructura como la que se muestra en la siguiente ilustración.

![Estructura de código típica que alinea una cuadrícula, una parte de detalle y un filtro rápido.](media/pfe-styles-header-code-structure2.png "Estructura de código típica que alinea una cuadrícula, una parte de detalle y un filtro rápido")

## <a name="additional-resources"></a>Recursos adicionales

- [Personalizar la interfaz de ejecución de la planta de producción](production-floor-execution-customize.md)
- [Diseñar la interfaz de ejecución de la planta de producción](production-floor-execution-tabs.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
