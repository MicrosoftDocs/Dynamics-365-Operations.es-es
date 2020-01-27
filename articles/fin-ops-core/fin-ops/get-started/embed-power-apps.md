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
ms.openlocfilehash: 8b5e64cb9ba916f9cbd628703394318b4044867b
ms.sourcegitcommit: dc953c316c396c45ddd596e25c2b358e39a95d84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2019
ms.locfileid: "2870250"
---
# <a name="embed-microsoft-power-apps"></a>Insertar Microsoft Power Apps

[!include [banner](../includes/banner.md)]

En la actualización de plataforma 14 se admite la integración con Microsoft Power Apps, un servicio para que desarrolladores y usuarios no técnicos compilen las aplicaciones personalizadas de negocio de los dispositivos móviles, las tabletas, y la Web sin escribir código. Las Power Apps desarrolladas por el usuario, su organización, o el ecosistema más amplio se pueden insertar en las aplicaciones de Finance and Operations para aumentar la funcionalidad de producto. Por ejemplo, puede que tenga que crear un Power Apps para complementar aplicaciones de Finance and Operations con la información recuperada de otro sistema.

Para obtener más información acerca de la integración de Power Apps, vea el vídeo corto [Cómo integrar Power Apps](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-power-app-to-a-page"></a>Agregar un Power Apps incrustado a una página

### <a name="overview"></a>Visión general

Antes de insertar un Power Apps en el cliente, primero tendrá que encontrar o compilar un Power Apps con las representaciones visuales y/o la funcionalidades deseadas. No describiremos el proceso detallado para crear un Power Apps aquí. El tema [Introducción a Power Apps](https://docs.microsoft.com/powerapps/getting-started) es un buen punto de inicio si es nuevo en Power Apps.

Cuando esté listo para incrustar un Power Apps específico, puede elegir entre una de dos formas de tener acceso al Power Apps en una página, sea cual sea la ruta que mejor se adapte a su ejemplo. La primera forma se realiza mediante el botón de Power Apps que se ha agregado al panel de acciones estándar. Las Power Apps agregadas mediante este mecanismo aparecerán como elementos de menú dentro del botón de menú de Power Apps. Cuando se seleccionan, cada uno de estos elementos de menú abren un panel lateral que contiene el Power Apps incrustado. Como alternativa, puede elegir mostrar un Power Apps directamente en una nueva página como ficha, ficha desplegable, hoja o como nueva sección en un área de trabajo.

Al configurar el Power Apps incrustado, puede seleccionar un solo campo que desee enviar como entrada al Power Apps. Esto permite que el Power Apps tenga capacidad de respuesta basándose en los datos que está viendo actualmente.

### <a name="details"></a>Detalles

Las instrucciones siguientes muestran cómo insertar un Power Apps en el cliente Web.

1. Vaya a la página en la que desee insertar el Power Apps. Esto será la misma página que contiene todos los datos que deben pasarse al Power Apps como entrada.
2. Abra el panel **Insertar un Power Apps**:

    - Haga click en **Opciones** y, después seleccione **Personalizar este formulario**. En el menú **Insertar**, seleccione **Power Apps**. Finalmente, seleccione la región donde desee agregar el Power Apps. Si desea insertar el Power Apps bajo el botón de menú de Power Apps, elija el panel de acciones. Si desea insertar el Power Apps directamente en la página, elija la ficha, la ficha desplegable, la hoja o la sección adecuadas (si se encuentra en un espacio de trabajo).
    - Si se va a acceder al Power Apps mediante el botón de menú de Power Apps, de forma alternativa, puede hacer clic en el botón del menú **Power Apps** en el panel de acciones estándar y, después, seleccionar **Insertar un Power Apps**.

3. Configurar el Power Apps incrustado:

    - El campo **Nombre** indica el texto que se muestra para el botón o la ficha o que contendrán el Power Apps incrustado. Muchas veces puede que desee repetir el nombre del Power Apps en este campo.
    - **Identificador de la aplicación** es el GUID para el Power Apps que desee insertar. Para recuperar este valor, encuentre el Power Apps en [web.powerapps.com](https://web.powerapps.com) y después busque el campo **Identificador de la aplicación** en **Detalles**.
    - Para **Datos de entrada para el Power Apps**, puede seleccionar opcionalmente el campo que contiene los datos que desea pasar al Power Apps como entrada. Consulte la sección que figura más adelante en este tema denominada [Creación de un Power Apps que saque provecho de los datos de aplicaciones de Finance and Operations](#building-a-power-app-that-leverages-data-sent-from-finance-and-operations-apps) para obtener información detallada sobre cómo el Power Apps puede tener acceso a los datos enviados desde aplicaciones de Finance and Operations.
    - Elija el **tamaño de la aplicación** que coincida con el tipo de Power Apps que se está insertando. Seleccione **Fino** para Power Apps creadas para dispositivos móviles, y **Ancho** para Power Apps creadas para tabletas. Esto garantiza que se asigne una cantidad de espacio suficiente para el Power Apps incrustado.
    - La ficha desplegable **Entidades jurídicas** proporciona la capacidad de elegir para qué entidades jurídicas está disponible el Power Apps. El valor predeterminado es mostrar el Power Apps en todas las entidades jurídicas.

4. Después de confirmar que la configuración es correcta, haga clic en **Insertar** para insertar el Power Apps en la página. Se le solicitará que actualice el explorador para ver el Power Apps incrustado.

## <a name="sharing-an-embedded-power-app"></a>Uso compartido de un Power Apps incrustado

Una vez que haya insertado un Power Apps en una página y confirmado que funciona correctamente con cualquier contexto de los datos pasado de la página, puede que desee compartir este Power Apps incrustado con otros usuarios en el sistema. Esto se puede realizar de dos formas distintas mediante las capacidades de personalización de producto:

- El escenario recomendado es a través del administrador del sistema, que puede insertar una personalización a todos los usuarios o un subconjunto de usuarios.
- Como alternativa, puede exportar las personalizaciones de la página, enviarlas a uno o varios usuarios y hacer que cada uno de estos usuarios importe los cambios. La opción Gestionar en la barra de herramientas de personalización le permite exportar e importar personalizaciones.

Consulte [Personalizar la experiencia del usuario](personalize-user-experience.md) para obtener más detalles sobre las capacidades de personalización en el producto y cómo utilizarlas.

## <a name="building-a-power-app-that-leverages-data-sent-from-finance-and-operations-apps"></a>Construcción de un Power Apps que aprovecha los datos enviados de aplicaciones de Finance and Operations

Una parte importante de crear un Power Apps que se insertará en aplicaciones de Finance and Operations es usar los datos de entrada de aplicaciones de Finance and Operations. En el Power Apps, se puede acceder a esos datos de entrada mediante la variable de Param (“EntityId”).

Por ejemplo, en función de la OnStart del Power Apps, puede establecer los datos de entrada desde aplicaciones de Finance and Operations a una variable como esta:

```
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-an-embedded-power-app"></a>Ver un Power Apps incrustado

Para ver un Power Apps incrustado en una página de aplicaciones de Finance and Operations, simplemente vaya a una página con un Power Apps incrustado. Recuerde que se puede acceder a Power Apps mediante el botón de Power Apps en el panel de acciones estándar, o se puede aparecer directamente en la página como una nueva ficha, ficha desplegable, hoja o como nueva sección en un espacio de trabajo. Cuando un usuario intenta cargar por primera vez un Power Apps en una página, se le solicitará que inicie sesión en Power Apps para asegurarse de que el usuario disponga de los permisos adecuados para usar el Power Apps.

## <a name="editing-an-embedded-power-app"></a>Editar un Power Apps incrustado

Después de que un Power Apps se haya insertado en una página, puede ser necesario realizar algunos cambios en la configuración de dicho Power Apps. Por ejemplo, tal vez desee modificar la etiqueta asociada al Power Apps incrustado o una nueva versión de Power Apps se ha creado y necesita actualizar el Id de la aplicación para seleccionar la última versión de Power Apps.

Siga estos pasos para editar la configuración de Power Apps incrustado:

1. Vaya al panel **Editar un Power Apps**.

    - Si se accede al Power Apps incrustado a través del botón de menú de Power Apps, haga clic con el botón secundario en el botón de menú de Power Apps y seleccione **Personalizar**. Seleccione el Power Apps que desea configurar del menú desplegable **Seleccionar Power Apps**.
    - Si el Power Apps incrustado aparece directamente en la página, seleccione **Opciones** y, después, seleccione **Personalizar este formulario**. Mediante la herramienta **Seleccionar**, haga clic en el Power Apps incrustado.

2. Haga las modificaciones necesarias a la configuración de Power Apps y, a continuación, haga clic en **Guardar**.

## <a name="removing-an-embedded-power-app"></a>Quitar un Power Apps incrustado

Después de que un Power Apps se haya insertado en una página, hay dos maneras de quitarla en caso necesario:

- Vaya al panel **Editar un Power Apps** mediante las instrucciones de [Editar un Power Apps incrustado](#editing-an-embedded-power-app) de la sección anterior en este tema. Confirme que el panel muestra información para el Power Apps incrustado que desea quitar y haga clic en el botón **Eliminar**.
- Debido a que un Power Apps incrustado está guardado como datos de personalización, desactivando la personalización de su página también quitará cualquier Power Apps incrustado en la página. Tenga en cuenta que borrar la personalización de la página es permanente y no se puede deshacer. Para quitar sus personalizaciones en una página, seleccione **Opciones** y después haga clic en **Personalizar este formulario**. En menú **Gestionar**, seleccione el botón **Borrar**. Después de actualizar su explorador, todas las personalizaciones anteriores para esta página se quitarán. Consulte [Personalizar la experiencia del usuario](personalize-user-experience.md) para obtener más información sobre cómo optimizar páginas utilizando la personalización.

## <a name="appendix"></a>Apéndice

### <a name="developer-control-over-where-a-power-app-can-be-embedded"></a>Control de desarrollador sobre dónde se puede insertar un Power Apps incrustado

De forma predeterminada, los usuarios pueden insertar Power Apps en cualquier página, en el botón de menú de Power Apps o directamente en la página como una ficha, ficha desplegable, hoja o como una nueva sección en un espacio de trabajo. Sin embargo, si procede, los desarrolladores también podrían configurar esta función para permitir solo insertar Power Apps en determinadas páginas implementando los métodos siguientes:

- **isPowerAppPersonalizationEnabled** - Si este método devuelve un valor falso en una página determinada, el botón de menú de Power Apps no se mostrará y los usuarios no podrán insertar Power Apps en ningún lugar de esta página, ni como ficha.
- **isPowerAppTabPersonalizationEnabled** - Si este método devuelve un valor falso en una página determinada, los usuarios no podrán insertar Power Apps directamente en la página como una ficha, ficha desplegable o sección de panorama. Los usuarios podrán seguir insertando Power Apps mediante el botón de menú de Power Apps si se permite la inserción en la página.

El ejemplo siguiente muestra una nueva clase con los dos métodos necesarios para configurar donde se puede insertar Power Apps.

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
