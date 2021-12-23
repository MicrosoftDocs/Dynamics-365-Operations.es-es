---
title: Marco de guías de proceso
description: Este tema proporciona información sobre el marco de la guía de procesos para los desarrolladores que están ampliando nuestros procesos móviles de almacén en X++.
author: Mirzaab
ms.date: 11/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 6882c979ad9b37eb4f95a04259b6ac0f0a0edcdc
ms.sourcegitcommit: fd6270dc7f49f93a8155d2b827153b13edb7be8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2021
ms.locfileid: "7902055"
---
# <a name="process-guide-framework"></a>Marco de guías de proceso

[!include [banner](../includes/banner.md)]

Este tema proporciona información sobre el marco de la guía de procesos para los desarrolladores que están ampliando los procesos móviles de almacén en X++. Los procesos móviles del almacén son extensibles como resultado de que los procesos se dividen en pequeños pasos. La lógica empresarial y la construcción de la interfaz de usuario de cada paso se han extraído en clases individuales, lo que permite la extensibilidad.

## <a name="overview-of-the-existing-design"></a>Resumen del diseño existente

Los flujos de ejecución móvil del almacén se exponen a través de un único punto final de servicio personalizado. La solicitud llega desde la aplicación móvil en forma de una cadena XML, que contiene los metadatos de la interfaz de usuario presentada en la aplicación móvil, así como los valores ingresados por el usuario.

Cuando se recibe la solicitud, el primer paso es deserializar este XML. La clase **WHSMobileAppServiceXMLTranslator** convierte el XML en un contenedor, que contiene tanto información de control como información de sesión.

A continuación, la información del contenedor se utiliza para deducir en qué proceso de almacén está trabajando el usuario o está a punto de comenzar (representado por la enumeración **WHSWorkExecuteMode**) y en consecuencia instanciar una clase derivada de **WHSWorkExecuteDisplay**. El método **displayform()** se invoca, que luego hace lo siguiente:

-   Procesa los datos del usuario (delegados a la clase **WHSRFControlData**, pero algunos procesos implementan una lógica especfica anulando el método **processControl()**).

-   Ejecuta lógica empresarial.

-   Incrementa el paso.

-   Crea el contenedor que representa la nueva interfaz de usuario (normalmente en un método **build…()**).

Luego, el contenedor se devuelve al traductor, que luego serializa el XML y lo envía como respuesta al dispositivo móvil.

El diagrama de secuencia siguiente muestra una visión general del flujo de ejecución. Tenga en cuenta que el diagrama es más una descripción esquemática y no una representación 1: 1 del código real.

![Información general esquemática del proceso.](media/schematic-overview.png) 

### <a name="reason-for-the-redesign"></a>Motivo del nuevo diseño

El diseño anterior ofrece un marco muy simple para construir procesos utilizados en flujos móviles. Sin embargo, como es evidente anteriormente, los métodos **displayform()** asumen múltiples responsabilidades. Los delega a otros métodos y clases, pero en ausencia de responsabilidades de clase concretas, se hace de manera inconsistente entre las clases. Además, a medida que la cantidad de escenarios admitidos crece orgánicamente, algunas de esas clases pueden volverse bastante complejas. Para hacer las cosas más interesantes, algunas de esas clases / métodos se anulan y se reutilizan en múltiples modos. El resultado son métodos extremadamente largos con una alta complejidad ciclomática. Estos han planteado problemas de mantenimiento en el pasado. Corregir errores en estos métodos ha sido riesgoso y propenso a la regresión.
Por ejemplo, el método **processWorkLine()** en la clase **WhsWorkExecuteDisplay** se refiere a múltiples procesos (básicamente, en cualquier lugar donde se realice la ejecución del trabajo).

Para hacerlos extensibles, una de las opciones sería dividir los métodos **displayForm** en métodos más pequeños e introducir puntos de extensibilidad. Sin embargo, debido a la matriz de escenarios, sería un desafío para los socios escribir extensiones y validar contra regresiones. No solo eso, debido a la falta de distribución estructurada de responsabilidades señalada anteriormente, el código seguiría creciendo de manera impredecible a lo largo del tiempo, lo que plantearía desafíos en la construcción de extensiones de calidad.

Como resultado, el rediseño es la opción sostenible, con el objetivo de tener clases claramente definidas con responsabilidades independientes. Una clase debe tener una responsabilidad, una razón para cambiar y una razón para ampliarse.

## <a name="design-overview"></a>Descripción general del diseño

En el marco rediseñado, la estrategia central gira en torno a dos principios: dividir el flujo de ejecución en componentes individuales con responsabilidades bien definidas y tener puntos de extensión bien definidos en cada uno de los componentes.

El nombre del nuevo marco es "ProcessGuide". Esto se debe a que el objetivo de estas clases es guiar al usuario a través de un proceso empresarial (a diferencia del cliente enriquecido, que es una experiencia basada en formularios en la que el usuario tiene más flexibilidad en la forma en que interactúan con los datos o en el orden en que se desempeñan las tareas).

> [!NOTE]
> Un detalle notable es la omisión deliberada del prefijo "WHS". Si bien los procesos móviles se introdujeron inicialmente para el almacenamiento, posteriormente han trascendido los límites para respaldar varios procesos de producción y gestión de inventario. Como resultado, la referencia al almacén se excluyó en el nombre del marco.

Para identificar los componentes, el primer paso es observar el proceso de Inicio de producción (clase **WhsWorkExecuteDisplayProdStart**). Este es un esquema del proceso.

![Imagen de proceso esquemático.](media/production-start-process-schematic.png)

En cuanto al flujo de control, los siguientes son componentes necesarios:

-   Un controlador para unir todo el proceso empresarial.
-   Un paso responsable de la ejecución de un paso en el proceso.
-   Un procesador de datos para procesar los datos en un paso.
-   Un creador de páginas responsable de crear la interfaz de usuario para un paso.
-   Un agente de navegación responsable de la transición de pasos.
-   Una clase responsable de ejecutar el proceso empresarial.

En el diagrama de flujo del proceso anterior, si comienza en el paso 1 y comienza a procesar los datos del paso anterior, y luego termina con la creación de una interfaz de usuario, los datos continuarán procesándose en el siguiente paso. Esto introduce un acoplamiento estrecho entre pasos consecutivos, como resultado, nuestro nuevo esquema de alto nivel se vería así:

![Imagen de proceso esquemático de alto nivel.](media/high-level-schematic.png)

Los siguientes son los componentes clave del proceso rediseñado:

-   **ProcessGuideController** - Esta clase organiza la ejecución general del proceso empresarial. Define las fábricas que instancian el paso y el agente de navegación, que posteriormente constituyen la ejecución del proceso, así como la lógica de limpieza para la cancelación o salida del proceso.

-   **ProcessGuideStep** - Esta clase representa un solo paso en el proceso empresarial. Esta clase contiene una definición de las fábricas que instancian un creador de páginas, acciones y procesadores de datos y es responsable de invocarlos en la secuencia correcta.

-   **ProcessGuideNavigationAgent** - Esta clase es responsable de la navegación entre los pasos. Cuando se completa un paso, el agente de navegación es responsable de definir el siguiente paso y pasa cualquier parámetro que el paso anterior pueda necesitar para comunicar al siguiente.

-   **ProcessGuidePageBuilder** - Esta clase es responsable de crear instancias de la interfaz de usuario.

-   **ProcessGuideAction** - Esta clase representa una acción, mostrada como un botón para el usuario.

-   **ProcessGuideDataProcessor** - Esta clase es responsable de procesar los datos ingresados por el usuario en un campo.

## <a name="execution-flow"></a>Flujo de ejecución

El punto de partida del flujo de ejecución permanece sin cambios. Por lo tanto, la solicitud aún llega a través de los mismos puntos finales, seguida de deserialización del XML en el contenedor. Este contenedor luego se pasa a **getNextFormState()**.

Hay tres clases importantes a tener en cuenta:

-  **ProcessGuideSessionState** - Contiene la información del estado de la sesión: modo, paso, controlador y paso que se está ejecutando, etc.

-  **ProcessGuidePage** - Contiene una representación fuertemente tipada de los metadatos de la interfaz de usuario.

-  **ProcessGuideRequest** - Contiene los dos anteriores como miembros y es una representación fuertemente tipada de la solicitud recibida desde el dispositivo móvil.

Estas clases se crean usando la información del contenedor (tanto el estado como los datos de control ingresados por el usuario). Esto proporciona una forma segura de acceder a los valores y manipularlos. En comparación con el acceso repetido al contenedor durante el proceso, esto proporciona beneficios tanto en términos de legibilidad como de rendimiento.

La información del estado de la sesión se utiliza para crear instancias de la clase **ProcessGuideController**. Una vez instanciado, el método **createResponse()** de la clase **ProcessGuideController** se invoca. Este método es el punto de entrada a la lógica de la guía del proceso y, después de la ejecución, vuelve con la respuesta (representada en la clase **ProcessGuideResponse**). Luego, la respuesta se convierte de nuevo al contenedor y se devuelve a la lógica heredada, que luego la serializa en XML y envía la respuesta al dispositivo móvil.

A continuación, el controlador debe encontrar el siguiente paso para ejecutar. Si este es el inicio de un nuevo proceso, el controlador llamará a **initialStep()** para dar el primer paso en el proceso. Después de eso, llamaría al método **execute()** en **ProcessGuideStep**. Este método luego instanciaría una clase **ProcessGuidePageBuilder** y llamaría a **buildPage()**, que volvería con un objeto **ProcessGuidePage**, que es una representación virtual de la interfaz de usuario que se presentará al usuario. El paso luego enviaría el resultado al controlador, que luego guardaría el estado de la sesión actual y luego devolvería el resultado a **getNextFormState()** en forma de clase **ProcessGuideResponse**. A partir de entonces, la respuesta se vuelve a convertir al contenedor y posteriormente se serializa a XML y envía la respuesta al dispositivo móvil.

El siguiente diagrama de secuencia explica este flujo de control. Tenga en cuenta que este es el flujo de control más común, simplificado para explicar el diseño.

![Flujo de control simplificado.](media/control-flow.png)

Cuando el usuario realiza una acción en el dispositivo móvil haciendo clic en un botón (o escaneando un valor, que generalmente activa la acción predeterminada), la solicitud llega al método **createResponse()** en la clase **ProcessGuideController** por la misma ruta. Esta vez, sin embargo, el controlador sabe a partir de la información del estado de la sesión en qué paso se encuentra el usuario. En consecuencia, instancia la clase **ProcessGuideStep** apropiada e invoca al método de ejecución. **ProcessGuideStep**, a su vez, lee el nombre de la acción invocada por el usuario y luego crea una instancia de la clase **ProcessGuideAction** y llama a **execute()**.

La clase **ProcessGuideAction** es responsable de ejecutar la acción específica, sin embargo, hay dos excepciones notables.

La primera es la clase **ProcessGuideOKAction**. Esta acción implica que el usuario quiere confirmar y avanzar en el proceso. De acuerdo con eso, este método en realidad hace una devolución de llamada a la clase ProcessGuideStep, lo que significa que el paso invoca **processData()** en **ProcessGuideDataProcessor**. Esto procesa los datos que el usuario ha ingresado y luego actualiza el estado del paso y envía el resultado al controlador. Según el resultado del procesador, el paso invoca al constructor de páginas para crear la interfaz de usuario adecuada o establece el estado del paso como completado. Esto se refleja en la mitad superior del diagrama de secuencia a continuación.

La otra excepción es la acción de cancelación, implementada en las clases **ProcessGuideCancelResetProcessAction** y **ProcessGuideCancelExitProcessAction**. Estas acciones representan una intención de cancelar el proceso y volver al inicio del proceso o salir del proceso por completo. Similar a la acción **OK**, estas acciones también realizan una devolución de llamada al paso, que indica la intención a **ProcessGuideController**. Luego, el controlador realiza la limpieza necesaria de las variables de estado y mueve el control al paso inicial del proceso o termina el proceso por completo.

Una vez completado el paso, si el estado del paso se establece en **Completado**, entonces el controlador crea una instancia de **ProcessGuideNavigationAgent**, que devuelve el nombre del siguiente paso. A continuación, el controlador crea una instancia de este paso e invoca el método **execute()** y el ciclo continúa. Más comúnmente, el nuevo paso invoca el correspondiente **ProcessGuidePageBuilder** para construir la interfaz de usuario para la siguiente pantalla que se presentará al usuario, que luego se enviará de regreso. Este flujo se refleja en la mitad inferior del diagrama de secuencia a continuación.

![Diagrama de secuencia.](media/sequence-diagram.png)

## <a name="building-a-new-process-using-the-processguide-framework"></a>Construyendo un nuevo proceso usando el marco ProcessGuide

La mejor manera de explicar el flujo de control es utilizando un ejemplo que existe en la aplicación: el proceso de Inicio de producción.

## <a name="overview-of-the-production-start-process"></a>Información general del proceso de inicio

Comencemos por comprender el flujo del proceso. En el primer paso, se solicita al usuario la identificación de la orden de producción.

![Solicitud de ID de producción.](media/production-id-prompt.png)

Cuando el usuario ingresa el ID de la orden de producción, se valida el número de la orden. Algunas de las validaciones que se ejecutan se basan en si el pedido está en el mismo almacén en el que el usuario está conectado y en el estado del pedido. Si la validación falla, se muestra un mensaje de error al usuario. Si la validación tiene éxito, se muestran al usuario los detalles de la orden de producción y el artículo.

El usuario puede cancelar para volver al inicio del proceso o hacer clic en **Aceptar** para confirmar. En el último caso, la orden de producción se establece en el estado **Empezado**, se contabilizan los diarios correspondientes, el control vuelve al primer paso y se muestra al usuario el mensaje "Trabajo completado".


## <a name="creating-the-controller"></a>Creando el controlador

El primer paso en la construcción del proceso empresarial es crear la clase de controlador, que se extiende desde la clase abstracta **ProcessGuideController** que implementa los comportamientos predeterminados de un controlador. El nuevo nombre de la clase es **ProdProcessGuideProductionStartController** y decorado con el valor **WHSWorkExecuteMode** de **StartProdOrder**. Se usa la misma instanciación basada en **SysExtension** que se utilizó en las clases **WHSWorkExecuteDisplay**, lo que ayuda a crear una instancia del controlador cuando el usuario ejecuta un elemento de menú para este modo.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode::StartProdOrder)]
public class ProdProcessGuideProductionStartController extends ProcessGuideController
```

> [!NOTE]
> El patrón de nomenclatura de la clase es **\<FunctionalArea\>ProcessGuide\<Businessprocessname\>Controller**. Este es el patrón que se usa para las clases de controlador y para extender a otras clases.


## <a name="building-the-first-step"></a>Construyendo el primer paso

A continuación, para definir el primer paso, cree la clase **ProdProcessGuidePromptProductionIdStep**, que se extiende desde **ProcessGuideStep**.

La tarea de instanciar la clase se delega a una fábrica de pasos, que es invocada por la clase base **ProcessGuideController**. La implementación predeterminada de la fábrica crea una instancia del paso según el nombre. Por lo tanto, para instanciar **ProdProcessGuidePromptProductionIdStep** como primer paso en el controlador, debe hacer dos cosas:

-   Decorar la clase **ProdProcessGuidePromptProductionIdStep** con un atributo **ProcessGuideStepName**.

    ```xpp
    [ProcessGuideStepName(classStr(ProdProcessGuidePromptProductionIdStep))] public class ProdProcessGuidePromptProductionIdStep extends ProcessGuideStep
    ```

-   En la clase del controlador, implemente el método abstracto **initialStepName()** para devolver el nombre del paso.

    ```xpp
    protected final ProcessGuideStepName initialStepName()
    {
        return classStr(ProdProcessGuidePromptProductionIdStep);
    }
    ````   
    
> [!NOTE]
> El valor del atributo **ProcessGuideStepName** no necesita coincidir exactamente con el nombre de la clase como se muestra arriba. Sin embargo, implementar esto permite uniformidad y seguridad de tipos alrededor de referencias cruzadas cuando se usa la clase. Se recomienda utilizar esta convención de nomenclatura.
>
> La instanciación basada en **ProcessGuideStepName** del paso se implementa en la clase **ProcessGuideStepDefaultFactory**. En el raro caso de que desee una estrategia diferente para instanciar el paso, debe hacer lo siguiente:
> -   Cree una nueva clase de fábrica heredando de **ProcessGuidStepAbstractFactory**.
> -   Opcionalmente, cree una nueva clase de parámetro implementando la interfaz **ProcessGuideIStepCreationParameters**, que contiene los parámetros que necesitaría la fábrica.
> -   En su clase de controlador, anule los métodos **stepFactory()** y **stepCreationParameters()** para devolver la fábrica y los parámetros anteriores.

El siguiente paso es implementar la funcionalidad de la clase **ProdProcessGuidePromptProductionIdStep**. Debe implementar la lógica para construir la interfaz de usuario, procesar los datos ingresados por el usuario y determinar cuándo se completa el paso.

### <a name="building-the-user-interface-for-the-first-step"></a>Construyendo la interfaz de usuario para el primer paso

La interfaz de usuario se construye utilizando una clase heredada de la clase abstracta **ProcessGuidePageBuilder**. Para este paso, nombre la clase para representar lo que hace: **ProdProcessGuidePromptProductionIdPageBuilder**.

El mecanismo de instanciación de la clase es similar a cómo se instancia el paso desde el controlador. 

-   Decorar la clase **ProdProcessGuidePromptProductionIdPageBuilder** con un atributo **ProcessGuidePageBuilderName**.

    ```xpp
    [ProcessGuidePageBuilderName(classStr(ProdProcessGuidePromptProductionIdPageBuilder))] public class ProdProcessGuidePromptProductionIdPageBuilder extends ProcessGuidePageBuilder
    ```

-   En la clase **ProdProcessGuidePromptProductionIdStep**, implemente el método abstracto **pageBuilderName()** para devolver este nombre.

    ```xpp
    protected final ProcessGuidePageBuilderName pageBuilderName()
    {
        return classStr(ProdProcessGuidePromptProductionIdPageBuilder);
    }
    ```    

> [!TIP]
> Similar a la fábrica de pasos, también hay un patrón de fábrica abstracto implementado para la fábrica de creadores de páginas. Así, en el raro caso de que desee una estrategia diferente para instanciar el generador de páginas, puede hacer lo siguiente:
> - Cree una nueva clase de fábrica heredando de **ProcessGuidePageBuilderAbstractFactory**.
> - Opcionalmente, cree una nueva clase de parámetro implementando la interfaz **ProcessGuideIPageBuilderCreationParameters**, que contiene los parámetros que necesitaría la fábrica.
> - En su clase de paso, anule los métodos **pageBuilderFactory()** y **pageBuilderCreationParameters()** para devolver la fábrica y los parámetros anteriores.

Para implementar la interfaz de usuario, necesita una página con un cuadro de texto para ingresar el ID de la orden de producción, más un botón **Aceptar** y un botón **Cancelar**. El botón **Cancelar** debería salir del proceso.

Para implementar esto, necesita anular dos métodos en la clase **ProdProcessGuidePromptProductionIdPageBuilder**:

-   Use el método **addDataControls()** para agregar el cuadro de texto.

    ```xpp
    protected final void addDataControls(ProcessGuidePage _page)
    {
        _page.addTextBox(ProcessGuideDataTypeNames::ProdId, "@SYS4398", extendedTypeNum(ProdId));
    }
    ```   

-   Use el método **addActionControls ()** para agregar los botones **Aceptar** y **Cancelar**.

    ```xpp
    protected final void addActionControls(ProcessGuidePage _page)
    {
        #ProcessGuideActionNames
        _page.addButton(step.createAction(#ActionOK), true);
        _page.addButton(step.createAction(#ActionCancelExitProcess));
    }
    ``` 

Esto agrega los controles de datos, seguidos de los botones. Sin embargo, si desea crear una pantalla con botones y controles de datos intercalados, puede anular el método **addControls()** en lugar de la flexibilidad.

Un escenario adicional a considerar es cómo reconstruir la página en caso de fallas de validación, por ejemplo, si el usuario ingresa una ID de orden de producción incorrecta. La clase base **ProcessGuidePageBuilder** implementa el comportamiento predeterminado, que reconstruye la interfaz de usuario, borra el valor escaneado y agrega el control de error con el mensaje de error. Dado que este es el comportamiento predeterminado que desea utilizar, no es necesario que agregue ningún código para manejar los errores.

> [!TIP]
> Si desea implementar un comportamiento personalizado de la interfaz de usuario para situaciones de error, puede anular uno o más de los métodos **rebuildFromRequestPage()**, **isErrorState()** y **reuseRequestPageOnError()**.

### <a name="processing-the-user-entered-data-in-the-first-step"></a>Procesar los datos ingresados por el usuario en el primer paso

El tratamiento de los datos se realiza en la clase **ProcessGuideDataProcessorDefault**, que a su vez invoca la clase heredada **WhsRfControlData**. No se necesitan cambios en este comportamiento predeterminado y **WhsRfControlData** ya tiene lógica para validar el campo **ProdId**, por lo que no necesita escribir ninguna lógica para manejar esto. En caso de que se requieran extensiones para la lógica de validación, considere usar el mecanismo de extensión basado en **WhsControl**.

### <a name="determine-if-the-first-step-is-complete"></a>Determine si el primer paso está completo

Cuando la validación es exitosa, es el momento de marcar el paso como completado. Esto se hace en la clase base, sin embargo, debe implementar la condición para determinar la finalización del paso. El siguiente método anulado hace eso.

```xpp
protected final boolean isComplete()
{
    WhsrfPassthrough pass = controller.parmSessionState().parmPass();
    ProdId prodId = pass.lookup(ProcessGuideDataTypeNames::ProdId);
        return (prodId != '');
}
```   

### <a name="step-two-view-order-details-and-confirm"></a>Paso dos: ver los detalles del pedido y confirmar

En el segundo paso del proceso, se muestra al usuario una pantalla con detalles sobre el pedido. El usuario puede hacer clic en el botón **Aceptar** para confirmar el inicio de la orden de producción, o hacer clic en **Cancelar** para volver al inicio del proceso. Para este ejemplo, nombre el paso **ProdProcessGuideConfirmProductionOrderStep** y la clase del constructor de páginas **ProdProcessGuideConfirmProductionOrderPageBuilder**.

La clase ProdProcessGuideConfirmProductionOrderStep tiene el siguiente aspecto.

```xpp
[ProcessGuideStepName(classStr(ProdProcessGuideConfirmProductionOrderStep))]
public class ProdProcessGuideConfirmProductionOrderStep extends ProcessGuideStep
{
    protected final ProcessGuidePageBuilderName pageBuilderName()
    {
        return classStr(ProdProcessGuideConfirmProductionOrderPageBuilder);
     }
}
```     

Debido a que el usuario no ingresa ningún valor aquí, no necesita anular el método **isComplete()**. El paso está completo cuando el usuario hace clic en **Aceptar**.

La clase del constructor de páginas anula el método **addDataControls()** para agregar tres etiquetas. La primera etiqueta muestra el ID de la orden de producción, la segunda contiene información del artículo (como el ID del artículo, las dimensiones o la descripción) y la tercera contiene la cantidad y la unidad de medida.

Luego **addActionControls ()** se anula para agregar 2 botones: el botón **Aceptar** y el botón **Cancelar** para cancelar el proceso y volver al inicio del proceso.

```xpp
/// <summary>
/// The <c>ProdProcessGuideConfirmProductionOrderPageBuilder</c> builds a page that allows the user to see details of a production order
/// and then confirm.
/// </summary>
[ProcessGuidePageBuilderName(classStr(ProdProcessGuideConfirmProductionOrderPageBuilder))]
public class ProdProcessGuideConfirmProductionOrderPageBuilder extends ProcessGuidePageBuilder
{
    protected void addDataControls(ProcessGuidePage _page)
    {
        WhsrfPassthrough pass = controller.parmSessionState().parmPass();
        ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
        UnitOfMeasureSymbol inventUOM = InventTableModule::find(prodTable.ItemId, ModuleInventPurchSales::Invent).UnitId;
        
        _page.addLabel(ProcessGuideDataTypeNames::ProdIdLabelName, strFmt("@WAX1684", prodTable.ProdId), extendedTypeNum(ProdId));
        _page.addLabel(ProcessGuideDataTypeNames::ItemInfo, this.generateItemInfoForProdId(pass.lookup(ProcessGuideDataTypeNames::ProdId)), extendedTypeNum(WHSRFUndefinedDataType));
        _page.addLabel(ProcessGuideDataTypeNames::QtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId)), inventUOM), extendedTypeNum(WHSRFQuantityAndUOM));

        if (PdsGlobal::pdsIsCWItem(prodTable.ItemId))
        {
            _page.addLabel(ProcessGuideDataTypeNames::InventQtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::pdsCWProposalStartupQty(prodTable.ProdId)), PdsCatchWeightItem::pdsCWUnitId(prodTable.ItemId)), extendedTypeNum(WHSRFQuantityAndUOM));
        }
    }

    protected void addActionControls(ProcessGuidePage _page)
    {
        #ProcessGuideActionNames
        _page.addButton(step.createAction(#ActionOK), true);
        _page.addButton(step.createAction(#ActionCancelResetProcess));
    }
```

> [!NOTE]
> Puede encontrar el mismo código fuente para los métodos X++ en este tema utilizando el Explorador de aplicaciones. Filtre por el nombre de la clase y luego haga clic con el botón derecho en el nombre de la clase y seleccione **Ver código**.

### <a name="step-3-start-the-production-order"></a>Paso 3: Iniciar el pedido de producción

El tercer paso es donde se ejecuta la lógica empresarial de iniciar la orden de producción. Este paso es algo diferente de los pasos anteriores, ya que este paso no tiene una interfaz de usuario. Este paso se ejecuta silenciosamente cuando el usuario hace clic en **Aceptar** en el paso anterior.

La clase abstracta **ProcessGuideStepWithoutPrompt** implementa el comportamiento predeterminado para tales pasos. El paso actual, por lo tanto, debe extender la clase **ProcessGuideStepWithoutPrompt** y anular el método **doExecute ()**.

El siguiente ejemplo de código muestra la clase y la implementación del método **doExecute ()**. El método simplemente recupera el ID de pedido y el ID de usuario del estado de la sesión e invoca el método para iniciar este pedido de producción.

```xpp
/// <summary>
/// The <c>ProdProcessGuideStartProductionOrderStep</c> represents a step that starts a production order.
/// </summary>
[ProcessGuideStepName(classStr(ProdProcessGuideStartProductionOrderStep))]
public class ProdProcessGuideStartProductionOrderStep extends ProcessGuideStepWithoutPrompt
{
    protected final void doExecute()
    {
        WhsrfPassthrough pass = controller.parmSessionState().parmPass();
        WHSUserId userId = pass.lookup(ProcessGuideDataTypeNames::UserId);
        ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
        WhsWorkExecute workExecute = WhsWorkExecute::construct();
        workExecute.prodStartUp(prodTable.ProdId, ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId), userId);

        this.addProcessCompletionMessage();

        super();
    }

}
```

En caso de una excepción, la lógica de manejo de excepciones del marco asegura que el proceso se revierte al paso anterior.

> [!NOTE]
> La invocación a **addProcessCompletionMessage()** agrega el mensaje "Trabajo completado" a los parámetros de navegación. El siguiente paso (asumiendo que tiene una interfaz de usuario) mostrará este mensaje. Las clases base manejan esta lógica y no es necesario agregar ningún código específico a las clases de proceso para lograr este comportamiento.


### <a name="building-the-navigation-through-the-steps"></a>Construyendo la navegación a través de los pasos

La clase base **ProcessGuideController** instancia la clase **ProcessGuideNavigationAgentDefault**, que se basa en una ruta de navegación predefinida, que es un mapa simple de pasos de origen y destino. Para el escenario de inicio de producción, debido a que no hay bifurcaciones condicionales, esta implementación sería suficiente. Por lo tanto, solo necesita anular el método **initializeNavigationRoute()** para definir la ruta de navegación.

```xpp
    protected ProcessGuideNavigationRoute initializeNavigationRoute()
    {
        ProcessGuideNavigationRoute navigationRoute = new ProcessGuideNavigationRoute();
        navigationRoute.addFollowingStep(classStr(ProdProcessGuidePromptProductionIdStep), classStr(ProdProcessGuideConfirmProductionOrderStep));
        navigationRoute.addFollowingStep(classStr(ProdProcessGuideConfirmProductionOrderStep), classStr(ProdProcessGuideStartProductionOrderStep));
        navigationRoute.addFollowingStep(classStr(ProdProcessGuideStartProductionOrderStep), classStr(ProdProcessGuidePromptProductionIdStep));

        return navigationRoute;
    }
```

Hay procesos en los que habrá bifurcaciones condicionales (basadas en acciones del usuario o cualquier otra condición). Estos procesos deben hacer lo siguiente:

-   Implementar agentes de navegación específicos heredados de la clase **ProcessGuideNavigationAgent**.

-   Implementar la fábrica de agentes de navegación específica heredada de la clase **ProcessGuideNavigationAgentAbstractFactory**, que contiene lógica para crear una instancia del agente de navegación correcto según el paso actual, el estado de la sesión, la acción del usuario u otra lógica.

-   Opcionalmente, anule **navigationAgentCreationParameters()** en la clase de controlador para pasar los parámetros adecuados.

-   Anule **navigationAgentFactory()** en el controlador para crear una instancia de la fábrica de agentes de navegación creada anteriormente.

### <a name="action-classes"></a>Clases de acción

Las clases de acción representan las acciones del usuario, por lo que este ejemplo utiliza la acción **Aceptar** para mostrar cómo se crean las acciones.

```xpp
[ProcessGuideActionName(#ActionOK)]
public class ProcessGuideOKAction extends ProcessGuideAction
{
    public final str label()
    {
        return "@SYS5473";
     }
     protected final void doExecute()
     {
        step.executeOKAction();
      }
}
```    

La clase debe implementar 2 métodos abstractos:

-   **label()**, que devuelve la etiqueta para que se muestre en un control de botón vinculado a esta acción.

-   **doExecute()**, que realiza la acción. Como se mencionó anteriormente, el botón **Aceptar** simplemente realiza una devolución de llamada al paso. Sin embargo, otras acciones pueden tener una lógica más compleja aquí.

Las acciones se instancian usando el marco **SysExtension** basado en el atributo **ProcessGuideActionName**. De manera similar a la creación de instancias de los creadores de páginas, la clase de paso implementa la fábrica de acciones predeterminada y es posible anularla. El creador de páginas agrega un control de botón como este.

```xpp
_page.addButton(step.createAction(#ActionOK), true);
```

Al hacerlo, solicita al paso que cree una clase de acción para el nombre pasado y vincula esa acción al botón.

### <a name="summary"></a>Resumen

Para resumir todo lo que se ha explicado en este tema, aquí hay un resumen completo del código necesario para el proceso:

1.  **ProdProcessGuideProductionStartController**

    1.  Anule **initialStepName()** para proporcionar el nombre del primer paso.
    2.  Anule **initializeNavigationRoute()** para construir el mapa de navegación.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideProductionStartController</c> class is the controller class for the production order start process guide.
        /// </summary>
        [WHSWorkExecuteMode(WHSWorkExecuteMode::StartProdOrder)]
        public class ProdProcessGuideProductionStartController extends ProcessGuideController
        {
            protected ProcessGuideStepName initialStepName()
            {
                return classStr(ProdProcessGuidePromptProductionIdStep);
            }

            protected ProcessGuideNavigationRoute initializeNavigationRoute()
            {
                ProcessGuideNavigationRoute navigationRoute = new ProcessGuideNavigationRoute();
                navigationRoute.addFollowingStep(classStr(ProdProcessGuidePromptProductionIdStep), classStr(ProdProcessGuideConfirmProductionOrderStep));
                navigationRoute.addFollowingStep(classStr(ProdProcessGuideConfirmProductionOrderStep), classStr(ProdProcessGuideStartProductionOrderStep));
                navigationRoute.addFollowingStep(classStr(ProdProcessGuideStartProductionOrderStep), classStr(ProdProcessGuidePromptProductionIdStep));

                return navigationRoute;
            }

        }
        ```

2.  **ProdProcessGuidePromptProductionIdStep**

    1.  Anule **isComplete()** para especificar cuándo el paso se considera completo.
    2.  Anule **pageBuilderName()** para especificar el constructor de páginas que se utilizará.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuidePromptProductionIdStep</c> represents a step that 
        /// that prompts the user for a production order id.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuidePromptProductionIdStep))]
        public class ProdProcessGuidePromptProductionIdStep extends ProcessGuideStep
        {
            protected boolean isComplete()
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                ProdId prodId = pass.lookup(ProcessGuideDataTypeNames::ProdId);

                return (prodId != '');
            }

            protected ProcessGuidePageBuilderName pageBuilderName()
            {
                return classStr(ProdProcessGuidePromptProductionIdPageBuilder);
            }

        }
        ```

3.  **ProdProcessGuidePromptProductionIdPageBuilder**

    1.  Anule **addDataControls()** para agregar el cuadro de texto **ID de producto**.
    2.  Anule **addActionControls()** para agregar los botones **Aceptar** y **Cancelar**.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuidePromptProductionIdPageBuilder</c> class builds a page 
        /// that prompts the user for a production order id.
        /// </summary>
        [ProcessGuidePageBuilderName(classStr(ProdProcessGuidePromptProductionIdPageBuilder))]
        public class ProdProcessGuidePromptProductionIdPageBuilder extends ProcessGuidePageBuilder
        {
            protected void addDataControls(ProcessGuidePage _page)
            {
                _page.addTextBox(ProcessGuideDataTypeNames::ProdId, "@SYS4398", extendedTypeNum(ProdId));
            }

            protected void addActionControls(ProcessGuidePage _page)
            {
                #ProcessGuideActionNames
                _page.addButton(step.createAction(#ActionOK), true);
                _page.addButton(step.createAction(#ActionCancelExitProcess));
            }

        }
        ```

4.  **ProdProcessGuideConfirmProductionOrderStep**

    1.  Anule **pageBuilderName()** para especificar el constructor de páginas que se utilizará.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideConfirmProductionOrderStep</c> class represents the step for viewing production order
        /// details and confirming the same.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuideConfirmProductionOrderStep))]
        public class ProdProcessGuideConfirmProductionOrderStep extends ProcessGuideStep
        {    
            protected ProcessGuidePageBuilderName pageBuilderName()
            {
                return classStr(ProdProcessGuideConfirmProductionOrderPageBuilder);
            }

        }
        ```

3.  **ProdProcessGuideConfirmProductionOrderPageBuilder**

    1.  Anule **addDataControls ()** para agregar las etiquetas de información de pedido, artículo y cantidad.

    2.  Anule **addActionControls()** para agregar los botones **Aceptar** y **Cancelar**.
        
        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideConfirmProductionOrderPageBuilder</c> builds a page that allows the user to see details of a production order
        /// and then confirm.
        /// </summary>
        [ProcessGuidePageBuilderName(classStr(ProdProcessGuideConfirmProductionOrderPageBuilder))]
        public class ProdProcessGuideConfirmProductionOrderPageBuilder extends ProcessGuidePageBuilder
        {
            protected void addDataControls(ProcessGuidePage _page)
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
                UnitOfMeasureSymbol inventUOM = InventTableModule::find(prodTable.ItemId, ModuleInventPurchSales::Invent).UnitId;

                _page.addLabel(ProcessGuideDataTypeNames::ProdIdLabelName, strFmt("@WAX1684", prodTable.ProdId), extendedTypeNum(ProdId));
                _page.addLabel(ProcessGuideDataTypeNames::ItemInfo, this.generateItemInfoForProdId(pass.lookup(ProcessGuideDataTypeNames::ProdId)), extendedTypeNum(WHSRFUndefinedDataType));
                _page.addLabel(ProcessGuideDataTypeNames::QtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId)), inventUOM), extendedTypeNum(WHSRFQuantityAndUOM));

                if (PdsGlobal::pdsIsCWItem(prodTable.ItemId))
                {
                    _page.addLabel(ProcessGuideDataTypeNames::InventQtyLabelName, strFmt("@WAX1685", WHSWorkExecuteDisplay::num2StrDisplay(ProdUpdStartUp::pdsCWProposalStartupQty(prodTable.ProdId)), PdsCatchWeightItem::pdsCWUnitId(prodTable.ItemId)), extendedTypeNum(WHSRFQuantityAndUOM));
                }
            }

            protected void addActionControls(ProcessGuidePage _page)
            {
                #ProcessGuideActionNames
                _page.addButton(step.createAction(#ActionOK), true);
                _page.addButton(step.createAction(#ActionCancelResetProcess));
            }

        ```

        > [!NOTE]
        > El método **generateItemInfoForProdId()**, que se utiliza para generar las etiquetas de información del artículo, se excluye de este tema. Este método consulta algunas tablas para obtener el ID del artículo, la descripción y las dimensiones. Si quiere una mejor comprensión de **generateItemInfoForProdId()**, mire el código fuente.

4.  **ProdProcessGuideStartProductionOrderStep**

    1.  Anule **doExecute()** para realizar el proceso de inicio de producción y agregar el mensaje de finalización del proceso.

        ```xpp
        /// <summary>
        /// The <c>ProdProcessGuideStartProductionOrderStep</c> represents a step that starts a production order.
        /// </summary>
        [ProcessGuideStepName(classStr(ProdProcessGuideStartProductionOrderStep))]
        public class ProdProcessGuideStartProductionOrderStep extends ProcessGuideStepWithoutPrompt
        {
            protected final void doExecute()
            {
                WhsrfPassthrough pass = controller.parmSessionState().parmPass();
                WHSUserId userId = pass.lookup(ProcessGuideDataTypeNames::UserId);
                ProdTable prodTable = ProdTable::find(pass.lookup(ProcessGuideDataTypeNames::ProdId));
                WhsWorkExecute workExecute = WhsWorkExecute::construct();
                workExecute.prodStartUp(prodTable.ProdId, ProdUpdStartUp::proposalStartUpQty(prodTable.ProdId), userId);

                this.addProcessCompletionMessage();

                super();
            }

        }
        ```

> [!NOTE]
> Tenga en cuenta que muchos de los patrones comunes (regeneración de la interfaz de usuario en caso de error, mensaje de finalización del proceso de configuración, comportamiento de **Aceptar** y **Cancelar**) se han movido al marco, lo que evita que el desarrollador de la aplicación escriba código repetitivo que es propenso a errores y tiene un riesgo de comportamiento incoherente en todos los procesos. Sin embargo, cuando el escenario necesita desviarse de la ruta común, el desarrollador de la aplicación tiene la opción de anular los métodos adecuados, pero esa es una desviación intencional que es tanto explícita como rastreable.


### <a name="extending-a-business-process"></a>Extender un proceso empresarial

Hasta ahora, este tema ha destacado cómo construir un nuevo proceso utilizando la estructura **ProcessGuide**. En esta sección final, encontrará algunos ejemplos de cómo se puede ampliar este proceso empresarial.

### <a name="add-a-step-in-a-flow-using-processguidenavigationagentdefault"></a>Agregar un paso en un flujo (usando ProcessGuideNavigationAgentDefault)

Dónde extender:

-   Hijo de la clase **ProcessGuideController** para el proceso.

Cómo extender:

-   Extender el método **initializeNavigationRoute()** en la clase del controlador e invocar **addFollowingStep()** en la clase **ProcessGuideNavigationRoute**.

### <a name="add-a-step-in-a-flow-using-custom-navigation-agent"></a>Agregar un paso en un flujo (usando un agente de navegación personalizado)

Dónde extender:

-   Elemento secundario de **ProdProcessGuideNavigationAgentFactory/ProdProcessGuideNavigationAgent**.

Cómo extender:

-   Cree una nueva clase secundaria de **ProcessGuideNavigationAgent** que devuelve el nombre del paso deseado.

-   Crea una nueva clase derivada de **ProcessGuideNavigationAgentFactory** que devuelve condicionalmente el agente de navegación creado anteriormente.

-   Extienda el método **navigationAgentFactory()** en la clase del controlador para devolver la fábrica creada anteriormente.

### <a name="add-a-new-control-in-the-ui-of-an-existing-step"></a>Agregar un nuevo control en la interfaz de usuario de un paso existente 

Dónde extender:

-   Elemento secundario de **ProdProcessGuidePageBuilder** para el paso.

Cómo extender:

-   Extienda el método **addDataControls()** y agregue el control adicional.

### <a name="complete-overhaul-of-the-user-interface-in-an-existing-step"></a>Revisión completa de la interfaz de usuario en un paso existente

Dónde extender:

-   Elemento secundario de **ProdProcessGuideStep**.

Cómo extender:

-   Cree una nueva clase secundaria de la clase **ProdProcessGuidePageBuilder** e implemente la interfaz de usuario deseada.

-   Extienda el método **pageBuildeName()** en la clase de paso para devolver **ProcessGuidePageBuilderNameAttribute** para la clase creada anteriormente.

### <a name="alter-logic-when-a-step-is-considered-complete"></a>Alterar la lógica cuando un paso se considera completo

Dónde extender:

-   Elemento secundario de **ProdProcessGuideStep**.

Cómo extender:

-   Extienda el método **isComplete()** para construir la lógica adicional.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]