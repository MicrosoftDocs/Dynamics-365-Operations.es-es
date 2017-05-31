---
title: Recursos de Operations
description: "Los recursos de operaciones realizan las actividades de un proyecto o de un proceso de producción. Pueden ser de distintos tipos y tener diferentes capacidades."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WrkCtrCapability
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 61943
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 30f5ef06fe20894f373e342d09a1e642ab1f0caf
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="operations-resources"></a>Recursos de Operations

[!include[banner](../includes/banner.md)]


Los recursos de operaciones realizan las actividades de un proyecto o de un proceso de producción. Pueden ser de distintos tipos y tener diferentes capacidades. 

<a name="operations-resources"></a>Recursos de Operations
--------------------

Los recursos de operaciones son las máquinas, las herramientas, los trabajadores, las instalaciones, las áreas físicas o los proveedores que realizan las actividades de un proyecto o de un proceso de producción. Pueden ser de distintos tipos y pueden tener diferentes capacidades.

-   **Proveedor**: un recurso externo que realiza las actividades de un proyecto o las operaciones de producción. Un ejemplo es un subcontratista. Al vincular recursos de proveedor a una cuanta de proveedor, puede generar compras para subcontratistas en función de las líneas de la lista de materiales (L. MAT.) o las líneas de producción.
-   **Recursos humanos**: un trabajador de proyecto o de producción que realiza una actividad, ya sea solo o como operador de una herramienta o de una máquina. Si usa la funcionalidad de recursos humanos, puede vincular recursos humanos a un trabajador. El motor de programación puede asignar a recursos, en función de las capacidades definidas para el trabajador correspondiente.
-   **Máquina**: una máquina u otro equipo de producción requerido en la producción.
-   **Herramienta**: un instrumento o un dispositivo que se suele usar junto con otro recurso para realizar una actividad en un proyecto o en producción.
-   **Ubicación**: una ubicación física de un tamaño determinado necesario para realizar una actividad. Un ejemplo es una zona de montaje.
-   **Instalación**: un edificio o una estructura fija que se requiere para realizar una actividad.

## <a name="calendars"></a>Calendarios
Un calendario se puede asignar un recurso de operaciones y describe la capacidad (en horas) de dicho recurso. Los horarios de trabajo del recurso de operaciones se determinan por el calendario asignado al grupo de recursos del que forma parte el recurso de operaciones. Puede establecer una fecha de vigencia y la fecha de vencimiento para el calendario asignado. A continuación, puede asignar más de un calendario a un recurso de operaciones. Sin embargo, las fechas de los calendarios asignados no se pueden superponer y el recurso de operaciones solo se puede asignar a un calendario cada vez. **Nota**: si no hay calendarios laborales efectivos para un grupo de recursos (por ejemplo, si el último calendario asignado o el único calendario asignado ha vencido), no podrá tener acceso a los recursos de operaciones asignados al grupo de recursos para la planificación de producción y la programación de operaciones. También puede asignar un calendario a un grupo de recursos para especificar los horarios de trabajo para el grupo de recursos y todos los recursos de operaciones asignados al grupo de recursos. La capacidad del grupo de recursos se calcula como la suma de las capacidades de cada recurso de operaciones asignado a ese grupo de recursos. El calendario asignado a un grupo de recursos puede cambiar a lo largo del tiempo.

## <a name="resource-capabilities"></a>Capacidades de recursos
Una capacidad es la posibilidad de que un recurso de operaciones realice una actividad concreta. Puede asignar una o más capacidades a un recurso de operaciones. A continuación, el motor de programación emparejará los requisitos de recurso de cada actividad con las capacidades de recursos de operaciones disponibles para asignar los recursos. Las capacidades se pueden asignar a todos los tipos de recursos de operaciones (**Herramienta**, **Proveedor**, **Máquina**, **Recursos humanos**, **Ubicación** o **Instalación**). Para asignar capacidades a los recursos de operaciones durante un tiempo limitado, defina una fecha de inicio y una fecha de vencimiento en la asignación de la capacidad. Para obtener más información, consulte [Capacidades de recursos](resource-capabilities.md).

## <a name="resource-groups"></a>Grupos de recursos
Un grupo de recursos es un conjunto de recursos de operaciones que representa la granularidad con la que desea programar los recursos cuando usa el método de programación de operaciones. Por lo tanto, los grupos de recursos corresponden normalmente a la organización física de celdas de trabajo, que están delimitadas por las líneas amarillas en la planta de producción. El grupo de recursos define el sitio, la unidad de producción y el contexto de almacén para los recursos asignados al grupo. Al asignar un recurso de operaciones a un grupo de recursos, se permite que el recurso se programe en el sitio en el que se encuentra el grupo de recursos. No es necesario asignar los recursos de operaciones que cree a un grupo de recursos. Sin embargo, debe asignar un recurso de operaciones a un grupo de recursos para poder programarlo para realizar un trabajo. Un recurso de operaciones se puede asignar a un grupo de recursos durante un tiempo limitado. También puede asignar un recurso de operaciones a varios grupos de recursos, de manera que después pueda compartir el recurso a través de sitios. Sin embargo, las fechas de vigencia y de vencimiento no se pueden superponer. En otras palabras, no se puede asignar un recurso de operaciones a dos grupos de recursos al mismo tiempo. Los cambios en asignaciones del grupo de recursos solo serán efectivas para las nuevas asignaciones de recursos. Las reservas de capacidades para trabajos, operaciones y previsiones de horas de proyecto que ya estén programadas ya no se verán afectadas. **Nota**: al asignar recursos de operaciones de tipo **Proveedor** a un grupo de recursos, todos los recursos de operaciones asignados a dicho grupo de recursos deben ser de tipo **Proveedor** y deben estar vinculados a la misma cuenta de proveedor.

## <a name="production-units"></a>Unidades de producción
Una unidad de producción es una unidad administrativa que agrupa los grupos de recursos. Una unidad de producción puede contener varios grupos de recursos, pero un grupo de recursos sólo se puede asignar a una unidad de producción. Una unidad de producción refleja el diseño físico de los recursos de producción y no tiene ningún efecto en las transacciones o en cómo estas se procesan. Debe asociar una unidad de producción a un sitio. También se puede asignar un almacén de picking y un almacén de almacenamiento para una unidad de producción. Una unidad de producción se puede usar para consolidar y filtrar. Por ejemplo, un gestor de planta puede ver un resumen adecuado de la carga de trabajo pendiente y la capacidad disponible para una unidad de producción concreta. La unidad de producción asignada a un grupo de recursos se puede modificar. También se puede eliminar una unidad de producción. Sin embargo, estas modificaciones de la unidad de producción sólo serán efectivas para los nuevos pedidos que se creen una vez ejecutada la programación maestra. Si desea aplicar la modificación de la unidad de producción en los pedidos existentes, deberá hacer el cambio manualmente.

## <a name="resource-scheduling"></a>Programación de recursos
Se asignan recursos de operaciones a las actividades cuando se programa un proyecto o una producción. Hay dos métodos de programación: programación de operaciones y programación de trabajos. Cuando usa la programación de operaciones, cada operación o actividad de proyecto se programa en el grupo de recursos que contiene los recursos de operaciones que coinciden con los requisitos de recurso que se especifican para la operación. Si se requiere un recurso de operaciones específico para la operación, la programación reserva capacidad solo en un recurso de operaciones específico del grupo. La programación del trabajo más detallado que la programación de operaciones. Analiza cada operación en tareas o trabajos individuales. Estos trabajos se asignan a los recursos de operación que los realizarán. La programación de operaciones reserva capacidad en el grupo de recursos en función de los tiempos de operación definidos en la ruta de producción o en las actividades de proyecto. Si trabaja con capacidad limitada, la programación depende de la disponibilidad de los recursos de operaciones necesarios para completar la actividad. Para la programación de operaciones, la capacidad del grupo de recursos es la suma de la capacidad disponible de los recursos de operaciones que forman parte de dicho grupo. Las reservas de capacidad que ya existen para los recursos de operaciones se consideran como capacidad no disponible. Si no hay suficiente capacidad disponible para la producción, los pedidos de producción pueden retrasarse e incluso detenerse. En la página **Recursos**, puede definir varias propiedades que controlan cómo se realizan las reservas de capacidades:

-   **Capacidad**: permite especificar la capacidad del recurso de operaciones por hora en términos de unidad de medida de la capacidad.
-   **Capacidad de lotes**: permite especificar el número máximo de piezas que el recurso de operaciones puede procesar en cada ejecución.
-   **Porcentaje de eficacia**: especifique la eficacia que espera del recurso de operaciones. El porcentaje de eficacia ajusta el rendimiento del recurso de operaciones y afecta al tiempo reservado para el recurso. Los plazos para las operaciones que usan el recurso de operaciones también se ajustan según corresponda. A continuación se indica la fórmula que se usa para el cálculo: Tiempo de programación = Tiempo × 100 ÷ Porcentaje de eficiencia En esta fórmula, *Tiempo* incluye el tiempo de ejecución y el tiempo de configuración.
-   **Porcentaje de programación de operaciones**: especifique el porcentaje máximo de capacidad del recurso de operaciones que desea utilizar en la programación de operaciones. Para proporcionar flexibilidad en la capacidad durante la programación del trabajo, debe establecer este porcentaje en un valor inferior al 100 por cien.
-   **Capacidad limitada**: establezca esta opción en **Sí** si el recurso de operaciones debe programarse en función de la capacidad real disponible y si deben tenerse en cuenta las reservas de capacidad existentes. Si esta opción se establece en **No**, se supone que el recurso de operaciones tiene capacidad infinita y, por lo tanto, el recurso puede estar reservado en exceso.
-   **Propiedad limitada**: permite establecer esta opción en **Sí** si desea que el recurso de operaciones se programe en función de la capacidad real disponible en cuanto a las propiedades de programación de horas de trabajo necesarias.
-   **Exclusivo**: establezca esta opción en **Sí** si no desea que el recurso esté disponible para otro trabajo u operación hasta finalizar la producción actual. En este caso, el recurso de operaciones no se puede utilizar incluso si hay espacios en el tiempo de ejecución del recurso.
-   **Recurso de cuello de botella**: permite definir el recurso de operaciones como recurso de cuello de botella. Un recurso de cuello de botella se programa mediante el uso de una capacidad limitada cuando se seleccionan las opciones **Capacidad limitada** y **Programación de cuello de botella** en la página **Planes maestros**.

Para programar varios recursos de operaciones al mismo tiempo para llevar a cabo, por ejemplo, una operación en producción, debe especificar los requisitos para los diferentes recursos mediante operaciones principales y secundarias. A continuación, puede reservar también varios recursos de operaciones que tengan otra capacidad. El recurso de operaciones que se programa para la operación principal determina la duración de la actividad.

## <a name="lean-work-cells"></a>Celdas de trabajo lean
Puede especificar que un grupo de recursos es una celda de trabajo lean. Entonces el grupo de recursos puede formar parte de un flujo de producción. Si especifica un grupo de recursos como celda de trabajo lean, también impide que el grupo de recursos y los recursos de operaciones asignados se destinen a las operaciones de un pedido de producción o de una previsión de horas del proyecto. Para cada grupo de recursos que actúa como celda de trabajo lean, debe especificar la información siguiente:

-   **Calendario**: el calendario laboral de la celda de trabajo, que debe tener la propiedad de un día laborable estándar.
-   **Almacén y ubicación de entrada**: la ubicación predeterminada que se usa para seleccionar el material para una actividad.
-   **Almacén y ubicación de salida**: la ubicación donde se coloca toda la salida de la celda de trabajo.
-   **Categoría de coste del tiempo de ejecución**: esta categoría se debe definir para la celda de trabajo si el seguimiento del trabajo directo se realiza en gestión de costes.

Cuando usa un grupo de recursos como celda de trabajo lean, la capacidad de la celda de trabajo se especifica directamente en el grupo de recursos. Por lo tanto, no es necesario asignar los recursos de operaciones al grupo de recursos. Solamente cuando un subcontratista gestiona la celda de trabajo, debe asignarse un recurso de operaciones de tipo **Proveedor** a la celda de trabajo. Si asigna un recurso de operaciones a un grupo de recursos marcado como celda de trabajo, la capacidad de la celda de trabajo no se ve afectada.

## <a name="costing-resources"></a>Recursos de gestión de costes
Al definir una actividad como una operación de ruta o una previsión de horas de proyecto, puede especificar el requisito para un recurso de operaciones o un grupo de recursos específico. Sin embargo, también puede especificar el requisito para un recurso de operaciones de un tipo específico o un recurso de operaciones que tiene una capacidad o una competencia específica. Por este motivo, la asignación real del recurso no se realiza hasta que se programe la actividad y se reserve la capacidad. Por lo tanto, en una operación de ruta, puede especificar que la estimación y el cálculo de L. MAT. deben basarse en un recurso de operaciones concreto. Hacen referencia a este recurso de operaciones como el recurso de gestión de costes. También puede transferir categorías de coste y tiempos de operación desde el recurso de gestión de costes a la actividad. Una vez programada la operación, la estimación y el cálculo de L. MAT. se realizan mediante el recurso de operaciones que esté programado.




