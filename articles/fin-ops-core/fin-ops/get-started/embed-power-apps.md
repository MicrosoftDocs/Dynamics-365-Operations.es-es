---
title: Insertar Power Apps
description: Este tema describe cómo insertar Power Apps en el cliente para aumentar la funcionalidad de producto.
author: jasongre
manager: AnnBe
ms.date: 12/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: 9585d5a399ebf45b0ad7640f3c4e48d8afc46cd8
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "3017737"
---
# <a name="embed-microsoft-power-apps"></a>Insertar Microsoft Power Apps

[!include [banner](../includes/banner.md)]

Finance and Operations admite la integración con Microsoft Power Apps, un servicio para que desarrolladores y usuarios no técnicos compilen las aplicaciones personalizadas de negocio de los dispositivos móviles, las tabletas, y la Web sin escribir código. Las aplicaciones Power Apps desarrolladas por el usuario, su organización, o el ecosistema más amplio se pueden insertar en las aplicaciones de Finance and Operations para aumentar la funcionalidad de producto. Por ejemplo, puede crear una aplicación en Power Apps que complemente a la aplicación de Finance and Operations con información recuperada de otro sistema.

Para obtener más información acerca de la integración de Power Apps, vea el vídeo corto [Cómo integrar Power Apps](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-app-from-power-apps-to-a-page"></a>Agregar una aplicación de Power Apps incrustada a una página

### <a name="overview"></a>Visión general

Antes de insertar una aplicación de Power Apps en el cliente, primero tendrá que encontrar o compilar una aplicación con las representaciones visuales y/o la funcionalidades deseadas. No describiremos el proceso detallado para crear aplicaciones aquí. El tema [Introducción a Power Apps](https://docs.microsoft.com/powerapps/getting-started) es un buen punto de inicio si es nuevo en Power Apps.

Cuando esté listo para incrustar una aplicación específica, puede elegir entre una de dos formas de tener acceso a la aplicación en una página, sea cual sea la ruta que mejor se adapte a su ejemplo. La primera forma se realiza mediante el botón de Power Apps que se ha agregado al panel de acciones estándar. Las aplicaciones agregadas mediante este mecanismo aparecerán como elementos de menú dentro del botón de menú de Power Apps. Cuando se seleccionan, cada uno de estos elementos de menú abren un panel lateral que contiene la aplicación incrustada. Como alternativa, puede elegir incrustar una aplicación directamente en una nueva página como ficha, ficha desplegable, hoja o como nueva sección en un área de trabajo.

Al configurar la aplicación incrustada, puede seleccionar un solo campo que desee enviar como contexto a la aplicación. Esto permite que la aplicación tenga capacidad de respuesta basándose en los datos que está viendo actualmente.

### <a name="details"></a>Detalles

Las instrucciones siguientes muestran cómo insertar una aplicación de Power Apps en el cliente web.

1. Vaya a la página en la que desee insertar la aplicación. Esto será la misma página que contiene todos los datos que deben pasarse la aplicación como entrada.
2. Abra el panel **Agregar una aplicación desde Power Apps**:

    - Haga click en **Opciones** y, después seleccione **Personalizar esta página**. En el menú **Insertar**, seleccione **Power Apps** Finalmente, seleccione la región donde desee agregar la aplicación. Si desea insertar la aplicación bajo el botón de menú de Power Apps, elija el panel de acciones. Si desea insertar la aplicación directamente en la página, elija la ficha, la ficha desplegable, la hoja o la sección adecuadas (si se encuentra en un espacio de trabajo).
    - Si se va a acceder a la aplicación mediante el botón de menú de Power Apps, de forma alternativa, puede hacer clic en el botón del menú **Power Apps** en el panel de acciones estándar y, después, seleccionar **Agregar una aplicación**.

3. Configurar la aplicación incrustada:

    - El campo **Nombre** indica el texto que se muestra para el botón o la ficha o que contendrán la aplicación incrustada. Muchas veces puede que desee repetir el nombre de la aplicación en este campo.
    - **Identificador de la aplicación** es el GUID para la aplicación que desee insertar. Para recuperar este valor, encuentre la aplicación en [web.powerapps.com](https://web.powerapps.com) y después busque el campo **Identificador de la aplicación** en **Detalles**.
    - Para **Contexto de entrada para la aplicación**, puede seleccionar opcionalmente el campo que contiene los datos que desea pasar a la aplicación como entrada. Consulte la sección que figura más adelante en este tema denominada [Creación de aplicaciones que saque provecho de las aplicaciones de Finance and Operations](#building-a-power-app-that-leverages-data-sent-from-finance-and-operations-apps) para obtener información detallada sobre cómo la aplicación puede tener acceso a los datos enviados desde aplicaciones de Finance and Operations.
    - Elija el **tamaño de la aplicación** que coincida con el tipo de aplicación que se está insertando. Seleccione **Fino** para aplicaciones creadas para dispositivos móviles y **Ancho** para aplicaciones creadas para tabletas. Esto garantiza que se asigne una cantidad de espacio suficiente para la aplicación incrustada.
    - La ficha desplegable **Entidades jurídicas** proporciona la capacidad de elegir para qué entidades jurídicas está disponible la aplicación. El valor predeterminado es hacer que la aplicación esté accesible para todas las entidades jurídicas. Esta opción solo está disponible cuando la característica [Vistas guardadas](saved-views.md) está deshabilitada. 

4. Después de confirmar que la configuración es correcta, haga clic en **Insertar** para insertar el Power Apps en la página. Se le solicitará que actualice el explorador para ver la aplicación incrustada.

## <a name="sharing-an-embedded-app"></a>Uso compartido de una aplicación incrustada

Una vez que haya insertado una aplicación en una página y confirmado que funciona correctamente con cualquier contexto de los datos pasado de la página, puede que desee compartir esta aplicación incrustada con otros usuarios en el sistema. Esto se puede realizar de dos formas distintas mediante las capacidades de personalización de producto:

- El escenario recomendado es a través del administrador del sistema, que puede insertar una personalización a todos los usuarios o un subconjunto de usuarios.
- Como alternativa, puede exportar las personalizaciones de la página, enviarlas a uno o varios usuarios y hacer que cada uno de estos usuarios importe los cambios. La barra de herramientas de personalización tiene acciones que permiten exportar e importar personalizaciones.

Consulte [Personalizar la experiencia del usuario](personalize-user-experience.md) para obtener más detalles sobre las capacidades de personalización en el producto y cómo utilizarlas.

## <a name="building-an-app-that-leverages-data-sent-from-finance-and-operations-apps"></a>Crear una aplicación que aproveche los datos enviados desde aplicaciones de Finance and Operations

Una parte importante de la construcción de una aplicación desde Power Apps para incrustarla en una aplicación de Finance and Operations es utilizar los datos de entrada de esa aplicación. Desde la experiencia de desarrollo de Power Apps, se puede acceder a los datos de entrada pasados desde una aplicación de Finance and Operations utilizando la variable Param("EntityId").

Por ejemplo, en la función de OnStart de la aplicación, puede establecer los datos de entrada desde aplicaciones de Finance and Operations en una variable como esta:

```
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-an-app"></a>Ver una aplicación

Para ver una aplicación incrustada en una página de aplicaciones de Finance and Operations, simplemente vaya a una página con una aplicación incrustada. Recuerde que se puede acceder a las aplicaciones mediante el botón de Power Apps en el panel de acciones estándar, o pueden aparecer directamente en la página como una nueva pestaña, ficha desplegable u hoja, o como una sección nueva en un espacio de trabajo. Cuando un usuario intenta cargar por primera vez una aplicación en una página, se le solicitará que inicie sesión para asegurarse de que el usuario disponga de los permisos adecuados para usar la aplicación.

## <a name="editing-an-embedded-app"></a>Editar una aplicación incrustada

Después de que una aplicación se haya insertado en una página, puede ser necesario realizar algunos cambios en la configuración de dicha aplicación. Por ejemplo, tal vez desee modificar la etiqueta asociada a la aplicación incrustada o una nueva versión de la aplicación se ha creado y necesita actualizar el id. de la aplicación para señalar a la última versión.

Siga estos pasos para editar la configuración de una aplicación incrustada:

1. Vaya al panel **Editar la aplicación**.

    - Si se accede a la aplicación incrustada a través del botón de menú de Power Apps, haga clic con el botón secundario en el botón de menú de Power Apps y seleccione **Personalizar**. Seleccione la aplicación que desea configurar en el menú desplegable **Seleccionar una aplicación**.
    - Si la aplicación incrustada aparece directamente en la página, seleccione **Opciones** y, después, seleccione **Personalizar esta página**. Mediante la herramienta **Seleccionar**, haga clic en la aplicación incrustada.

2. Haga las modificaciones necesarias a la configuración de la aplicación y, a continuación, haga clic en **Guardar**.

## <a name="removing-an-app"></a>Eliminar una aplicación

Después de que una aplicación se haya insertado en una página, hay dos maneras de quitarla en caso necesario:

- Vaya al panel **Editar una aplicación** mediante las instrucciones de [Editar una aplicación incrustada](#editing-an-embedded-power-app) en la sección anterior en este tema. Confirme que el panel muestra información para la aplicación incrustada que desea quitar y haga clic en el botón **Eliminar**.
- Debido a que la aplicación incrustada está guardado como datos de personalización, desactivando la personalización de su página también quitará cualquier aplicación incrustada en la página. Tenga en cuenta que borrar la personalización de la página es permanente y no se puede deshacer. Para quitar sus personalizaciones de una página, seleccione **Opciones** y después haga clic en **Personalizar esta página** y finalmente en el botón **Borrar**. Después de actualizar su explorador, todas las personalizaciones anteriores para esta página se quitarán. Consulte [Personalizar la experiencia del usuario](personalize-user-experience.md) para obtener más información sobre cómo optimizar páginas utilizando la personalización.

## <a name="appendix"></a>Apéndice

### <a name="developer-control-over-where-an-app-can-be-embedded"></a>Control de desarrollador sobre dónde se puede insertar una aplicación

De forma predeterminada, los usuarios pueden insertar aplicaciones en cualquier página, en el botón de menú de Power Apps o directamente en la página como una ficha, ficha desplegable, hoja o como una nueva sección en un espacio de trabajo. Sin embargo, si procede, los desarrolladores también podrían configurar esta función para permitir solo insertar aplicaciones en determinadas páginas implementando los métodos siguientes:

- **isPowerAppPersonalizationEnabled** - Si este método devuelve un valor falso en una página determinada, el botón de menú de Power Apps no se mostrará y los usuarios no podrán insertar aplicaciones en ningún lugar de esta página, ni como ficha.
- **isPowerAppTabPersonalizationEnabled** - Si este método devuelve un valor falso en una página determinada, los usuarios no podrán insertar aplicaciones directamente en la página como una ficha, ficha desplegable o sección de panorama. Los usuarios podrán seguir insertando aplicaciones mediante el botón de menú de Power Apps si se permite la inserción en la página.

El ejemplo siguiente muestra una nueva clase con los dos métodos necesarios para configurar dónde se puede insertar aplicaciones.

```
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
