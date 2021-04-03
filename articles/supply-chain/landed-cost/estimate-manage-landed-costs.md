---
title: Estimar y administrar los costos descargados
description: El sistema utiliza su configuración de costo automático para determinar una estimación de su costo de entrega. Este tema explica cómo puede definir varios escenarios para ofrecer una estimación más precisa.
author: sherry-zheng
manager: tfehr
ms.date: 01/26/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMCostTemplateTable, ITM CostEstimateDialog, ITMCostEstimateTable, SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-26
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: cbd652f2b29f7a78ad9e4e1d3dda4a3ef8a9f3f3
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501279"
---
# <a name="estimate-and-manage-landed-costs"></a>Estimar y administrar los costos descargados

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

El sistema utiliza su [configuración de costo automático](auto-cost-setup.md) para determinar una estimación de su costo descargado. Además, puede definir varios escenarios para ofrecer una estimación más precisa. Estos escenarios se almacenan. Por lo tanto, puede revisarlos más tarde y compararlos con los datos reales de un informe. También puede actualizar el precio del artículo.

## <a name="set-up-cost-estimates"></a>Configurar estimaciones de costes

### <a name="set-up-cost-templates"></a>Configurar plantillas de coste

Las plantillas de costos establecen configuraciones predeterminadas que los usuarios que obtienen la estimación no necesariamente conocerán. Las plantillas pueden ayudar a reducir la complejidad en el proceso de estimación al minimizar las selecciones que los usuarios deben especificar para obtener una estimación precisa. Si está utilizando el modelo de costo estándar, puede usar plantillas de costos mientras configura el costo de los bienes.

Para configurar sus plantillas de costos, vaya a **Coste de aterrizaje \> Configuración de costos \> Plantillas de costos**. Sobre la página **Plantillas de costos**, el panel de lista de la izquierda muestra todas las plantillas de costos actuales. Puede utilizar los botones del Panel de acciones para crear, eliminar y editar plantillas.

En la tabla siguiente se describen los campos disponibles para cada plantilla.

| Campo | Descripción |
|---|---|
| Plantilla de coste | Permite introducir un nombre único para la plantilla de costes. El nombre generalmente describe el factor o el multiplicador de costos de la plantilla. |
| Descripción | Especificar una descripción de la plantilla de coste. |
| Empresa de transporte | Seleccione la empresa de envío que debe aplicarse cuando se utiliza la plantilla. |
| Modo de entrega | Seleccione el modo de entrega, como marítimo o aéreo, que se debe aplicar cuando se utiliza la plantilla. Este campo ayuda a determinar los costos de automóviles asociados con los bienes en una estimación de costos. |
| Tipo de contenedor de envío | Seleccione el tipo de contenedor de envío que debe aplicarse cuando se utiliza la plantilla. Este campo ayuda a determinar los costos de automóviles asociados con los bienes en una estimación de costos. |
| Agente de aduanas | El agente de aduana (proveedor) que debe aplicarse cuando se utiliza la plantilla. Este campo ayuda a determinar los costos de automóviles asociados con la estimación de costos. |
| Factor | Ingrese el multiplicador (porcentaje) que se debe aplicar automáticamente a la estimación de costos cuando se utiliza la plantilla. Por ejemplo, para agregar un 10 por ciento al costo estimado calculado, ingrese *1,10*. |

### <a name="create-a-cost-estimate"></a>Crear una estimación de coste

Utilizar el cuadro de diálogo **Costo estimado** para generar una nueva estimación de costos basada en una plantilla de costos seleccionada, un conjunto seleccionado de elementos y otros detalles de un viaje. Luego, estos ajustes se utilizan para determinar los costos de desembarque estimados de los bienes. Estas estimaciones de costos se utilizan principalmente para trabajar con elementos de costo estándar. Al agregar los costos estimados de desembarque al costo estándar de los bienes en el inventario, debe experimentar transacciones de variación más pequeña cuando los bienes se agregan a un viaje, porque el costo estándar reflejará las estimaciones de esos costos de desembarque.

Para abrir el cuadro de diálogo **Costo estimado**, vaya a **Coste de aterrizaje \> Tareas periódicas \> Costo estimado**. Luego, configure los campos que se describen en las siguientes subsecciones. Finalmente, seleccione **Aceptar** para crear la nueva estimación. La página **Costo estimado** (**Coste de aterrizaje \> Consultas \> Coste estimado**) luego aparece y muestra su nueva estimación, como se describe más adelante en este tema.

### <a name="settings-on-the-parameters-tab"></a>Configuración en la pestaña Parámetros

La siguiente tabla describe los campos que están disponibles en la pestaña **Parámetros** del cuadro de diálogo **Estimación de coste**.


| Campo | Descripción |
|---|---|
| Plantilla de coste | Seleccionar una plantilla de coste. La configuración que está asociada con la plantilla seleccionada se usará para determinar los costos automáticos que se aplican. |
| Fecha de estimación | De forma predeterminada, este campo se establece en la fecha de hoy, pero puede cambiar el valor. La fecha especificada se utilizará para seleccionar los precios de venta, los precios de compra, los costos del automóvil y la tasa de cambio apropiados si se usa una tasa de envío. |
| Medida | Los costos pueden depender de una medición. Por ejemplo, cuando se utiliza transporte aéreo, es posible que se apliquen precios volumétricos. Si el costo depende de una medición, ingrese el valor de esa medición. De lo contrario, le recomendamos que establezca este campo en *1*, a menos que esté seguro de que no se produce ningún reparto mediante el uso de la medición. Especificar un valor decimal. La unidad es la que se define en el registro de costo automático aplicable. |
| Plantilla de recorrido | Seleccione una [plantilla de recorrido](multi-leg-journey-setup.md). Este campo se utiliza para determinar los costos de auto correctos que se deben aplicar. |
| Puerto de origen | El puerto desde el que se enviarán los artículos. Este campo se establece en función de la plantilla de viaje seleccionada. |
| Puerto de destino | El puerto al que se enviarán los artículos. Este campo se establece en función de la plantilla de viaje seleccionada. |
| Divisa | Seleccione la moneda en la que se comprarán los artículos. |
| Contenedores | Si normalmente se utilizan varios contenedores, especifique el número de contenedores. Luego, el sistema utilizará los costos de varios contenedores cuando calcule los costos. |
| Folios | Si normalmente se utilizan varias publicaciones, especifique la cantidad. (La cantidad suele ser *1*). |
| Sitio | Especifique el lugar donde se entregarán las mercancías. |

### <a name="settings-on-the-items-tab"></a>Configuración en la pestaña Artículos

En la pestaña **Artículos**, puede agregar tantos elementos al presupuesto como necesite. Utilice la barra de herramientas para agregar elementos a la cuadrícula o eliminar elementos. Seleccione **Inventario \> Dimensiones de la pantalla** en la barra de herramientas para abrir un cuadro de diálogo donde puede agregar columnas de dimensión a la cuadrícula o eliminar columnas.

En la tabla siguiente se describen los campos disponibles para cada artículo.

| Campo | Descripción |
|---|---|
| Número de artículo | Seleccione el artículo para determinar el precio. (Si el artículo aún no existe en el sistema, cree un artículo ficticio, adjúntelo opcionalmente a un grupo de costo de artículo de viaje y luego deje el precio en blanco o cree o cambie el precio). |
| Cuenta del proveedor | Seleccione el proveedor que se utilizará para la estimación de este artículo. Si se asigna un proveedor predeterminado al artículo, este campo se configura automáticamente. |
| Cantidad | Seleccione la cantidad que adquirirá. |
| Precio de coste | El sistema usa sus reglas de precios para encontrar un precio inicial, pero puede anular ese precio si es necesario. |
| Precio de venta | Introduzca el precio de venta esperado de los artículos. |
| Medida | Introduzca un valor decimal para la medición de la mercancía. La unidad es la que está configurada para el producto comercializado correspondiente. |
| Actualizar peso o volumen de artículo | Seleccione esta casilla de verificación para actualizar la medición de peso o volumen del producto lanzado para que coincida con el valor **Medición** que se ingresa para esta fila. |
| (Otras dimensiones) | Según las dimensiones que haya seleccionado para mostrar, es posible que vea columnas adicionales de información sobre cada elemento. |

Para ver o ajustar los detalles de volumen y / o peso de un artículo, seleccione el artículo en la cuadrícula y luego use los campos en la parte inferior de la página.

## <a name="manage-estimated-costs"></a>Gestionar costes estimados

Para ver y editar las estimaciones de costos que ha creado, vaya a **Coste de aterrizaje \> Consultas \> Coste estimado**. Sobre la página **Estimaciones de costos**, el panel de lista de la izquierda muestra todas las estimaciones de costos actuales. Puede utilizar los botones del Panel de acciones para trabajar con una estimación seleccionada. Tenga en cuenta que no puede crear una nueva estimación de costos a partir de la página **Coste estimado**. En su lugar, use el cuadro de diálogo **Costo estimado** (**Coste de aterrizaje \> Tareas periódicas \> Costo estimado**), como se describió anteriormente en este tema.

La página **Coste estimado** muestra cómo se derivó cada costo estimado. También muestra el costo de entrega estimado para cada artículo. Puede modificar una estimación de costos cambiando el precio de costo y / o la moneda asociada con los diversos bienes. También puede modificar los costos de viaje asociados tanto a nivel de viaje como a nivel de contenedor. Cuando usa esta página para modificar los costos, se le solicita que vuelva a calcular los costos estimados para los artículos en la estimación de costos. Cuando esté listo, puede usar las estimaciones para actualizar el precio de costo de los artículos en la plantilla de costo.

### <a name="information-on-the-header"></a>Información en el encabezado

La parte superior de la página **Coste estimado** muestra la configuración que se utilizó para generar la estimación de costo seleccionada, como se describe en la sección anterior. 

### <a name="settings-and-buttons-on-the-lines-fasttab"></a>Configuración y botones en la ficha desplegable Líneas

La ficha desplegable **Líneas** enumera cada elemento que se incluye en la estimación actual. En la tabla siguiente se describe el campo disponible para cada fila.

| Campo | Descripción |
|---|---|
| Cuenta del proveedor | La cuenta de proveedor asociada al artículo. |
| Número de artículo | Número de artículo. |
| Cantidad | La cantidad de artículos que se utilizan para determinar el costo. |
| Precio de coste | El precio de costo según el acuerdo comercial. Este valor se muestra en la divisa local. |
| Medida | La medida individual. La unidad es la que está definida para el producto comercializado correspondiente. |
| Coste descargado estimado | El costo de aterrizaje estimado para la cantidad total. |
| Por unidad | El costo de aterrizaje estimado dividido entre la cantidad. |
| (Otras dimensiones) | Según las dimensiones que haya seleccionado para mostrar, es posible que vea columnas adicionales de información sobre cada elemento. |

La tabla siguiente describe los botones disponibles en la barra de herramientas de la ficha desplegable **Líneas**.

| Botón | Descripción |
|---|---|
| Agregar | Agregue artículos a la estimación de costos. Después de agregar elementos, debe seleccionar **Recalcular** en el Panel de acciones. |
| Eliminar | Elimine elementos del cálculo de costos. Después de quitar elementos, debe seleccionar **Recalcular** en el Panel de acciones. |
| Costes de viaje | Abra una página donde puede ver y editar varios tipos de costos de viaje para el artículo. |
| Inventario \> Mostrar dimensiones | Abra un cuadro de diálogo donde puede agregar columnas de dimensión a la cuadrícula o eliminar columnas. |

### <a name="settings-on-the-general-fasttab"></a>Configuración en la ficha desplegable General

La ficha desplegable **General** muestra detalles sobre el elemento que está seleccionado actualmente en la ficha desplegable **Líneas**. Gran parte de esta información se repite de la ficha desplegable **Líneas** y se puede editar en cualquier lugar. Sin embargo, también hay detalles adicionales disponibles aquí. Los valores de los campos adicionales se basan en la configuración del producto liberado correspondiente.

### <a name="settings-on-the-dimension-fasttab"></a>Configuración en la ficha desplegable Dimensión

La ficha desplegable **Dimensión** muestra los valores de todas las dimensiones de inventario disponibles para el artículo seleccionado en la ficha desplegable **Líneas**, independientemente de las dimensiones que haya elegido mostrar allí. Los valores que se muestran aquí provienen de la plantilla de estimación de costos correspondiente. Son opcionales en la plantilla de estimación de costos.

### <a name="buttons-on-the-action-pane"></a>Botones en el panel de acciones

Puede utilizar los botones del panel de acciones de la página **Coste estimado** para trabajar con la estimación de costos seleccionada. En la tabla siguiente se describen los botones disponibles.

| Acción | Descripción |
|---|---|
| Consulta de coste | Ver todos los costos del viaje. Puede ver los costos a nivel del artículo individual según sea necesario. |
| Actualizar coste estándar | <p>Actualice el costo estándar utilizando la versión de cálculo de costos predeterminada que se define en la página **Parámetros de costo aterrizado**. Puede anular esta versión.</p><p>**Nota:** Si un artículo tiene varias dimensiones de artículo (por ejemplo, varios tamaños, colores y configuraciones), pero estas dimensiones no se han seleccionado para la estimación, el sistema creará un precio pendiente para cada combinación.</p><p>**Importante:** El desglose de precios se crea y se utiliza para determinar la variación de costo estándar por costo de entrega.</p> |
| Costes de viaje | Vea y edite los costos del viaje para todas las mercancías del envío. |
| Volver a calcular | Actualice los costos estimados de aterrizaje después de que los costos del viaje se actualicen, agreguen o eliminen. |
| Bloquear | Bloquee el registro de estimación de costos para que no se puedan realizar más cambios. |

## <a name="item-cost-price-update"></a>Actualizar precio de coste de artículo

La tarea periódica **Actualización del precio de costo del artículo** actualiza todas las estimaciones de costos que coinciden con los filtros que estableció al ejecutar la tarea. El efecto es similar al efecto de seleccionar **Actualizar el costo estándar** en el Panel de acciones para obtener una sola estimación. Sin embargo, en este caso, la actualización se aplica a todas las estimaciones coincidentes.

Para ejecutar la tarea periódica, siga estos pasos.

1. Vaya a **Coste de aterrizaje \> Tareas periódicas \> Actualización del precio de costo del artículo**.
1. En el cuadro de diálogo **Actualizar el precio de costo de la estimación**, configure los siguientes campos según sea necesario para limitar el alcance de la actualización:

    - **Versión** - Actualizar solo las estimaciones que utilizan la versión de cálculo de costes especificada.
    - **Sitio** - Actualizar solo las estimaciones que utilizan el sitio especificado.
    - **Plantilla de costes** - Actualizar solo las estimaciones que utilizan la plantilla especificada.
    - **Puerto de destino** - Actualizar solo las estimaciones que utilizan el puerto de destino especificado.
    - **Fecha estimada** - Actualizar solo estimaciones que tengan la fecha especificada.

1. Configure las opciones en la ficha desplegable **Registros para incluir** y **Ejecutar en segundo plano** como de costumbre para tareas periódicas.
1. Seleccione **Aceptar** para ejecutar la tarea.

> [!NOTE]
> Esta tarea periódica solo se ejecutará correctamente siempre que se disponga de la siguiente información:
>
> - Cada producto relevante debe tener valores de **Profundidad bruta**, **Ancho bruto** y **Altura bruta** definidos.
> - Cada proveedor relevante debe tener un valor de **Puerto de destino** definido.
