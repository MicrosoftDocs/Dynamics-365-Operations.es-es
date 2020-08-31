---
title: Crear directivas de ubicación
description: Este tema explica cómo crear directivas de ubicación. Las directivas de ubicación son reglas definidas por el usuario que ayudan a identificar las ubicaciones de picking y de colocación para el movimiento de inventario.
author: Mirzaab
manager: tfehr
ms.date: 07/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-28
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: bdd99b5faefd7054023b45a91fad070aac055a26
ms.sourcegitcommit: ecad92c9cb7e9e57688e678f79f747673c921df5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "3692147"
---
# <a name="create-location-directives"></a>Crear directivas de ubicación

[!include [banner](../includes/banner.md)]

Este tema explica cómo crear directivas de ubicación. Las directivas de ubicación son reglas definidas por el usuario que ayudan a identificar las ubicaciones de picking y de colocación para el movimiento de inventario. Por ejemplo, para una transacción de pedido de ventas, una directiva de ubicación determina dónde se hará el picking de los artículos y dónde se colocarán los artículos seleccionados.

> [!NOTE]
> Este tema se aplica a las características del módulo **Gestión de almacenes**. No se aplica a las características del módulo [Gestión de inventarios](../inventory/inventory-home-page.md).

Puede usar directivas de ubicación para realizar las tareas siguientes:

- Guardar artículos entrantes.
- Realizar el picking de los artículos y establecer su ubicación provisional para las transacciones de salida.
- Realizar el picking y la colocación de las materias primas para la producción.
- Reabastecer las ubicaciones.

## <a name="prerequisites"></a>Requisitos previos

Para poder crear una directiva de ubicación, debe seguir estos pasos a fin de asegurarse de que se cumplan los requisitos previos.

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Almacenes**.
1. Cree un almacén.
1. En la ficha desplegable **Almacenes**, establezca la opción **Usar procesos de gestión de almacenes** en *Sí*.
1. Cree ubicaciones, tipos de ubicación, perfiles de ubicación y formatos de ubicación. Para obtener más información, consulte [Configurar ubicaciones en un almacén con WMS](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).
1. Cree sitios, zonas y grupos de zona. Para obtener más información, consulte [Configuración de almacén](https://docs.microsoft.com/dynamics365/commerce/channels-setup-warehouse) y [Configurar ubicaciones en un almacén con WMS](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/tasks/configure-locations-wms-enabled-warehouse).

## <a name="setup"></a>Configurar

### <a name="create-location-directives"></a>Crear directivas de ubicación

Para crear una directiva de ubicación, realice los pasos siguientes.

1. Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.
1. En el panel de lista, establezca como valor del campo **Tipo de orden de trabajo** el tipo de transacción de inventario para el que está creando una directiva de ubicación.
1. En el panel de acciones, seleccione **Nuevo** para crear una directiva de ubicación.
1. Para la nueva directiva de ubicación, configure los campos como se describe en la siguiente tabla.

    | Campo | Descripción |
    |---|---|
    | Número de secuencia | Introduzca un número entero que indique la posición secuencial de la directiva de ubicación. Las posiciones secuenciales determinan cuándo se procesa cada directiva de ubicación para el tipo de orden de trabajo seleccionado. |
    | Nombre | Especifique un nombre para la directiva de ubicación. | 
    | Tipo de trabajo | Seleccione el tipo de trabajo que se debe realizar. La lista de valores depende del tipo de transacción de inventario seleccionada en el campo **Tipo de orden de trabajo**. Los siguientes valores pueden estar disponibles:<ul><li>**Colocar**: la directiva de ubicación intentará encontrar la mejor ubicación para colocar o ubicar el inventario que entra en el sistema mediante ajustes de recepción, producción o inventario. La directiva de ubicación también se utiliza para definir la ubicación de colocación provisional o la ubicación de envío a compuerta final en el flujo de salida.</li><li>**Picking**: la directiva de ubicación intentará encontrar las mejores ubicaciones de las que reservar físicamente el inventario (crear trabajo). La selección se podrá completar (es decir, la línea de trabajo de la selección se puede cerrar) aunque no se haya completado el trabajo. El usuario puede completar el picking físico. En el sistema, esa acción es un paso de picking. El usuario puede cancelar entonces desde el dispositivo móvil y completar el trabajo (por ejemplo, colocar) posteriormente. Sin embargo, el encabezado del trabajo se cierra cuando se completa la colocación final.</li><li>**Recuento**, **Ajustes**, **Personalizar**, **Cambio de estado de inventario**, **Creación de matrículas de entidad de almacén**, **Impresión**, **Cambio de estado**, **Paquete a matrículas de entidad de almacén anidadas**: estos valores no se pueden usar en ninguna configuración de la directiva de la ubicación.</li></ul> |
    | Sitio | Seleccione el sitio en el que se debe completar el trabajo. |
    | Almacén | Seleccione la ubicación de almacén en la que se debe completar el trabajo. |
    | Código de directiva | Seleccione un código de directiva para guiar la selección de directivas de ubicación relacionadas con las líneas de colocación de plantilla de trabajo que tienen asignado este código. En la página **Código de directiva** puede crear nuevos códigos para utilizarlos con el fin de conectar una plantilla de trabajo con una directiva de ubicación. También puede usar esa página para establecer el vínculo entre cualquier línea de plantilla de trabajo y una directiva de ubicación (como compuerta o ubicación provisional). Para obtener más información sobre cómo configurar un código de directiva con una plantilla de trabajo, consulte [Controlar el trabajo de almacén con plantillas de trabajo y directivas de ubicación](control-warehouse-location-directives.md).<p>Si se establece un código de directiva, cuando haya que generar trabajo el sistema buscará las directivas de ubicación por código de directiva, y no por secuencia. De esta manera, se puede ser más específico sobre la plantilla de ubicación que se usa para un paso determinado en una plantilla de trabajo, como el paso de almacenamiento provisional de los materiales.</p> |
    | Código de disposición | Seleccione un código de disposición para redirigir la colocación de los artículos recibidos en una ubicación. (Para obtener más información, consulte [Configurar códigos de disposiciones](tasks/set-up-dispositions-codes.md)). Este campo solo está disponible cuando el campo **Tipo de orden de trabajo** está establecido en *Ordenes de compra*, *Órdenes de devolución* o *Ubicación de bienes terminados*. |
    | Varios SKU | Establezca esta opción en *Sí* para usar varias referencias de almacén (SKU) en una ubicación. Por ejemplo, esta opción debe establecerse en *Sí* para la compuerta.<p>Si la opción **Varios SKU** están establecidas en *Sí*, la ubicación de colocación se especificará en el trabajo (como se espera). Sin embargo, la ubicación de colocación solo podrá manejar la colocación de varios elementos si el trabajo incluye diferentes SKU que hay que seleccionar y colocar, no si el trabajo incluye solo un SKU que hay que colocar.</p><p>Si la opción **Varios SKU** está establecida en *No*, la ubicación de colocación solo se especificará si la colocación tiene un solo tipo de SKU.</p><p>Para usar ambos enfoques, debe especificar dos líneas que tengan la misma estructura y configuración, pero establezca la opción **Varios SKU** en *Sí* para una de las líneas y en *No* para la otra. Es decir, son necesarias dos directivas de ubicación idénticas para las operaciones de colocar, aunque no tenga que distinguir entre SKU únicas y SKU múltiples en el identificador de trabajo. También debe configurar una dirección de ubicación para picking si tiene un pedido con más de un artículo.</p><p>**Nota:** Si establece la opción **Varios SKU** en *Sí* para una directiva de ubicación del tipo de trabajo *Colocar*, el sistema siempre seleccionará la primera línea de directiva de ubicación, con independencia de otras restricciones creadas en las líneas.</p> |

1. Opcional: en el panel de acciones, seleccione **Editar consulta** para seleccionar las ubicaciones o para especificar las restricciones que se aplican al seleccionar una directiva de ubicación específica.
1. En la ficha desplegable **Líneas**, cree una o varias líneas para especificar las unidades y localizar o reservar una cantidad en un almacén.
1. En cada línea nueva, configure los campos como se describe en la siguiente tabla.

    | Campo | Descripción |
    |---|---|
    | Número de secuencia | Introduzca un número entero que indique la posición secuencial de la directiva de ubicación. Las posiciones secuenciales determinan cuándo se procesa cada directiva de ubicación para el tipo de trabajo seleccionado. |
    | Cantidad inicial | Especifique el intervalo de cantidades inicial para los casos en que debe seleccionarse la secuencia de la cuadrícula del medio. Especifique la cantidad con la unidad de medida seleccionada en el campo **Unidad**. |
    | Cantidad final | Especifique el intervalo de cantidades final para los casos en que debe seleccionarse la secuencia de la cuadrícula del medio. Especifique la cantidad con la unidad de medida seleccionada en el campo **Unidad**. |
    | Unidad | Seleccione la unidad de medida de los artículos.<p>Puede especificar una cantidad mínima y una cantidad máxima a la que debe aplicarse la directiva. También puede especificar que la directiva debe usarse para una unidad de inventario específica. El campo **Unidad** solo se usa para la evaluación de la cantidad.</p><p>Para determinar si se aplica una línea de directiva de ubicación, el sistema evalúa las cantidades mediante el valor de **Unidad** que se especifica en la línea. Cada vez que se acceda a una línea directiva de la ubicación, el sistema intentará convertir la unidad de la demanda en una unidad especificada en la línea. Si no hay conversión de unidades, el sistema pasará a la siguiente línea.</p> |
    | Cantidad para localizar | Este campo solo es válido cuando se intenta poner o ubicar una cantidad en el almacén. En otras palabras, solo es válido para trabajo de *Poner*. Seleccione el método que se usa para evaluar si la cantidad está en el intervalo establecido en los campos **Cantidad inicial** y **Cantidad final**. Si la directiva de ubicación es para una transacción de entrada, seleccione una de las siguientes opciones:<ul><li>**Cantidad de matrícula de entidad de almacén**: para evaluar si una cantidad está dentro del intervalo de la cantidad de destino, utilice la cantidad de la matrícula de entidad de almacén que se recibe.</li><li>**Cantidad dividida en unidades**: para evaluar si una cantidad está dentro del intervalo de la cantidad de destino, utilice la cantidad que se va a dividir en unidades durante la transacción. Por ejemplo, si en un almacén puede recibir una cantidad de 1000 y dividirla en 10 matrículas de entidad de almacén de 100 cada una, puede usar una cantidad de 1000 artículos en lugar de la cantidad de la matrícula de entidad de almacén de 100.</li><li>**Cantidad restante**: para evaluar si la cantidad está dentro del intervalo de la cantidad de destino, use la que queda por recibir en la línea de pedido de compra que se está registrando actualmente.</li><li>**Cantidad esperada**: para evaluar si una cantidad está dentro del intervalo de la cantidad de destino, use la cantidad total de la línea de pedido de compra, sea cual sea la cantidad que ya se ha recibido.</li></ul> |

1. Opcional: en la ficha desplegable **Líneas** puede establecer los campos adicionales siguientes.

    | Campo | Descripción |
    |---|---|
    | Restringir por unidad | Active esta casilla para restringir las unidades de medida que se consideran criterios de selección válidos para las líneas de directiva de ubicación. Cuando se han especificado unidades de medida, solo los elementos en los que la unidad coincide con al menos una unidad definida para el grupo de secuencias de unidades se considerarán válidos para la selección de línea.<p>Por ejemplo, la unidad está restringida a palés y el artículo está asociado con un grupo de secuencias de unidades que incluye la unidad *palés*. En este caso, los artículos se considerarán una opción válida para la directiva de ubicación.</p><p>Sin embargo, la casilla **Restringir por unidad** no controla la unidad o unidades que se aplican en las líneas de trabajo. La restricción de unidades se aplica solo a las unidades que están disponibles a través del grupo de secuencias de unidades.</p><p>Por ejemplo, un artículo está asociado con un grupo de secuencias de unidades incluye las unidades *palés* y *uds*. Se ha definido una unidad de medida donde 1 palé = 100 unidades, y la directiva de ubicación utiliza la funcionalidad de **Restringir por unidad** solo para palés. Además, se ha definido una plantilla de trabajo que limita la creación de encabezados de trabajo a 50 uds. En este caso, se crearán líneas de trabajo de 50 uds.</p><p>Para especificar la unidad de medida para la restricción, siga estos pasos</p><ol><li>En la ficha desplegable **Líneas**, seleccione **Restringir por unidad**. Este botón solo está disponible después de que haya activado la casilla **Restringir por unidad** en la línea y, a continuación, seleccione **Guardar**.</li><li>En el campo **Unidad**, seleccione la unidad de medida por la que hay que restringir para los procesos de picking y colocación.</li></ol> |
    | Redondear por arriba a unidad | Seleccione esta opción para indicar si la selección de la materia prima se redondea a un múltiplo de la unidad de manipulación especificada en el campo **Restringir por unidad**. Este campo solo se aplica a las directivas de picking de materias primas y ubicación del tipo *Picking*. |
    | Localizar cantidad de embalaje | Active esta casilla si se ha especificado una cantidad de unidades de embalaje en la página **Pedido de ventas**. Si activa esta casilla, solo se seleccionan las ubicaciones con esta cantidad de unidades de embalaje. |
    | Permitir división | Active esta casilla para dividir la cantidad entre varias ubicaciones. |
    | Plantilla de reabastecimiento inmediato | Cree una conexión a una plantilla de reabastecimiento para comenzar el reabastecimiento inmediatamente si los artículos no están asignados. Si deja este campo en blanco, el reaprovisionamiento de elementos no comenzará hasta que todas las líneas de la directiva de ubicación hayan sido procesadas.<p>Este campo está disponible solo en tipos de órdenes de trabajo seleccionados donde se permite el reabastecimiento, como *Órdenes de venta* y *Picking de materia prima*.</p> |

1. En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Nuevo** para seleccionar la ubicación o el intervalo de ubicaciones.
1. El campo **Secuencia numérica** muestra la secuencia en la que se procesará la directiva de ubicación para el tipo de trabajo seleccionado. Puede modificar la secuencia. Sin embargo, tenga cuidado con los números de secuencia para las acciones de directiva de ubicación, ya que las acciones de directiva de ubicación siempre se ejecutarán en esta secuencia.
1. En el campo **Nombre**, especifique el nombre de la acción de la directiva de ubicación. Sea específico, para que quede claro cuál es la acción.
1. Opcional: Seleccione **Editar consulta** para modificar las ubicaciones de almacén y otros criterios.
1. Opcional: puede establecer los campos adicionales siguientes para una directiva de ubicación.

    | Campo | Descripción |
    |---|---|
    | Uso de ubicaciones fijas | Seleccione qué ubicaciones debe considerar la directiva de ubicación.<ul><li>**Ubicaciones fijas y no fijas**: la directiva de la ubicación tendrá en cuenta todas las ubicaciones.</li><li>**Solo ubicaciones fijas para el producto**: la directiva de la ubicación solo tendrá en cuenta las ubicaciones fijas de los productos.</li><li>**Solo ubicaciones fijas para la variante del producto**: la directiva de la ubicación tendrá en cuenta solo las ubicaciones fijas para las variantes de productos.</li></ul> |
    | Permitir inventario negativo | Active esta casilla para permitir un inventario negativo en la ubicación de almacén especificada. |
    | Habilitado para lotes | Active esta casilla para usar estrategias de lote para los artículos habilitados para lotes. Si esta casilla está activa y el campo **Estrategia** está establecido en *Ninguna*, el sistema pasará a la siguiente línea de acción. |
    | Estrategia | Seleccione la estrategia que debe utilizar la directiva de ubicación:<ul><li>**Ninguna**: no se utilizará ninguna estrategia.</li><li>**Coincidencia de la cantidad de embalaje**: esta estrategia comprueba si una ubicación de picking tiene la cantidad de embalaje especificada. Esta estrategia es válida solo cuando el campo **Tipo de trabajo** está establecido en *Picking*.</li><li>**Consolidar**: esta estrategia consolida los artículos en una ubicación concreta cuando ya hay disponibles artículos similares. Esta estrategia es válida solo cuando el campo **Tipo de trabajo** está establecido en *Poner*. En una configuración típica de poner, el sistema intenta consolidarse en la primera línea de acción y, a continuación, en la segunda línea de acción, intenta colocar sin consolidación. La consolidación de mercancías hace más eficiente la selección posterior.</li><li>**Reserva de lote FEFO**: esta estrategia se usa cuando el inventario se localiza mediante una fecha de vencimiento de lote y se asigna para la reserva de lotes. La estrategia de reserva de lote primero en expirar, primero en salir (FEFO) también se usa cuando el inventario se ubica mediante una fecha de consumo preferente de lote además de la fecha de vencimiento. Esta estrategia solo se puede usar para artículos habilitados para lotes. Esta estrategia es válida solo cuando el campo **Tipo de trabajo** está establecido en *Picking*. Cuando selecciona esta estrategia, anula cualquier ordenación de consulta para los números de lote que se aplican.</li><li>**Redondear por arriba hasta matrícula de entidad de almacén completa**: esta estrategia se usa para redondear hacia arriba la cantidad de inventario de modo que coincida con la cantidad de matrícula de entidad de almacén asignada a los artículos que se van a seleccionar. Esta estrategia solo se puede utilizar para el tipo de reabastecimiento de las directivas de ubicación, y solo cuando el campo **Tipo de trabajo** esté establecido en *Picking*.</li><li>**Ubicación en blanco sin trabajo entrante**: esta estrategia se usa para localizar ubicaciones vacías. Una ubicación se considera vacía si no tiene ningún inventario físico y ningún trabajo entrante previsto. Esta estrategia es válida solo cuando el campo **Tipo de trabajo** está establecido en *Poner*.</li></ul> |

## <a name="example-of-the-use-of-location-directives"></a>Ejemplo del uso de las directivas de la ubicación

En este ejemplo, considere un proceso de pedido de compra en el que la directiva de la ubicación debe encontrar capacidad libre dentro de un almacén para los artículos de inventario que acaban de registrarse en el muelle de recepción. Primero, tiene que encontrar capacidad libre dentro del almacén consolidando con el inventario disponible. Si la consolidación no es posible, tendrá que encontrar una ubicación vacía.

Para esta situación, tiene que definir dos acciones de la directiva de la ubicación. La primera acción de la secuencia debe ser usar la estrategia **Consolidar**, y la segunda debería ser la estrategia **Vaciar la ubicación sin trabajo entrante**. A menos que defina una tercera acción para gestionar una situación de desbordamiento, dos resultados son posibles si no hay capacidad en el almacén: el trabajo puede ser creado aunque no se define ninguna ubicación o el proceso de creación de trabajo puede fallar. El resultado viene determinado por la configuración en la página **Fallos de la directiva de la ubicación**, donde puede decidir si seleccionar la opción **Detener trabajo si falla la directiva de la ubicación** para cada tipo de pedido de trabajo.

## <a name="next-step"></a>Paso siguiente

Tras crear las directivas de ubicación, puede asociar cada código de directiva a un código de plantilla de trabajo para la creación de trabajos. Para obtener más información, consulte [Controlar el trabajo de almacén usando plantillas de trabajo y directivas de ubicación](https://docs.microsoft.com/dynamics365/supply-chain/warehousing/control-warehouse-location-directives).

## <a name="technical-information-for-system-admins"></a>Información técnica para administradores de sistema

Si no tiene acceso a las páginas que se usan para completar esta tarea, póngase en contacto con el administrador del sistema y proporcione la información que se indica en la tabla siguiente.

| Categoría | Requisito previo |
|---|---|
| Configuration Keys | Vaya a **Administración del sistema \> Configuración \> Configuración de licencias**. Expanda la clave de licencia **Comercial** y, a continuación, seleccione la clave de configuración **Administración del almacén y el transporte**. |
