---
title: Insertar aplicaciones de lienzo desde Power Apps
description: Este tema explica cómo insertar aplicaciones de lienzo de Microsoft Power Apps en el cliente para aumentar la funcionalidad de producto.
author: jasongre
ms.date: 08/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: 37ef6101a5a69e9c820347dd6f61c987467d40b3
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344538"
---
# <a name="embed-canvas-apps-from-power-apps"></a>Insertar aplicaciones de lienzo desde Power Apps

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Microsoft Power Apps es un servicio que permite tanto a desarrolladores como a usuarios no técnicos crear aplicaciones empresariales personalizadas para dispositivos móviles, tabletas y la Web sin escribir código. Las aplicaciones de Finance and Operations admiten la integración con Power Apps. Las aplicaciones de lienzo que usted, su organización,o el ecosistema más amplio desarrollan se pueden insertar en las aplicaciones de Finance and Operations para aumentar la funcionalidad de producto. Por ejemplo, puede crear una aplicación de lienzo en Power Apps que complemente a la aplicación de Finance and Operations con información recuperada de otro sistema.

Para obtener más información acerca de la integración de aplicaciones de lienzo, vea el vídeo corto [Cómo insertar aplicaciones de lienzo](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-canvas-app-from-power-apps-to-a-page"></a>Agregar una aplicación de lienzo de Power Apps incrustada a una página

Antes de incrustar una aplicación de lienzo de Power Apps en el cliente, primero debe encontrar o compilar una aplicación con las representaciones visuales y/o la funcionalidades deseadas. Este tema no incluye una descripción detallada del proceso para crear aplicaciones. Si es nuevo en Power Apps, mire la [documentación de Power Apps](/powerapps/).

Hay tres formas de insertar una aplicación de lienzo en una aplicación de Finance and Operations. Puede utilizar el enfoque que se adapte mejor a su escenario. 

- Inserte la aplicación de lienzo en el botón **Power Apps** del panel de acciones estándar de una página. Las aplicaciones que agrega de esta manera aparecen como elementos en el botón de menú **Power Apps** y las aplicaciones se abren en los paneles laterales. 
- Inserte la aplicación de lienzo directamente en una página existente como una página de pestaña nueva (pestaña dinámica, pestaña desplegable, hoja o sección del espacio de trabajo).
- Cree una nueva experiencia de página completa para la aplicación de lienzo desde el panel.

Al configurar la aplicación de lienzo incrustada, puede seleccionar un solo campo que desee enviar como contexto a la aplicación. Este paso permite que la aplicación tenga capacidad de respuesta basándose en los datos que está viendo actualmente.

> [!NOTE]
> No puede usar este mecanismo para insertar aplicaciones basadas en modelos.

### <a name="embedding-a-canvas-app-on-an-existing-page"></a>Insertar una aplicación de lienzo en una página existente

El siguiente procedimiento muestra cómo insertar una aplicación de lienzo en una página existente de Power Apps.

1. Vaya a la página en la que desee insertar la aplicación de lienzo. Esta página contendrá los datos que deben pasarse a la aplicación como entrada.
2. Abra el panel **Agregar una aplicación desde Power Apps**:

    - Si la aplicación se va a insertar directamente en la página, seleccione **Opciones** \> **Personalizar esta página** \> **Más** y siga uno de estos pasos:

        - Si la característica **Aplicaciones de página completa** está activada, seleccione **Agregar una página** y, a continuación, seleccione la región en la que desea agregar la aplicación. Para insertar la aplicación en el botón de menú de **Power Apps**, seleccione el panel de acciones. Para insertar la aplicación directamente en la página, seleccione la pestaña correspondiente, la ficha desplegable, la hoja o la sección adecuadas (si se encuentra en un espacio de trabajo). A continuación, en el panel **Agregar una aplicación**, seleccione **Power Apps**.
        - Si la característica **Aplicaciones de página completa** está desactivada, seleccione **Agregar una aplicación desde Power Apps** y, a continuación, seleccione la región en la que desea agregar la aplicación. Para insertar la aplicación en el botón de menú de **Power Apps**, seleccione el panel de acciones. Para insertar la aplicación directamente en la página, seleccione la pestaña correspondiente, la ficha desplegable, la hoja o la sección adecuadas (si se encuentra en un espacio de trabajo).

    - Si se va a acceder a la aplicación mediante el botón de menú de **Power Apps**, de forma alternativa puede hacer clic en el botón del menú de **Power Apps** en el panel de acciones estándar y, a continuación, seleccionar **Agregar una aplicación**.

3. Configure la aplicación insertada. Para obtener más información, consulte la sección [Configurar una aplicación de lienzo](#configuring-a-canvas-app) más adelante en este tema.
4. Cuando haya confirmado que la configuración es correcta, seleccione **Insertar**.

    - Si la característica **Vistas guardadas** está desactivada, se le pedirá que actualice el explorador para ver la aplicación insertada.
    - Si la característica **Vistas guardadas** está activada, debe guardar la vista para que el cambio persista.

### <a name="embedding-a-canvas-app-as-a-full-page-experience-from-the-dashboard"></a>Insertar una aplicación de lienzo como una experiencia de página completa desde el panel de información

Es posible que desee insertar una aplicación de lienzo desde el panel de información si la aplicación no está relacionada con una página existente, o si desea que la aplicación solo se vea como una experiencia de página completa dentro de la aplicación de Finance and Operations.

> [!NOTE]
> Para que esta capacidad esté disponible, debe activar la característica **Aplicaciones de página completa** en la Administración de características. 

1. Abra el panel.
2. Seleccione y mantenga presionada (o haga clic con el botón derecho) la página, seleccione **Personalizar** y luego seleccione **Agregar una página**.
3. En el panel **Agregar una página**, seleccione **Power Apps**.
4. Configure la aplicación insertada. Para obtener más información, consulte la sección [Configurar una aplicación de lienzo](#configuring-a-canvas-app) más adelante en este tema.
5. Seleccione **Guardar** para agregar la aplicación al panel de información como un nuevo mosaico.
6. Seleccione el nuevo icono en el panel de información y confirme que la aplicación de lienzo aparece como se esperaba.

### <a name="configuring-a-canvas-app"></a>Configurar una aplicación de lienzo

Al insertar una aplicación de lienzo, debe establecer los siguientes parámetros:

- **Nombre**: escriba el texto que debe mostrarse para el botón o la pestaña que va a contener la aplicación insertada. Muchas veces puede que desee repetir el nombre de la aplicación en este campo.
- **Id. de aplicación**: indica el identificador único global (GUID) de la aplicación de lienzo que desea insertar. Para recuperar este valor, encuentre la aplicación en [make.powerapps.com](https://make.powerapps.com) y después mire en el campo **Identificador de la aplicación** en **Detalles**.
- **Contexto de entrada para la aplicación**: opcionalmente, puede seleccionar el campo que contiene los datos que desea pasar a la aplicación como entrada. Para obtener información detallada sobre cómo la aplicación puede tener acceso a los datos enviados desde aplicaciones de Finance and Operations, consulte la sección [Creación de una aplicación que aproveche los datos enviados desde aplicaciones de Finance and Operations](#building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps) que figura más adelante en este tema.

    A partir de la versión 10.0.19, la entidad jurídica actual también se pasará a la aplicación de lienzo como contexto a través del parámetro de URL **cmp**. Este comportamiento no afectará a la aplicación de lienzo de destino hasta que la aplicación use esa información.

- **Tamaño de la aplicación**: seleccione el tipo de aplicación que va a insertar. Seleccione **Fino** para aplicaciones creadas para dispositivos móviles y **Ancho** para aplicaciones creadas para tabletas. Este parámetro garantiza que se asigne una cantidad de espacio suficiente para la aplicación incrustada.
- **Entidades jurídicas**: puede seleccionar las entidades jurídicas para las que la aplicación debería estar disponible. De forma predeterminada, la aplicación está disponible para todas las entidades jurídicas. Esta opción solo está disponible cuando se inserta directamente en una página existente y la características **[Vistas guardadas](saved-views.md)** está desactivada.

## <a name="sharing-an-embedded-app"></a>Uso compartido de una aplicación incrustada

Una vez que haya insertado una aplicación de lienzo en una página y confirmado que funciona correctamente, puede que desee compartir la aplicación con otros usuarios en el sistema. Para compartir una aplicación de lienzo incrustada, siga estos pasos.

1. Puede [Compartir la aplicación de lienzo en Power Apps](/powerapps/maker/canvas-apps/share-app) con los usuarios adecuados, para que puedan acceder a la aplicación en Power Apps.
2. Comparta con los usuarios que desee las personalizaciones asociadas con la aplicación insertada. Puede usar los siguientes enfoques:

    - **Publicar la vista (recomendado):** si la característica **[Vistas guardadas](saved-views.md)** está activada, el enfoque recomendado y preferido es crear una vista que incluya la aplicación de lienzo insertada y publicar esa vista para los usuarios deseados. Este enfoque garantiza que todos los usuarios que tienen los roles de seguridad a los que se dirige la vista publicada verán la aplicación de lienzo en la página.

        También puede publicar una aplicación de lienzo que se haya insertado como una experiencia de página completa desde el panel. En el tablero, seleccione y mantenga presionado (o haga clic con el botón derecho) en el mosaico asociado con la aplicación, seleccione **Personalizar** y luego seleccione **Publicar página**. Se muestra una experiencia que se asemeja a la experiencia *Publicar vistas*, y puede seleccionar los roles de seguridad en los que desea publicar. En la actualización 10.0.21 o posterior, si la característica **Compatibilidad mejorada con entidades jurídicas para vistas guardadas** está activada, también puede publicar la aplicación para las entidades jurídicas deseadas.

    - Si la característica **Vistas guardadas** está desactivada, el administrador del sistema puede dar una personalización que incluya la aplicación de lienzo al conjunto de usuarios adecuado a través de la página **Personalización**. Como alternativa, puede exportar las personalizaciones de la página y enviarlas a uno o más usuarios. Cada uno de esos usuarios podrá importar la personalización. La barra de herramientas de personalización tiene botones que permiten exportar e importar personalizaciones.

> [!NOTE]
> Si la aplicación de lienzo se ha compartido con usuarios externos, esos usuarios no pueden usar la aplicación incorporada dentro de aplicaciones de Finance and Operations. Sin embargo, pueden acceder a la aplicación directamente desde Power Apps. Los usuarios externos incluyen invitados y usuarios que no pertenecen al directorio de Azure de Microsoft 365 donde la aplicación de Finance and Operations está implementada.

Consulte [Personalizar la experiencia del usuario](personalize-user-experience.md) para obtener más detalles sobre las capacidades de personalización en el producto y cómo utilizarlas.

## <a name="building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps"></a>Creación de una aplicación de lienzo que utiliza datos enviados desde aplicaciones de Finance and Operations

Cuando crea una aplicación de lienzo que se incrustará en una aplicación de Finance and Operations, una parte importante del proceso es utilizar los datos de entrada de esa aplicación de Finance and Operations. Desde la experiencia de desarrollo de Power Apps, se puede acceder a los datos de entrada que se pasan desde una aplicación de Finance and Operations utilizando la variable **Param("EntityId")**. Además, a partir de la versión 10.0.19, la entidad jurídica actual también se pasará como contexto a la aplicación de lienzo a través de la variable **Param("cmp")**. 

Por ejemplo, en la función de OnStart de la aplicación, puede establecer los datos de entrada desde aplicaciones de Finance and Operations en una variable como esta:

``` Power Apps
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));

If(!IsBlank(Param("cmp")), Set(FinOpsLegalEntity, Param("cmp")), Set(FinOpsLegalEntity, ""));
```

## <a name="viewing-a-canvas-app"></a>Ver una aplicación de lienzo

Para ver una aplicación de lienzo incrustada en una página de aplicaciones de Finance and Operations, simplemente vaya a una página con una aplicación incrustada. Recuerde que se puede acceder a las aplicaciones mediante el botón **Power Apps** en el panel de acciones estándar. Como alternativa, pueden aparecer directamente en la página como nueva ficha, ficha desplegable u hoja, o como nueva sección en un área de trabajo. Cuando los usuarios intentan cargar una aplicación en una página por primera vez, se les pedirá que inicien sesión. Este paso asegura que los usuarios tengan los permisos adecuados para usar la aplicación.

## <a name="editing-an-embedded-app"></a>Editar una aplicación incrustada

Después de que una aplicación se haya insertado en una página, puede ser necesario realizar algunos cambios en la configuración de dicha aplicación. Por ejemplo, tal vez desee modificar la etiqueta asociada a la aplicación incrustada o una nueva versión de la aplicación se ha creado y necesita actualizar el id. de la aplicación para señalar a la última versión.

Siga estos pasos para editar la configuración de una aplicación incrustada:

1. Vaya al panel **Editar la aplicación**.

    - Si se accede a la aplicación incrustada a través del botón de menú de Power Apps, seleccione y mantenga presionado (o haga clic con el botón secundario en) el botón de menú de Power Apps y seleccione **Personalizar**. Seleccione la aplicación que desea configurar en el menú desplegable **Seleccionar una aplicación**.
    - Si la aplicación incrustada aparece directamente en la página, seleccione **Opciones** y, después, seleccione **Personalizar esta página**. Mediante la herramienta **Seleccionar**, haga clic en la aplicación incrustada.
    - Si la aplicación insertada se agregó desde el panel de información, abra el panel, seleccione y mantenga presionado (o haga clic con el botón derecho en) el icono asociado con la aplicación de lienzo, seleccione **Personalizar** y, a continuación, seleccione **Editar página**.

2. Haga las modificaciones necesarias a la configuración de la aplicación y, a continuación, haga clic en **Guardar**.

## <a name="removing-an-app"></a>Eliminar una aplicación

Después de insertar una aplicación en una página, hay algunas maneras de quitarla si es necesario:

- Vaya al panel **Editar una aplicación** mediante las instrucciones de [Editar una aplicación incrustada](#editing-an-embedded-app) en la sección anterior en este tema. Confirme que el panel muestra información para la aplicación incrustada que desea quitar y haga clic en el botón **Eliminar**.
- Si la aplicación insertada se agregó desde el panel de información, abra el panel, seleccione y mantenga presionado (o haga clic con el botón derecho en) el icono asociado con la aplicación de lienzo, seleccione **Personalizar** y, a continuación, seleccione **Quitar página**. 
- Debido a que la aplicación incrustada está guardado como datos de personalización, desactivando la personalización de su página también quitará cualquier aplicación incrustada en la página. Tenga en cuenta que borrar la personalización de la página es permanente y no se puede deshacer. Para quitar sus personalizaciones de una página, seleccione **Opciones** y después haga clic en **Personalizar esta página** y finalmente en el botón **Borrar**. Después de actualizar su explorador, todas las personalizaciones anteriores para esta página se quitarán. Consulte [Personalizar la experiencia del usuario](personalize-user-experience.md) para obtener más información sobre cómo optimizar páginas utilizando la personalización.

## <a name="appendix"></a>Apéndice

### <a name="developer-modeling-a-canvas-app-on-a-form"></a>[Desarrollador] Modelado de una aplicación de lienzo en un formulario

Si bien este tema se centra en la incrustación de aplicaciones de lienzo mediante la personalización, los desarrolladores también tienen la opción de agregar una aplicación de lienzo a un formulario mediante la experiencia de desarrollo de Visual Studio. Para hacer esto, simplemente agregue un PowerAppsHostControl al formulario. Las propiedades de metadatos disponibles en el control brindan las mismas capacidades que la experiencia de personalización.

### <a name="developer-specifying-where-an-app-can-be-embedded"></a>[Desarrollador] Especificar dónde se puede insertar una aplicación

De forma predeterminada, los usuarios pueden insertar aplicaciones en cualquier página, en el botón de menú de Power Apps o directamente en la página como una ficha, ficha desplegable, hoja o como una nueva sección en un espacio de trabajo. Sin embargo, si procede, los desarrolladores también podrían configurar esta función para permitir solo insertar aplicaciones en determinadas páginas implementando los métodos siguientes:

- **isPowerAppPersonalizationEnabled** - Si este método devuelve un valor falso en una página determinada, el botón de menú de Power Apps no se mostrará y los usuarios no podrán insertar aplicaciones en ningún lugar de esta página, ni como ficha.
- **isPowerAppTabPersonalizationEnabled** - Si este método devuelve un valor falso en una página determinada, los usuarios no podrán insertar aplicaciones directamente en la página como una ficha, ficha desplegable o sección de panorama. Los usuarios podrán seguir insertando aplicaciones mediante el botón de menú de Power Apps si se permite la inserción en la página.

El ejemplo siguiente muestra una nueva clase con los dos métodos necesarios para configurar dónde se puede insertar aplicaciones.

```powerapps
[ExtensionOf(classStr(FormRunConfigurationPowerAppsConfiguration))]

public final class ClassTest_Extension
{
    public static boolean isPowerAppPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppPersonalizationEnabled(pageName);
        return result;
    }
    
    public static boolean isPowerAppTabPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppTabPersonalizationEnabled(pageName);
        return result;
    }
}
```

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
