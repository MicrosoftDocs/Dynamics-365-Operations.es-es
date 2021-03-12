---
title: Directivas de trabajo
description: En este tema se explica cómo configurar directivas de trabajo.
author: perlynne
manager: tfehr
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 530abffb4c80a2d2f0e58e0c5a34294f7cba0b1a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4998462"
---
# <a name="work-policies"></a>Directivas de trabajo

[!include [banner](../includes/banner.md)]

En este tema se explica cómo configurar el sistema y la aplicación de almacén para que admitan directivas de trabajo. Puede utilizar esta funcionalidad para registrar rápidamente el inventario sin crear trabajos de colocación cuando reciba pedidos de compra o transferencia, o cuando complete los procesos de fabricación. Este tema proporciona información general. Para obtener información detallada relacionada con la recepción de matrículas de entidad de almacén, consulte [Recepción de matrículas de entidad de almacén a través de la aplicación de almacén](warehousing-mobile-device-app-license-plate-receiving.md).

Una directiva de trabajo controla si el trabajo de almacén se crea cuando un artículo manufacturado se informa como terminado o cuando se reciben bienes mediante la aplicación de almacén. Configure cada política de trabajo definiendo las condiciones donde se aplica: los tipos y procesos de órdenes de trabajo, la ubicación del inventario y (opcionalmente) los productos. Por ejemplo, una orden de compra para el producto *A0001* debe recibirse en la ubicación *RECV* del almacén *24*. Más tarde, el producto se usa en otro proceso en la ubicación *RECV*. En este caso, puede configurar una directiva de trabajo para evitar que se cree un trabajo de almacenamiento cuando un trabajador notifica el producto *A0001* como recibido en la ubicación *RECV*.

> [!NOTE]
> - Para que una política de trabajo esté activa, debe definir al menos una ubicación para ella en la ficha desplegable **Ubicaciones de inventario** de la página **Directivas de trabajo**. 
> - No puede especificar la misma ubicación para múltiples políticas de trabajo.
> - La opción **Imprimir etiqueta** para almacenar elementos del menú del dispositivo móvil no imprimirá una etiqueta de matrícula de entidad de almacén a no ser que se cree trabajo.

## <a name="activate-the-features-in-your-system"></a>Activar las características en su sistema

Para que todas las funciones que se describen en este tema estén disponibles en su sistema, active las siguientes dos características en [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md):

- Mejoras en la recepción de matrícula de entidad de almacén
- Mejoras de la directiva de trabajo para el trabajo de entrada

## <a name="the-work-policies-page"></a>La página directivas del trabajo

Para configurar directivas de trabajo, vaya a **Administración de almacenes \> Configurar \> Trabajo \> Directivas de trabajo**. Luego, en cada ficha desplegable, configure los campos como se describe en las siguientes subsecciones.

### <a name="the-work-order-types-fasttab"></a>La ficha desplegable de tipos de orden de trabajo

En la ficha desplegable **Tipos de orden de trabajo**, agregue todos los tipos de orden de trabajo y los procesos de trabajo relacionados a los que se aplica la política de trabajo. Los siguientes tipos de órdenes de trabajo y procesos de trabajo relacionados son compatibles con las políticas de trabajo.

| Tipo de pedido de trabajo | Proceso de trabajo |
|---|---|
| Picking de materia prima| Todos los procesos relacionados |
| Ubicación de coproducto y producto derivado | Todos los procesos relacionados |
| Colocación de bienes terminados | Todos los procesos relacionados |
| Recibo de transferencia | Recepción de matrícula de entidad de almacén (y colocación) |
| Pedidos de compra | <ul><li>Recepción de matrícula de entidad de almacén (y colocación)</li><li>Recepción de artículo de carga (y colocación)</li><li>Recepción de línea del pedido de compra (y colocación)</li><li>Recepción de artículo del pedido de compra (y colocación)</li></ul> |

Para configurar una directiva de trabajo para que se aplique a varios procesos de trabajo del mismo tipo de orden de trabajo, agregue una línea separada para cada proceso de trabajo a la cuadrícula.

Para cada línea en la cuadrícula, establezca el campo **Método de creación de trabajo** en uno de los siguientes valores:

- **Nunca**: este valor indica que la directiva de trabajo evitará que se genere el trabajo del almacén para el tipo de pedido de trabajo seleccionado y los procesos de trabajo relacionados.
- **Tránsito directo**: la directiva de trabajo creará trabajo de tránsito directo utilizando la política que seleccione en el campo **Nombre de la directiva de tránsito directo**.

### <a name="the-inventory-locations-fasttab"></a>La ficha desplegable Ubicaciones de inventario

En la ficha desplegable **Ubicaciones de inventario**, agregue todas las ubicaciones donde se debe aplicar esta directiva de trabajo. Si no se asocia ninguna ubicación a una directiva de trabajo, la directiva de trabajo no se aplica a ningún proceso.

No puede especificar la misma ubicación para múltiples políticas de trabajo.

Puede utilizar una ubicación de almacén asignada a un perfil de ubicación incluso cuando la opción **Utilizar el seguimiento de matrículas de entidad de almacén** no está activada. En este caso, los trabajadores registrarán directamente el inventario disponible.

### <a name="the-products-fasttab"></a>La ficha desplegable Productos

En la pestaña **Productos**, configure el campo **Selección de producto** para controlar a qué productos debe aplicarse la política:

- **Todos**: la directiva debe aplicarse a todos los productos.
- **Seleccionado**: la directiva debe aplicarse solo a los productos que figuran en la cuadrícula. Use la barra de herramientas en la ficha desplegable **Productos** para agregar productos a la cuadrícula o eliminarlos de la cuadrícula.

## <a name="default-and-custom-to-locations"></a>Ubicaciones predeterminadas y personalizadas de "destino"

> [!NOTE]
> Para que la funcionalidad que se describe en esta sección esté disponible en su sistema, debe activar las características *Mejoras en la recepción de matrículas de entidad de almacén* y *Mejoras en la directiva de trabajo para el trabajo entrante* en [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Anteriormente, el sistema admitía recibir solo en la ubicación predeterminada que se define para cada almacén. Sin embargo, los elementos del menú del dispositivo móvil que utilizan los siguientes procesos de creación de trabajo ahora ofrecen la opción **Usar datos predeterminados**. Esta opción le permite asignar una ubicación "destino" personalizada a uno o más elementos del menú. (Esta opción ya estaba disponible para algunos otros tipos de elementos de menú).

- Recepción de matrícula de entidad de almacén (y colocación)
- Recepción de artículo de carga (y colocación)
- Recepción de línea del pedido de compra (y colocación)
- Recepción de artículo del pedido de compra (y colocación)

La configuración **Ubicación de destino** de un elemento del menú anula la ubicación de recepción predeterminada para el almacén, para todos los pedidos que se procesan utilizando ese elemento del menú.

Para configurar un elemento de menú del dispositivo móvil para admitir la recepción en una ubicación personalizada, siga estos pasos.

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. Seleccione o cree un elemento de menú que use uno de los procesos de creación de trabajo enumerados anteriormente en esta sección.
1. En la ficha desplegable **General**, configure la opción **Usar datos predeterminados** en **Sí**.
1. En el panel Acciones, seleccione **Datos predeterminados**.
1. En la página **Datos predeterminados**, establezca los valores siguientes:

    - **Campo de datos predeterminado**: Establezca este campo en *Ubicación de destino*.
    - **Almacén**: seleccione el almacén de destino para usar con este elemento del menú.
    - **Ubicación**: este campo enumera todos los identificadores de ubicación que están disponibles para el almacén seleccionado. Sin embargo, la configuración de este campo en realidad no tiene ningún efecto. Por tanto, no se puede dejar en blanco. Sin embargo, puede usar la lista para confirmar el identificador que debe especificar en el campo **Valor codificado**.
    - **Valor codificado**: especifique el identificador de ubicación para la ubicación de recepción que se aplica a este elemento del menú.

> [!TIP]
> Una directiva de trabajo solo se puede aplicar si todas las ubicaciones de recepción se enumeran en la configuración de directiva de trabajo relevante. Este requisito se aplica independientemente de si está utilizando la ubicación de recepción de almacén predeterminada o una ubicación "destino" personalizada.

## <a name="example-scenario-warehouse-receiving"></a>Escenario de ejemplo: recepción de almacén

Todos los productos que se reciben mediante el proceso *Orden de compra de artículos recibidos (y colocación)* debe estar registrado en la ubicación *FL-001*, y deben estar disponibles en el almacén *24*. Sin embargo, el trabajo no debe ser creado. Los productos que se reciben por cualquier otro proceso (es decir, mediante el uso de otros elementos del menú del dispositivo móvil) deben registrarse en la ubicación de recepción predeterminada del almacén (*RECV*), y el trabajo debe crearse como de costumbre. (Este escenario no muestra la configuración de recepción predeterminada).

Este escenario requiere los siguientes elementos:

- Una directiva de trabajo para el proceso *Recepción del artículo del pedido de compra (y colocación)* en la ubicación *FL-001*, para todos los productos
- Un elemento de menú del dispositivo móvil que tiene datos predeterminados y que establece el campo **Ubicación de destino** en *FL-001*.

### <a name="prerequisites"></a>Requisitos previos

Para que la funcionalidad que se describe en este escenario esté disponible en su sistema, debe activar las características *Mejoras en la recepción de matrículas de entidad de almacén* y *Mejoras en la directiva de trabajo para el trabajo entrante* en [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Este escenario usa datos de demostración estándar. Por tanto, si quiere trabajar en él utilizando los valores que se presentan en este tema, asegúrese de trabajar en un sistema donde se instalen datos de demostración estándar. Además, también debe seleccionar la entidad legal **USMF**.

### <a name="set-up-a-work-policy"></a>Configurar una directiva de trabajo

1. Vaya a **Gestión de almacenes \> Configuración \> Trabajo \> Directivas de trabajo**.
1. Seleccione **Nuevo**.
1. En el campo **Nombre de la directiva de trabajo**, especifique *No hay trabajo de colocación de artículos*.
1. Seleccione **Guardar**.
1. En la ficha desplegable **Tipos de orden de trabajo**, seleccione **Agregar** para agregar una fila a la cuadrícula y luego establecer los siguientes valores para la nueva fila:

    - **Tipo de orden de trabajo**: *Pedidos de compra*
    - **Proceso de trabajo**: *Recepción de artículos de pedido de compra (y colocación)*
    - **Método de creación de trabajo**: *Nunca*
    - **Nombre de directiva de tránsito directo**: deje este campo en blanco.

1. En la ficha desplegable **Ubicaciones de inventario**, seleccione **Agregar** para agregar una fila a la cuadrícula y luego establecer los siguientes valores para la nueva fila:

    - **Almacén**: *24*
    - **Ubicación**: *FL-001*

1. En la ficha desplegable **Productos**, configure el campo **Selección de productos** en *Todos*.
1. Seleccione **Guardar**.

### <a name="set-up-a-mobile-device-menu-item-to-change-the-receiving-location"></a>Configurar un elemento de menú del dispositivo móvil para cambiar la ubicación de recepción

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. En el panel izquierdo, seleccione el elemento de menú **Recepción de compra**.
1. En la ficha desplegable **General**, configure la opción **Usar datos predeterminados** en *Sí*.
1. Seleccione **Guardar**.
1. En el panel Acciones, seleccione **Datos predeterminados**.
1. En la ficha desplegable **Datos predeterminados**, en el panel Acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula y luego establecer los siguientes valores para la nueva fila:

    - **Campo de datos predeterminados**: *Ubicación de destino*
    - **Almacén**: *24*
    - **Ubicación**: deje este campo en blanco.
    - **Valor codificado**: *FL-001*

1. Seleccione **Guardar**.

### <a name="receive-a-purchase-order-without-creating-work"></a>Recibir una orden de compra sin crear trabajo

El ejemplo en esta sección muestra cómo recibir un artículo de pedido de compra, pero sin crear trabajo, en una ubicación que difiere de la ubicación de recepción predeterminada que está configurada para el almacén. Este ejemplo utiliza la directiva de trabajo y el elemento del dispositivo móvil que creó anteriormente en este escenario.

#### <a name="create-a-purchase-order"></a>Crear un pedido de compra

1. Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**.
1. Seleccione **Nuevo**.
1. En el cuadro de diálogo **Crear pedido de compras**, establezca los siguientes valores:

    - **Cuenta del proveedor**: *US-101*
    - **Sitio**: *2*
    - **Almacén**: *24*

1. Seleccione **Aceptar** para crear el nuevo cuadro de diálogo y abrir el nuevo pedido de compras.
1. En la ficha desplegable **Líneas de orden de compra**, establezca los siguientes valores para la fila vacía:

    - **Código de artículo:** *A0001*
    - **Cantidad:** *1*

1. Seleccione **Guardar**.
1. Anote el número del pedido de compra.

#### <a name="receive-a-purchase-order"></a>Recibir un pedido de compra

1. En el dispositivo móvil, inicie sesión en el almacén *24* utilizando *24* como el identificador de usuario y *1* como la contraseña.
1. Seleccione **Entrada**.
1. Seleccione **Recepción de compra**. El campo **Ubicación** debe establecerse en *FL-001*.
1. Especifique el número de orden de compra para la orden de compra que creó en el procedimiento anterior.
1. En el campo **Número de artículo**, especifique *A0001*.
1. Seleccione **Aceptar**.
1. En el campo **Cantidad**, especifique *1*.
1. Seleccione **Aceptar**.

El pedido de compra ahora se recibe, pero no hay trabajo asociado. El inventario disponible ha sido actualizado y una cantidad de *1* del artículo *A0001* ahora está disponible en la ubicación *FL-001*.

## <a name="example-scenario-manufacturing"></a>Escenario de ejemplo: fabricación

En el siguiente ejemplo, hay dos pedidos de producción, *PRD-001* y *PRD-002*. El pedido de producción *PRD-001* tiene una operación llamada *Montaje*, en la que el producto *SC1* se notifica a la ubicación *001* como terminado. El pedido de producción *PRD-002* tiene una operación llamada *Pintura* y consume el producto *SC1* de la ubicación *001*. El pedido de producción *PRD-002* también consume la materia prima *RM1* de la ubicación *001*. La materia prima *RM1* se almacena en la ubicación del almacén *BULK-001* y el trabajo del almacén lo escogerá como recogida de materia prima a la ubicación *001*. El trabajo de recogida se genera cuando se lanza la producción *PRD-002*.

[![Directivas de trabajo de almacén](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png)

Cuando tenga previsto configurar una directiva de trabajo del almacén para este escenario, debe tener en cuenta los siguientes puntos:

- El trabajo del almacén para la colocación del producto terminado no es necesario cuando informa de que el producto *SC1* se ha completado del pedido de producción *PRD-001* a la ubicación *001*. El motivo es que la operación *Pintura* del pedido de producción *PRD-002* consume el producto *SC1* en la misma ubicación.
- El trabajo de almacén para la recogida de la materia prima se requiere para mover la materia prima *RM1* de la ubicación del almacén *BULK-001* a la ubicación *001*.

A continuación se muestra un ejemplo de una directiva de trabajo que puede configurar, en función de estas cuestiones:

- **Nombre de la directiva de trabajo**: *Sin trabajo de colocación*
- **Tipos de orden de trabajo**: *Colocación de productos terminados* y *Colocación de coproductos y subproductos*
- **Ubicaciones de inventario**: almacén *51* y ubicación *001*
- **Productos**: *SC1*

El siguiente escenario de ejemplo proporcionan instrucciones detalladas sobre cómo configurar la directiva de trabajo del almacén para esta situación.

## <a name="example-scenario-report-as-finished-to-a-location-that-isnt-license-platecontrolled"></a>Escenario de ejemplo: informar de una orden de producción como terminada a una ubicación no controlada por matrícula.

En este escenario se muestra un ejemplo donde un pedido de producción se registra como completado en una ubicación no controlada por matrículas de entidad de almacén.

Este escenario usa datos de demostración estándar. Por tanto, si quiere trabajar en él utilizando los valores que se presentan en este tema, asegúrese de trabajar en un sistema donde se instalen datos de demostración estándar. Además, también debe seleccionar la entidad legal **USMF**.

### <a name="set-up-a-warehouse-work-policy"></a>Configurar una directiva de trabajo de almacén

Los procesos de almacén no siempre incluyen trabajo de almacén. Al definir una directiva de trabajo, puede evitar la creación de trabajo para picking de materia prima y colocación de bienes terminados para un conjunto de productos en ubicaciones específicas.

1. Vaya a **Gestión de almacenes \> Configuración \> Trabajo \> Directivas de trabajo**.
1. Seleccione **Nuevo**.
1. En el campo **Nombre de la directiva de trabajo**, especifique *No hay trabajo de colocación*.
1. En el panel Acciones, seleccione **Guardar**.
1. En la ficha desplegable **Tipos de orden de trabajo**, seleccione **Agregar** para agregar una fila a la cuadrícula y luego establecer los siguientes valores para la nueva fila:

    - **Tipo de pedido de trabajo**: *Colocación de productos terminados*
    - **Proceso de trabajo**: *Todos los procesos de trabajo relacionados*
    - **Método de creación de trabajo**: *Nunca*
    - **Nombre de directiva de tránsito directo**: deje este campo en blanco.

1. Seleccione **Agregar** de nuevo para agregar una segunda fila a la cuadrícula y luego establecer los siguientes valores para la nueva fila:

    - **Tipo de pedido de trabajo**: *Colocación de coproductos y subproductos*
    - **Proceso de trabajo**: *Todos los procesos de trabajo relacionados*
    - **Método de creación de trabajo**: *Nunca*
    - **Nombre de directiva de tránsito directo**: deje este campo en blanco.

1. En la ficha desplegable **Ubicaciones de inventario**, seleccione **Agregar** para agregar una fila a la cuadrícula y luego establecer los siguientes valores para la nueva fila:

    - **Almacén**: *51*
    - **Ubicación**: *001*

1. En la ficha desplegable **Productos**, configure el campo **Selección de productos** en *Seleccionado*.
1. En la ficha desplegable **Productos**, seleccione **Agregar** para agregar una fila a la cuadrícula.
1. En la nueva fila, establezca el campo **Número de elemento** en *L0101*.
1. En el panel Acciones, seleccione **Guardar**.

### <a name="set-up-an-output-location"></a>Configurar una ubicación de salida

1. Vaya a **Administración de la organización \> Recursos \> Grupos de recursos**.
1. En el panel izquierdo, seleccione el grupo de recursos **5102**.
1. En la ficha desplegable **General**, establezca los valores siguientes:

    - **Almacén de salida**: *51*
    - **Ubicación de salida**: *001*

1. En el panel Acciones, seleccione **Guardar**.

> [!NOTE]
> La ubicación *001* no es una ubicación controlada mediante matrículas de entidad de almacén. Puede configurar una ubicación de salida que no esté controlada por matrículas de entidad de almacén si existe una directiva aplicable de trabajo para la ubicación.

### <a name="create-a-production-order-and-report-it-as-finished"></a>Crear un pedido de producción y notificarlo como terminado

1. Vaya a **Control de producción \> Pedidos de producción \> Todos los pedidos de producción**.
1. En el panel de acciones, seleccione **Nuevo pedido de producción**.
1. En el cuadro de diálogo **Crear orden de producción**, establezca el campo **Número de artículo** en *L0101*.
1. Seleccione **Crear** para crear el pedido de ventas y cerrar el cuadro de diálogo.

    Se agrega una nueva orden de producción a la cuadrícula en la página **Todos los pedidos de producción**.

    Mantenga seleccionada la nueva orden de producción.

1. En el panel Acciones, en la pestaña **Pedido de producción**, en el grupo **Proceso**, seleccione **Estimación**.
1. En el cuadro de diálogo **Estimación**, lea la estimación y luego seleccione **Aceptar** para cerrar el cuadro de diálogo.
1. En el panel Acciones, en la pestaña **Pedido de producción**, en el grupo **Proceso**, seleccione **Inicio**.
1. En el cuadro de diálogo **Inicio**, en la pestaña **General**, configure el campo **Consumo automático de L.MAT.** en *Nunca*.
1. Seleccione **Aceptar** para guardar la configuración y cerrar el cuadro de diálogo.
1. En el panel Acciones, en la pestaña **Pedido de producción**, en el grupo **Proceso**, seleccione **Notificar como terminado**.
1. En el cuadro de diálogo **Informar como terminado**, en la pestaña **General**, configure la opción **Aceptar error** en *Sí*.
1. Seleccione **Aceptar** para guardar la configuración y cerrar el cuadro de diálogo.
1. En el panel de acciones, en la pestaña **Almacén**, en el grupo **General**, seleccione **Detalles de trabajo**.

Cuando el pedido de producción se haya notificado como finalizado, no se habrá generado ningún trabajo para su colocación. Este comportamiento ocurre porque se define una directiva de trabajo que impide que el trabajo se genere cuando el producto *L0101* se notifique como finalizado para la ubicación *001*.

## <a name="more-information"></a>Más información

Para obtener más información sobre los elementos del menú del dispositivo móvil, consulte [Configurar dispositivos móviles para trabajos de almacén](configure-mobile-devices-warehouse.md).

Para obtener más información sobre la recepción de matrículas de entidad de almacén y las directivas de trabajo, consulte [Recepción de matrículas de entidad de almacén a través de la aplicación de almacén](warehousing-mobile-device-app-license-plate-receiving.md).

Para más información sobre la gestión de cargas entrantes , consulte [Gestión de almacén de cargas entrantes para pedidos de compra](inbound-load-handling.md).
