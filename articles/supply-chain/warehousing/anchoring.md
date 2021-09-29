---
title: Anclaje
description: Este tema explica cómo habilitar y usar el anclaje.
author: GalynaFedorova
ms.date: 07/29/2021
ms.topic: article
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-07-29
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a17574cccbdf6f26f0453bda67eabaa16d559cd3
ms.sourcegitcommit: 99bde425ade701ef244c6bca6d411aef94a59b3c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2021
ms.locfileid: "7505601"
---
# <a name="anchoring"></a>Anclaje

[!include [banner](../includes/banner.md)]

Este tema proporciona detalles sobre el proceso de anclaje. Describe la configuración que se requiere y la lógica que se ejecuta cuando un trabajador del almacén cambia la ubicación de almacenamiento provisional o la de carga.

La administración de anclaje le permite invalidar la ubicación de carga o preparación. Todas las colocaciones abiertas se dirigirán a la nueva ubicación de almacenamiento provisional o de carga que especifique.

Esta característica puede ayudar a los trabajadores a ser más eficientes mientras envían mercancías. A continuación, encontrará algunos ejemplos:

- Un trabajador que debe colocar los artículos para el pedido 1 en una ubicación de almacenamiento provisional de un muelle 1 no puede completar esta operación porque una carga anterior no ha despejado la ubicación. En lugar de esperar a que la ubicación de almacenamiento provisional del muelle 1 esté disponible, el trabajador decide usar la ubicación de almacenamiento provisional del muelle 2. Por tanto, el trabajador invalida la ubicación provisional sugerida. La ubicación de colocación para todos los artículos restantes del trabajo se actualiza a la ubicación de almacenamiento provisional del muelle 2.
- Un trabajador que debe realizar varias recogidas para la misma entrega puede estar seguro de que todos los elementos colocados se reúnan en el mismo lugar. Por lo tanto, se requiere menos tiempo para cargar los artículos en el camión.

Puede configurar el anclaje para los elementos del menú de dispositivo móvil mediante la opción **Anclaje**. Si establece esta opción en *Sí*, puede usar el campo **Anclar por** para especificar si desea anclar por envío o por carga. Si establece el campo **Anclar por** en *Envío*, las colocaciones abiertas subsiguientes se cambiarán a la nueva ubicación para ese envío. Si lo establece en *Carga*, las colocaciones abiertas subsiguientes se cambiarán a la nueva ubicación para ese carga.

> [!IMPORTANT]
> La ubicación de las colocaciones abiertas posteriores se cambiará solo en las líneas de trabajo que se generen a partir de la misma línea de plantilla de trabajo. En otras palabras, el sistema anclará las líneas de colocación que se originan en la misma línea de plantilla de trabajo.

Este tema proporciona un escenario que muestra cómo funciona el anclaje. Durante el escenario, creará un conjunto de pedidos de ventas y los enviará al almacén. Luego, anulará la ubicación de almacenamiento provisional sugerida y verificará que todo el trabajo de colocación restante se dirija a la nueva ubicación.

## <a name="scenario-prerequisite-make-demo-data-available"></a>Requisito previo del escenario: hacer que los datos de demostración estén disponibles

El escenario de este tema hace referencia a valores y registros que se incluyen en los datos de demostración estándar que se proporcionan para Microsoft Dynamics 365 Supply Chain Management. Si desea utilizar los valores que se proporcionan aquí mientras realiza los ejercicios, asegúrese de trabajar en un entorno donde estén instalados los datos de demostración y configure la entidad jurídica en *USMF* antes de empezar.

## <a name="scenario-setup"></a>Configuración de escenario

Antes de trabajar en el escenario de ejemplo, debe habilitar el anclaje para el elemento de menú de dispositivo móvil relevante.

### <a name="set-up-a-mobile-device-menu-item-to-enable-anchoring"></a>Configurar un elemento de menú de dispositivo móvil para habilitar el anclaje

Siga estos pasos para habilitar el anclaje para un elemento del menú de dispositivo móvil.

1. Vaya a **Gestión de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú de dispositivo móvil**.
1. En el panel de lista, seleccione el registro que se llama *Selección de ventas*. Si ningún registro existente tiene este nombre, créelo. Confirme o establezca los siguientes valores para el registro:

    - **Nombre del elemento del menú:** *Selección de ventas*
    - **Título:** *Selección de ventas*
    - **Modo:** *Trabajo*
    - **Usar trabajo existente:** *Sí*
    - **Dirigido por:** *Dirigido por el usuario*
    - **Anclaje:** *Sí*

        Esta configuración hace que el sistema ancle varias líneas de órdenes de trabajo juntas durante la recogida para ventas.

    - **Anclar por:** *Carga*

        Esta configuración hace que el sistema se ancle por carga.

    - **Anular matrícula de entidad de almacén de destino:** *Sí*
    - **Anular la matrícula durante la colocación:** *Sí*
    - **Mantener trabajo bloqueado por el usuario:** *Sí*
    - **Permitir selección en exceso:** *Sí*

### <a name="set-up-a-work-template-to-enable-staging"></a>Configurar una plantilla de trabajo para habilitar el almacenamiento provisional

Siga estos pasos para configurar una plantilla de trabajo para habilitar el almacenamiento provisional. Esta configuración admitirá el escenario en el que un trabajador coloca artículos para un pedido en una ubicación de almacenamiento provisional.

1. Vaya a **Gestión de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.
1. En el campo **Tipo de orden de trabajo**, seleccione *Pedidos de ventas*.
1. En la cuadrícula, seleccione la plantilla de trabajo **61 Almacenamiento provisional SO**.
1. En la sección **Detalles de la plantilla de trabajo** , asegúrese de que existan las siguientes líneas y estén configuradas como se muestra aquí:

    - Línea 1:

        - **Tipo de trabajo**: *Recoger*
        - **Obligatorio:** Seleccionado (= *Sí*)
        - **Identificador de la clase de trabajo**: *SO picking*

    - Línea 2:

        - **Tipo de trabajo**: *Ubicar*
        - **Obligatorio:** Seleccionado (= *Sí*)
        - **Código de directiva:** *Almacenamiento provisional*
        - **Identificador de la clase de trabajo**: *SO picking*

    - Línea 3:

        - **Tipo de trabajo**: *Recoger*
        - **Obligatorio:** Seleccionado (= *Sí*)
        - **Detener trabajo:** *Sí*
        - **Id. de clase de trabajo**: *Recogida SO*

    - Línea 4:

        - **Tipo de trabajo**: *Ubicar*
        - **Obligatorio:** Seleccionado (= *Sí*)
        - **Código de directiva:** *Puerta de muelle*
        - **Id. de clase de trabajo**: *Recogida SO*

1. En el panel de acciones, seleccione **Editar consulta** para abrir el editor de consultas.
1. En la pestaña **Rango**, asegúrese de que la siguiente línea esté presente:

    - **Tabla:** *Transacciones laborales temporales*
    - **Tabla derivada:** *Transacciones de trabajo temporales*
    - **Campo:** *Almacén*
    - **Criterio:** *61*

1. En la pestaña **Ordenación**, asegúrese de que la siguiente línea esté presente:

    - **Tabla:** *Transacciones laborales temporales*
    - **Tabla derivada:** *Transacciones de trabajo temporales*
    - **Campo:** *Identificación del envío*
    - **Dirección de búsqueda:** *Ascendente*

1. Seleccione **Aceptar** para aplicar los ajustes y cierre el editor de consultas. Acepte los cambios si se le solicita.
1. En el panel de acciones, seleccione **Saltos de encabezado de trabajo**.
1. En la línea donde el campo **Nombre del campo** esté establecido en *Id. de envío*, asegúrese de que la casilla **Agrupar por este campo** esté seleccionada.

### <a name="set-up-license-plates-locations-and-inventory"></a>Configurar matrículas, ubicaciones e inventario

Antes de crear pedidos de venta y envíos, debe asegurarse de que existan las ubicaciones, las placas de matrícula y el inventario requeridos.

1. Vaya a **Gestión de almacenes \> Configuración \> Almacén \> Matrículas** y cree dos matrículas:

    - MyLP1
    - MyLP2

1. Vaya a **Gestión de almacenes \> Configuración \> Almacén \> Ubicaciones** y cree las siguientes ubicaciones si aún no están presentes.

    | Almacén | Ubicación   | Id. de perfil de ubicación | Id. de zona   |
    |-----------|------------|---------------------|-----------|
    | 61        | 06A01R2S1B | PICK-06             | FLOOR     |
    | 61        | 06A01R3S1B | PICK-06             | FLOOR     |
    | 61        | STAGE01    | FASE               | *(En blanco)* |
    | 61        | STAGE02    | FASE               | *(En blanco)* |
    | 61        | STAGE03    | FASE               | *(En blanco)* |
    | 61        | STAGE04    | FASE               | *(En blanco)* |

1. Asegúrese de que el siguiente inventario esté disponible. Si debe ajustar el inventario, puede crear movimientos manuales, utilizar la reposición o utilizar cualquier otro flujo.

    | Número de artículo | Cantidad | Almacén | Ubicación   | Matrícula de entidad de almacén |
    |-------------|----------|-----------|------------|---------------|
    | A0001       | 100      | 61        | 06A01R2S1B | MyLP1         |
    | A0002       | 100      | 61        | 06A01R3S1B | MyLP2         |

### <a name="create-demand"></a>Crear demanda

Para poder probar la funcionalidad de anclaje, debe crear cierta demanda. Para este escenario, creará tres pedidos de ventas para el mismo cliente.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Seleccione **Nuevo** para crear el primer pedido de ventas.
1. En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:

    - **Cuenta de cliente:** *US-001*
    - **Almacén**: *61*

1. Seleccione **Aceptar**.
1. Se abre el nuevo pedido de ventas. Incluye una línea vacía en la ficha desplegable **Líneas de pedido de ventas**. Establezca los siguientes valores para esta línea:

    - **Código de artículo:** *A0001*
    - **Cantidad:** *1*

1. En la barra de herramientas, seleccione **Agregar línea** para agregar una segunda línea de pedido de ventas y establezca los siguientes valores para ella:

    - **Código de artículo:** *A0002*
    - **Cantidad:** *1*

1. Repita estos pasos para cada línea de ventas del pedido para reservarle inventario:

    1. En la ficha desplegable **Líneas de pedido de ventas**, seleccione una línea de pedido de ventas.
    1. En la barra de herramientas, seleccione **Inventario \> Reserva**.
    1. En la página **Reserva**, seleccione **Reservar lote** y después cierre la página.
    1. En el panel Acciones, seleccione **Guardar**.

1. Repita los pasos del 2 al 6 para crear un segundo pedido de ventas. Establezca los siguientes valores para este registro:

    - En el cuadro de diálogo **Crear un pedido de ventas**:

        - **Cuenta de cliente:** *US-001*
        - **Almacén**: *61*

    - En la línea de pedido de ventas 1:

        - **Código de artículo:** *A0001*
        - **Cantidad:** *2*

    - En la línea de pedido de ventas 2:

        - **Código de artículo:** *A0002*
        - **Cantidad:** *2*

1. Repita el paso 7 para reservar cada línea en el pedido de ventas 2.
1. Repita los pasos del 2 al 6 para crear un tercer pedido de ventas. Establezca los siguientes valores para este registro:

    - En el cuadro de diálogo **Crear un pedido de ventas**:

        - **Cuenta de cliente:** *US-001*
        - **Almacén**: *61*

    - En la línea de pedido de ventas 1:

        - **Código de artículo:** *A0001*
        - **Cantidad:** *3*

    - En la línea de pedido de ventas 2:

        - **Código de artículo:** *A0002*
        - **Cantidad:** *3*

1. Repita el paso 7 para reservar cada línea en el pedido de ventas 3.

### <a name="use-the-load-planning-workbench-to-create-a-load-and-release-it-to-the-warehouse"></a>Use el área de trabajo de planificación de la carga para crear una carga y enviarla al almacén

Siga estos pasos para crear una carga para los pedidos que creó para este escenario y luego envíela al almacén.

1. Vaya a **Gestión de almacén \> Cargas \> Área de trabajo de planificación de la carga**.
1. En la pestaña **Lineas de venta**, busque y seleccione todas las líneas de pedido de ventas para el pedido de ventas 1 y el pedido de ventas 2.
1. En el panel de acciones, en la ficha **Suministro y demanda**, en el grupo **Agregar**, seleccione **A una carga nueva**.
1. En el cuadro de diálogo **Cargar asignación de plantilla**, en el campo **Cargar id. de plantilla**, seleccione una plantilla de carga, como *Plantilla de carga estándar*.
1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.
1. En la sección **Cargas**, busque y seleccione la carga que ha creado.
1. En la barra de herramientas, seleccione **Envío \> Envío al almacén**.
1. En el cuadro de diálogo **Despachar carga al almacén**, seleccione **Aceptar** para liberar la carga seleccionada al almacén.
1. Vaya a **Gestión de almacenes \> Trabajo \> Todo el trabajo** para ver el trabajo que se ha creado. Debería encontrar dos nuevos id. de trabajo, uno para cada envío. Cada id. de trabajo tiene líneas de recogida y colocación que llevan el inventario desde las ubicaciones de recogida hasta la ubicación de almacenamiento provisional y desde la ubicación de almacenamiento provisional hasta la puerta del muelle. Tome nota del valor **Id. de trabajo** del primer envío, porque lo necesitará en el siguiente procedimiento.

### <a name="sales-order-picking-to-the-staging-location-for-the-first-shipment"></a>Recogida de pedidos de venta hacia la ubicación de almacenamiento provisional para el primer envío

1. Inicie sesión en la aplicación móvil Warehouse Management como trabajador del almacén *61*. (En los datos de demostración estándar, puede iniciar sesión utilizando _61_ como id. de usuario y _1_ como contraseña).
1. En el menú principal, seleccione **Saliente**.
1. En el menú **Saliente**, seleccione **Selección de ventas**.
1. Seleccione el campo **Id.** y luego introduzca el id. de trabajo para el primer envío.
1. Confirme su entrada.
1. En el campo **LP**, introduzca un número de matrícula para el primer artículo (*MyLP1*).
1. Confirme su entrada.
1. En el campo **LP de destino**, introduzca cualquier número (la matrícula del objetivo no tiene por que existir ya).

    Seleccionará todas las líneas que se crearon a partir de la oleada procesada en la misma matrícula de destino.

1. Confirme su entrada.
1. En el campo **LP**, introduzca un número de matrícula para el segundo artículo (*MyLP2*).
1. Confirme su entrada.

    Imagínese que el trabajador ya ha recogido el pedido, pero cuando llega al lugar de preparación que especificó en el trabajo, se encuentra con que el espacio ya está ocupado. Sin embargo, el trabajador puede ver que otra ubicación cercana (*STAGE03*) está disponible. Por lo tanto, solicitarán cambiar la ubicación del almacenamiento provisional. Debido a que la función de anclaje está habilitada, el sistema actualizará automáticamente la ubicación de almacenamiento provisional para este y todo el trabajo relacionado.

1. Seleccione **Invalidar ubicación** para invalidar la ubicación de almacenamiento provisional sugerida.
1. En el campo **Excepciones de trabajo**, especifique *Carril de almacenamiento provisional cambiado*.
1. En el campo **Ubicación**, introduzca una nueva ubicación de almacenamiento intermedio (*STAGE03*).
1. Confirme su entrada. Recibe un mensaje "Trabajo completado".
1. Vaya a **Gestión de almacenes \> Trabajo\> Todos los trabajos**.
1. Abra el id. de trabajo para el primer envío. Verifique que la ubicación de almacenamiento provisional se haya actualizado a la nueva ubicación (*STAGE03*) que se definió mediante el uso del dispositivo móvil.
1. Abra el id. de trabajo para el segundo envío. Verifique que la ubicación de almacenamiento provisional se haya actualizado a la nueva ubicación de almacenamiento provisional (*STAGE03*) debido a la configuración de anclaje.

> [!NOTE]
> La ubicación de todas las líneas de trabajo de colocación abiertas restantes que tienen la misma ubicación de almacenamiento provisional y que se generaron a partir de la misma línea de plantilla de trabajo se actualizará a la nueva ubicación.

### <a name="use-the-load-planning-workbench-to-add-the-new-sales-order-to-the-existing-load"></a>Utilice el banco de trabajo de planificación de carga para agregar el nuevo pedido de ventas a la carga existente

Siga estos pasos para agregar un pedido a la carga y luego enviarlo al almacén.

1. Vaya a **Gestión de almacén \> Cargas \> Área de trabajo de planificación de la carga**.
1. En la pestaña **Lineas de venta**, busque y seleccione todas las líneas de pedido de ventas para el pedido de ventas 3.
1. En el Panel de acciones, en la pestaña **Suministro y demanda**, en el grupo **Agregar**, seleccione **A carga existente** para agregar las líneas de pedidos seleccionadas a una carga existente.
1. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.
1. En la sección **Cargas**, busque y seleccione la carga en los pasos anteriores.
1. Seleccione **Lanzamiento \> Liberar al almacén**.
1. En el cuadro de diálogo **Despachar carga al almacén**, seleccione **Aceptar** para liberar la carga seleccionada al almacén.
1. Vaya a **Gestión de almacenes \> Trabajo \> Todo el trabajo** para ver el trabajo que se ha creado. Tome nota del valor **Id. de trabajo**, porque lo necesitará en el siguiente procedimiento.

### <a name="sales-order-picking-to-the-staging-location-for-the-third-shipment"></a>Recogida de pedidos de venta hacia la ubicación de almacenamiento provisional para el tercer envío

1. Inicie sesión en la aplicación móvil como un trabajador en el almacén *61*.
1. En el menú principal, seleccione **Saliente**.
1. En el menú **Saliente**, seleccione **Selección de ventas**.
1. Seleccione el campo **Id.** y luego introduzca el id. de trabajo para el tercer envío.
1. Confirme su entrada.
1. En el campo **LP**, introduzca un número de matrícula para el primer artículo (*MyLP1*).
1. Confirme su entrada.
1. En el campo **LP de destino**, introduzca cualquier número (la matrícula del objetivo no tiene por que existir ya).
1. Confirme su entrada.
1. En el campo **LP**, introduzca un número de matrícula para el segundo artículo (*MyLP2*).
1. Confirme su entrada.

    En cuanto a la primera carga, imagine que el trabajador descubre que la ubicación de almacenamiento provisional no está disponible. Por lo tanto, quieren usar una ubicación de almacenamiento provisional diferente (*STAGE04*).

1. Seleccione **Invalidar ubicación** para invalidar la ubicación de almacenamiento provisional sugerida.
1. En el campo **Excepciones de trabajo**, especifique *Carril de almacenamiento provisional cambiado*.
1. En el campo **Ubicación**, introduzca una nueva ubicación de almacenamiento provisional (*STAGE04*).
1. Confirme su entrada. Recibe un mensaje "Trabajo completado".
1. Vaya a **Gestión de almacenes \> Trabajo\> Todos los trabajos**.
1. Abra el id. de trabajo para el primer envío. Verifique que la ubicación de almacenamiento provisional no se haya actualizado a la nueva ubicación de almacenamiento provisional (*STAGE04*) porque la línea de colocación abierta restante no corresponde a la línea de plantilla de trabajo de la línea de colocación completada.
1. Abra el id. de trabajo para el segundo envío. Verifique que la ubicación de almacenamiento provisional no se haya actualizado a la nueva ubicación de almacenamiento provisional (*STAGE04*) porque la línea de almacenamiento provisional abierta restante no corresponde a la ubicación de almacenamiento provisional de la línea de colocación completada. En otras palabras, la línea de trabajo de colocación terminada y la línea de trabajo abierta restante tienen diferentes ubicaciones de almacenamiento provisional y, en este caso, solo se actualizan las líneas que tienen las mismas ubicaciones de almacenamiento provisional.
1. Abra el id. de trabajo para el tercer envío. Verifique que la ubicación de almacenamiento provisional se haya actualizado a la nueva ubicación de almacenamiento provisional (*STAGE04*).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
