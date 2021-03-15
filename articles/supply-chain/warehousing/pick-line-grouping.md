---
title: Picking de agrupación de líneas
description: Este tema proporciona una descripción general de la agrupación de líneas de selección.
author: Mirzaab
manager: tfehr
ms.date: 12/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: e70244d46ec2787fefdb097d0354af7910b55e9c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989727"
---
# <a name="pick-line-grouping"></a>Picking de agrupación de líneas

[!include [banner](../includes/banner.md)]

La agrupación de líneas de selección habilita varias líneas de trabajo que tienen el mismo artículo y ubicación para combinarlas en una sola selección que se presenta al usuario en el dispositivo móvil. Esto permite que los trabajadores del almacén puedan recibir las instrucciones más eficaces, pero la separación de líneas de trabajo requeridas (para diferentes contenedores, pedidos, etc.) aún se puede mantener en el sistema.

## <a name="turn-on-the-pick-line-grouping-feature"></a>Activar la característica de agrupación de la línea de selección

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar el espacio de trabajo [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:

- **Módulo:** *Gestión de almacén*
- **Nombre de la función:** *Seleccionar agrupación de líneas*

## <a name="set-up-pick-line-grouping"></a>Configurar la agrupación de líneas de selección

### <a name="create-a-mobile-device-menu-item"></a>Crear un elemento de menú del dispositivo móvil

1. Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.
1. En el panel de acciones, haga clic en **Nueva**.
1. En el campo **Nombre del elemento del menú**, especifique *Selección de línea de grupo de ventas*.
1. En el campo **Título**, especifique *Selección de línea de grupo de ventas*. Este título se mostrará en el menú del dispositivo móvil.
1. En el campo **Modo**, seleccione *Trabajo*.
1. Establezca la opción **Usar trabajo existente** en *Sí*.
1. En la ficha desplegable **General**, establezca los valores siguientes:

    - En el campo **Dirigido por**, seleccione *Dirigido por el usuario*.
    - Seleccione la opción **Generar matrícula de entidad de almacén** en *Sí*.
    - Establezca la opción **Selección de grupo** en *Sí*.
    - Acepte los valores predeterminados del resto de opciones.

1. Siga estos pasos para configurar las clases de trabajo válidas para el elemento de menú del dispositivo móvil:

    1. En la ficha desplegable **Clases de trabajo**, seleccione **Nuevo**.
    2. En el campo **Identificador de la clase de trabajo**, puede seleccionar tanto *Ventas* como *Selección de pedidos de ventas* en función del almacén que vaya a utilizar. Para este escenario, seleccione *Selección de pedidos de ventas*.

        El campo **Tipo de orden de trabajo** se configura automáticamente en *Pedidos de ventas*.

### <a name="set-up-a-mobile-device-menu"></a>Configurar un menú de dispositivo móvil

Siga estos pasos para agregar el elemento de menú que acaba de crear al menú **Salida**.

1. Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.
1. En el panel Acciones, seleccione **Editar**.
1. El panel de lista muestra todos los menús de dispositivos móviles existentes. En la lista, seleccione *Salida*.
1. En la lista **Elementos de menús y menús disponibles**, busque y seleccione el elemento de menú *Selección de línea de grupo de ventas* que ha creado.
1. Seleccione el botón de flecha derecha para mover el elemento de menú *Selección de línea de grupo de ventas* a la lista **Estructura del menú**.
1. Utilice los botones de flecha hacia arriba o flecha hacia abajo para mover el elemento del menú a la posición deseada en la estructura de menú.
1. En el panel Acciones, seleccione **Guardar**.

### <a name="set-up-a-work-template"></a>Configurar una plantilla de trabajo

1. Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.
1. En el campo **Tipo de orden de trabajo**, seleccione *Pedidos de ventas*.
1. En la cuadrícula **Visión general**, busque y seleccione la plantilla de trabajo que debe usarse con esta función. Para este escenario, seleccione la plantilla *51 Recoger para preparar*.
1. En el panel Acciones, seleccione **Editar consulta**.
1. En el cuadro de diálogo de editor de consulta, en la pestaña **Ordenación**, seleccione **Añadir** y luego establezca los siguientes valores para la nueva fila:

    - En la columna **Tabla**, seleccione *Transacciones de trabajo temporal*.
    - En la columna **Tabla derivada**, seleccione *Transacciones de trabajo temporal*.
    - En la columna **Campo**, seleccione *Número de artículo*.
    - En la columna **Dirección de búsqueda**, seleccione *Ascendente*.

1. Seleccione **Aceptar** para cerrar el cuadro de diálogo y guardar la selección.
1. Recibirá el siguiente mensaje: "La agrupación se restablecerá, ¿continuar?" Seleccione **Sí** para continuar.

> [!IMPORTANT]
> Para que la funcionalidad de agrupación de líneas de selección funcione, las líneas de trabajo deben ordenarse por id. de artículo. Si las líneas que tienen los mismos artículos no se secuencian una tras otra, no se agruparán.

## <a name="example"></a>Ejemplo

### <a name="create-picking-work"></a>Crear trabajo de selección

Antes de poder configurar la agrupación de líneas de clúster debe crear un trabajo de salida válido.

1. Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.
1. Seleccione **Nuevo** para crear un pedido de ventas.
1. En el campo **Cuenta de cliente**, seleccione *US-004*.
1. En la ficha desplegable **General**, en el campo **Almacén**, seleccione el almacén *51*.
1. Seleccione **Aceptar**.
1. En la ficha desplegable **Líneas de pedido de ventas**, agregue las seis líneas siguientes:

    - **Línea 1:** en el campo **Número de artículo**, seleccione *M9200*. En el campo **Cantidad**, especifique *3*.
    - **Línea 2:** en el campo **Número de artículo**, seleccione *M9201*. En el campo **Cantidad**, especifique *3*.
    - **Línea 3:** en el campo **Número de artículo**, seleccione *M9202*. En el campo **Cantidad**, especifique *2*.
    - **Línea 4:** en el campo **Número de artículo**, seleccione *M9200*. En el campo **Cantidad**, especifique *1*.
    - **Línea 5:** en el campo **Número de artículo**, seleccione *M9200*. En el campo **Cantidad**, especifique *3*.
    - **Línea 6:** en el campo **Número de artículo**, seleccione *M9202*. En el campo **Cantidad**, especifique *7*.

    A continuación se muestra un resumen de las cantidades totales para cada artículo:

    - **Artículo M9200:** *7* cada uno
    - **Artículo M9201:** *3* cada uno
    - **Artículo M9202:** *9* cada uno

1. Antes de liberar los pedidos al almacén, debe asegurarse de que las ubicaciones de selección tengan suficiente inventario para todos los artículos en todos los pedidos. Revisa la configuración de **Directiva de ubicación** para determinar qué ubicaciones de selección se utilizan para la selección de pedidos de ventas. Si usa el entorno de datos de demostración de Contoso para el almacén *51*, confirme que hay inventario disponible.

    Ahora debe reservar el inventario para cada línea.

1. En la ficha desplegable **Líneas de orden de venta**, seleccione una de las líneas que se deben reservar.
1. En el menú **Inventario** sobre la cuadrícula, seleccione **Reserva**.
1. En la página **Reserva**, en el Panel de acciones, seleccione **Reservar lote** para aplicar la reserva. A continuación, cierre la página.
1. Repita los pasos del 8 al 10 para las líneas restantes que se deben reservar.

    Ahora debe lanzar el pedido de ventas al almacén.

1. En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.

    Recibe un mensaje que indica que se ha creado un envío y un lanzamiento, y que el lanzamiento se ha enviado para ejecutarse en un lote.

    Cuando se han completado el lanzamiento y todos los trabajos posteriores, se crea un ID de trabajo para el trabajo que tiene seis líneas. Las líneas se ordenan por número de artículo.

1. Vaya a **Gestión de almacenes \> Trabajo \> Todo el trabajo** para ver el trabajo que se ha creado. Tome nota del valor **Id. de trabajo**, porque lo necesitará en el siguiente procedimiento.

### <a name="initiate-picking-from-the-mobile-device"></a>Iniciar la recolección desde el dispositivo móvil

1. Inicie sesión en el dispositivo móvil como un usuario configurado para el almacén *51*.
1. En el dispositivo móvil, seleccione el menú que incluye el nuevo elemento de menú del dispositivo móvil. Para este escenario, seleccione **Salida**.
1. Seleccione el elemento de menú **Selección de línea de grupo de ventas** para iniciar la selección.
1. Introducir el valor del **ID de trabajo** que anotó en el procedimiento anterior.

    Debería ver un paso de selección donde todas las líneas de selección para el artículo *M9200* están agrupadas y debería recibir una instrucción para elegir *7* de cada uno de los elementos *M9200*.

    > [!IMPORTANT]
    > En el dispositivo móvil, el trabajo de selección para las tres líneas de trabajo de selección se ha agregado en un paso de selección para el usuario.

1. Confirme el paso de selección.
1. Vaya a la pantalla de trabajo para el ID del trabajo y observe que las tres líneas de selección para el artículo *M9200* se han cerrado simultáneamente.
1. Regrese al dispositivo móvil y continúe con la selección. La línea de trabajo 4 para el artículo *M9201* debe ser presentada. Debido a que solo había una línea de trabajo en el pedido, no hay nada que agregar.
1. Confirme el paso de selección.
1. El último paso de selección en el dispositivo móvil agrega las dos últimas líneas de selección de la orden de trabajo.
1. Complete el paso de selección para *9* de cada uno del artículo *M9202*.
1. Confirme el paso de colocación y cualquier par adicional de selección/colocación para completar el trabajo.

> [!IMPORTANT]
>
> - Las líneas de trabajo solo se pueden agrupar si están en secuencia.
> - No se admite la siguiente funcionalidad:
>
>   - Artículos con peso capturado
>
>    Si hay artículos con peso capturado en el trabajo, recibirá un mensaje de error antes de iniciar la selección.
>
>   - Selección de piezas
>   - Líneas de trabajo que tienen trabajo de reabastecimiento sin terminar
>   - Selección en exceso
>   - Selección corta con reasignación de artículos


[!INCLUDE[footer-include](../../includes/footer-banner.md)]