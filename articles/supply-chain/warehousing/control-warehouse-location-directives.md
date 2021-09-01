---
title: Controlar el trabajo de almacén usando plantillas de trabajo y directivas de ubicación
description: Este tema describe cómo usar plantillas de trabajo y directivas de ubicación para determinar cómo y dónde se realiza el trabajo en el almacén.
author: perlynne
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocDirFailure, WHSLocDirHint, WHSLocDirTable, WHSLocDirTableUOM, WHSRFMenuItem, WHSWork, WHSWorkClass, WHSWorkPool, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72921
ms.assetid: 377ab8af-5b0c-4b5e-a387-06ac1e1820c0
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a7e955fba12e963a443c0304f0a8a0e395c46909dd34de12cd51fa9788491786
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770153"
---
# <a name="control-warehouse-work-by-using-work-templates-and-location-directives"></a>Controlar el trabajo de almacén usando plantillas de trabajo y directivas de ubicación

[!include [banner](../includes/banner.md)]

Este tema describe cómo usar plantillas de trabajo y directivas de ubicación para determinar cómo y dónde se realiza el trabajo en el almacén.

Las instrucciones que los trabajadores de almacén reciben en un dispositivo móvil están determinadas por las plantillas de trabajo de Dynamics 365 Supply Chain Management que configura para definir los distintos procesos y tareas de almacén. Las plantillas de trabajo determinan cómo se realiza el trabajo para cada proceso de almacén. Si vincula un directorio de ubicación a plantillas de trabajo, puede ayudar a garantizar que el trabajo se produce en áreas físicas específicas de los almacenes.

## <a name="work-templates"></a>Plantillas de trabajo

La página **Plantillas de trabajo** le permite definir las operaciones de trabajo que se deben realizar en el almacén. Normalmente, las operaciones de trabajo del almacén constan de un par de acciones: un trabajador de almacén recoge inventario disponible en una ubicación y después pone el inventario seleccionado en otra ubicación. 

Las plantillas de trabajo constan de un encabezado y las líneas asociadas. Cada plantilla de trabajo es para un determinado *tipo de pedido de trabajo*. Muchos tipos de pedido de trabajo están asociados con los documentos de origen, como pedidos de ventas o compras. Sin embargo, otros tipos de pedido de trabajo representan procesos independientes de almacén, como recuento cíclico. El *id. del grupo de trabajo* le permite organizar el trabajo en grupos. 

Use los ajustes en la definición del encabezado del trabajo para determinar cuándo se debe crear un nuevo elemento de trabajo. Por ejemplo, puede establecer un número máximo de líneas de selcción y un máximo previsto de tiempo de selección. Luego, si el trabajo para un proceso de selección de un pedido de ventas supera cualquiera de estos valores, el trabajo se divide en dos partes.

Utilice el botón **Descansos del encabezado de trabajo** para definir cuándo el sistema debe crear nuevos encabezados de trabajo. Por ejemplo, para crear un encabezado de trabajo para cada _Número de orden_, seleccione **Editar consulta** en el Panel de acciones y luego agregue el campo **Número de orden** a la pestaña **Clasificación** del editor de consultas. Los campos que se agregan a la pestaña **Clasificación** están disponibles para su selección como *campos de agrupación*. Para configurar sus campos de agrupación, seleccione **Descansos del encabezado de trabajo** en el Panel de acciones y, a continuación, para cada campo que desee utilizar como campo de agrupación, seleccione la casilla de verificación en la columna **Agrupar por este campo**.

Las líneas de trabajo representan las tareas físicas que son necesarias para procesar el trabajo. Por ejemplo, para un proceso de salida de almacén, puede haber una línea de trabajo para seleccionar los artículos dentro del almacén y otra línea para configurar dichos artículos en una zona de espera. Después, puede haber una línea adicional para seleccionar los artículos provisionales de la zona de espera, y otra línea para poner los artículos en un camión como parte del proceso de carga. Puede establecer unn *código directivo* en líneas de la plantilla de trabajo. Un código directivo está vinculado a una ubicación directiva y, por tanto, ayuda a garantizan que el trabajo del almacén se ha procesado en la ubicación correcta en el almacén.

Puede configurar una consulta para controlar si se usa una determinada plantilla de trabajo. Por ejemplo, puede establecer una limitación para poder utilizar una determinada plantilla solo para el trabajo en un almacén específico. Como alternativa, puede tener varias plantillas que se usan para crear el trabajo para procesar pedidos de venta salientes, en función del origen de venta. El sistema usa el campo **Número de secuencia** para determinar el orden en que las plantillas de trabajo disponibles son evaluadas. Por lo tanto, si tiene una consulta muy específica para una determinada plantilla de trabajo, debe darle un número de secuencia bajo. Dicha consulta se evaluará antes que otras consultas más generales.

> [!NOTE]
> Para evitar que el sistema sobrescriba automáticamente los *números de secuencia* de la plantilla de trabajo una vez eliminada una plantilla, active la función *Conservar los números de secuencia de la plantilla de trabajo al eliminar* en [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Para detener o poner en pausa un proceso de trabajo, puede usar la configuración **Detener trabajo** en la línea de trabajo. En ese caso, no se le solicitará al trabajador que se está realizando el trabajo que realice la siguiente etapa de trabajo. Para pasar al siguiente paso, dicho trabajador u otro trabajador debe seleccionar el trabajo de nuevo. También puede separar las tareas dentro de un elemento de trabajo mediante un *id. de clase de trabajo* diferente en las líneas de la plantilla de trabajo.

## <a name="location-directives"></a>Directivas de ubicación

Las directivas de ubicación son reglas que ayudan a identifica las ubicaciones de picking y de colocación para el movimiento de inventario. Por ejemplo, en una transacción de pedido de ventas, una directiva de ubicación determina dónde se hará el picking de los artículos y dónde se colocarán los artículos seleccionados. Los directorios de la ubicación constan de un encabezado y las líneas asociadas, y se crean en la página **Directorios de ubicación**.

En el encabezado, cada directorio de ubicación se debe asociar a un *tipo de pedido de trabajo* que especifica el tipo de transacción de inventario para el cual el directorio se usará, como pedidos de ventas, reabastecimiento o selección de la materia prima. El *tipo de trabajo* especifica si el directorio de la ubicación se usará para seleccionar o colocar el trabajo, o para otro proceso de almacén, como cómputo o cambios de estado del inventario. También debe especificar un *sitio* y un *almacén*. Un *código directivo* que se especifica en el encabezado se puede usar para vincular el directorio de la ubicación a una o varias plantillas de trabajo. 

En cuanto a plantillas de trabajo, puede configurar una consulta para determinar cuándo se usa un directorio concreto de la ubicación. Por ejemplo, puede especificar que cuando el comercio electrónico es el origen de un pedido de ventas, el inventario se debe seleccionar en un área dedicada en el almacén. El sistema usa el campo **Número de secuencia** para determinar el orden en que las directivas disponibles de la ubicación son evaluadas.

Las líneas directivas de la ubicación establecen restricciones adicionales en la aplicación de las reglas de búsqueda de la ubicación. Puede especificar una cantidad mínima y una cantidad máxima en las que el directorio se debe basar, y puede especificar que el directorio debe ser para una unidad de inventario específica. Por ejemplo, si la unidad de medida es pallets, entonces los artículos en pallets se pueden colocar en una ubicación concreta. También puede especificar si la cantidad se puede dividir entre varias ubicaciones. Como el encabezado de la directiva de ubicación, cada línea directiva de la ubicación tiene un número de secuencia que determina la orden en que las líneas se evalúan.

Las directivas de la ubicación tienen un nivel de detalle adicional: *acciones de la directiva de la ubicación*. Puede definir varias acciones de las directivas de la ubicación para cada línea. De nuevo, se usa un número de secuencia para determinar el orden en que se evalúan las acciones. En este nivel, puede configurar una consulta para definir cómo encontrar la mejor ubicación en el almacén. También puede usar una configuración de **Estrategia** predefinida para encontrar una ubicación óptima.

Para obtener más información sobre cómo crear y configurar directivas de ubicación, consulte [Crear una directiva de ubicación](create-location-directive.md).

### <a name="how-location-directives-work"></a>Cómo funcionan las directivas de ubicación

Las directivas de ubicación determinan *dónde* los artículos deben ser recogidos y *dónde* deberían ponerse. El sistema evalúa una directiva de ubicación para cada línea de trabajo y luego selecciona una ubicación, según los detalles de la línea de trabajo. El sistema primero encuentra todas las directivas de ubicación que coinciden con una línea de trabajo en particular (por ejemplo, son para el almacén correcto y coinciden con la consulta). Luego evalúa secuencialmente las directivas que ha encontrado.

> [!NOTE]
> Hay casos especiales en los que la ubicación de picking o la ubicación de colocación están preseleccionadas. Por ejemplo, durante el _registro de compra_, la primera selección es siempre desde la ubicación donde se realiza el registro. Otro ejemplo es el *movimiento de inventario por plantilla*, donde el trabajador del almacén selecciona la ubicación de picking y solo las ubicaciones de colocación se encuentran a través de las directivas de ubicación.

## <a name="additional-resources"></a>Recursos adicionales

- Vídeo: [Análisis profundo de la configuración de la gestión de almacenes](https://community.dynamics.com/365/b/techtalks/posts/warehouse-management-configuration-deep-dive-october-14-2020)
- Tema de ayuda: [Trabajar con directivas de ubicación](create-location-directive.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]