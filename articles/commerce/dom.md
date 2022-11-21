---
title: Gestión de pedidos distribuida (DOM)
description: En este artículo se describe la funcionalidad de gestión de pedidos distribuida (DOM) de Dynamics 365 Commerce.
author: josaw1
ms.date: 02/08/2022
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
ms.openlocfilehash: a18441c44869e0e95cf79e35045dd7eacca7e43d
ms.sourcegitcommit: 4f987aad3ff65fe021057ac9d7d6922fb74f980e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2022
ms.locfileid: "9764191"
---
# <a name="distributed-order-management-dom"></a>Gestión de pedidos distribuida (DOM)

[!include [banner](includes/banner.md)]

En este artículo se describe la funcionalidad de gestión de pedidos distribuida (DOM) de Microsoft Dynamics 365 Commerce.

DOM es una solución para la optimización del proceso de entrega de pedidos de omnicanal que ayuda a maximizar este proceso en una red de cadena de suministro. DOM le ayudará garantizar que los productos se entregan a los clientes en las cantidades correctas, desde el origen debido y en el momento adecuado. DOM también puede ayudarle a maximizar las ganancias, minimizar los costes y cumplir los requisitos de nivel de servicio.

DOM utiliza programación en enteros mixta (MIP) y modelos de análisis predictivo para optimizar los procesos en el nivel de lote y en el nivel de pedidos individuales. Esta capacidad permite a los minoristas utilizar reglas definidas para equilibrar muchas necesidades de procesos de entrega conflictivos. En una red de suministro moderna, en la que el proceso de entrega del producto puede provenir de múltiples canales, las organizaciones deben adaptarse rápidamente a los cambios en los pedidos, los problemas de disponibilidad de los proveedores y los picos de demanda. DOM le ayuda a sacar el máximo partido del proceso de entrega de pedidos y a encontrar los orígenes adecuados para la entrega de productos, en función de las restricciones y objetivos comerciales, como, por ejemplo, minimizar los costes a través de procesos de entrega de pedidos desde el origen más cercano. DOM utiliza la distancia entre los orígenes para el proceso de entrega de productos y los destinos de envío, los factores de costes que se establecen como objetivos de optimización y las reglas definidas a modo de restricciones, como el inventario en los nodos del proceso de entrega para optimizar el proceso de entrega de los pedidos. DOM permite definir múltiples perfiles para que las empresas puedan ejecutar diferentes estrategias de optimización, según el tipo de negocio o segmento de consumidores. 

La siguiente ilustración muestra el ciclo de vida de un pedido de ventas en un sistema DOM.

![Ciclo de vida de pedido de ventas en el contexto de DOM.](./media/flow.png "Ciclo de vida de pedido de ventas en el contexto de DOM")

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
    - **Tipo de solucionador**: seleccione un valor. Retail incluye dos tipos de solucionador con Commerce: **Solucionador de producción** y **Solucionador simplificado**. Para todos los equipos que ejecuten DOM (es decir, todos los servidores que formen parte del grupo DOMBatch) hay que seleccionar **Solucionador de producción**. El Solucionador de producción requiere la clave de licencia especial que se otorga e implementa en los entornos de producción, de forma predeterminada. En entornos de nivel 2 o más, el Solucionador de producción ya estará habilitado. Para los entornos que no sean de producción esta clave de licencia debe implementarse manualmente. Siga estos pasos para implementar manualmente la clave de licencia:

        1. En Microsoft Dynamics Lifecycle Services, abra la Biblioteca de activos compartidos, seleccione **Modelo** como tipo de activo y descargue el archivo **Licencia de DOM**.
        1. Inicie el Administrador de Microsoft Internet Information Services (IIS), haga clic con el botón derecho en **Sitio web de AOSService** y, a continuación, seleccione **Explorar**. Se abre una ventana del Explorador de Windows en **\<AOS service root\>\\webroot**. Anote la ruta de acceso a \<AOS Service root\>. La va a utilizar en el paso siguiente.
        1. Copie el archivo de configuración en el directorio **\<AOS Service root\>\\PackagesLocalDirectory\\DOM\\bin**.
        1. Vaya al cliente de Headquarters y abra la página **Parámetros de DOM**. En la pestaña **Solucionador**, en el campo **Tipo de solucionador**, seleccione **Solucionador de producción** y confirme que no aparece ningún mensaje de error.

        > [!NOTE]
        > El Solucionador simplificado se proporciona para que los minoristas puedan probar la característica DOM sin tener que implementar la licencia especial. Las organizaciones no deben usar el Solucionador simplificado en entornos de producción.
        >
        > El Solucionador de producción mejora el rendimiento (como el número de pedidos y líneas de pedido que se pueden manejar en una ejecución) y la convergencia de resultados (dado que un lote de pedidos puede no producir el mejor resultado en algunas situaciones). La regla **Pedidos parciales** requiere el Solucionador de producción.

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
    > En Commerce versión 10.0.12 y posteriores, la **Capacidad para especificar ubicaciones como "Envío" o "Recogida" habilitada dentro del grupo de cumplimiento** debe estar habilitada en el espacio de trabajo **Administración de características**.
    >
    > Esta característica agrega nuevas configuraciones en la página **Grupo de cumplimiento** para que pueda definir si el almacén se puede utilizar para envíos o si la combinación de almacén y tienda se puede utilizar para envíos, recogidas o ambos. 
    >
    > Si habilita la característica, se actualizarán las opciones disponibles para la selección de ubicación al crear pedidos de recogida o envío en PDV.
    >
    > Al habilitar la característica también se actualizan páginas en PDV cuando se seleccionan las operaciones "enviar todo" o "enviar selección".

9. Para definir reglas, vaya a **Retail y Commerce \> Gestión de pedidos distribuida \> Configuración \> Administrar reglas**. Actualmente se admiten las siguientes reglas de DOM:

    - **Regla de inventario mínimo**: este tipo de regla permite a las organizaciones "proteger" una cantidad específica de un producto para propósitos distintos al cumplimiento de pedidos. Por ejemplo, las organizaciones pueden preferir que DOM no considere todo el inventario disponible en una tienda para el cumplimiento de pedidos. En lugar de ello, pueden preferir que reserven parte del inventario para los clientes que acudan a la tienda. Cuando se utiliza este tipo de regla, se podrá definir el inventario mínimo que deberá conservarse para una categoría de productos, un producto individual o una variante del producto, por ubicación o por grupo de ubicaciones. También puede definir el inventario mínimo mediante una jerarquía de categoría complementaria. Si un producto se inscribe en varias categorías, la categoría complementaria tendrá máxima importancia para todas las reglas en las que puede usar categorías.
    - **Regla de prioridad de ubicación para el proceso de entrega**: este tipo de regla permite a las organizaciones definir una jerarquía de ubicaciones para establecer la prioridad que debe tener en cuenta el motor de DOM cuando intente identificar ubicaciones en el proceso de entrega para productos concretos. El intervalo válido de prioridades es de 1 a 10, donde 1 es la máxima prioridad y 10 es la prioridad más baja. Las ubicaciones que tienen mayor prioridad se consideran antes que las ubicaciones de prioridad más baja. Si la regla se define como una regla de restricción completa, los pedidos se gestionarán solo para las ubicaciones que tengan una prioridad definida. DOM da preferencia al envío de pedidos completos desde una ubicación. Por tanto, si un pedido completo y sus líneas no están disponibles desde una ubicación con prioridad 1, DOM intentará procesar la entrega desde una ubicación con prioridad 2.
    - **Regla de pedidos parciales**: en la versión 10.0.5 de Retail, el parámetro **Procesar entrega del pedido desde una sola ubicación** se cambió a **Ubicaciones máximas para procesamiento de entrega**. El parámetro anterior permitía a los usuarios configurar si se podían procesar entregas de pedidos desde una sola ubicación o desde tantas ubicaciones como fuera posible. El nuevo parámetro permite a los usuarios especificar si el proceso de entrega puede efectuarse desde un conjunto definido de ubicaciones (hasta cinco) o desde tantas ubicaciones como sea posible. Para todas las opciones, excepto el proceso de entrega desde una ubicación, DOM dividirá la línea, porque el procesamiento del pedido se realiza por línea. Esta regla solo funciona con el Solucionador de problemas.
    - **Regla de ubicación para proceso de entrega sin conexión**: esta regla permite a las organizaciones especificar una ubicación o un grupo de ubicaciones sin conexión o como no disponibles para DOM, de modo que no se puede asignar pedidos a esas ubicaciones para el proceso de entrega.
    - **Regla de número máximo de rechazos**: la regla permite a las organizaciones definir un umbral de rechazos. Cuando se alcance el umbral, el procesador de DOM marcará un pedido o una línea de pedido como una excepción y los excluirá del procesamiento posterior. Para garantizar el rendimiento, DOM no analiza el historial de todos los rechazos. 

        Después de que se hayan asignado líneas de pedido a una ubicación, esta puede rechazar una línea de pedido asignada si no la puede cumplir por alguna razón. Las líneas rechazadas se marcan como excepciones y se colocan en un grupo para procesarlas en la siguiente ejecución. Durante la siguiente ejecución, DOM intentará asignar la línea rechazada a otra ubicación. La nueva ubicación también puede rechazar la línea de pedido asignada. Este ciclo de asignación y rechazo puede repetirse varias veces. Cuando el recuento de rechazos alcanza el umbral definido, DOM marcará la línea de pedido como una excepción permanente y no volverá a seleccionar esa línea para su asignación. DOM solo volverá a considerar la línea de pedido para su reasignación si un usuario restablece manualmente el estado de la línea de pedido.

    - **Regla de distancia máxima**: esta regla permite a las organizaciones definir la distancia máxima a la que debe estar una ubicación o un grupo de ubicaciones para cumplir el pedido. Si se definen para una ubicación reglas de distancia máxima que se superponen, DOM aplicará a dicha ubicación la distancia máxima definida que sea menor.
    - **Regla de número máximo de pedidos**: esta regla permite a las organizaciones definir el número máximo de pedidos que una ubicación o un grupo de ubicaciones pueden procesar. Durante el proceso de optimización, el sistema tendrá en cuenta los pedidos que no se han enviado desde estas ubicaciones. Esta comprobación se realiza en todos los perfiles. Por lo tanto, si se definen números máximos superpuestos de pedidos en perfiles de la misma ubicación, el sistema tendrá en cuenta el número máximo de pedidos definido en todos los perfiles. 

    Veamos algunos de los atributos comunes que se pueden definir para todos los tipos de reglas descritos anteriormente:

    - **Fecha de inicio** y **Fecha de finalización**: puede utilizar estos campos para activar las fechas de cada regla.
    - **Deshabilitada**: en una ejecución de DOM solo se tendrán en cuenta las reglas que tengan el valor **No** en este campo.
    - **Restricción completa**: una regla se puede definir como de restricción completa o no. Cada ejecución de DOM realiza dos iteraciones. En la primera iteración, cada regla se trata como una regla de restricción completa, independientemente del valor de este campo. Es decir, se aplican todas las reglas. La única excepción es la regla de **Prioridad de ubicación**. En la segunda iteración se quitan las reglas que no se hayan definido como reglas de restricción completa, y se asignarán a ubicaciones los pedidos y las líneas de pedido que no se asignaron a ubicaciones cuando se aplicaron todas las reglas.

10. Se utilizan perfiles de cumplimiento para agrupar un conjunto de reglas, entidades jurídicas, orígenes de pedido de ventas y modos de entrega. Cada ejecución de DOM es para un perfil de cumplimiento específico. De esta manera, las organizaciones pueden definir y ejecutar un conjunto de reglas para un conjunto de entidades jurídicas en los pedidos que tengan orígenes de pedido de ventas y modos de entrega específicos. Por lo tanto, si hubiera que ejecutar conjunto de reglas distintos para conjuntos de orígenes de pedido de ventas o conjuntos de modos de entrega diferentes, es posible definir los perfiles de cumplimiento correspondientes. Siga estos pasos para configurar perfiles de cumplimiento:  

    1. Vaya a **Retail y Commerce \> Gestión de pedidos distribuida \> Configuración \> Perfiles de cumplimiento**.
    2. Seleccione **Nuevo**.
    3. Escriba valores en los campos **Perfil** y **Descripción**.
    4. Establezca la opción **Aplicar resultado automáticamente**. Si establece esta opción en **Sí**, los resultados de la ejecución de DOM para el perfil se aplicarán automáticamente a las líneas de pedido de ventas. Si la establece en **No**, los resultados solo se podrán visualizar en el plan de cumplimiento. No se aplicarán a las líneas de pedido de ventas.
    5. Si desea que el perfil de DOM se ejecute para pedidos que tengan cualquier origen de pedido de ventas, como pedidos cuyo origen de pedido de ventas esté indefinido, establezca la opción **Procesar pedidos con origen de ventas vacío** en **Sí**. Para ejecutar el perfil para solo unos pocos orígenes de pedido de ventas, puede definirlos en la página **Orígenes de ventas**, tal como se explica más adelante.

        > [!NOTE]
        > En Commerce versión 10.0.12 y posteriores, debe estar habilitada la características **Capacidad para asignar un grupo de proceso de entrega a un perfil de proceso de entrega** en el espacio de trabajo **Administración de características**. Esta característica le permite especificar una lista de almacenes que DOM debe considerar cuando se ejecuta la optimización con un perfil de cumplimiento. Si no se especifica esta lista de almacenes, DOM buscará en todos los almacenes de las entidades jurídicas definidas en el perfil.
        >
        > Esta característica agrega una nueva configuración en la página **Perfil de proceso de entrega** que se puede asociar a un solo grupo de proceso de entrega. 
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

Después de aplicar las reglas, las restricciones de inventario y la optimización, DOM elige la ubicación más cercana a la dirección de entrega del cliente. DOM convierte las direcciones del tipo **Entrega** a los valores de latitud y longitud. Luego convierte la dirección de entrega del pedido de ventas a valores de latitud y longitud, y actualiza estos valores de latitud y longitud de la dirección para uso posterior. DOM depende de Bing Maps para determinar los valores precisos de latitud y longitud según la información de la dirección, la ciudad y el código postal.

DOM usa la API de Bing Maps para calcular la distancia aérea o por carretera, en función de la configuración. Luego utiliza esta información para determinar el coste del envío. El modelo de optimización prioriza el proceso de entrega de un pedido que se envía en su totalidad desde una ubicación. Aunque parte de un pedido esté disponible en la misma ciudad o código postal, el modelo se ha optimizado para reducir el número de envíos. 

DOM busca el inventario disponible examinando el inventario existente en las entidades V2 del almacén. En cada ejecución por lotes, DOM divide los pedidos en lotes, en función del valor del parámetro **Procesador DOM** de las tareas que se definen en el perfil. El valor predeterminado de este parámetro es **2000**. Por ejemplo, si se optimizan 10 000 líneas de pedido en una ejecución y el parámetro **Procesador DOM** se establece en el valor predeterminado **2000**, DOM creará cinco lotes que se procesarán simultáneamente. Posteriormente, los planes de proceso de entrega se obtendrán del optimizador y se aplicarán en la línea. Si hay que dividir la línea de pedido entre dos ubicaciones, DOM garantiza que los precios y los impuestos se distribuyan adecuadamente entre las líneas.

![Criterios de pedidos de ventas.](./media/ordercriteria.png "Criterios de pedidos de ventas")

## <a name="results-of-dom-runs"></a>Resultados de las ejecuciones de DOM

Si el perfil de proceso de entrega se establece en **Aplicar resultado automáticamente**, los resultados de la ejecución se aplicarán automáticamente a las líneas de pedido de ventas y el plan de proceso de entrega se podrá ver por separado. Sin embargo, si el perfil de cumplimiento no está establecido en **Aplicar resultado automáticamente**, los resultados de la ejecución solo se podrán ver desde la vista de plan de cumplimiento. 

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
- Microsoft no ha probado DOM con funciones avanzadas de gestión de almacenes. Por tanto, los clientes y los socios deben determinar meticulosamente si DOM es compatible con las funciones y los procesos avanzados de gestión de almacenes que necesitan. El almacenamiento avanzado permite dimensiones configurables, como, por ejemplo, el estado del inventario, que no ofrecen datos esclarecedores precisos sobre el inventario disponible. DOM ofrece un método extensible que permite configurar el inventario disponible para las implementaciones que utilizan almacenamiento avanzado. Se puede utilizar para trabajar con valores personalizados del estado del inventario y otras dimensiones.

    La extensibilidad en DOM es limitada porque la optimización se produce en el modelo MIP generado previamente y que tiene en cuenta la optimización y sus restricciones. Ya están disponibles varios puntos extensibles para configurar el inventario y la optimización del procesamiento posterior. Los perfiles DOM pueden diferir según el origen de las ventas y el modo de entrega. El origen del pedido de ventas se puede definir durante la ingesta del pedido y se pueden usar diferentes estrategias de optimización en función de estos valores. DOM también admite la creación de trabajos por lotes personalizados que puede utilizar la tarea del procesador DOM como entrada y permitir pasar el perfil como parámetro. Por tanto, se puede ejecutar una optimización tras otra para admitir diferentes escenarios comerciales.

- DOM solo está disponible en la versión de Commerce para la nube. No se admite en implementaciones locales.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
