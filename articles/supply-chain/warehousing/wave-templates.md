---
title: Plantillas de oleada
description: En este tema se describe cómo configurar los criterios que determinan si las oleadas se procesan manual o automáticamente, y el trabajo que se genera para un almacén cuando se procesa una oleada.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: b02283a6e0a4ef0d61be8b66f82be8c125028cb0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813636"
---
# <a name="wave-templates"></a>Plantillas de oleada

[!include [banner](../includes/banner.md)]

En este tema se describe cómo configurar los criterios que determinan si las oleadas se procesan manual o automáticamente, y el trabajo que se genera para un almacén cuando se procesa una oleada. Especifique los criterios configurando consultas y plantillas de oleada que hagan coincidir una oleada con las líneas emitidas en pedidos de ventas, pedidos de producción, y kanbans.

## <a name="settings-for-wave-templates"></a>Configuración de las plantillas de oleada

Cuando configure una plantilla de oleada, especifique lo siguiente:

- El **Sitio** y el **Almacén** para los que la plantilla creará el trabajo.
- El orden en que se evaluarán las plantillas. La secuencia en la que las plantillas coinciden con líneas emitidas de pedidos de ventas, pedidos de producción y kanbans. Cuando se libera una línea, el sistema aplica la primera plantilla de oleada para la que la línea cumple los criterios. Cuanto más amplios sean los criterios, más probable es que una línea cumpla con los criterios, por lo que debe colocar las plantillas con los criterios más específicos en la parte superior de la lista. Utilice los botones **Subir** y **Bajar** del panel de acciones para organizar las plantillas en la lista.
- Las acciones realizadas por cada plantilla. La oleada **Métodos** realiza las acciones que crea la plantilla, como la creación o la distribución de trabajo para cada tipo de plantilla de oleada.
- Los atributos de oleada (filtros) que deben aplicarse para que se utilice la plantilla de oleada.

> [!NOTE]
> Si es necesario, un programador puede crear métodos adicionales. Puede ver la lista completa de métodos en la página **Métodos de proceso de oleadas**.

Algunos ajustes representan decisiones estratégicas para el procesamiento de la oleada, del siguiente modo:

- Si la plantilla se usa para enviar artículos para pedidos de ventas y pedidos de transferencia, o se usa para mover artículos a la producción para los pedidos de producción o kanbans.
- Si una oleada se procesa manual o automáticamente, del modo siguiente:

  - **Procesamiento manual**: la línea se agrega a una oleada y el inventario se reserva, sin embargo, debe seleccionar **Procesos** en la página de lista **Todas las oleadas** para crear el trabajo de picking para el pedido.
  - **Procesamiento automático**: puede automatizar completamente o parcialmente el procesamiento de la oleada. Si ha automatizado completamente el procesamiento de la oleada, se crea una oleada que incluye la línea del pedido de ventas, el pedido de producción o el kanban cuando se crean un pedido de ventas, un pedido de producción o un kanban. Los artículos se deducen de inventario disponible y se crea el trabajo de picking. Si automatiza parcialmente el procesamiento de la oleada, puede especificar los valores que desencadenarán el procesamiento de la oleada. Por ejemplo, puede especificar un peso máximo para los envíos que desencadenarán el procesamiento de la oleada cuando el peso total de las líneas de la oleada alcance el valor.

- Si asigna envíos a una oleada abierta. Por ejemplo, si promete a los clientes que un pedido realizado a las 12:00 p.m. se enviará en el plazo de 24 horas, puede configurar la plantilla de oleada para asignar automáticamente las líneas de pedido a una oleada abierta hasta las 12:00 p.m. En aquel momento la oleada se procesa automáticamente.

Cuando se procesa una oleada, el trabajo de picking que se crea se basa en la plantilla de trabajo y la directiva de ubicación especificada para el almacén. La plantilla de trabajo especifica cómo se crea el trabajo de picking, y la directiva de ubicación especifica las ubicaciones de picking y colocación.

## <a name="create-a-wave-template"></a>Crear una plantilla de oleada

Para configurar una plantilla de oleada, siga estos pasos:

1. Vaya a **Gestión de almacenes** \> **Configurar** \> **Oleadas** \> **Plantillas de oleada**.
1. Seleccione **Nuevo** para crear una nueva plantilla de oleada.
1. En el campo **Tipo de plantilla de oleada**, seleccione una de las siguientes opciones:

    - *Envío*: use la plantilla de oleada para enviar artículos para los pedidos de ventas y los pedidos de transferencia.
    - *Pedidos de producción*: use la plantilla de oleada para mover artículos para los pedidos de producción.
    - *Kanban*: use la plantilla de oleada para mover artículos para los pedidos kanban.

1. En los campos **Nombre de la plantilla de oleada** y **Descripción de la plantilla de oleada**, introduzca un nombre y una descripción para la plantilla de la oleada.

    > [!NOTE]
    > Si más de una plantilla se crea para un almacén, el número en el campo **Secuencia de plantilla de oleada** indica la posición de la plantilla en la secuencia en que las plantillas se aplican cuando se cumplen los criterios de la plantilla. Puede seleccionar **Mover arriba** o **Mover abajo** para reorganizar la secuencia de plantillas.

1. En los campos **Sitio** y **Almacén**, seleccione el sitio y el almacén para los que la plantilla de oleada creará oleadas y trabajo de picking.
1. Si desea automatizar el procesamiento de oleadas, realice los siguientes ajustes según sea necesario:

    - **Creación automática de oleada**: establezca esta opción a *Sí* crear automáticamente una oleada cuando un pedido de ventas, un pedido de producción o un kanban se libera al almacén.
    - **Asignar a oleadas abiertas**: establezca esto en *Sí* para asignar líneas automáticamente a una oleada abierta cuando se liberan las líneas. Las líneas se asignan a oleadas basadas en el filtro de consulta de la plantilla de oleada.
    - **Procesar oleada en el momento de liberar al almacén**: Establezca esto en *Sí* para procesar automáticamente la oleada y crear trabajo cuando se libera una línea al almacén.
    - **Procesar oleada automáticamente en umbral**: establezca esta opción a *Sí* para procesar automáticamente la oleada cuando sus valores lleguen a los umbrales del peso, el envío y las líneas especificadas en el grupo de campos **Umbrales de oleada**. Esta configuración sólo está activa si se ha seleccionado *Envío* en el campo **Tipo de plantilla oleada**.
    - **Automatizar la liberación de oleadas**: establezca esto en *Sí* para liberar automáticamente la ola. El trabajo de picking se crea y se pone a disposición en los dispositivos móviles.
    - **Liberar automáticamente el trabajo de reabastecimiento**: establezca esta opción en *Sí* para crear trabajo de reabastecimiento basado en demandas y libérelo automáticamente. Debe agregar el método de oleada de reabastecimiento en la plantilla de oleada, y crear una plantilla de reabastecimiento usando el tipo *Demanda de oleadas*. Configure una plantilla de reabastecimiento en la página **Plantillas de reabastecimiento**. Esto requiere que se agregue el método de reabastecimiento a la plantilla de oleada.
    - **Continuat procesado de oleado cuando la creación de trabajo falla**: cuando se establece en *Sí*, el sistema usará una ubicación en blanco si no puede reservar inventario en la ubicación propuesta por la directiva de ubicación (por ejemplo, porque el inventario ya no está disponible). Cuando se establece en *No*, la oleada no prosperará si el sistema no puede reservar el inventario.

1. Seleccione el grupo de campo **Umbrales de onda** según sea necesario:
    - **Umbral de peso de la oleada**: introduzca el peso máximo que puede contener una ola.
    - **Umbral de envío**: introduzca el número máximo de envíos que se pueden incluir en una ola.
    - **Umbral de línea**: introduzca el número máximo de líneas que se pueden incluir en una ola.

1. En el grupo del campo **Valores predeterminados**, seleccione los atributos de oleada para usarlos como criterios adicionales para la plantilla de oleada. Los atributos de oleada son útiles para asignar criterios adicionales, como un nombre de cliente específico, a una plantilla de oleada. Puede crear estos atributos en la página **Atributos de oleada**. 

1. Establezca **Directiva de notificación de olas** a la directiva que desea utilizar para generar notificaciones relacionadas con las ondas que utilizan esta plantilla. Para ver un ejemplo de una directiva de notificación de oleadas, consulte [Notificaciones de ejecución de olas](wave-execution-notifications.md).

1. En la ficha desplegable **Métodos**, en el panel **Métodos seleccionados** se muestran los métodos para la plantilla de oleada seleccionada. Los métodos de oleada realiza las acciones que crea la plantilla, como la creación o la distribución de trabajo. Estas acciones también se conocen como pasos de oleada. Los métodos de oleada están predefinidos para cada tipo de plantilla de oleada. No puede quitar los métodos predefinidos de oleada, sin embargo, puede reorganizar el orden de los métodos y agregar métodos adicionales. Por ejemplo, si está creando una plantilla de oleada para envíos, puede agregar métodos para el reabastecimiento y la creación de contenedores. La creación de contenedores de oleada se puede agregar a una secuencia de métodos de oleada para definir la creación de contenedores de las líneas procesadas en una plantilla de oleada. Para agregar un método adicional, haga lo siguiente:

    - Seleccione un método en el panel **Métodos restantes**, y después seleccione la flecha **Izquierda** para agregarlo al panel **Métodos seleccionados**.
    - Para cambiar la secuencia, seleccione un método y seleccione las flechas **Arriba** o **Abajo**.

    > [!NOTE]
    > Si agrega un método, se muestra automáticamente en la ubicación adecuada de la secuencia de pasos.

1. Para configurar la consulta que hará coincidir las líneas publicadas con una oleada adecuada, seleccione **Editar consulta** en el Panel de acciones.
1. Para comprobar que la configuración de la plantilla de oleada es válida, seleccione **Validar plantilla**.
