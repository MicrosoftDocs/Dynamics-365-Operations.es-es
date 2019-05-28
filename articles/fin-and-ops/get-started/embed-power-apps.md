---
title: Integrar aplicaciones PowerApps
description: Este tema describe cómo insertar PowerApps en el cliente de Finance and Operations para aumentar la funcionalidad de producto.
author: jasongre
manager: AnnBe
ms.date: 09/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FormRunConfigurationAddPAControl, FormRunConfigurationEditPAControl
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-02-28
ms.dyn365.ops.version: Platform update 14
ms.openlocfilehash: 262d34cbc50251595d22c27387fbd3f1045d1fbb
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1552797"
---
# <a name="embed-powerapps-apps"></a>Integrar aplicaciones de PowerApps

[!include [banner](../includes/banner.md)]

En la actualización de plataforma 14, Microsoft Dynamics 365 for Finance and Operations admite la integración con Microsoft PowerApps, un servicio para que desarrolladores y usuarios no técnicos compilen las aplicaciones personalizadas de negocio de los dispositivos móviles, las tabletas, y la Web sin escribir código. Las PowerApps desarrolladas por el usuario, su organización, o el ecosistema más amplio se pueden insertar en el cliente de Finance and Operations para aumentar la funcionalidad de producto. Por ejemplo, puede que crear un PowerApp para complementar Finance and Operations con la información recuperada de otro sistema.

Para obtener más información acerca de la integracón de PowerApps, vea el vídeo corto [Cómo integrar PowerApps en Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=x3qyA1bH-NY).

## <a name="adding-an-embedded-powerapp-to-a-page"></a>Agregar un PowerApp incrustado a una página

### <a name="overview"></a>Información general

Antes insertar un PowerApp en el cliente de Finance and Operations, primero tendrá que encontrar o compilar un PowerApp con las representaciones visuales y/o la funcionalidades deseadas. No describiremos el proceso detallado para crear un PowerApp aquí. El tema [Introducción a PowerApps](https://docs.microsoft.com/powerapps/getting-started) es un buen punto de inicio si es nuevo en PowerApps.

Cuando esté listo para incrustar un PowerApp específico, puede elegir entre una de dos formas de tener acceso al PowerApp en una página, sea cual sea la ruta que mejor se adapte a su ejemplo. La primera forma se realiza mediante el botón de PowerApps que se ha agregado al panel de acciones estándar. Las PowerApps agregadas mediante este mecanismo aparecerán como elementos de menú dentro del botón de menú de PowerApps. Cuando se seleccionan, cada uno de estos elementos de menú abren un panel lateral que contiene el PowerApp incrustado. Como alternativa, puede elegir mostrar un PowerApp directamente en una nueva página como ficha, ficha desplegable, hoja o como nueva sección en un área de trabajo.

Al configurar el PowerApp incrustado en Finance and Operations, puede seleccionar un solo campo que desee enviar como entrada al PowerApp. Esto permite que el PowerApp tenga capacidad de respuesta basándose en los datos que está viendo actualmente en Finance and Operations.

### <a name="details"></a>Detalles

Las instrucciones siguientes muestran cómo insertar un PowerApp en el cliente Web de Finance and Operations.

1. Vaya a la página en la que desee insertar el PowerApp. Esto será la misma página que contiene todos los datos que deben pasarse al PowerApp como entrada.
2. Abra el panel **Insertar una PowerApp**:

    - Haga click en **Opciones** y, después seleccione **Personalizar este formulario**. En el menú **Insertar**, seleccione **PowerApp**. Finalmente, seleccione la región donde desee agregar el PowerApp. Si desea insertar el PowerApp bajo el botón de menú de PowerApps, elija el panel de acciones. Si desea insertar el PowerApp directamente en la página, elija la ficha, la ficha desplegable, la hoja o la sección adecuadas (si se encuentra en un espacio de trabajo).
    - Si se va a acceder al PowerApp mediante el botón de menú de PowerApps, de forma alternativa, puede hacer clic en el botón del menú **PowerApps** en el panel de acciones estándar y, después, seleccionar **Insertar un PowerApp**.

3. Configurar el PowerApp incrustado:

    - El campo **Nombre** indica el texto que se muestra para el botón o la ficha o que contendrán el PowerApp incrustado. Muchas veces puede que desee repetir el nombre del PowerApp en este campo.
    - **Identificador de la aplicación** es el GUID para la PowerApp que desee insertar. Para recuperar este valor, encuentre el PowerApp en [web.powerapps.com](https://web.powerapps.com) y después busque el campo **Identificador de la aplicación** en **Detalles**.
    - Para **Datos de entrada para PowerApp**, puede seleccionar opcionalmente el campo que contiene los datos que desea pasar a PowerApp como entrada. Consulte la sección que figura más adelante en este tema denominada [Creación de un PowerApp que saque provecho de los datos de Finance and Operations](#building-a-powerapp-that-leverages-data-sent-from-finance-and-operations) para obtener información detallada sobre cómo el PowerApp puede tener acceso a los datos enviados desde Finance and Operations.
    - Elija el **tamaño de la aplicación** que coincida con el tipo de PowerApp que se está insertando. Seleccione **Fino** para PowerApps creadas para dispositivos móviles, y **Ancho** para PowerApps creadas para tabletas. Esto garantiza que se asigne una cantidad de espacio suficiente para el PowerApp incrustado.
    - La ficha desplegable **Entidades jurídicas** proporciona la capacidad de elegir para qué entidades jurídicas está disponible PowerApp. El valor predeterminado es mostrar el PowerApp en todas las entidades jurídicas.

4. Después de confirmar que la configuración es correcta, haga click en **Insertar** para insertar el PowerApp en la página. Se le solicitará que actualice el explorador para ver el PowerApp incrustado.

## <a name="sharing-an-embedded-powerapp"></a>Uso compartido de un PowerApp incrustado

Una vez que haya insertado un PowerApp en una página y confirmado que funciona correctamente con cualquier contexto de los datos pasado de la página, puede que desee compartir este PowerApp incrustado con otros usuarios en el sistema. Esto se puede realizar de dos formas distintas mediante las capacidades de personalización de producto:

- El escenario recomendado es a través del administrador del sistema, que puede insertar una personalización a todos los usuarios o un subconjunto de usuarios.
- Como alternativa, puede exportar las personalizaciones de la página, enviarlas a uno o varios usuarios y hacer que cada uno de estos usuarios importe los cambios. La opción Gestionar en la barra de herramientas de personalización le permite exportar e importar personalizaciones.

Consulte [Personalizar la experiencia del usuario](personalize-user-experience.md) para obtener más detalles sobre las capacidades de personalización en el producto y cómo utilizarlas.

## <a name="building-a-powerapp-that-leverages-data-sent-from-finance-and-operations"></a>La construcción de un PowerApp que aprovecha los datos enviados de Finance and Operations

Una parte importante de crear un PowerApp que se insertará en Finance and Operations es usar los datos de entrada de Finance and Operations. En PowerApp, se puede acceder a esos datos de entrada mediante la variable de Param (“EntityId”).

Por ejemplo, en función de la OnStart de PowerApp, puede establecer los datos de entrada desde Finance and Operations a una variable como esta:

```
If(!IsBlank(Param("EntityId")), Set(FinOpsInput, Param("EntityId")), Set(FinOpsInput, ""));
```

## <a name="viewing-an-embedded-powerapp"></a>Ver un PowerApp incrustado

Para ver un PowerApp incrustado en una página de Finance and Operations, simplemente vaya a una página con un PowerApp incrustado. Recuerde que se puede acceder a PowerApps mediante el botón de PowerApps en el panel de acciones estándar, o se puede aparecer directamente en la página como una nueva ficha, ficha desplegable, hoja o como nueva sección en un espacio de trabajo. Cuando un usuario intenta cargar por primera vez un PowerApp en una página, se le solicitará que inicie sesión en PowerApps para asegurarse de que el usuario disponga de los permisos adecuados para usar PowerApp.

## <a name="editing-an-embedded-powerapp"></a>Editar un PowerApp incrustado

Después de que un PowerApp se haya insertado en una página, puede ser necesario realizar algunos cambios en la configuración de dicho PowerApp. Por ejemplo, tal vez desee modificar la etiqueta asociada al PowerApp incrustado o una nueva versión de un PowerApp se ha creado y necesita actualizar el Id de la aplicación para seleccionar la última versión de PowerApp.

Siga estos pasos para editar la configuración de un PowerApp incrustado:

1. Vaya al panel **Editar un PowerApp**.

    - Si se accede al PowerApp incrustado a través del botón de menú de PowerApps, haga clic con el botón secundario en el botón de menú de PowerApps y seleccione **Personalizar**. Seleccione el PowerApp que desea configurar del menú desplegable **Seleccionar PowerApp**.
    - Si el PowerApp incrustado aparece directamente en la página, seleccione **Opciones** y, después, seleccione **Personalizar este formulario**. Mediante la herramienta **Seleccionar**, haga clic en el PowerApp incrustado.

2. Haga las modificaciones necesarias a la configuración de PowerApps y, a continuación, haga clic en **Guardar**.

## <a name="removing-an-embedded-powerapp"></a>Quitar un PowerApp incrustado

Después de que un PowerApp se haya insertado en una página, hay dos maneras de quitarlo en caso necesario:

- Vaya al panel **Editar un PowerApp** mediante las instrucciones [Editar un PowerApp incrustado](#editing-an-embedded-powerapp) de la sección anterior en este tema. Confirme que el panel muestra información para el PowerApp incrustado que desea quitar y haga clic en el botón **Eliminar**.
- Debido a que un PowerApp incrustado está guardado como datos de personalización, desactivando la personalización de su página también quitará cualquier PowerApps incrustado en la página. Tenga en cuenta que borrar la personalización de la página es permanente y no se puede deshacer. Para quitar sus personalizaciones en una página, seleccione **Opciones** y después haga clic en **Personalizar este formulario**. En menú **Gestionar**, seleccione el botón **Borrar**. Después de actualizar su explorador, todas las personalizaciones anteriores para esta página se quitarán. Consulte [Personalizar la experiencia del usuario](personalize-user-experience.md) para obtener más información sobre cómo optimizar páginas utilizando la personalización.

## <a name="appendix"></a>Apéndice

### <a name="developer-control-over-where-a-powerapp-can-be-embedded"></a>Control de desarrollador sobre dónde se puede insertar un PowerApp

De forma predeterminada, los usuarios pueden insertar PowerApps en cualquier página, en el botón de menú de PowerApps o directamente en la página como una ficha, ficha desplegable, hoja o como una nueva sección en un espacio de trabajo. Sin embargo, si procede, los desarrolladores también podrían configurar esta función para permitir solo insertar PowerApps en determinadas páginas implementando los métodos siguientes:

- **isPowerAppPersonalizationEnabled** - Si este método devuelve un valor falso en una página determinada, el botón de menú de PowerApps no se mostrará y los usuarios no podrán insertar PowerApps en ningún lugar de esta página, ni como ficha.
- **isPowerAppTabPersonalizationEnabled** - Si este método devuelve un valor falso en una página determinada, los usuarios no podrán insertar PowerApps directamente en la página como una ficha, ficha desplegable o sección de panorama. Los usuarios podrán seguir insertando PowerApps mediante el botón de menú de PowerApps si se permite la inserción en la página.

El ejemplo siguiente muestra una nueva clase con los dos métodos necesarios para configurar donde se puede insertar PowerApps.

```
[ExtensionOf(classStr(FormRunConfigurationPowerAppsConfiguration))]

public final class ClassTest_Extension
{
    public static boolean isPowerAppPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppPersonalizationEnabled(pageName);
        return true;
    }
    public static boolean isPowerAppTabPersonalizationEnabled(str pageName)
    {
        var result = next isPowerAppTabPersonalizationEnabled(pageName);
        return true;
    }
}
```
