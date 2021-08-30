---
title: Insertar aplicaciones de lienzo desde Power Apps
description: Este tema explica cómo insertar aplicaciones de lienzo de Microsoft Power Apps en el cliente para aumentar la funcionalidad de producto.
author: jasongre
ms.date: 04/23/2021
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
ms.openlocfilehash: 4031be484c13136369803ad1c502c4998496143985d84835168a887bd474db0e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767684"
---
# <a name="embed-canvas-apps-from-power-apps"></a>Insertar aplicaciones de lienzo desde Power Apps

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Microsoft Power Apps es un servicio que permite tanto a desarrolladores como a usuarios no técnicos crear aplicaciones empresariales personalizadas para dispositivos móviles, tabletas y la Web sin escribir código. Las aplicaciones de Finance and Operations admiten la integración con Power Apps. Las aplicaciones de lienzo que usted, su organización,o el ecosistema más amplio desarrollan se pueden insertar en las aplicaciones de Finance and Operations para aumentar la funcionalidad de producto. Por ejemplo, puede crear una aplicación de lienzo en Power Apps que complemente a la aplicación de Finance and Operations con información recuperada de otro sistema.

Para obtener más información acerca de la integración de aplicaciones de lienzo, vea el vídeo corto [Cómo insertar aplicaciones de lienzo](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-canvas-app-from-power-apps-to-a-page"></a>Agregar una aplicación de lienzo de Power Apps incrustada a una página

### <a name="overview"></a>Información general

Antes de incrustar una aplicación de lienzo de Power Apps en el cliente, primero debe encontrar o compilar una aplicación con las representaciones visuales y/o la funcionalidades deseadas. Este tema no incluye una descripción detallada del proceso para crear aplicaciones. Si es nuevo en Power Apps, mire la [documentación de Power Apps](/powerapps/).

Hay dos formas de acceder a una aplicación de lienzo específica en una página cuando esté listo para insertar la aplicación. Puede elegir el enfoque que mejor se adapte a su escenario. El primer enfoque usa el botón de **Power Apps** que se ha agregado al panel de acciones estándar. Las aplicaciones que agrega mediante este enfoque aparecen como elementos en el botón de menú **Power Apps**. Cuando selecciona uno de estos elementos, aparece un panel lateral que contiene la aplicación incrustada. Como alternativa, puede incrustar una aplicación directamente en una nueva página como ficha, ficha desplegable u hoja, o como nueva sección en un área de trabajo.

Al configurar la aplicación de lienzo incrustada, puede seleccionar un solo campo que desee enviar como contexto a la aplicación. Este paso permite que la aplicación tenga capacidad de respuesta basándose en los datos que está viendo actualmente.

> [!NOTE]
> Actualmente no puede usar este mecanismo para insertar aplicaciones basadas en modelos.  

### <a name="details"></a>Detalles

El siguiente procedimiento muestra cómo insertar una aplicación de lienzo de Power Apps en el cliente web.

1. Vaya a la página en la que desee insertar la aplicación de lienzo. Esta página será la misma que contiene todos los datos que deben pasarse la aplicación como entrada.
2. Abra el panel **Agregar una aplicación desde Power Apps**:

    - Haga click en **Opciones** y, después seleccione **Personalizar esta página**. En el menú **Insertar**, seleccione **Power Apps** Finalmente, seleccione la región donde desee agregar la aplicación. Si desea insertar la aplicación bajo el botón de menú de Power Apps, elija el panel de acciones. Si desea insertar la aplicación directamente en la página, elija la ficha, la ficha desplegable, la hoja o la sección adecuadas (si se encuentra en un espacio de trabajo).
    - Si se va a acceder a la aplicación mediante el botón de menú de Power Apps, de forma alternativa, puede hacer clic en el botón del menú **Power Apps** en el panel de acciones estándar y, después, seleccionar **Agregar una aplicación**.

3. Configurar la aplicación incrustada:

    - El campo **Nombre** indica el texto que se muestra para el botón o la ficha o que contendrán la aplicación incrustada. Muchas veces puede que desee repetir el nombre de la aplicación en este campo.
    - El campo **ID de aplicación** indica el identificador único global (GUID) de la aplicación de lienzo que desea incrustar. Para recuperar este valor, encuentre la aplicación en [make.powerapps.com](https://make.powerapps.com) y después mire en el campo **Identificador de la aplicación** en **Detalles**.
    - Para **Contexto de entrada para la aplicación**, puede seleccionar opcionalmente el campo que contiene los datos que desea pasar a la aplicación como entrada. Para obtener información detallada sobre cómo la aplicación puede tener acceso a los datos enviados desde aplicaciones de Finance and Operations, consulte la sección que figura más adelante en este tema denominada [Creación de una aplicación que aproveche los datos enviados desde aplicaciones de Finance and Operations](#building-a-canvas-app-that-uses-data-that-is-sent-from-finance-and-operations-apps). 
        - A partir de la versión 10.0.19, la entidad jurídica actual también se pasará como contexto a la aplicación de lienzo a través del parámetro de URL **cmp**. Esto no tendrá ningún impacto en la aplicación de lienzo de destino hasta que esa aplicación haga uso de esta información. 
    - Elija el **tamaño de la aplicación** que coincida con el tipo de aplicación que se está insertando. Seleccione **Fino** para aplicaciones creadas para dispositivos móviles y **Ancho** para aplicaciones creadas para tabletas. Esto garantiza que se asigne una cantidad de espacio suficiente para la aplicación incrustada.
    - La ficha desplegable **Entidades jurídicas** proporciona la capacidad de elegir para qué entidades jurídicas está disponible la aplicación. El valor predeterminado es hacer que la aplicación esté accesible para todas las entidades jurídicas. Esta opción solo está disponible cuando la característica [Vistas guardadas](saved-views.md) está deshabilitada. 

4. Después de confirmar que la configuración es correcta, haga clic en **Insertar** para insertar el Power Apps en la página. Se le solicitará que actualice el explorador para ver la aplicación incrustada.

## <a name="sharing-an-embedded-app"></a>Uso compartido de una aplicación incrustada

Una vez que haya insertado una aplicación de lienzo en una página y confirmado que funciona correctamente con cualquier contexto de los datos pasado de esa página, puede que desee compartir la aplicación con otros usuarios en el sistema. Para compartir una aplicación de lienzo incrustada, siga estos pasos.

1. [Comparta la aplicación de lienzo](/powerapps/maker/canvas-apps/share-app) con los usuarios adecuados, para que puedan acceder a la aplicación en Power Apps. 

2. Asegúrese de que los usuarios objetivo tengan las personalizaciones adecuadas, de modo que la aplicación incrustada aparezca cuando esos usuarios vean la página. Puede usar los siguientes enfoques:

    - Recomendado: utilice la función [Vistas guardadas](saved-views.md) para crear y publicar una vista que incluye la aplicación incrustada. Este enfoque garantiza que todos los usuarios que tienen los roles de seguridad a los que se dirige la vista publicada verán la aplicación en aplicaciones de Finance and Operations. 
    - Si no tiene activada la función Vistas guardadas, puede hacer que el administrador del sistema envíe una personalización que incluya la aplicación incorporada a todos los usuarios o un subconjunto de usuarios. Alternativamente, puede exportar las personalizaciones de su página y enviarlas a uno o más usuarios. Cada uno de esos usuarios puede importar las personalizaciones. La barra de herramientas de personalización tiene acciones que permiten exportar e importar personalizaciones. 
    
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

    - Si se accede a la aplicación incrustada a través del botón de menú de Power Apps, haga clic con el botón secundario en el botón de menú de Power Apps y seleccione **Personalizar**. Seleccione la aplicación que desea configurar en el menú desplegable **Seleccionar una aplicación**.
    - Si la aplicación incrustada aparece directamente en la página, seleccione **Opciones** y, después, seleccione **Personalizar esta página**. Mediante la herramienta **Seleccionar**, haga clic en la aplicación incrustada.

2. Haga las modificaciones necesarias a la configuración de la aplicación y, a continuación, haga clic en **Guardar**.

## <a name="removing-an-app"></a>Eliminar una aplicación

Después de que una aplicación se haya insertado en una página, hay dos maneras de quitarla en caso necesario:

- Vaya al panel **Editar una aplicación** mediante las instrucciones de [Editar una aplicación incrustada](#editing-an-embedded-app) en la sección anterior en este tema. Confirme que el panel muestra información para la aplicación incrustada que desea quitar y haga clic en el botón **Eliminar**.
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
