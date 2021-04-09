---
title: Gestión de pedidos distribuida (DOM)
description: En este tema se describe la funcionalidad de gestión de pedidos distribuida (DOM) de Dynamics 365 Commerce.
author: josaw1
ms.date: 01/08/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: f50bc2828df19062a6bdced6faaa7b4d66c38bed
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792784"
---
# <a name="distributed-order-management-dom"></a>Gestión de pedidos distribuida (DOM)

[!include [banner](includes/banner.md)]

En el nuevo paradigma de las operaciones de Commerce, los comercios minoristas se esfuerzan por proporcionar una captación de clientes personalizada, experiencias en varios canales simultáneos e interacciones fluidas. Hay muchas opciones disponibles, por lo que los consumidores comprarán dónde puedan disfrutar de la experiencia más favorable. En muchos casos, los precios y los productos ya no son los factores principales en las decisiones de los consumidores.

Para ayudar a mejorar la experiencia del cliente, los comercios minoristas deben disponer de visibilidad de su inventario en tiempo real y a través de todos sus canales. Una sola vista integral de todo el inventario puede ayudar a optimizar el cumplimiento, la asignación y la distribución de pedidos. Por lo tanto, la adopción y la implementación de un sistema de gestión de pedidos distribuida (DOM) es cada vez más importante para los minoristas.

DOM optimiza el cumplimiento de pedidos a través de una red compleja de sistemas y procesos. Se basa en una sola vista global del inventario en toda la organización para administrar de forma inteligente los pedidos, a fin de realizarlos de forma precisa y más rentable. Al mejorar la eficacia de la cadena de suministro de un minorista, DOM ayuda al minorista a cumplir mejor las expectativas del cliente.

La siguiente ilustración muestra el ciclo de vida de un pedido de ventas en un sistema DOM.

![Ciclo de vida de pedido de ventas en el contexto de DOM](./media/flow.png "Ciclo de vida de pedido de ventas en el contexto de DOM")

## <a name="set-up-dom"></a>Configurar DOM

1. Vaya a **Administración del sistema \> Configuración \> Configuración de licencias**.
2. En la pestaña **Claves de configuración**, expanda el nodo **Commerce** y seleccione la casilla **Gestión de pedidos distribuida**.
3. Vaya a **Retail y Commerce \> Gestión de pedidos distribuida \> Configuración \> Parámetros de DOM**.
4. En la pestaña **General**, establezca los valores siguientes:

    - **Habilitar gestión de pedidos distribuida**: establezca esta opción en **Sí**.
    - **Confirmar uso de mapas de Bing para DOM**: establezca esta opción en **Sí**.


        > [!NOTE]
        > Puede establecer esta opción en **Sí** solo si la opción **Habilitar Mapas de Bing** de la pestaña **Mapas de Bing** de la página **Parámetros compartidos de Commerce** (**Retail y Commerce \> Configuración de Headquarters \> Parámetros \> Parámetros compartidos de Commerce**) también está establecida en **Sí**, y si se ha especificado una clave válida en el campo **Clave de Mapas de Bing**.
        >
        > El portal [Centro de desarrollo de Mapas de Bing](https://www.bingmapsportal.com/) le permite restringir el acceso a sus claves de API de Mapas de Bing a un conjunto de dominios que especifique. Con esta característica, los clientes pueden definir un conjunto estricto de valores de referencia o rangos de direcciones IP frente a los que se validará la clave. Las solicitudes que se originan en su lista de permitidos se procesarán normalmente, mientras que las solicitudes de fuera de su lista devolverán una respuesta de acceso denegado. La adición de seguridad de dominio a su clave de API es opcional y las claves que se dejan como están seguirán funcionando. La lista de permitidos para una clave es independiente del resto de sus claves, lo que le permite tener reglas distintas para cada una de sus claves. La administración de pedidos distribuida no admite la configuración de propiedades referidas al dominio.


    - **Período de retención en días**: especifique cuánto tiempo se conservarán en el sistema los planes de cumplimiento que las ejecuciones de DOM generan. El trabajo por lotes **Configuración de trabajo de eliminación de datos de cumplimiento de DOM** eliminará cualquier plan de cumplimiento que sea más antiguo que el número de días especificado aquí.
    - **Período de rechazo (en días)**: especifique el tiempo que debe transcurrir antes de que una línea de pedido rechazada se pueda asignar a la misma ubicación.

5. En la pestaña **Solucionador**, establezca los siguientes valores:

    - **Número máximo de reintentos de cumplimiento**: especifique cuántas veces intentará el motor de DOM gestionar una línea de pedido para una ubicación. Si el motor de DOM no puede gestionar una línea de pedido para una ubicación en el número específico de intentos, marcará la línea de pedido como una excepción. Después omitirá esa línea en futuras ejecuciones hasta que se restablezca el estado manualmente.
    - **Radio de región de tienda local**: especifique un valor. Este campo ayuda a determinar cómo se agrupan las ubicaciones y se consideran iguales en términos de distancia. Por ejemplo, si especifica **100**, cada tienda o centro de distribución que esté dentro de un intervalo de 160 km de la dirección de cumplimiento se considerará igual en términos de distancia.
    - **Tipo de solucionador**: seleccione un valor. Retail incluye dos tipos de solucionador con Commerce: **Solucionador de producción** y **Solucionador simplificado**. Para todos los equipos que ejecuten DOM (es decir, todos los servidores que formen parte del grupo DOMBatch) hay que seleccionar **Solucionador de producción**. El Solucionador de producción requiere la clave de licencia especial que, de forma predeterminada, se otorga e implementa en los entornos de producción. Para los entornos que no sean de producción esta clave de licencia debe implementarse manualmente. Siga estos pasos para implementar manualmente la clave de licencia:

        1. En Microsoft Dynamics Lifecycle Services, abra la Biblioteca de activos compartidos, seleccione **Modelo** como tipo de activo y descargue el archivo **Licencia de DOM**.
        1. Inicie el Administrador de Microsoft Internet Information Services (IIS), haga clic con el botón derecho en **Sitio web de AOSService** y, a continuación, seleccione **Explorar**. Se abre una ventana del Explorador de Windows en **\<AOS service root\>\\webroot**. Anote la ruta de acceso a \<AOS Service root\>. La va a utilizar en el paso siguiente.
        1. Copie el archivo de configuración en el directorio **\<AOS Service root\>\\PackagesLocalDirectory\\DOM\\bin**.
        1. Vaya al cliente de Headquarters y abra la página **Parámetros de DOM**. En la pestaña **Solucionador**, en el campo **Tipo de solucionador**, seleccione **Solucionador de producción** y confirme que no aparece ningún mensaje de error.


        > [!NOTE]
        > El Solucionador simplificado se proporciona para que los minoristas puedan probar la característica DOM sin tener que implementar la licencia especial. Las organizaciones no deben usar el Solucionador simplificado en entornos de producción.
        >
        > El Solucionador de producción mejora el rendimiento (como el número de pedidos y líneas de pedido que se pueden manejar en una ejecución) y la convergencia de resultados (dado que un lote de pedidos puede no producir el mejor resultado en algunas situaciones). Algunas reglas, como **Órdenes parciales** y **Número máximo de ubicaciones** requieren del Solucionador de producción.
     
6. Vuelva a **Retail y Commerce \> Administración de pedidos distribuida \> Configuración \> Parámetros de DOM**.
7. En la pestaña **Secuencias numéricas**, asigne las secuencias numéricas necesarias a las distintas entidades de DOM.

    > [!NOTE]
    > Para poder asignar secuencias numéricas a las entidades, deben definirse en la página **Secuencias numéricas** (**Administración de la organización \> Secuencias numéricas \> Secuencias numéricas**).

8. La funcionalidad de DOM permite definir diversos tipos de reglas de DOM, y las organizaciones pueden configurar varias reglas en función de sus necesidades empresariales. Se pueden definir reglas de DOM para un grupo de ubicaciones o para ubicaciones individuales, y para una categoría de productos, un producto o una variante específicos. Para crear la agrupación de ubicaciones que se deben usar para las reglas de DOM, siga estos pasos:

    1. Vaya a **Retail y Commerce \> Configuración de canal \> Grupos de cumplimiento**.
    2. Seleccione **Nuevo** y especifique un nombre y una descripción del nuevo grupo.
    3. Seleccione **Guardar**.
    4. Seleccione **Agregar línea** para agregar una sola ubicación al grupo. Como alternativa, seleccione **Agregar líneas** para agregar distintas ubicaciones.
    
    > [!NOTE]
    > En Commerce versión 10.0.12 y posterior, la **Capacidad para especificar ubicaciones como 'Envío' o 'Recogida' habilitada dentro del grupo de cumplimiento** debe estar habilitada en el espacio de trabajo **Administración de características**.
    >
    > Esta característica agrega nuevas configuraciones en la página **Grupo de cumplimiento** para que pueda definir si el almacén se puede utilizar para envíos o si la combinación de almacén/tienda se puede utilizar para envíos, recogidas o ambos. 
    >
    > Si habilita la característica, se actualizarán las opciones disponibles para la selección de ubicación al crear pedidos de recogida o envío en PDV.
    >
    > Al habilitar la característica también se actualizan páginas en PDV cuando se seleccionan las operaciones "enviar todo" o "enviar selección".

9. Para definir reglas, vaya a **Retail y Commerce \> Gestión de pedidos distribuida \> Configuración \> Administrar reglas**. Actualmente se admiten las siguientes reglas de DOM:

    - **Regla de inventario mínimo**: este tipo de regla permite a las organizaciones "proteger" una cantidad específica de un producto para propósitos distintos al cumplimiento de pedidos. Por ejemplo, las organizaciones pueden preferir que DOM no considere todo el inventario disponible en una tienda para el cumplimiento de pedidos. En lugar de ello, pueden preferir que reserven parte del inventario para los clientes que acudan a la tienda. Cuando se utiliza este tipo de regla, puede definir el inventario mínimo que se debe conservar para una categoría de productos, un producto individual o una variante del producto, por ubicación o por grupo de ubicaciones.
    - **Regla de prioridad de ubicación de cumplimiento**: este tipo de regla permite a las organizaciones definir una jerarquía de ubicaciones para establecer la prioridad que debe tener en cuenta el motor de DOM cuando intente identificar ubicaciones de cumplimiento para productos concretos. El intervalo válido de prioridades es de 1 a 10, donde 1 es la máxima prioridad y 10 es la prioridad más baja. Las ubicaciones que tienen mayor prioridad se consideran antes que las ubicaciones de prioridad más baja. Si la regla se define como una regla de restricción completa, los pedidos se gestionarán solo para las ubicaciones que tengan una prioridad definida.
    - **Regla de pedidos parciales**: la regla permite a las organizaciones definir si un pedido o las líneas de pedido se pueden cumplir parcialmente. Están disponibles los siguientes parámetros:

        - **¿Desea completar pedidos parciales?** – Si esta opción se establece en **Sí**, DOM puede cumplir solo una parte de la cantidad en una línea de pedido. Este cumplimiento parcial se logra dividiendo la línea de pedido.
        - **¿Desea completar líneas parciales?** – Si esta opción se establece en **Sí**, DOM puede cumplir una cantidad parcial de líneas de pedido. Este cumplimiento parcial se logra dividiendo la línea de pedido.
        - **¿Desea completar el pedido desde una sola ubicación?**: si esta opción se establece en **Sí**, DOM se asegura de cumplir todas las líneas de un pedido desde una sola ubicación.


        En la tabla siguiente se explica el comportamiento que se produce cuando se define una combinación de estos parámetros.

        | Número de combinación | Completar pedidos parciales | Completar líneas parciales | Completar el pedido desde una sola ubicación | Descripción |
        |------|------------------------|-----------------------|--------------------------------------|-------------|
        | 1    | Sí                    | Sí                   | Sí                                  | Se pueden cumplir unas cuantas líneas del pedido y se pueden cumplir líneas individuales parcialmente, pero todas las líneas deben ser de una misma ubicación en una instancia de la ejecución de DOM. (Esta combinación no se admite actualmente). |
        | 2    | Sí                    | No                    | Sí                                  | Se pueden cumplir unas cuantas líneas del pedido, pero no se pueden cumplir líneas individuales parcialmente, y todas las líneas cumplidas deben ser de una misma ubicación en una instancia de la ejecución de DOM. (Esta combinación no se admite actualmente). |
        | 3    | Sí                    | Sí                   | No                                   | Se pueden cumplir unas cuantas líneas del pedido, pero no se pueden cumplir líneas individuales parcialmente, y cada línea se puede cumplir desde más de una ubicación en una instancia de la ejecución de DOM. |
        | 4\*  | No                     | No aplicable        | No                                   | Deben cumplirse todas las líneas de pedido, las líneas individuales no se pueden cumplir parcialmente y cada línea de pedido se puede cumplir desde una ubicación diferente. |
        | 5\*  | No                     | No aplicable        | Sí                                  | Deben cumplirse todas las líneas de pedido, las líneas individuales no se pueden cumplir parcialmente y todas las líneas de pedido se pueden entregar desde una sola ubicación. |
        | 6\*  | No                     | No aplicable        | No                                   | Esta combinación funciona como la combinación 4, ya que **Completar líneas parciales** no se puede establecer en **Sí** cuando **Completar pedidos parciales** está establecida en **No**. |
        | 7\*  | No                     | No aplicable        | Sí                                  | Esta combinación funciona como la combinación 5, ya que **Completar líneas parciales** no se puede establecer en **Sí** cuando **Completar pedidos parciales** está establecida en **No**. |
        | 8    | Sí                    | No                    | No                                   | Se pueden cumplir unas cuantas líneas del pedido, pero no se pueden cumplir líneas individuales parcialmente, y las distintas líneas de pedido se pueden cumplir desde más de una ubicación en una instancia de la ejecución de DOM. |
        | 9\*  | No                     | No aplicable        | Sí                                  | Deben cumplirse todas las líneas de pedido, y todas desde una sola ubicación. |

        \* Si **Completar pedidos parciales** está establecida en **No**, siempre se considerará que **Completar líneas parciales** está establecida en **No**, independientemente de cuál sea su valor real.

        > [!NOTE]
        > En Retail versión 10.0.5, el parámetro **Completar el pedido desde una sola ubicación** se cambió a **Ubicaciones de cumplimiento máximas**. En lugar de permitir que un usuario configure si los pedidos se pueden completar a partir de una ubicación únicamente o completar desde las máximas ubicaciones posibles, los usuarios pueden especificar ahora si el cumplimiento puede ser de un conjunto de ubicaciones determinado (hasta un máximo de 5) o de tantas ubicaciones como sea posible. Esto ofrece una mayor flexibilidad en cuanto al número de ubicaciones desde las que se puede completar el pedido. Esta regla solo funciona con el Solucionador de problemas. 

   - **Regla de ubicación de cumplimiento sin conexión**: esta regla permite a las organizaciones especificar una ubicación o un grupo de ubicaciones como sin conexión o no disponibles para DOM, de manera que no se les puedan asignar pedidos a esas ubicaciones para cumplimiento.
    - **Regla de número máximo de rechazos**: la regla permite a las organizaciones definir un umbral de rechazos. Cuando se alcance el umbral, el procesador de DOM marcará un pedido o una línea de pedido como una excepción y los excluirá del procesamiento posterior.

        Después de que se hayan asignado líneas de pedido a una ubicación, la ubicación puede rechazar una línea de pedido asignada si no la puede cumplir por alguna razón. Las líneas rechazadas se marcan como excepciones y se colocan en un grupo para procesarlas en la siguiente ejecución. Durante la siguiente ejecución, DOM intentará asignar la línea rechazada a otra ubicación. La nueva ubicación también puede rechazar la línea de pedido asignada. Este ciclo de asignación y rechazo puede repetirse varias veces. Cuando el recuento de rechazos alcanza el umbral definido, DOM marcará la línea de pedido como una excepción permanente y no volverá a seleccionar esa línea para su asignación. DOM solo volverá a considerar la línea de pedido para su reasignación si un usuario restablece manualmente el estado de la línea de pedido.

   - **Regla de distancia máxima**: esta regla permite a las organizaciones definir la distancia máxima a la que debe estar una ubicación o un grupo de ubicaciones para cumplir el pedido. Si se definen para una ubicación reglas de distancia máxima que se superponen, DOM aplicará a dicha ubicación la distancia máxima definida que sea menor.
    - **Regla de número máximo de pedidos**: esta regla permite a las organizaciones definir el número máximo de pedidos que una ubicación o un grupo de ubicaciones pueden procesar en un día de calendario. Si el número máximo de pedidos se asigna a una ubicación en un solo día, DOM no asignará más pedidos a esa ubicación durante el resto de ese día de calendario.

   Veamos algunos de los atributos comunes que se pueden definir para todos los tipos de reglas descritos anteriormente:

   - **Fecha de inicio** y **Fecha de finalización**: estos campos se pueden usar para establecer las fechas de vigencia de cada regla.
   - **Deshabilitada**: en una ejecución de DOM solo se tendrán en cuenta las reglas que tengan el valor **No** en este campo.
   - **Restricción completa**: una regla se puede definir como de restricción completa o no. Cada ejecución de DOM realiza dos iteraciones. En la primera iteración, cada regla se trata como una regla de restricción completa, independientemente del valor de este campo. Es decir, se aplican todas las reglas. La única excepción es la regla de **Prioridad de ubicación**. En la segunda iteración se quitan las reglas que no se hayan definido como reglas de restricción completa, y se asignarán a ubicaciones los pedidos y las líneas de pedido que no se asignaron a ubicaciones cuando se aplicaron todas las reglas.

10. Se utilizan perfiles de cumplimiento para agrupar un conjunto de reglas, entidades jurídicas, orígenes de pedido de ventas y modos de entrega. Cada ejecución de DOM es para un perfil de cumplimiento específico. De esta manera, las organizaciones pueden definir y ejecutar un conjunto de reglas para un conjunto de entidades jurídicas en los pedidos que tengan orígenes de pedido de ventas y modos de entrega específicos. Por lo tanto, si hubiera que ejecutar conjunto de reglas distintos para conjuntos de orígenes de pedido de ventas o conjuntos de modos de entrega diferentes, es posible definir los perfiles de cumplimiento correspondientes. Siga estos pasos para configurar perfiles de cumplimiento:  

    1. Vaya a **Retail y Commerce \> Gestión de pedidos distribuida \> Configuración \> Perfiles de cumplimiento**.
    2. Seleccione **Nuevo**.
    3. Escriba valores en los campos **Perfil** y **Descripción**.
    4. Establezca la opción **Aplicar resultado automáticamente**. Si establece esta opción en **Sí**, los resultados de la ejecución de DOM para el perfil se aplicarán automáticamente a las líneas de pedido de ventas. Si la establece en **No**, los resultados solo se podrán visualizar en el plan de cumplimiento. No se aplicarán a las líneas de pedido de ventas.
    5. Si desea que el perfil de DOM se ejecute para pedidos que tengan cualquier origen de pedido de ventas, como pedidos cuyo origen de pedido de ventas esté indefinido, establezca la opción **Procesar pedidos con origen de ventas vacío** en **Sí**. Para ejecutar el perfil para solo unos pocos orígenes de pedido de ventas, puede definirlos en la página **Orígenes de ventas**, tal como se explica más adelante.

    > [!NOTE]
    > En Commerce versión 10.0.12 y posterior, la **Capacidad para asignar un grupo de cumplimiento a un perfil de cumplimiento** debe estar habilitada en el espacio de trabajo **Administración de características**. 
    >
    > Esta característica agrega una nueva configuración en la página **Perfil de cumplimiento** que se puede asociar a un solo grupo de cumplimiento. 
    >
    > Si selecciona el grupo de cumplimiento, las reglas de DOM para ese perfil de cumplimiento se ejecutarán de manera eficiente frente a los almacenes de "envío" incluidos en el grupo de cumplimiento. 
    > 
    > Para utilizar esta característica de manera efectiva, asegúrese de que haya un grupo de cumplimiento que contenga todos los almacenes de envío y luego asocie ese grupo de cumplimiento al perfil de cumplimiento.
    
    6. En la ficha desplegable **Entidades jurídicas** seleccione **Agregar** y, a continuación, seleccione una entidad jurídica.
    7. En la ficha desplegable **Reglas**, seleccione **Agregar** y seleccione la regla que desee vincular al perfil.
    8. Repita los dos pasos anteriores hasta que haya asociado todas las reglas necesarias al perfil.
    9. Seleccione **Guardar**.
    10. En el panel de acciones, en la pestaña **Configuración**, seleccione **Modos de entrega**.
    11. En la página **Modos de entrega**, seleccione **Nuevo**.
    12. En el campo **Empresa**, seleccione la entidad jurídica. La lista de empresas se limita a las entidades jurídicas que agregó anteriormente.
    13. En el campo **Modo de entrega**, seleccione el modo de entrega que desea asociar a este perfil. Un modo de entrega no se puede asociar a varios perfiles activos.
    14. Repita los dos pasos anteriores hasta que haya asociado todos los modos de entrega necesarios al perfil.
    15. Cierre la página **Modos de entrega**.
    16. En el panel de acciones, en la pestaña **Configuración**, seleccione **Orígenes de pedido de ventas**.
    17. En la página **Orígenes de ventas**, seleccione **Nuevo**.
    18. En el campo **Empresa**, seleccione la entidad jurídica. La lista de empresas se limita a las entidades jurídicas que agregó anteriormente.
    19. En el campo **Origen de la venta**, seleccione el origen de ventas que desea asociar a este perfil. Un origen de ventas no se puede asociar a varios perfiles activos.
    20. Repita los dos pasos anteriores hasta que haya asociado todos los orígenes de ventas necesarios al perfil.
    21. Cierre la página **Orígenes de ventas**.
    22. Establezca la opción **Habilitar perfil** en **Sí**. Si hubiera algún error en la configuración, aparecerá un mensaje de advertencia.

## <a name="dom-processing"></a>Procesamiento de DOM

DOM solo se ejecutará en un trabajo por lotes. Para configurar el trabajo por lotes de DOM, siga estos pasos.

1. Vaya a **Retail y Commerce \> Gestión de pedidos distribuida \> Procesamiento por lotes \> Configuración de trabajo del procesador de DOM**.
1. En la ficha desplegable **Parámetros**, en el campo **Perfil de cumplimiento**, seleccione un perfil para el que se pueda ejecutar DOM.
1. En la ficha desplegable **Ejecutar en segundo plano**, en el campo **Grupo de lotes**, seleccione un grupo de lotes configurado.
1. En el campo **Descripción de la tarea**, escriba un nombre descriptivo para el trabajo por lotes.
1. Seleccione **Periodicidad** y defina la periodicidad del trabajo por lotes.
1. Seleccione **Aceptar**.

Durante el procesamiento, DOM tendrá en cuenta los pedidos y las líneas de pedido como se describe a continuación:

- Las líneas de pedido que cumplan con los criterios para orígenes de pedido de ventas, modos de entrega y entidad jurídica definidos en el perfil de DOM, y que además cumplan cualquiera de estos criterios:

    - Se crean desde canales de Commerce.
    - DOM nunca las ha gestionado.
    - DOM las ha gestionado antes, pero se han marcado como excepciones y están por debajo del umbral de número máximo de intentos.
    - El modo de entrega no es recogida o entrega electrónica.
    - No se han marcado para entrega.
    - No se han excluido manualmente.

- Pedidos que no están en espera.

Después de aplicar las reglas, las restricciones de inventario y la optimización, DOM elige la ubicación más cercana a la dirección de entrega del cliente.

![Criterios de pedidos de ventas](./media/ordercriteria.png "Criterios de pedidos de ventas")

## <a name="results-of-dom-runs"></a>Resultados de las ejecuciones de DOM

Si el perfil de cumplimiento se establece en **Aplicar resultado automáticamente**, los resultados de la ejecución se aplicarán automáticamente a las líneas de pedido de ventas, y el plan de cumplimiento se podrá ver por separado. Sin embargo, si el perfil de cumplimiento no está establecido en **Aplicar resultado automáticamente**, los resultados de la ejecución solo se podrán ver desde la vista de plan de cumplimiento. 

Para ver todos los planes de cumplimiento generados, siga estos pasos.

1. Vaya a **Retail y Commerce \> Gestión de pedidos distribuida \> Gestión de pedidos distribuida**.
2. En el espacio de trabajo **Gestión de pedidos distribuida**, seleccione el icono **Planes de cumplimiento**.
3. Seleccione el identificador del plan de cumplimiento que desee ver.

    La sección de detalles del pedido del plan de cumplimiento muestra las líneas de pedido de ventas originales que formaron parte de la ejecución. Además de los campos de línea de pedido de ventas estándar, la sección de detalles del pedido también incluye los tres campos siguientes relacionados con DOM:

    - **Tipo de cumplimiento**: este campo indica si la línea de pedido de ventas está totalmente gestionada para una ubicación, parcialmente asignada o no está asignada.
    - **Dividir**: este campo indica si la línea de pedido de ventas se ha dividido y gestionado para distintas ubicaciones.
    - **Número de ubicaciones de cumplimiento**: este campo indica cuántas líneas de cumplimiento se han creado para una línea de pedido de ventas (en función del número de ubicaciones a las que se asignó la línea de pedido de ventas original).

    La sección de detalles de cumplimiento de pedido muestra la asignación de las líneas de pedido de ventas originales a distintas ubicaciones, junto con sus cantidades.

## <a name="order-line-actions-and-statuses"></a>Acciones y estados de línea de pedido

A continuación se describen los valores de configuración de la línea de pedido. Para abrir la línea de pedido, vaya a **Retail y Commerce \> Clientes \> Todos los pedidos de ventas**.
- Si establece en **Sí** la opción **Excluir de procesamiento de DOM** en la pestaña **General** de la línea de pedido de ventas, el pedido o la línea de pedido se excluirán del procesamiento de DOM.
- El campo **Estado de DOM** en la pestaña **General** de la línea de pedido de ventas se puede establecer en uno de los siguientes valores:

    - **Ninguno**: la línea de pedido nunca se ha gestionado.
    - **Completado**: la línea de pedido se ha gestionado y asignado correctamente a una ubicación.
    - **Excepción**: la línea de pedido se ha gestionado pero no se puede asignar a una ubicación. Las excepciones tienen varios subtipos que se pueden ver en el espacio de trabajo de DOM:

        - **Ninguna cantidad disponible**: no hay inventario disponible para asignar el pedido en las ubicaciones.
        - **Número máximo de rechazos**: la línea de pedido ha alcanzado el umbral de número máximo de rechazos.
        - **Conflicto de modificación de datos**: la línea de pedido de ventas ha cambiado desde que se gestionó el pedido. Por lo tanto, no se puede aplicar el plan de cumplimiento al pedido.
        - **Excepción específica de línea de pedido**: hay varias excepciones en la línea de pedido.

- Durante la entrada del pedido de ventas, DOM puede ejecutarse en modo interactivo. Al introducir una línea de pedido, después de especificar el producto y la cantidad, puede seleccionar **Actualizar línea** y, a continuación, seleccionar **Sugerir ubicación de cumplimiento** en **DOM**. Verá una lista de ubicaciones basada en las reglas de DOM que pueden cumplir la cantidad de la línea de pedido. Esta lista se ordena por distancia. Seleccione una ubicación para establecer el sitio y el almacén de datos correspondientes en la línea de pedido de ventas. Para poder utilizar esta funcionalidad debe haber un perfil de cumplimiento activo que coincida con el origen de ventas y el modo de entrega en la línea de ventas.
- Para ver los registros de ejecución de DOM para una línea de pedido de ventas, seleccione **Línea de pedido de ventas** y, a continuación, seleccione **Ver registros de DOM** en **DOM**. Los registros de DOM muestran todos los eventos y registros generados por la ejecución de DOM. Los registros pueden ayudarle a comprender por qué se ha asignado una ubicación concreta a la línea de pedido, y qué reglas y restricciones se aplicaron como parte de la asignación. En la pestaña **Administrar**, los registros de DOM también están disponibles en el nivel del encabezado del pedido de ventas.

## <a name="run-a-clean-up-job-for-dom-fulfillment-plans"></a>Ejecutar un trabajo de limpieza de planes de cumplimiento de DOM

Se crean planes de cumplimiento a medida que se ejecuta el procesamiento de DOM. Con el tiempo, el sistema acumulará una gran cantidad de planes de cumplimiento. Para administrar el número de planes de cumplimiento conservados por el sistema, puede configurar un trabajo por lotes que elimine los planes de cumplimiento más antiguos en función del valor de **Período máximo de retención en días**.

1. Vaya a **Retail y Commerce \> Gestión de pedidos distribuida \> Procesamiento por lotes \> Configuración de trabajo de eliminación de datos de cumplimiento de DOM**. 
1. En el campo **Grupo de lotes**, seleccione un grupo de lotes configurado.
1. Seleccione **Periodicidad** y defina la periodicidad del trabajo por lotes.
1. Seleccione **Aceptar**.

## <a name="more-information"></a>Más información

Veamos algunas cosas que hay que tener en cuenta al usar la característica DOM:

- Actualmente, DOM solo tiene en cuenta los pedidos creados en los canales de Commerce. Los pedidos de ventas se identifican como pedidos de ventas cuando la opción **Venta de Commerce** está establecida en **Sí**.
- Microsoft no ha probado DOM con funciones avanzadas de gestión de almacenes. Los clientes y los socios deben determinar si DOM es compatible con las capacidades y los procesos avanzados de gestión de almacenes que necesitan.
- DOM solo está disponible en la versión de Commerce para la nube. No se admite en implementaciones locales.


[!INCLUDE[footer-include](../includes/footer-banner.md)]