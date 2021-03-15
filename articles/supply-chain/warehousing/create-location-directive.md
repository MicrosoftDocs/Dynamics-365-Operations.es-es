---
title: Trabajar con directivas de ubicación
description: Este tema describe cómo trabajar con directivas de ubicación. Las directivas de ubicación son reglas definidas por el usuario que ayudan a identificar las ubicaciones de picking y de colocación para el movimiento de inventario.
author: Mirzaab
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirTable, WHSLocDirHint, WHSLocDirTableUOM, WHSLocDirFailure
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-11-13
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: b1b3bafb24ff6eb0c42d901fac3b6668cedf39ef
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963319"
---
# <a name="work-with-location-directives"></a>Trabajar con directivas de ubicación

[!include [banner](../includes/banner.md)]

Las directivas de ubicación son reglas que ayudan a identifica las ubicaciones de picking y de colocación para el movimiento de inventario. Por ejemplo, en una transacción de pedido de ventas, una directiva de ubicación determina dónde se hará el picking de los artículos y dónde se colocarán los artículos seleccionados. Las directivas de ubicación constan de un encabezado y líneas asociadas. Se crean para *tipos de órdenes de trabajo*.

> [!NOTE]
> Este tema se aplica a las características del módulo **Gestión de almacenes**. No se aplica a las características del módulo [Gestión de inventarios](../inventory/inventory-home-page.md).

Puede usar directivas de ubicación para realizar las tareas siguientes:

- Guardar artículos entrantes.
- Realizar el picking de los artículos y establecer su ubicación provisional para las transacciones de salida.
- Realizar el picking y la colocación de las materias primas para la producción.
- Reabastecer las ubicaciones.

## <a name="prerequisites"></a>Requisitos previos

Para poder crear una directiva de ubicación, debe seguir estos pasos a fin de asegurarse de que se cumplan los requisitos previos.

1. Asegúrese de que la clave de licencia requerida esté activada. Vaya a **Administración del sistema \> Preparar \> Configuración de licencia**, amplíe la clave de licencia **Comercio** y luego seleccione la clave de configuración **Gestión de almacén y transporte**. Tenga en cuenta que se requiere acceso de administrador para este paso.
1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Almacenes**.
1. Cree un almacén.
1. En la ficha desplegable **Almacenes**, establezca la opción **Usar procesos de gestión de almacenes** en *Sí*.
1. Cree ubicaciones, tipos de ubicación, perfiles de ubicación y formatos de ubicación. Para obtener más información, consulte [Configurar ubicaciones en un almacén con WMS](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).
1. Cree sitios, zonas y grupos de zona. Para obtener más información, consulte [Configuración de almacén](https://docs.microsoft.com/dynamics365/commerce/channels-setup-warehouse) y [Configurar ubicaciones en un almacén con WMS](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).

## <a name="work-order-types-for-location-directives"></a>Tipos de órdenes de trabajo para directivas de ubicación

Muchos de los campos que se pueden configurar para las directivas de ubicación son comunes a todos los tipos de órdenes de trabajo. Sin embargo, otros campos son específicos para tipos de órdenes de trabajo particulares.

![Tipos de órdenes de trabajo de directivas de ubicación](media/Location_Directives_Work_Order_Types.png "Tipos de órdenes de trabajo de directivas de ubicación")

> [!NOTE]
> Dos tipos de órdenes de trabajo, *Trabajo cancelado* e *Inventario cíclico*, son utilizados únicamente por el sistema. No se pueden crear directivas de ubicación para estos tipos de órdenes de trabajo.

Las tablas de las siguientes subsecciones enumeran los campos comunes y específicos del tipo de orden de trabajador que están disponibles cuando configura una directiva de ubicación.

### <a name="fields-that-are-common-to-all-work-order-types"></a>Campos que son comunes a todos los tipos de órdenes de trabajo

La siguiente tabla enumera los campos que son comunes a todos los tipos de órdenes de trabajo.

| Ficha desplegable | Campo |
|---|---|
| Directivas de ubicación | Tipo de trabajo |
| Directivas de ubicación | Sitio |
| Directivas de ubicación | Almacén |
| Directivas de ubicación | Código de directiva |
| Directivas de ubicación | Varios SKU |
| Líneas | Número de secuencia |
| Líneas | Cantidad inicial |
| Líneas | Cantidad final |
| Líneas | Unidad |
| Líneas | Cantidad para localizar |
| Líneas | Restringir por unidad |
| Líneas | Redondear por arriba a unidad |
| Líneas | Localizar cantidad de embalaje |
| Líneas | Permitir división |
| Acciones de directiva de ubicación | Número de secuencia |
| Acciones de directiva de ubicación | Nombre |
| Acciones de directiva de ubicación | Uso de ubicaciones fijas |
| Acciones de directiva de ubicación | Permitir inventario negativo |
| Acciones de directiva de ubicación | Habilitado para lotes |
| Acciones de directiva de ubicación | Estrategia |

### <a name="fields-that-are-specific-to-work-order-types"></a><a name="fields-specific-types"></a>Campos que son específicos para los tipos de órdenes de trabajo

La siguiente tabla enumera los campos que son específicos para tipos de órdenes de trabajo en concreto.

| Ficha desplegable | Campo | Tipo de orden de trabajo |
|---|---|---|
| Directivas de ubicación | Ubicar por | Pedidos de compra |
| Directivas de ubicación | Código de disposición aplicable | Pedidos de compra |
| Directivas de ubicación | Código de disposición | Pedidos de compra |
| Directivas de ubicación | Código de disposición aplicable | Ubicación de bienes terminados |
| Directivas de ubicación | Código de disposición | Ubicación de bienes terminados |
| Directivas de ubicación | Código de disposición aplicable | Pedidos de devolución |
| Directivas de ubicación | Código de disposición | Pedidos de devolución |
| Directivas de ubicación | Código de disposición aplicable | Ubicación de kanban |
| Directivas de ubicación | Código de disposición aplicable | Picking de kanban |
| Líneas | Plantilla de reabastecimiento inmediato | Pedidos de ventas |
| Líneas | Plantilla de reabastecimiento inmediato | Picking de materia prima |
| Líneas | Plantilla de reabastecimiento inmediato | Emisión de transferencia |
| Líneas | Plantilla de reabastecimiento inmediato | Picking de kanban |

## <a name="open-the-location-directives-page"></a>Abra la página de directivas de ubicación

Para abrir la página **Directivas de ubicación**, vaya a **Gestión de almacenes \> Configuración \> Directivas de ubicación**.

Desde allí, puede ver, crear y editar sus directivas de ubicación mediante los comandos del Panel de acciones. Consulte las secciones restantes de este tema para obtener información sobre cómo utilizar todos los campos que están disponibles en la página.

## <a name="action-pane"></a>Panel de acciones

El panel de acciones de la página **Directivas de ubicación** contiene botones que puede utilizar para crear, editar y eliminar directivas (**Editar**, **Nuevo** y **Eliminar**). También contiene los siguientes botones que le permiten ajustar la secuencia en la que se procesa la directiva de ubicación y configurar una consulta que define los criterios para aplicar la directiva de ubicación:

- **Ascender** - Mueva la directiva de ubicación seleccionada hacia arriba en la secuencia. Por ejemplo, puede moverlo del número de secuencia 4 al número de secuencia 3.
- **Bajar** - Mueva la directiva de ubicación seleccionada hacia abajo en la secuencia. Por ejemplo, puede moverlo del número de secuencia 4 al número de secuencia 5.
- **Editar consulta** - Abra un cuadro de diálogo donde puede definir las condiciones bajo las cuales se debe procesar la directiva de ubicación seleccionada. Por ejemplo, es posible que desee que se aplique solo a un almacén específico.

## <a name="location-directives-header"></a>Encabezado de directivas de ubicación

El encabezado de la directiva de ubicación incluye los siguientes campos para el número de secuencia y el nombre descriptivo de la directiva de ubicación:

- **Secuencia de números** - Este campo indica la secuencia en la que el sistema intenta aplicar cada directiva de ubicación para el tipo de orden de trabajo seleccionado. Los números bajos se aplican primero. Puede cambiar la secuencia utilizando los botones **Subir** y **Bajar** en el Panel de acciones.
- **Nombre** - Especifique un nombre descriptivo para la directiva de ubicación. Este nombre debería ayudar a identificar el propósito general de la directiva. Por ejemplo, ingrese *Preparación de pedidos de venta en el almacén 24*.

## <a name="location-directives-fasttab"></a>Ficha desplegable de directivas de ubicación

Los campos en la ficha desplegable **Directivas de ubicación** son específicos del tipo de orden de trabajo que se selecciona en el campo **Tipo de orden de trabajo** en el panel de lista.

- **Tipo de trabajo** – Seleccione el tipo de trabajo que se debe realizar. Los valores disponibles dependen del tipo de transacción de inventario seleccionada en el campo **Tipo de orden de trabajo**. Seleccione uno de los siguientes valores:

    - **Colocar**: la directiva de ubicación intentará encontrar la ubicación más ideal para colocar o ubicar el inventario que entra en el sistema desde los ajustes de recepción, producción o inventario. También se puede usar para definir la colocación en la ubicación de la etapa o en una ubicación de envío de compuerta final.
    - **Picking**: la directiva de ubicación intentará encontrar las ubicaciones más ideales de las que reservar físicamente el inventario (es decir, crear trabajo). La selección se podrá completar (es decir, la línea de trabajo de la selección se puede cerrar) aunque no se haya completado el trabajo. El usuario puede completar el picking físico. En el sistema, esa acción es un paso de picking. El usuario puede cancelar entonces desde el dispositivo móvil y completar el trabajo posteriormente. Sin embargo, el encabezado del trabajo se cierra cuando se completa la colocación final.

    > [!IMPORTANT]
    > Los otros valores del campo **Tipo de trabajo** no son relevantes para las directivas de ubicación. Aparecen solo porque el campo no se filtra para que coincida con el tipo de orden de trabajo seleccionado.

- **Sitio** - Este campo es obligatorio porque la directiva de la ubicación debe poder determinar el sitio y el almacén para la que es válida.
- **Almacén** - Este campo es obligatorio porque la directiva de la ubicación debe poder determinar el sitio y el almacén para la que es válida.
- **Código de directiva** - Seleccione el código de directiva que se debe asociar con una plantilla de trabajo o de reabastecimiento. En la página **Código de directiva** puede crear nuevos códigos para utilizarlos con el fin de conectar plantillas de trabajo o plantillas de reabastecimiento a directivas de ubicación. También pueden usar códigos de directiva para establecer un vínculo entre cualquier línea de plantilla de trabajo y una directiva de ubicación (como compuerta o ubicación provisional).

    > [!TIP]
    > Si se establece un código de directiva, el sistema no buscará las directivas de ubicación por número de secuencia cuando se debe generar el trabajo. En cambio, buscará por código de directiva. De esta manera, se puede ser más específico sobre la plantilla de ubicación que se usa para un paso determinado en una plantilla de trabajo, como el paso de almacenamiento provisional de los materiales.

- **Múltiples SKU** – Establezca esta opción en *Sí* para habilitar varias referencias de almacén (SKU) para usar en una ubicación. Por ejemplo, se deben habilitar varios SKU para la ubicación de la puerta de bahía. Si habilita varios SKU, su ubicación de colocación se especificará en el trabajo, como se esperaba. Sin embargo, la ubicación de colocación solo podrá manejar una colocación de varios elementos (si el trabajo incluye diferentes SKU que deben seleccionarse y colocarse). No podrá manejar una sola puesta de SKU. Si configura esta opción en *No*, su ubicación de colocación se especificará solo si su colocación tiene solo un tipo de SKU.

    > [!IMPORTANT]
    > Para poder realizar colocaciones de varios elementos y de un solo SKU, debe especificar dos líneas que tengan la misma estructura y configuración, pero debe establecer la opción **Varios SKU** en *Sí* para una línea y *No* para la otra. Por lo tanto, para las operaciones de colocación, debe tener dos directivas de ubicación idénticas, aunque usted no distinga entre SKU únicas y SKU múltiples en el identificador de trabajo. A menudo, si no configura estas dos directivas de ubicación, las ubicaciones inesperadas de los procesos comerciales vendrán de la directiva de ubicación aplicada. Debe utilizar una configuración similar para las directivas de ubicación que tienen un **Tipo de trabajo** de *selección* si necesita procesar pedidos que incluyen varios SKU.

    Utilice la opción **Varios SKU** para líneas de trabajo que manejan más de un número de artículo. (El número de artículo estará en blanco en los detalles del trabajo y se mostrará como **Múltiple** en las páginas de procesamiento en la aplicación del almacén).

    En un escenario de ejemplo típico, una plantilla de trabajo se configura de modo que tenga más de un par de selección/colocación. En este caso, es posible que desee buscar una ubicación de ensayo específica para usar para las líneas con un **Tipo de trabajo** de *Ubicación*.

    > [!NOTE]
    > Si la opción **Varios SKU** está configurada en *Sí*, no puede seleccionar **Editar consulta** en el Panel de acciones, porque la consulta no se puede evaluar a nivel de elemento cuando hay varios elementos. Para asegurarse de que se selecciona la directiva de ubicación deseada, utilice el campo **Código de directiva** para guiar la selección de la directiva de ubicación que está relacionada con las líneas de colocación donde se asigna ese código de directiva en la plantilla de trabajo.

    A menos que siempre trabaje con operaciones de un solo elemento o de elementos mixtos, es importante que defina dos directivas de ubicación para el tipo de trabajo *Ubicación*: una donde la opción **Varios SKU** está configurada como *Sí* y una donde está configurada como *No*.

- **Código de disposición aplicable** – Especifique si el código de disposición de la ubicación de la directiva debe coincidir con el código de disposición que se aplica cuando se recibe el artículo o si la ubicación de la directiva se puede seleccionar en función de los códigos de disposición. Si selecciona *Coincidencia exacta* y el campo **Código de disposición** está en blanco, solo se tendrán en cuenta los códigos de disposición en blanco para esta directiva de ubicación.

    > [!NOTE]
    > Este campo está disponible solo para tipos de órdenes de trabajo seleccionados donde se permite el reabastecimiento. Para obtener una lista completa, consulte la sección [Campos que son específicos de los tipos de órdenes de trabajo](#fields-specific-types) antes en este tema.

- **Localizar por** - Especifique si la cantidad almacenada debe ser la cantidad total en la placa de matrícula o si debe ser artículo por artículo. Utilice este campo para asegurarse de que todo el contenido de una placa se coloque en una ubicación y que el sistema no sugiera que divida el contenido en varias ubicaciones para procesos **ASN** (recepción de matrículas), de recepción de **Matrícula mixta** y de recepción de **Clúster**. (El proceso de recepción de **Clúster** requiere que la *Función de almacenamiento en grupo* esté activada). El comportamiento de la consulta de la directiva de ubicación, las líneas y las acciones de la directiva de ubicación variarán, según el valor que seleccione. La ficha desplegable **Líneas** solo se usa cuando **Localizar por** se establece en *Artículo*.

    > [!NOTE]
    > Este campo está disponible solo para tipos de órdenes de trabajo seleccionados donde se permite el reabastecimiento. Para obtener una lista completa, consulte la sección [Campos que son específicos de los tipos de órdenes de trabajo](#fields-specific-types).

- **Código de disposición** - Este campo se utiliza para las directivas de ubicación que tienen un tipo de orden de trabajo de *Órdenes de compra*, *Almacenamiento de productos terminados* o *Órdenes de devolución*, y un tipo de trabajo de *Ubicación*. Úselo para guiar el flujo para usar una directiva de ubicación específica, según el código de disposición que seleccionó un trabajador en la aplicación de almacén. Por ejemplo, puede dirigir los productos devueltos a una ubicación de inspección antes de que se devuelvan al stock. Un código de disposición se puede vincular a un estado de inventario. De esta forma, se puede utilizar para cambiar el estado del inventario como parte de un proceso de recepción. Por ejemplo, tiene un código de disposición, *QA*, que establece el estado del inventario en *QA*. Luego, puede tener una directiva de ubicación separada para mover ese inventario a una ubicación de cuarentena.

    > [!NOTE]
    > Este campo está disponible solo para tipos de órdenes de trabajo seleccionados donde se permite el reabastecimiento. Para obtener una lista completa, consulte la sección [Campos que son específicos de los tipos de órdenes de trabajo](#fields-specific-types).

## <a name="lines-fasttab"></a>Ficha desplegable Líneas

Utilice la ficha desplegable **Líneas** para establecer condiciones para aplicar las acciones relacionadas que se especifican en la ficha desplegable **Acciones de directiva de ubicación**. Para cada línea, puede especificar la cantidad mínima y la cantidad máxima a las que deben aplicarse las acciones. También puede especificar que las acciones deben aplicarse a una unidad de inventario específica.

- **Secuencia numérica** - Introduzca la secuencia en la que se procesará cada línea de directiva de ubicación para el tipo de trabajo seleccionado. Puede cambiar la secuencia según necesite utilizando los botones **Subir** y **Bajar** en la barra de herramientas.
- **De cantidad** - Especifique el inicio del rango de cantidades al que se aplica la línea. Especifique la cantidad con la unidad de medida seleccionada en el campo **Unidad**.
- **Ae cantidad** - Especifique el final del rango de cantidades al que se aplica la línea. Especifique la cantidad con la unidad de medida seleccionada en el campo **Unidad**.
- **Unidad** - Seleccione la unidad de medida de los artículos. Puede especificar una cantidad mínima y una cantidad máxima en las que el directorio se debe basar, y puede especificar que el directorio debe ser para una unidad de inventario específica. El campo **Unidad** *solo* se usa para la evaluación de la cantidad. Para determinar si se aplica la línea de directiva de ubicación en absoluto, el sistema usa la cantidad en la unidad que se especifica en esa línea. Cada vez que se alcanza una línea de directiva de ubicación, el sistema intenta convertir la unidad de la demanda en una unidad especificada en la línea. Si no hay conversión de unidades de medida, el sistema pasará a la siguiente línea.
- **Localizar cantidad** - Este campo se usa solo durante los intentos de colocar o ubicar artículos en el almacén. (Por lo tanto, es válida solo cuando el campo **Tipo de trabajo** está establecido en *Ubicación*). Seleccione uno de los siguientes valores para especificar la cantidad que se utiliza para evaluar si una cantidad está dentro del rango **De cantidad** a **A cantidad**:

    - **Cantidad de matrículas** - Use la cantidad en la placa que se está recibiendo.
    - **Cantidad unificada** - Utilice la cantidad que se utiliza durante la transacción. Por ejemplo, recibe una cantidad de 1000 en un almacén y la divide en 10 placas, cada una de las cuales tiene una cantidad de 100. En este caso, puede utilizar una cantidad de 1000 artículos en lugar de la cantidad de placa de 100.
    - **Cantidad restante** - Utilice la cantidad que aún debe recibirse en la línea de orden de compra que se está procesando.
    - **Cantidad esperada** - Utilice la cantidad total de la línea de la orden de compra, independientemente de lo que ya se haya recibido.

- **Restringir por unidad** - Esta casilla de verificación le permite hacer que la línea de la directiva de ubicación sea específica para una unidad de medida o varias unidades de medida. Actívela para restringir las unidades de medida que se consideran criterios de selección válidos para las líneas de directiva de ubicación. Esta funcionalidad funciona solo para directivas de ubicación donde el campo **Tipo de trabajo** está configurado en *Selección*.

    Por ejemplo, cuando reserva cantidades, desea reservar paletas solo de un conjunto específico de ubicaciones. En este caso, las líneas restringirán esa secuencia a las paletas de tal manera que cualquier cantidad que sea menor que una paleta no será seleccionada para la directiva de ubicación.

    Tenga en cuenta qeu la casilla **Restringir por unidad** no controla la unidad o unidades que se aplican en las líneas de trabajo. La restricción de unidades se aplica solo a las unidades que están disponibles a través del grupo de secuencias de unidades. Por ejemplo, un artículo está asociado con un grupo de secuencias de unidades incluye la unidad *palés* y las unidades *uds*. Se ha definido una unidad de medida, donde 1 palé = 100 unidades, y la directiva de ubicación utiliza la funcionalidad de **Restringir por unidad** solo para palés. Además, se ha definido una plantilla de trabajo que limita la creación de encabezados de trabajo a 50 uds. En este caso, se crearán líneas de trabajo de 50 uds. Para especificar la unidad de medida para la restricción, siga estos pasos:

    1. Sobre la ficha desplegable **Líneas**, seleccione **Restringir por unidad** en la barra de herramientas. (Este botón solo está disponible después de que haya activado la casilla **Restringir por unidad** en la línea y, a continuación, seleccione **Guardar**).
    1. En la página **Restringir por unidades**, en el campo **Unidad**, seleccione la unidad de medida que desea restringir para los procesos de picking y colocación.

- **Redondear a la unidad** - Este campo trabaja junto con la casilla **Restringir por unidad**. Por ejemplo, se seleccionan **Restringir por unidad** y **Redondear hasta unidad** en la línea de directiva de ubicación, el trabajo generado por la directiva para la selección de la materia prima se debe redondear a un múltiplo de una unidad de manipulación especificada en la página **Restringir por unidad**.

    > [!NOTE]
    > Esta configuración de **Redondear a la unidad** solo funciona para el tipo de orden de trabajo *Recogida de materia prima*, y solo para las directivas de ubicación donde el campo **Tipo de trabajo** está configurado en *Selección*.

- **Localizar la cantidad de embalaje** - Si especifica una cantidad de empaque en una orden de venta, orden de transferencia u orden de producción, esta casilla de verificación le permite restringir el sistema para que pueda seleccionar solo ubicaciones que tengan al menos esa cantidad de empaque.

    > [!NOTE]
    > Esta funcionalidad solo funciona con directivas de la ubicación del tipo *Selección*.

- **Permitir división** – Especifique si la directiva de la ubicación puede dividir la cantidad que se recibe o se reserva entre varias ubicaciones de almacén, o si la cantidad completa debe estar ubicada en una sola ubicación o reservada en una sola ubicación para crear el trabajo.
- **Plantilla de reabastecimiento inmediato** – Use este campo para creer una conexión a una plantilla de reabastecimiento para comenzar el reabastecimiento inmediatamente si los artículos no están asignados. Si deja este campo en blanco, el reaprovisionamiento de elementos no comenzará hasta que todas las líneas de la directiva de ubicación hayan sido procesadas.

    > [!NOTE]
    > Este campo está disponible solo para tipos de órdenes de trabajo seleccionados donde se permite el reabastecimiento. Para obtener una lista completa, consulte la sección [Campos que son específicos de los tipos de órdenes de trabajo](#fields-specific-types).

## <a name="location-directive-actions-fasttab"></a>Ficha desplegable de acciones de directivas de ubicación

Puede definir varias acciones de las directivas de la ubicación para cada línea. De nuevo, se usa un número de secuencia para determinar el orden en que se evalúan las acciones. En este nivel, puede configurar una consulta para definir cómo se encuentra la mejor ubicación en el almacén. También puede usar una configuración de valores de **Estrategia** predefinidos para encontrar una ubicación óptima.

- **Secuencia numérica** - Este campo muestra la secuencia en la que se procesan las acciones para el tipo de trabajo seleccionado. Puede cambiar la secuencia utilizando los botones **Subir** y **Bajar** en la barra de herramienats.
- **Nombre** - Especifique el nombre de la acción de la directiva de ubicación. Sea específico, de modo que la acción que se realiza quede clara en el nombre.
- **Uso de ubicación fija** - Especifique qué ubicaciones debe considerar la directiva de ubicación. Seleccione uno de los siguientes valores:

    - **Ubicaciones fijas y no fijas**: la directiva de la ubicación tendrá en cuenta todas las ubicaciones.
    - **Solo ubicaciones fijas para el producto**: la directiva de la ubicación solo tendrá en cuenta las ubicaciones fijas de los productos.
    - **Solo ubicaciones fijas para la variante del producto**: la directiva de la ubicación tendrá en cuenta solo las ubicaciones fijas para las variantes de productos.

- **Permitir inventario negativo** – Active esta casilla para permitir inventario negativo en la ubicación de almacén especificada en las directivas de ubicación.
- **Habilitado para lotes** – Active esta casilla para usar estrategias de lote para los artículos habilitados para lotes. Es importante que seleccione esta casilla de verificación para los procesos que utilizan directivas de ubicación para encontrar ubicaciones desde las que seleccionar los artículos rastreados por número de lote. De esta manera, se incluye la búsqueda de ubicaciones que contienen artículos con seguimiento de número de lote. Si esta casilla está activa y el campo **Estrategia** está establecido en *Ninguna*, el sistema pasará a la siguiente línea de acción.
- **Estrategia** – Para facilitar y agilizar la definición de las acciones asociadas con cada línea de directiva de ubicación, puede seleccionar una de las estrategias predefinidas siguientes:

    - **Ninguna**: no se utilizará ninguna estrategia.
    - **Coincidencia de la cantidad de embalaje**: esta estrategia verifica si una ubicación de picking tiene la cantidad de embalaje especificada. Esta estrategia es válida solo cuando el campo **Tipo de trabajo** está establecido en *Picking*.
    - **Consolidar**: esta estrategia consolida los artículos en una ubicación concreta cuando ya hay disponibles artículos similares. Esta estrategia es válida solo cuando el campo **Tipo de trabajo** está establecido en *Poner*. Una configuración típica de ubicación, el sistema intenta consolidarse en la primera línea de acción y, a continuación, en la segunda línea, intenta colocar sin consolidación. La consolidación de mercancías hace más eficiente la selección posterior.
    - **Reserva de lotes FEFO** - Esta estrategia utiliza reservas de lote de primer vencimiento, primero en salir (FEFO). Úsela cuando el inventario se localiza mediante una fecha de vencimiento de lote y está asignado para la reserva de lote. Esta estrategia solo se puede usar para artículos habilitados para lotes. Es válida solo cuando el campo **Tipo de trabajo** está establecido en *Picking*.
    - **Redondea al lote completo LP y FEFO** - Esta estrategia combina los elementos de las esterategias *Reserva de lotes FEFO* y *Redondea a un LP completo*. Es válido solo para elementos habilitados por lotes y directivas de ubicación que tienen un tipo de trabajo de *Selección*. La línea debe estar habilitada por lotes para usar la estrategia *Reserva de lotes FEFO* y la estrategia *Redondea a un LP completo* solo se puede utilizar para el reabastecimiento. Si esta estrategia se configura junto con un límite de existencias de la ubicación, puede provocar que la ubicación de trabajo seleccionada se sobrecargue y se ignoren los límites de existencias.
    - **Redondear por arriba hasta matrícula de entidad de almacén completa**: esta estrategia se usa para redondear hacia arriba la cantidad de inventario de modo que coincida con la cantidad de matrícula de entidad de almacén asignada a los artículos que se van a seleccionar. Solo puede usar esta estrategia para las directivas de ubicación de reabastecimiento del tipo *Selección*. Si esta estrategia se configura junto con un límite de existencias de la ubicación, puede provocar que la ubicación de trabajo seleccionada se sobrecargue y se ignoren los límites de existencias.
    - **Guiado por matrícula** – Use esta estrategia cuando libere el pedido al almacén para crear el trabajo de picking y colocación. Puede usar este enfoque para varias matrículas de entidad de almacén. Esta estrategia guiada por matrículas tratará de reservar y crear trabajo de picking en las ubicaciones que contienen las matrículas solicitadas que se han asociado con las líneas de orden de transferencia. Sin embargo, si estas acciones no se pueden completar, pero aún desea crear un trabajo de recolección, debe recurrir a otra estrategia para las acciones de directiva de ubicación. Dependiendo de los requisitos de su proceso empresarial, es posible que también desee buscar inventario en otra área del almacén.
    - **Ubicación en blanco sin trabajo entrante**: use esta estrategia para localizar ubicaciones vacías. Una ubicación se considera vacía si no tiene ningún inventario físico y ningún trabajo entrante previsto. Solo puede usar esta estrategia para las directivas de ubicación que tienen el tipo de trabajo *Selección*.
    - **Vencimiento de ubicación FIFO** – Puede usar la estrategia FIFO para enviar artículos con seguimiento por lotes y artículos sin seguimiento por lotes, según la fecha en que el inventario entró en el almacén. Esta capacidad puede ser especialmente útil para el inventario sin seguimiento por lotes, en el que una fecha de vencimiento no está disponible para utilizarla en la clasificación. La estrategia FIFO busca la ubicación que contiene la fecha de vencimiento más antigua y luego asigna el picking en función de esa fecha de vencimiento.
    - **Vencimiento de ubicación LIFO** – Puede usar la estrategia LIFO para enviar artículos con seguimiento por lotes y artículos sin seguimiento por lotes, según la fecha en que el inventario entró en el almacén. Esta capacidad puede ser especialmente útil para el inventario sin seguimiento por lotes, en el que una fecha de vencimiento no está disponible para utilizarla en la clasificación. La estrategia LIFO busca la ubicación que contiene la fecha de vencimiento más reciente y luego asigna el picking en función de esa fecha de vencimiento.

## <a name="example-using-location-directives"></a>Ejemplo: Usar directivas de ubicación

En este ejemplo, considere un proceso de pedido de compra en el que la directiva de la ubicación debe encontrar capacidad libre dentro de un almacén para los artículos de inventario que acaban de registrarse en el muelle de recepción. Primero, tiene que encontrar capacidad libre dentro del almacén consolidando con el inventario disponible. Si la consolidación no es posible, tendrá que encontrar una ubicación vacía.

Para esta situación, tiene que definir dos acciones de la directiva de la ubicación. La primera acción de la secuencia debe ser usar la estrategia *Consolidar*, y la segunda debería ser la estrategia *Vaciar la ubicación sin trabajo entrante*. A menos que defina una tercera acción para gestionar una situación de desbordamiento, dos resultados son posibles si no hay capacidad en el almacén: el trabajo puede ser creado aunque no se define ninguna ubicación o el proceso de creación de trabajo puede fallar. El resultado viene determinado por la configuración en la página **Fallos de la directiva de la ubicación**, donde puede elegir si seleccionar la opción **Detener trabajo si falla la directiva de la ubicación** para cada tipo de pedido de trabajo.

## <a name="next-step"></a>Paso siguiente

Tras crear las directivas de ubicación, puede asociar cada código de directiva a un código de plantilla de trabajo para la creación de trabajos. Para obtener más información, consulte [Controlar el trabajo de almacén usando plantillas de trabajo y directivas de ubicación](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/control-warehouse-location-directives).

## <a name="additional-resources"></a>Recursos adicionales

- Vídeo: [Análisis profundo de la configuración de la gestión de almacenes](https://community.dynamics.com/365/b/techtalks/posts/warehouse-management-configuration-deep-dive-october-14-2020)
- Tema de ayuda: [Controlar el trabajo de almacén usando plantillas de trabajo y directivas de ubicación](control-warehouse-location-directives.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]