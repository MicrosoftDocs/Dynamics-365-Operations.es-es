---
title: Planificación maestra para productos con vida útil limitada
description: Este artículo describe cómo configurar y utilizar las funciones de planificación que tienen en cuenta la vida útil de los productos perecederos.
author: t-benebo
ms.date: 08/10/2022
ms.topic: article
ms.search.form: ReqPlanSched, CustTable, EcoResProductDetailsExtended, InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-08-10
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 68a1ba2bfe90aaf0462917c405d483fa12bf8126
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428231"
---
# <a name="master-planning-for-products-with-limited-shelf-life"></a>Planificación maestra para productos con vida útil limitada

[!include [banner](../../includes/banner.md)]

La vida útil es la cantidad de tiempo que un producto se puede almacenar hasta que ya no se pueda usar o vender. Para los productos que tienen una vida útil limitada, probablemente utilizará una estrategia de almacén de primer vencimiento, primero en salir (FEFO), que prioriza el consumo y la venta de artículos en función de su vida útil restante. Esta estrategia de almacenamiento es relevante para alimentos, medicamentos y otros bienes que se caracterizan por un tiempo de almacenamiento corto. Según FEFO, los artículos en el almacén se almacenan como bienes en un estante de supermercado: los productos que tienen una vida útil prolongada se colocan en lo profundo de los estantes, de modo que los productos que tienen una vida útil restante más corta se envían primero.

## <a name="using-shelf-life-in-master-planning"></a>Usar la vida útil en la planificación maestra

Esta sección explica cómo la planificación maestra sugiere el suministro de artículos con vida útil.

Cuando ejecuta un plan maestro, genera pedidos planificados sugeridos (suministro) que satisfarán su demanda y también minimizarán los retrasos. Si su plan incluye artículos que tienen una vida útil limitada, los cálculos de planificación se vuelven más complejos, porque el plan no solo debe minimizar los retrasos, sino también utilizar el suministro existente antes de que caduque. El plan debe tratar de usar el suministro que esté más cerca de su fecha de vencimiento antes que el suministro que venza más tarde. Por lo tanto, la planificación maestra busca alcanzar los siguientes objetivos, en este orden:

1. Minimizar la suma de retrasos.
1. Maximizar la suma del suministro FEFO.
1. Minimizar la reposición de inventario.

En algunos casos, puede haber un conflicto entre los dos primeros objetivos y se debe tomar una decisión: ¿desea retrasar un envío o desea utilizar el suministro que vence más tarde en lugar del suministro que vence antes? Para resolver este conflicto durante la planificación maestra, el sistema prioriza la minimización de los retrasos sobre el uso del suministro que está a punto de caducar. En general, este tipo de conflicto se presenta cuando puede haber retrasos y cobertura por periodo. Por lo tanto, le recomendamos que utilice un período de cobertura que sea más corto que la vida útil de un artículo. Es poco probable que otros tipos de cobertura (como el requisito) encuentren este tipo de conflicto.

## <a name="set-up-shelf-life"></a>Configurar la vida útil

### <a name="configure-each-master-plan-to-consider-shelf-life"></a>Configure cada plan maestro para considerar la vida útil

De forma predeterminada, los planes maestros no tienen en cuenta la vida útil. Utilice el siguiente procedimiento para habilitar los cálculos de vida útil para cada plan maestro que los requiera.

1. Vaya a **Planificación maestra \> configurar \> planes \> Planes maestros**.
1. Seleccione un plan existente en el panel de lista o cree uno nuevo.
1. En la ficha desplegable **General**, configure la opción **Usar fechas de vida útil** en *Sí*.

### <a name="configure-tracking-dimension-groups-to-track-the-batch-dimension"></a>Configurar grupos de dimensiones de seguimiento para seguir la dimensión de lote

La vida útil de un artículo se puede rastrear solo si ese artículo se rastrea en la dimensión del lote. En otras palabras, la referencia del lote y las fechas requeridas deben registrarse al momento de la recepción o fabricación, ya través de cada transacción de inventario del artículo. Para administrar esta opción, configure uno o más grupos de dimensiones de seguimiento para realizar el seguimiento requerido y luego asigne los elementos relevantes a estos grupos según sea necesario.

Utilice el siguiente procedimiento para configurar un grupo de dimensiones de seguimiento para realizar un seguimiento de la dimensión del lote.

1. Vaya a **Gestión de información de producto \> Preparar \> Dimensión y grupos de variantes \> Seguimiento de grupos de dimensiones**.
1. Siga uno de estos pasos:

    - En el panel de acciones, seleccione **Nuevo** para crear un nuevo grupo de dimensiones de seguimiento. Escriba un nombre y una descripción y luego seleccione **Guardar** en el panel de acciones.
    - En el panel de lista, seleccione el grupo de dimensiones de seguimiento existente que desea configurar para realizar un seguimiento de la dimensión del lote.

1. En la ficha rápida **Dimensión de seguimiento**, en la fila **Número de lote**, seleccione las casillas de verificación en las columnas **Activo** e **Inventario físico**.

### <a name="set-up-shelf-life-for-a-product"></a>Configurar la vida útil para un producto

Utilice el siguiente procedimiento para configurar la vida útil de un producto.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Cree o abra el producto que desea configurar.
1. Para utilizar los ajustes de vida útil, en la ficha desplegable **General**, establezca el campo **Grupo de dimensiones de seguimiento** en un grupo de dimensiones de seguimiento configurado para realizar un seguimiento de la dimensión de lote. Puede configurar este campo solo cuando crea un producto por primera vez. No puede cambiar el valor de los productos existentes.
1. En la ficha desplegable **Administrar inventario**, configure los siguientes campos:

    - **Período de aviso de estantería en días** – Especifique el período (en días) por el cual verificar un lote de este producto para asegurarse de que sea apto para el consumo o la reventa. El valor de este campo se agrega a la *fecha de fabricación* de un lote para determinar su *fecha de aviso de estantería*. Puede configurar el sistema para generar pedidos de calidad cuando un lote se acerque a su fecha de recomendación.
    - **Período de vida útil en días** – Especifique el número de días antes de que caduque un lote de este producto. Este valor se suma a la *fecha de manufactura* para determinar la *fecha de caducidad*. El lote se considera inutilizable después de esta fecha.
    - **Mejor antes del período en días** – Especifique el período (en días) después del cual se considera que un lote de este producto aún se puede vender, pero ya no puede conservar algunas de sus propiedades originales. Este valor se suma a la *fecha de manufactura* para determinar la *fecha de caducidad*. Puede ejecutar informes para identificar el inventario que ya pasó su fecha de consumo preferente. 

### <a name="set-a-sellable-days-rule-for-each-customer"></a>Establecer una regla de días vendibles para cada cliente

*Días vendibles* La funcionalidad garantiza que los productos de un lote que caducará pronto no se envíen a los clientes. Además, garantiza que cuando los productos se envían a un cliente, aún quedará una cantidad adecuada de días vendibles después de la entrega.

Para utilizar la funcionalidad de días de venta, debe definir la cantidad de días de venta que se aplica a cada producto (o grupo de productos) para cada cliente. Debe completar manualmente este proceso, porque no hay una entidad de datos para ello.

Utilice el siguiente procedimiento para configurar los días de venta de cada producto para cada cliente.

1. Vaya a **Ventas y marketing \> Clientes \> Todos los clientes**.
1. Busque y seleccione el cliente que desea configurar.
1. En el panel Acciones, en la pestaña **Vender** del grupo **Configurar**, seleccione **Vender \> Días vendibles**.
1. En la página **Días vendibles para el cliente**, la cuadrícula enumera las reglas de días de venta existentes para cada producto o grupo de productos. Utilice los botones del Panel de acciones para agregar o editar filas en la cuadrícula según sea necesario. Se proporciona un **fltro** para ayudarlo a encontrar las filas existentes.
1. Para cada fila, establezca los siguientes campos:

    - **Código de artículo**: seleccione uno de los siguientes valores para especificar el ámbito de los artículos que se verán afectados.

        - *Tabla*: la fila se aplica a un artículo específico.
        - *Grupo* - La fila se aplica a un grupo de artículos específico.
        - *Todos*: la fila se aplica a todos los artículos.

    - **Relación de artículo**: si estableció el valor del campo **Código de artículo** en *Tabla*, seleccione un artículo específico. Si estableció el campo **Código de artículo** en *Grupo*, seleccione un grupo de artículos. Si establece *Todo* como **Código de artículo**, este campo no estará disponible.
    - **Días vendibles** – Introduzca el número mínimo de días que el cliente debe tener para vender productos coincidentes antes de que caduque el lote. El valor de días vendibles se basa en la fecha de recepción solicitada (o la fecha de recepción confirmada, si está definida) para los productos coincidentes en el pedido de ventas.
    - *(Otras dimensiones del producto)* – Para limitar aún más el alcance de una fila, especifique otros valores de dimensión (como **Tamaño** y **Color**) según sea necesario. Para controlar qué dimensiones adicionales se muestran en la cuadrícula, seleccione **Dimensiones de la pantalla** en el Panel de acciones.

### <a name="set-up-all-relevant-products-so-that-they-are-fefo-date-controlled"></a>Configure todos los productos relevantes para que estén controlados por fecha FEFO

Para que funcionen los días vendibles, cada artículo relevante debe pertenecer a un grupo de modelo de artículo donde la casilla **FEFO controlado por fecha** está seleccionada.

Utilice el siguiente procedimiento para configurar un grupo de modelos de artículos para que admita la funcionalidad de días vendibles.

1. Vaya a **Gestión del inventario \> Configurar \> Inventario \> Grupos de modelos de inventario**.
1. Seleccione un grupo existente en el panel de lista o cree una nueva directiva seleccionando **Nuevo** en el panel de acciones.
1. En la ficha desplegable **Directivas de inventario**, seleccione la casilla **Controlado por fecha FEFO**.
1. Establezca otros campos del grupo según sea necesario.

Utilice el siguiente procedimiento para ver o configurar el grupo de modelos de artículos al que pertenece un producto.

1. Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.
1. Abra el producto que desee inspeccionar o editar.
1. En la ficha desplegable **General**, establezca el campo **Grupo de modelo de artículo** en un grupo donde la casilla **FEFO controlado por fecha** está seleccionada.

## <a name="example-1-simple-fefo-10-day-period-zero-days-of-lead-time"></a>Ejemplo 1: FEFO simple, período de 10 días, cero días de tiempo de entrega

Este ejemplo muestra un ejemplo básico de vida útil, donde la vinculación entre las órdenes de suministro y la demanda se realiza para satisfacer los siguientes objetivos del sistema:

- Minimizar la suma de retrasos.
- Maximizar la suma del suministro FEFO.
- Minimizar la reposición de inventario.

El sistema tiene las siguientes parametrizaciones de artículo y plan maestro:

- **Código de cobertura (estrategia de reposición):** Período 
- **Período de cobertura:** 10 días (igual a la vida útil)
- **Vida útil:** 10 días
- **Días para ventas:** 0 días
- **Plazo en días:** 0 días
- **Días negativos:** 0 días
- **Tipo de orden planificada (configuración de orden predeterminada del artículo):** Orden de compra

Las siguientes órdenes de venta para el artículo existen en el sistema:

- **SO1:** Cantidad (cantidad) = 2, fecha de entrega solicitada = hoy + 1 día
- **SO2:** Cantidad = 1, fecha de entrega solicitada = hoy + 4 días
- **SO3:** Cantidad = 1, fecha de entrega solicitada = hoy + 5 días

Todas estas órdenes de venta crean demanda para el artículo.

El siguiente suministro existe para el artículo:

- **Inventario disponible:** Cantidad = 1, fecha de caducidad = hoy + 5 días
- **Orden de compra 1 (PO1):** Fecha de recepción = hoy + 2 días, cantidad = 1, fecha de vencimiento = hoy + 4 días

El sistema crea una lista de suministros que pueden cubrir esta demanda y ordena la lista por fecha de vencimiento (usando FEFO).

La planificación maestra crea la vinculación necesaria entre la oferta y la demanda. También crea cualquier demanda requerida basada en la lista de suministro (mediante FEFO) y considera la fecha de disponibilidad.

- SO1 se puede cumplir con la cantidad disponible, pero no se puede cumplir con PO1, porque la fecha de disponibilidad para PO1 es un día posterior a lo que requiere SO1. Por lo tanto, SO1 genera demanda por una unidad de bienes.
- SO2 puede ser cubierto por PO1, porque PO1 llegará a la hora solicitada y la fecha de vencimiento seguirá siendo válida. Por lo tanto, el requerimiento de SO2 está completamente cubierto por PO1.
- SO3 no está cubierto porque los recursos no están disponibles. Por lo tanto, SO3 genera demanda por una unidad de bienes.

Para cubrir todas las necesidades restantes, el sistema debe crear la siguiente orden de compra planificada:

- **PPO1:** Fecha de recepción = hoy, cantidad = 2, fecha de vencimiento = hoy + 10 días

En la tabla siguiente se resume el resultado.

| Demanda | Fijación |
|---|---|
| **SO1:** Fecha de entrega = hoy + 1 día, cantidad = 2 | <p>**Disponible:** Cantidad = 1, fecha de caducidad = hoy + 5 días</p><p>**PPO1:** Fecha de recepción = hoy, cantidad = 1, fecha de vencimiento = hoy + 10 días</p> |
| **SO2:** Fecha de entrega = hoy + 4 días, cantidad = 1 | **PO1:** Fecha de recepción = hoy + 2 días, 1 cant., fecha de vencimiento = hoy + 4 días |
| **SO3:** Fecha de entrega = hoy + 5 días, cantidad = 1 | **PPO1:** Fecha de recepción = hoy, cantidad = 2, fecha de vencimiento = hoy + 10 días |

La ilustración siguiente muestra la escala de tiempo para este ejemplo.

![Ejemplo 1: FEFO simple, período de 10 días, cero días de tiempo de entrega.](media/fefo-example-1.png "Ejemplo 1: FEFO simple, período de 10 días, cero días de tiempo de entrega")

## <a name="example-2-simple-fefo-requirement-three-days-of-lead-time"></a>Ejemplo 2: FEFO simple, requisito, tres días de plazo

Este ejemplo muestra cómo el intento del sistema de minimizar los retrasos a veces puede provocar que se produzcan pedidos excesivos.

El sistema tiene las siguientes parametrizaciones de artículo y plan maestro:

- **Código de cobertura (estrategia de reposición):** requisito
- **Vida útil:** 10 días
- **Días para ventas:** 0 días
- **Tiempo de espera:** Establecido por los siguientes acuerdos comerciales de proveedores:

    - **Acuerdo comercial 1:** Si cant. = 1, plazo = 4
    - **Acuerdo comercial 2:** Si cant. = 2, plazo = 3

- **Días negativos:** 0 días
- **Tipo de orden planificada (configuración de orden predeterminada del artículo):** Orden de compra

La siguiente orden de venta existe en el sistema:

- **SO1:** Cantidad = 2, fecha de entrega solicitada = hoy + 3 días

Esta demanda se cubre con la oferta existente y una orden de compra confirmada:

- **Inventario disponible:** Disponible = hoy, cant. = 1, fecha de caducidad = hoy + 2 días
- **PO1:** Fecha de recepción = hoy + 3 días, cant. = 1, fecha de vencimiento = hoy + 4 días

SO1 no se puede cumplir con el inventario disponible porque la fecha de vencimiento del inventario es anterior a la fecha de envío. PO1 puede cubrir el requerimiento de SO1 con una cantidad de solo 1. Por lo tanto, SO1 genera demanda por una unidad de bienes. Para cubrir este requerimiento, el sistema crea una orden de compra planificada (PPO1).

El sistema tiene dos acuerdos comerciales (uno para cant. = 1, plazo de entrega = 4 días y otro para cant. = 2, plazo de entrega = 3 días). Por lo tanto, el sistema intenta minimizar los retrasos creando una orden de compra planificada (PPO1) que cumpla con el segundo acuerdo comercial. El resultado es una sobreentrega (cantidad = 2, fecha de vencimiento = hoy + 10 días).

En la tabla siguiente se resume el resultado.

| Demanda | Fijación |
|---|---|
| **SO1:** Fecha de entrega = hoy + 3 días, cantidad = 2 | <p>**PO1:** Fecha de recepción = hoy + 3 días, cant. = 1, fecha de vencimiento = hoy + 4 días</p><p>**PPO1:** Fecha de recepción = hoy + 3 días, cant. = 1, fecha de vencimiento = hoy + 10 días</p> |

La ilustración siguiente muestra la escala de tiempo para este ejemplo.

![Ejemplo 2: FEFO simple, requisito, tres días de plazo.](media/fefo-example-2.png "Ejemplo 2: FEFO simple, requisito, tres días de plazo")

## <a name="example-3-simple-fefo-requirement-three-days-of-lead-time-five-sellable-days"></a>Ejemplo 3: FEFO simple, requisito, tres días de plazo, cinco días vendibles

Este ejemplo muestra cómo funciona la vida útil cuando se agregan días vendibles para un artículo.

El sistema tiene las siguientes parametrizaciones de artículo y plan maestro:

- **Código de cobertura (estrategia de reposición):** requisito
- **Vida útil:** 10 días
- **Días para ventas:** 5 días
- **Plazo en días:** 5 días
- **Días negativos:** 0 días
- **Tipo de orden planificada (configuración de orden predeterminada del artículo):** Orden de compra

Las siguientes órdenes de venta existen en el sistema:

- **SO1:** Cantidad = 2, fecha de entrega solicitada = hoy + 2 días
- **SO2:** Cantidad = 1, fecha de entrega solicitada = hoy + 3 días
- **SO3:** Cantidad = 1, fecha de entrega solicitada = hoy + 5 días

Esta demanda se puede cubrir con el suministro existente y una orden de compra confirmada:

- **Inventario disponible:** Disponible = hoy, cant. = 1, fecha de caducidad = Hoy + 6 días
- **PO1:** Fecha de recepción = hoy + 2 días, cant. = 3, fecha de vencimiento = hoy + 10 días

El sistema crea una lista de candidatos de trazabilidad, según la lista de suministro (FEFO) y las fechas de disponibilidad. Por lo tanto, SO1 no puede cumplirse con el inventario disponible, porque ese inventario vence antes del final de los días vendibles que requiere el cliente (fecha de recepción solicitada + 5 días). PO1 puede cubrir el requerimiento de SO1 con dos unidades y el requerimiento de SO2 con una unidad. Por lo tanto, solo SO3 todavía tiene demanda descubierta para una unidad de bienes. Para cubrir este requerimiento, el sistema crea la siguiente orden de compra planificada:

- **PP01:** Fecha de recepción = hoy + 5 días, cant. = 1, fecha de vencimiento = hoy + 10 días

En la tabla siguiente se resume el resultado.

| Demanda | Fijación |
|---|---|
| **SO1:** Fecha de entrega = hoy + 2 días, cantidad = 2 | **PO1:** Fecha de recepción = hoy + 2 días, cant. = 2, fecha de vencimiento = hoy + 10 días |
| **SO2:** Fecha de entrega = hoy + 3 días, cantidad = 1 | **PO1:** Fecha de recepción = hoy + 2 días, cant. = 1, fecha de vencimiento = hoy + 10 días |
| **SO3:** Fecha de entrega = hoy + 5 días, cantidad = 1 | **PPO1:** Fecha de recepción = hoy + 5 días, cant. = 1, fecha de vencimiento = hoy + 10 días |

La ilustración siguiente muestra la escala de tiempo para este ejemplo.

![Ejemplo 3: FEFO simple, requisito, tres días de plazo, cinco días vendibles.](media/fefo-example-3.png "Ejemplo 3: FEFO simple, requisito, tres días de plazo, cinco días vendibles")

## <a name="example-4-simple-fefo-period-lead-time-depends-on-the-quantity"></a>Ejemplo 4: FEFO simple, período, el tiempo de entrega depende de la cantidad

Este ejemplo muestra cómo el intento del sistema de minimizar los retrasos a veces puede provocar que se produzcan pedidos excesivos.

El sistema tiene las siguientes parametrizaciones de artículo y plan maestro:

- **Código de cobertura (estrategia de reposición):** Período
- **Período de cobertura:** 10 días (igual a la vida útil)
- **Vida útil:** 10 días
- **Días para ventas:** 0 días
- **Tiempo de espera:** Establecido por los siguientes acuerdos comerciales de proveedores:

    - **Acuerdo comercial 1:** Si cant. = 1, plazo = 5
    - **Acuerdo comercial 2:** Si cant. = 2, plazo = 0

- **Días negativos:** 0 días
- **Tipo de orden planificada (configuración de orden predeterminada del artículo):** Orden de compra

Las siguientes órdenes de venta existen en el sistema:

- **SO1:** Cantidad = 1, fecha de entrega solicitada = hoy
- **SO2:** Cantidad = 1, fecha de entrega solicitada = hoy + 6 días

Esta demanda puede ser parcialmente cubierta por la oferta existente de las siguientes órdenes de compra confirmadas:

- **PO1:** Fecha de recepción = hoy + 1 días, cant. = 1, fecha de vencimiento = hoy + 2 días
- **PO2:** Fecha de recepción = hoy + 3 días, cant. = 1, fecha de vencimiento = hoy + 7 días

El sistema tiene dos acuerdos comerciales (uno para cant. = 1, plazo de entrega = 5 días y otro para cant. = 2, plazo de entrega = 0 días). Por lo tanto, el sistema intenta minimizar el retraso creando la siguiente orden de compra planificada que cumpla con el segundo acuerdo comercial:

- **PP01:** Fecha de recepción = hoy, cantidad = 2, fecha de vencimiento = hoy + 10 días

SO1 estará cubierto por una unidad de PPO1. SO2 estará cubierto por PO2, porque PO2 expira antes que PPO1.

En la tabla siguiente se resume el resultado.

| Demanda | Fijación |
|---|---|
| **SO1:** Fecha de entrega = hoy. cant. = 1 | **PPO1:** Fecha de recepción = hoy, cantidad = 1, fecha de vencimiento = hoy + 10 días |
| **SO2:** Fecha de entrega = hoy + 6 días, cantidad = 1 | **PO2:** Fecha de recepción = hoy + 3 días, cant. = 1, fecha de vencimiento = hoy + 7 días |

> [!NOTE]
> PO1 no se utiliza porque llegará demasiado tarde para S01 y caducará antes de que se entregue S02. PPO1 ha pedido una unidad en exceso para permitir que el tiempo de entrega sea 0 (cero), por acuerdo comercial 2.

La ilustración siguiente muestra la escala de tiempo para este ejemplo.

![Ejemplo 4: FEFO simple, período, el tiempo de entrega depende de la cantidad.](media/fefo-example-4.png "Ejemplo 4: FEFO simple, período, el tiempo de entrega depende de la cantidad")

## <a name="example-5-simple-fefo-requirement-10-negative-days"></a>Ejemplo 5: FEFO simple, requisito, 10 días negativos

Este ejemplo muestra cómo funciona la vida útil cuando se agrega un gran número de días negativos para un artículo. Los días negativos on el número de días que está dispuesto a esperar antes de que pida un nuevo reabastecimiento de un artículo que tiene inventario negativo. El sistema no crea suministro a menos que se supere el número de días negativos.

El sistema tiene las siguientes parametrizaciones de artículo y plan maestro:

- **Código de cobertura (estrategia de reposición):** requisito
- **Plazo en días:** 0 días
- **Días negativos:** 10 días
- **Tipo de orden planificada (configuración de orden predeterminada del artículo):** Orden de compra

La siguiente orden de venta existe en el sistema:

- **SO1:** Cantidad = 1, fecha de entrega solicitada = hoy

Esta demanda puede ser cubierta por la oferta existente de la siguiente orden de compra confirmadas:

- **PO1:** Fecha de recepción = hoy + 3 días, cant. = 1, fecha de vencimiento = hoy + 5 días

Debido a que el sistema está configurado para permitir 10 días negativos, cubre la demanda de SO1 mediante el uso de PO1, aunque el resultado será un retraso de tres días porque SO1 crea un inventario negativo hasta que llega PO1. No se crea ningún pedido de compra planificado, aunque el tiempo de entrega es 0 (cero) y la creación de un pedido de compra planificado reduciría los retrasos.

En la tabla siguiente se resume el resultado.

| Demanda | Fijación |
|---|---|
| **SO1:** Fecha de entrega = hoy. cant. = 1 | **PO1:** Fecha de recepción = hoy + 3 días, cant. = 1, fecha de vencimiento = hoy + 5 días |

La ilustración siguiente muestra la escala de tiempo para este ejemplo.

![Ejemplo 5: FEFO simple, requisito, 10 días negativos.](media/fefo-example-5.png "Ejemplo 5: FEFO simple, requisito, 10 días negativos")

## <a name="example-6-simple-fefo-requirement-five-negative-days"></a>Ejemplo 6: FEFO simple, requisito, cinco días negativos

Este ejemplo muestra cómo funciona la vida útil cuando el número de días negativos para un artículo es menor que su período de vida útil.

El sistema tiene las siguientes parametrizaciones de artículo y plan maestro:

- **Código de cobertura (estrategia de reposición):** requisito
- **Días para ventas:** 0 días
- **Plazo en días:** 0 días
- **Días negativos:** 5 días
- **Tipo de orden planificada (configuración de orden predeterminada del artículo):** Orden de compra

La siguiente orden de venta existe en el sistema:

- **SO1:** Cantidad = 2, fecha de entrega solicitada = hoy

Esta demanda puede ser cubierta por la oferta existente de las siguientes órdenes de compra confirmadas:

- **PO1:** Fecha de recepción = hoy, cantidad = 1, fecha de vencimiento = hoy + 1 día
- **PO2:** Fecha de recepción = hoy + 2 días, cant. = 1, fecha de vencimiento = hoy + 3 días

Sin embargo, el sistema debe respetar la restricción de que los artículos enviados no pueden estar vencidos en el momento del envío. Por lo tanto, PO2 y PO1 no se pueden usar para SO1, porque PO1 caduca antes de que llegue PO2. El sistema crea la siguiente orden de compra planificada para finalizar la cobertura de la demanda para SO1:

- **PPO1:** Fecha de recepción = hoy, cantidad = 1, fecha de vencimiento = hoy + 10 días

El sistema puede aprovechar los cinco días negativos y utilizar PO2 y PPO1 para cubrir SO1. Sin embargo, este enfoque hará que la entrega se retrase hasta que llegue la PO2 y, mientras tanto, la PO1 caducará. Por lo tanto, el sistema cubre SO1 usando PPO1 y PO1.

En la tabla siguiente se resume el resultado.

| Demanda | Fijación |
|---|---|
| **SO1:** Fecha de entrega = hoy. cant. = 2 | <p>**PO1:** Fecha de recepción = hoy, cantidad = 1, fecha de vencimiento = hoy + 1 día</p><p>**PPO1:** Fecha de recepción = hoy, cantidad = 1, fecha de vencimiento = hoy + 10 días</p> |

La ilustración siguiente muestra la escala de tiempo para este ejemplo.

![Ejemplo 6: FEFO simple, requisito, cinco días negativos.](media/fefo-example-6.png "Ejemplo 6: FEFO simple, requisito, cinco días negativos")
