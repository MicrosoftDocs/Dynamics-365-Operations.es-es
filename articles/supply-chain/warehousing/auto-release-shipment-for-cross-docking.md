---
title: Liberación automática de envío para tránsito directo
description: En este tema se describe una estrategia de tránsito directo que le permite liberar automáticamente un pedido de demanda al almacén cuando el pedido de producción que suministra la cantidad de demanda se indique como terminado, de modo que la cantidad se mueve directamente de la ubicación de salida de producción a la ubicación de salida.
author: omulvad
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 619133cb1ef5f85222a42a08fd5fb77250c3d911
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233184"
---
# <a name="auto-release-shipment-for-cross-docking"></a>Liberación automática de envío para tránsito directo

[!include [banner](../includes/banner.md)]

En este tema se describe una estrategia de tránsito directo que le permite liberar automáticamente un pedido de demanda al almacén cuando el pedido de producción que suministra la cantidad de demanda se indique como terminado. De esta manera, la cantidad necesaria para el cumplimiento del pedido de demanda se mueve directamente de la ubicación de salida de producción a la ubicación de salida.

El tránsito directo es un flujo de manipulación en el almacén en el que la cantidad que se requiere para satisfacer un pedido de salida se dirige al muelle de salida o al área provisional del pedido desde la ubicación en la que se recibió el pedido de entrada. (El pedido de entrada puede ser un pedido de compra, un pedido de transferencia o un pedido de producción.) Mientras que la característica Tránsito directo avanzado admite todos los pedidos de suministro y demanda, y requiere que la demanda de salida se libere antes de que se identifique la oportunidad de tránsito directo, la característica Liberación automática de envío tiene estas características:

- Solo admite pedidos de producción como suministro, y solo pedidos de ventas y pedidos de transferencia como demanda.
- La operación de tránsito directo puede iniciarse incluso si el pedido de demanda no se liberó al almacén antes de que se registrarse la recepción de suministro (es decir, antes de que la producción se indicase como terminada).

Esta funcionalidad de tránsito directo tiene dos ventajas:

- Las operaciones de almacén pueden omitir el paso de ubicar cantidades de productos terminados al área de almacenamiento normal del almacén si esas cantidades solo se recogerán de nuevo para cumplir el pedido de salida. En su lugar, las cantidades se pueden mover una vez, desde la ubicación de salida a una ubicación de embalaje/envío. De esta manera, la funcionalidad ayuda a minimizar el número de veces que se gestionan las existencias y, en última instancia, ayuda a maximizar el ahorro de tiempo y espacio en la planta del almacén.
- Las operaciones de almacén pueden posponer la liberación de pedidos de ventas y de pedidos de transferencia al almacén hasta que la salida de productos terminados para el pedido de producción asociado se indique como terminada. Esta ventaja puede ser especialmente relevante en entornos de producción de fabricación sobre pedido, donde los plazos de entrega de la fabricación tienden a ser más largos que los plazos de entrega en entornos de fabricación sobre existencias.

## <a name="prerequisites"></a>Requisitos previos

| Requisito previo | Descripción |
|---|---|
| Elemento | El artículo se debe habilitar para procesos de administración de almacenes.<p>**Nota:** los artículos habilitados para peso capturado no se pueden incluir en los procesos de tránsito directo.</p> |
| Almacén | El almacén se debe habilitar para procesos de administración de almacenes. |
| Plantillas de tránsito directo | Se debe configurar al menos una plantilla de tránsito directo que utilice la directiva de liberación de demanda **En la recepción de suministro** para un determinado almacén. |
| Clase de trabajo | El id. de clase de trabajo de tránsito directo debe crearse para el tipo de pedido de trabajo **Tránsito directo**. |
| Plantillas de trabajo | Se requieren plantillas de trabajo del tipo de pedido de trabajo **Tránsito directo** para crear el trabajo de picking y colocación de tránsito directo. |
| Directivas de ubicación | Se requieren directivas de ubicación del tipo de pedido de trabajo **Tránsito directo** para guiar el trabajo de colocación en las ubicaciones en las que se empaquetarán y enviarán cantidades de pedido de ventas. |
| Marcar entre un pedido de demanda y un pedido de producción | El sistema del almacén puede activar la liberación automática del envío de pedidos de salida y crear el trabajo de tránsito directo desde la ubicación de salida en la acción de notificar como terminado solo si los pedidos de ventas y los pedidos de transferencia se reservan y se marcan en un pedido de producción. |

## <a name="example-cross-docking-flow"></a>Ejemplo de flujo de tránsito directo

Un flujo de tránsito directo habitual consta de los siguientes pasos principales.

1. Un creador de pedidos de ventas crea un pedido de ventas para un producto de fabricación sobre pedido. Normalmente, la cantidad solicitada no está disponible y primero debe producirse.
2. El creador de pedidos de ventas crea un pedido de producción directamente desde la línea de pedido de ventas. De esta manera, el creador de pedidos de ventas reserva y marca la cantidad de pedido de ventas frente a la cantidad de pedido de producción. 

    Como alternativa, un planificador de producción especifica que el marcado se debe actualizar cuando los pedidos planificados están en firme.

3. El pedido de producción pasa por los siguientes pasos:

    1. Un planificador de producción estima y libera el pedido de producción. (La estimación incluye la reserva de materia prima y la liberación incluye la liberación a un almacén.)
    2. Un trabajador del almacén inicia y completa el picking de materia prima desde la ubicación de almacenamiento a la ubicación de entrada de producción, según el trabajo de selección de producción.
    3. Un operador de planta inicia el pedido de producción.
    4. En la última operación, un operario de la máquina utiliza el dispositivo móvil para indicar el pedido de producción como terminado.

4. El sistema usa la configuración para identificar el evento de tránsito directo para los dos pedidos vinculados y luego completa estas tareas:

    1. Liberar automáticamente el pedido de ventas asociado a un almacén para crear un envío.
    2. Crear automáticamente el trabajo de tránsito directo que tiene instrucciones para seleccionar los productos terminados desde la ubicación de salida y moverlos a la ubicación de salida que las directivas de ubicación de tránsito directo asignaron al pedido de ventas.
    3. Pedir a un operario de la máquina que complete el trabajo de tránsito directo inmediatamente después de que el pedido de producción se indique como terminado.

5. Después de que se completo el trabajo de tránsito directo y las cantidades se cargan en el vehículo, un planificador de almacén de salida confirma el envío de ventas.

## <a name="example-scenario"></a>Supuesto de ejemplo

Para este escenario, los datos de prueba deben estar instalados y debe usar la compañía de los datos de prueba **USMF**.

### <a name="set-up-cross-docking-that-uses-the-auto-release-shipment-feature"></a>Configurar un tránsito directo que utiliza la característica de liberación automática de envío

#### <a name="cross-docking-template"></a>Plantilla de tránsito directo

1. Vaya a **Gestión de almacenes** \> **Configurar** \> **Trabajo** \> **Plantillas de tránsito directo**.
2. Seleccione **Nuevo**.
3. En el campo **Número de secuencia**, escriba **1**.
4. En el campo **Id. de plantilla de tránsito directo**, escriba un nombre, como **XDock\_Notificado como terminado**.
5. En el campo **Directiva de liberación de demanda**, seleccione **En la recepción de suministro**.
6. En el campo **Almacén**, introduzca el número del almacén en el que desea configurar el proceso de tránsito directo. Para este ejemplo, seleccione **51**.

    > [!NOTE]
    > En cuanto seleccione **En la recepción de suministro** como la directiva de liberación de demanda para la plantilla, el resto de campos de la página deja de estar disponible. Del mismo modo, tampoco puede definir ninguna fuente de suministro. Este comportamiento se produce porque el tránsito directo que utiliza la característica de liberación automática de envío admite solo pedidos de producción como fuentes de suministro, y requiere que exista una marca entre los pedidos de ventas y los pedidos de producción. Si selecciona **Antes de recepción de suministro** como la directiva de liberación de demanda, los campos en las pestañas **Planificación** y **Fuentes de suministro** están disponibles y se pueden editar.

#### <a name="work-classes"></a>Clases de trabajo

1. Vaya a **Gestión de almacenes** \> **Configurar** \> **Trabajo** \> **Clases de trabajo**.
2. Seleccione **Nuevo**.
3. En el campo **Identificador de la clase de trabajo**, escriba un nombre, como **CrossDock**.
4. En el campo **Tipo de orden de trabajo**, seleccione **Tránsito directo**.

Para limitar los tipos de ubicaciones en las que se pueden colocar productos terminados de tránsito directo, puede especificar uno o más tipos de ubicación válidos.

#### <a name="work-templates"></a>Plantillas de trabajo

1. Vaya a **Gestión de almacenes** \> **Configurar** \> **Trabajo** \> **Plantillas de trabajo**.
2. En el campo **Tipo de orden de trabajo**, seleccione **Tránsito directo**.
3. Seleccione **Nuevo**.
4. En el campo **Número de secuencia**, escriba **1**.
5. En el campo **Plantilla de trabajo**, escriba un nombre, como **CrossDock\_51**.
6. Seleccione **Guardar**.
7. En la sección **Detalles de plantilla de trabajo**, seleccione **Nuevo**.
8. Para la línea nueva, en el campo **Tipo de trabajo**, seleccione **Seleccionar**. En el campo **Identificador de la clase de trabajo**, seleccione **CrossDock**.
9. Seleccione **Nuevo**.
10. Para la línea nueva, en el campo **Tipo de trabajo**, seleccione **Colocar**. En el campo **Identificador de la clase de trabajo**, seleccione **CrossDock**.

#### <a name="location-directives"></a>Directivas de ubicación

Un proceso de ubicación estándar para productos terminados requiere una directiva de ubicación **Colocar** para guiar el movimiento de cantidades de producción seleccionadas a un espacio de almacenamiento regular. Del mismo modo, debe configurar una directiva de ubicación **Colocar** de tránsito directo para indicar al trabajo que coloque la cantidad terminada en una ubicación de salida designada que atiende el envío del pedido de ventas asociado.

Para un tránsito directo, al igual que para la colocación regular de productos terminados, no tiene que crear una directiva de ubicación para la acción de trabajo de picking porque se otorga la ubicación de salida. Además, se espera que esta ubicación de salida se configure como la ubicación de salida predeterminada en uno de los registros relacionados con el recurso (es decir, el recurso, la relación del grupo de recursos o el grupo de recursos) o como una ubicación de productos terminados de producción predeterminada para un almacén.

1. Vaya a **Gestión de almacenes** \> **Configurar** \> **Directivas de ubicación**.
2. En el campo **Tipo de orden de trabajo**, seleccione **Tránsito directo**.
3. Seleccione **Nuevo**.
4. En el campo **Número de secuencia**, escriba **1**.
5. En el campo **Nombre**, escriba un nombre, como **Baydoor**.
6. En el campo **Tipo de trabajo**, seleccione **Colocar**.
7. En el campo **Sitio**, seleccione **5**.
8. En el campo **Almacén**, seleccione **51**.
9. En la ficha desplegable **Líneas**, seleccione **Nueva**.
10. En el campo **Cantidad final**, introduzca la cantidad máxima del intervalo, como **1000000**.
11. Seleccione **Guardar**.
12. En la ficha desplegable **Acciones de directivas de ubicación**, seleccione **Nueva**.
13. En el campo **Nombre**, escriba un nombre, como **Baydoor**.
14. Seleccione **Guardar**.
15. Puede usar la instalación de la consulta estándar para limitar las ubicaciones de colocación a una o varias ubicaciones específicas. Seleccione **Editar consulta** y seleccione **51** como el criterio para el campo **Almacén** en la tabla **Ubicaciones**.

### <a name="cross-dock-finished-goods-to-the-outbound-location"></a>Productos terminados de tránsito directo a la ubicación de salida

Para realizar un tránsito directo de la cantidad de productos terminados a la ubicación de salida del pedido de ventas asociado, siga estos pasos.

1. Vaya a **Ventas y marketing** \> **Pedidos de ventas** \> **Todos los pedidos de ventas**.
2. Seleccione **Nuevo**.
3. Para el encabezado de pedidos de ventas, seleccione la cuenta de cliente **US-001** y un almacén que se configura para el tránsito directo que utiliza la característica de liberación automática de envío.
4. Agregue una línea para un producto terminado y escriba **10** como la cantidad.
5. En la sección **Líneas de pedido de ventas**, seleccione **Producto y suministro** \> **Pedido de producción**.
6. En el cuadro de diálogo **Crear pedido de producción**, revise los valores predeterminados y, a continuación, seleccione **Crear**. Se crea un nuevo pedido de producción y se vincula al pedido de ventas (es decir, se reserva y se marca).
7. Opcional: Cambie el valor del campo **Cantidad** de modo que sea superior al valor necesario para cumplir el pedido de ventas. Cuando la cantidad de producción se indica como terminada, el sistema creará un trabajo de tránsito directo para la cantidad marcada y el trabajo de ubicación para la cantidad restante, según el procedimiento regular para gestionar la colocación de productos terminados.

    Como se mencionó anteriormente, una marca debe existir entre el pedido de ventas y el pedido de producción. De lo contrario, el tránsito directo no funcionará. Una marca se puede crear de varias formas:

    - El sistema puede crear automáticamente el marcado en las siguientes situaciones:

        - El pedido de producción se crea de forma manual directamente desde la línea de pedido de ventas (consulte el paso 6).
        - Los pedidos de producción planificados está en firme y el campo **Actualizar marcado** se establece en **Estándar**.

    - El usuario puede crear manualmente el marcado abriendo la página **Marcado** desde la línea de pedido de demanda.

    > [!NOTE]
    > Un marcado no se puede crear manualmente para artículos que se han configurado para usar la media estándar y ponderada como modelos de inventario.

8. En la página **Pedido de producción**, en el panel de acciones, en la pestaña **Pedido de producción**, en el grupo **Procesar**, seleccione **Estimar** y luego seleccione **Aceptar**. Se estima el pedido y la cantidad de materias primas se reserva para la producción.
9. En el panel de acciones, en la pestaña **Pedido de producción**, en el grupo **Procesar**, seleccione **Liberar** y luego seleccione **Aceptar**. Se crea el trabajo de picking de almacén para materias primas.
10. Abra y revise el trabajo. En el panel de acciones, en la pestaña **Almacén**, en el grupo **General**, seleccione **Detalles de trabajo**. Anote el id. de trabajo.
11. Inicie sesión en la aplicación de almacén para ejecutar trabajos en el almacén 51.
12. Vaya a **Producción** \> **Selección de producción**.
13. Introduzca el id. de trabajo para iniciar y complete el picking de materia prima. 

    Después de que el trabajo se indique como terminado, la cantidad de materias primas está disponible en la ubicación de entrada de producción (**005** en datos de demostración USMF) y se puede iniciar la ejecución del pedido de producción.

14. En la página **Pedido de producción**, en el panel de acciones, en la pestaña **Pedido de producción**, en el grupo **Procesar**, seleccione **Iniciar** y luego seleccione **Aceptar**.
15. En la aplicación, vaya a **Producción** \> **Notificado como terminado y ubicación**.
16. En el campo **Id. producción**, introduzca el número de pedido de producción y otros detalles obligatorios y, a continuación, seleccione **Aceptar**.

Tenga en cuenta que se producen los eventos siguientes:

- La liberación a un almacén se activa para el pedido de ventas vinculado.
- En función de la liberación, se crea el envío y el trabajo de tránsito directo. Este trabajo indica al operador del almacén que seleccione las cantidades necesarias para cumplir la línea de pedido de ventas y colocarlas en la ubicación de salida que especificó en la directiva de ubicación de tránsito directo.
- Si la cantidad de pedido de producción es mayor que la cantidad requerida por el pedido de ventas, se crea el trabajo de ubicación regular. Este trabajo indica al operador del almacén que seleccione la cantidad de productos terminados que quedan después del tránsito directo y lo mueve al almacenamiento regular, según la directiva de ubicación.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]