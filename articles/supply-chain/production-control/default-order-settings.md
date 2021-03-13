---
title: Configuración predeterminada de pedidos para dimensiones y variantes de producto.
description: Los configuración de pedido predeterminada define el sitio y el almacén de dónde se originan o almacenan los artículos, las cantidades mínimas, máximas, múltiples y estándar que se usarán en la gestión de comercio o de inventario, los plazos, el indicador de detención y el método prometedor del pedido.
author: t-benebo
manager: tfehr
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventItemOrderSetup, InventItemIdLookupByDefaultOrderSetting, EcoResProductReleasedStoppedAllChartPart, UnitTestPartitions
audience: Application User
ms.reviewer: kamaybac
ms.custom: 223084
ms.assetid: fbfbcd7b-dc75-44ab-bffc-8bad576804a4
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 2202b6b50d4b4b675759275379023a182b01af17
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007275"
---
# <a name="default-order-settings-for-dimensions-and-product-variants"></a>Configuración predeterminada de pedidos para dimensiones y variantes de producto

[!include [banner](../includes/banner.md)]

Los configuración de pedido predeterminada en Dynamics 365 Supply Chain Management define el sitio y el almacén de dónde se originan o almacenan los artículos, las cantidades mínimas, máximas, múltiples y estándar que se usarán en la gestión de comercio o de inventario, los plazos, el indicador de detención y el método prometedor del pedido. La configuración de pedido predeterminada se usa al crear pedidos de compra, pedidos de ventas, pedidos de transferencia, diarios de inventario y para generar pedidos planificados mediante planificación principal. La configuración de pedido predeterminada puede ser específica del artículo, del sitio, de la variante del producto o de la dimensión de producto.

Para definir la configuración de pedido predeterminada para un producto, siga estos pasos.

1. Vaya a **Gestión de información de productos** &gt; **Productos** &gt; **Productos emitidos**.
1. Seleccione el producto correspondiente en la cuadrícula.
1. En el panel de acciones, siga uno de estos pasos para abrir la página **Configuración de pedido predeterminada** del producto seleccionado:

    - En la pestaña **Plan**, en el grupo **Configuración de pedido**, seleccione **Configuración de pedido predeterminada**.
    - En la pestaña **Administrar inventario**, en el grupo **Configuración de pedido**, seleccione **Configuración de pedido predeterminada**.

1. Configure las opciones de la manera descrita en el resto de este tema.

## <a name="default-order-settings"></a>Configuración predeterminada de pedido

Hay tres tipos de configuración predeterminada de pedido para compras, ventas e inventario. Los valores de pedido predeterminados para las compras se usan al crear:

- Líneas de pedido de compra
- Líneas del acuerdo de compra
- Líneas de solicitud de presupuesto
- Líneas de solicitud de compra
- Líneas de reabastecimiento de consignación (parcialmente admitidas, ver nota)
- Pedidos de compra planificados

> [!NOTE]
> Para las líneas de orden de reabastecimiento de consignación, la única configuración de la ficha desplegable **Pedido de compra** de la página **Configuración de pedido predeterminado** que se aplica es la del campo **Sitio por defecto**, el campo **Almacén predeterminado** y la casilla **Detenido**.

Los valores de pedido predeterminados para las ventas se usan al crear:

- Líneas de pedido de ventas
- Líneas del acuerdo de ventas
- Líneas de presupuesto de ventas
- Líneas de pedido de devolución y líneas de sustitución de artículo
- Líneas de previsión de la demanda

Los valores predeterminados del pedido de ventas también se aplican al crear:

- Requisitos de artículos del proyecto
- Requisitos de los artículos de pedido de servicio

Los valores de pedido predeterminados para el inventario se usan al crear:

- Diarios de inventario
- Transferir pedidos
- Pedidos de transferencia planificados

Los valores predeterminados del pedido de inventario también se aplican al crear:

- Órdenes de cuarentena
- Pedidos de calidad
- Pedidos de producción
- Líneas de L. MAT
- Pedidos de producción planificados

## <a name="full-definition-of-a-released-product"></a>Definición completa de un producto emitido

Al crear una transacción, debe especificar la definición completa de un producto emitido en la línea para que Supply Chain Management intente identificar la configuración de pedido predeterminada. En la definición completa del producto emitido, el número de artículo y todas las dimensiones de producto activo, como la configuración, tamaño, estilo, versión y color, se especifican en la transacción. Por ejemplo, si crea manualmente una línea de pedido de compra para una variante del producto emitido, debe especificar todas las dimensiones de producto requeridas para que el sitio, el almacén, las cantidades y el plazo aparezcan de forma predeterminada en la línea de pedido. 

No se aplicarán todos los parámetros de la configuración de pedido predeterminada al crear líneas de pedido o líneas de diario. Las cantidades y los plazos se muestran de forma predeterminada únicamente cuando son adecuados. Por ejemplo, al realizar el recuento de una línea de diario, solo el sitio y el almacén mostrarán de forma predeterminada cuándo se ha creado la línea. Por este motivo, al crear la línea o registrar el diario, no se realizan faltas de pago de la cantidad o cheques en múltiplos y mínimos. 

El sistema intenta siempre encontrar un sitio y un almacén predeterminado cuando se crea un pedido o una línea de diario. El sitio no siempre aparece de forma predeterminada desde la configuración de pedido. Por ejemplo, al crear un pedido de ventas o un pedido de compra, el sitio desde la cabecera del pedido se usa automáticamente en las líneas de pedido. Al crear una línea de L.M., se usa el sitio de la cabecera de L.M. Una vez se determina el sitio, se usará para buscar las opciones de pedido específicas del sitio que se pueden utilizar como valor predeterminado para el almacén. 

El tipo de pedido predeterminado, la compra y los plazos de inventario se pueden sobrescribir por las reglas de cobertura en la página **Cobertura de artículos**. Aunque la configuración de pedido predeterminada no permiten la distinción entre la producción y el plazo de transferencia, las reglas de cobertura de artículos la permiten. Sin embargo, la Planificación maestra (MRP) solo usará la configuración de cobertura del artículo al crear la producción y los pedidos de transferencia planificados y no se aplicará al crear manualmente pedidos de producción y de transferencia. 

## <a name="default-order-settings-rules"></a>Reglas de la configuración predeterminada de pedido

Puede definir la configuración de pedido predeterminada y cualquier número de reglas de configuración de pedido predeterminadas que se aplicarán solo en determinadas condiciones, como el sitio, una dimensión específica de producto o una combinación de las dimensiones del producto. No se puede definir la configuración específica de pedido del almacén.

### <a name="rank-in-default-order-settings"></a>Clasificar la configuración predeterminada de pedido

Las reglas de configuración de pedido predeterminada tienen categorías. Cuanto mayor sea la categoría, más importante es la regla, lo que significa que tendrá una prioridad más alta y se usará antes de las reglas de categorías inferiores. La configuración general de pedido predeterminada tienen la categoría cero, que no se puede modificar. Sólo puede haber una rregla con categoría cero. Las reglas pueden tener la misma categoría, siempre que las dimensiones que aplican sean diferentes. Esto resulta útil para modelar la configuración de pedido específica del sitio. Cuando se crea una nueva regla de configuración de pedido predeterminada, los parámetros de los valores de pedidos, el indicador de detención, etc. se heredan de la regla con categoría cero, pero se pueden sustituir.

### <a name="default-order-settings-for-released-products"></a>Configuración predeterminada de pedido para productos emitidos

Para productos emitidos distintos, puede definir la configuración general de pedido o la configuración específica. La configuración general de pedido siempre tiene categoría cero. Si configura nuevos valores de pedido de ventas, compras e inventario al mismo tiempo, se recomienda usar la **Vista de detalles** en la página **Configuración predeterminada de pedido**. Para cambiar a la vista de detalles, vaya a **Opciones** &gt; **Opciones de página** &gt; **Cambiar vista** &gt; **Vista de detalles**.

### <a name="site-specific-order-settings"></a>Configuración de pedido específica del sitio

Para crear la configuración específica de pedido del sitio, seleccione **Nuevo**. En **Vista de detalles**, especifique el sitio en el campo **Sitio** de la sección **Valores aplicables para**. En **Vista de cuadrícula**, especifique el sitio en la columna **Sitio**. A la nueva regla se le asigna automáticamente un nuevo valor de categoría que es mayor que 0 (cero). Puede crear tantas reglas específicas de sitio como necesite. Para indicar que son igualmente importantes, puede asignar el mismo valor de categoría a todas las reglas específicas del sitio.

Si está en **Vista de detalles**, no puede obtener información general de las reglas creadas para el artículo. Use el botón **Mostrar/Ocultar lista** para ver la información general. Si se crea una línea de pedido de cualquier tipo y no proporciona ningún sitio, Supply Chain Management busca una regla sin sitio especificado. Esto ayuda a determinar un sitio predeterminado en la línea de pedido. Este sitio se usa para buscar una regla específica del sitio, donde se haya configurado un almacén predeterminado. Este almacén se aplica a la línea de pedido.

### <a name="specific-order-settings-for-product-dimension"></a>Configuración específica de pedido para la dimensión del producto

Puede definir las reglas de configuración del pedido para cualquier dimensión de producto activo o combinación de dimensiones de producto activo. Si un campo de dimensión de producto está vacío, esa regla se aplica a todos los valores de dimensión de producto. 

Considere el siguiente producto de ejemplo.

|                                                     |                                         |
|-----------------------------------------------------|-----------------------------------------|
| **Nombre de producto**                                    | Sensor fotoeléctrico                    |
| **Número de artículo**                                     | XW56                                    |
| **Configuración** (usada para mostrar el tipo de luz) | C1-Luz roja visible, C2-luz infrarroja |
| **Versión** | V1, V2, V3                              |

Para este ejemplo, supongamos que el producto se ha adquirido y no se ha producido. Supongamos también que la configuración C1 se usa normalmente, por lo que tiene plazos más cortos. 

Cree la siguiente configuración de pedido predeterminada para mostrar esta situación.

| Clasificación | Sitio | Configuración | Versión | Compra - Sobrescribir la configuración predeterminada | Plazo de compra | Compra - Detenida | Ventas - Sobrescribir la configuración predeterminada | Ventas - Detenidas |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | C1            |       | Sí                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

Si una línea de pedido de compra o un pedido de compra planificado se crea para el artículo XW56, configuración C1, independientemente de la versión o el sitio donde se ubica la línea, el plazo se considerará 2. Supongamos que se detienen todas las versiones además de V3.

Puede crear las siguientes reglas de configuración predeterminada de pedido.

| Clasificación | Sitio | Configuración | Versión | Compra - Sobrescribir la configuración predeterminada | Plazo de compra | Compra - Detenida | Ventas - Sobrescribir la configuración predeterminada | Ventas - Detenidas |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 20   |      |               | V2    | Sí                                  |                    | Sí                | Sí                               | Sí             |
| 20   |      |               | V1    | Sí                                  |                    | Sí                | Sí                               | Sí             |
| 10   |      | C1            |       | Sí                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

Las dos reglas para detener las versiones antiguas tienen la misma categoría. Por lo tanto, son igualmente importantes. Como ambas reglas tienen una categoría mayor que la regla para la configuración C1, tendrán prioridad con respecto a la regla para la configuración C1. 

En este ejemplo se explica la necesidad de la categoría. Si no se usa la categoría, cuando se cree un pedido de compra para la configuración C1 y la versión V2, las dos reglas definidas para V2 y C1 serán ambiguas. Para solucionar la ambigüedad, Supply Chain Management buscará entre las reglas en orden descendente de categoría y aplicará la primera regla aplicable. En el ejemplo actual, cuando una línea de pedido de compra se crea para la configuración C1 y la versión V2, el usuario obtendrá un mensaje de advertencia que indica que el artículo está en espera y que esto se debe al valor de la versión. Si la regla para la configuración tuviera una categoría mayor que la de la versión, la creación de una línea de pedido de compra para la configuración C1 y la versión V2 se habría realizado correctamente y el usuario no vería el mensaje de "artículo en espera". 

Tenga en cuenta las siguientes reglas de configuración predeterminada de pedido.

| Clasificación | Sitio | Configuración | Versión | Sitio predeterminado | Almacén predeterminado | Compra - Reemplazar las dimensiones predeterminadas de almacenamiento | Almacén de compra |
|------|------|---------------|-------|--------------|-------------------|------------------------------------------------|--------------------|
| 20   | 2    |               |       |              |                   | Sí                                            | 22                 |
| 10   |      | C1            |  V2   |  2           |  21               |                                                |                    |
| 0    |      |               |       | 1            | 11                |                                                |                    |

El sistema cruza el conjunto de reglas dos veces para determinar el sitio y el almacén. Si se crea una línea de pedido de compra para la configuración C1, versión V2, el sitio se determina en función de la regla con categoría 10. A continuación, el sistema busca una regla para que el sitio 2 determine un almacén. Se encuentra la regla 20 y, dado que tiene una categoría más alta, el almacén de la línea de pedido de compra será 22, y no 21.

Como norma general, las reglas específicas y las reglas para las dimensiones que son más importantes que otras dimensiones obtienen categorías más altas, mientras que las reglas más genéricas obtienen categorías inferiores. 

La regla con categoría cero sirve como red de seguridad. Si no aparece ninguna otra regla, se usará la configuración predeterminada de pedido de la regla cero. 

Dado que el número de categoría es tan importante, en el panel de acciones **Configuración predeterminada de pedido**, hay funciones para mover una regla hacia arriba o hacia abajo y volver a numerar las reglas, de modo que están siempre en incrementos de 10. 

Se puede crear un gran número de reglas para un producto emitido. Para tener una compresión más clara de lo que sustituye cada regla y por qué es necesario, se recomienda ir a **Vista de cuadrícula** en la página de **Configuración predeterminada de pedido**. Puede habilitar la vista de cuadrícula en **Opciones** &gt; **Opciones de página** &gt; **Cambiar vista** &gt; **Vista de cuadrícula**. El número de columnas mostradas en la cuadrícula podría ser bastante significativo, especialmente para las fichas de ventas y de inventario. Para limitar el número de columnas que se muestran en la cuadrícula, se pueden ocultar o mostrar grupos de columnas mediante los botones del menú **Configuración predeterminada de pedido** &gt; **Visualización de la columna**.

### <a name="specific-order-settings-for-released-product-variant"></a>Configuración específica de pedido para la variante del producto emitido

Si el sistema de la regla para la configuración predeterminada de pedido es demasiado complicado, existe la opción de definir la configuración predeterminada de pedido para cada variante del producto. En el siguiente ejemplo se muestra cómo se buscará el producto y los casos descritos anteriormente.

| Clasificación | Sitio | Configuración | Versión | Compra - Sobrescribir la configuración predeterminada | Plazo de compra | Compra - Detenida | Ventas - Sobrescribir la configuración predeterminada | Ventas - Detenidas |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | C2            | V3    | Sí                                  | 5                  |                    |                                   |                 |
| 10   |      | C2            | V2    | Sí                                  | 5                  | Sí                | Sí                               | Sí             |
| 10   |      | C2            | V1    | Sí                                  | 5                  | Sí                | Sí                               | Sí             |
| 10   |      | C1            | V3    | Sí                                  | 2                  |                    |                                   |                 |
| 10   |      | C1            | V2    | Sí                                  | 2                  | Sí                | Sí                               | Sí             |
| 10   |      | C1            | V1    | Sí                                  | 2                  | Sí                | Sí                               | Sí             |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

La categoría en este caso no importa realmente, por lo que puede elegir ocultarla. Esta solución presenta potencialmente un problema de mantenimiento. Sin embargo, es posible que desee tener en cuenta esta configuración si tiene previsto realizar la integración con los sistemas de Product Lifecycle Management (PLM).

## <a name="use-strict-or-standard-validation-of-default-order-quantities"></a>Usar una validación estricta o estándar de las cantidades de pedido predeterminadas

Puede elegir hasta qué punto debe ser estricto el sistema al validar las cantidades especificadas en la opción **Configuración de pedido predeterminad** para un producto. Cuando utiliza la nueva opción de estricto, la opción **Cantidad de pedido estándar** siempre debe ser un múltiplo **Múltiplo** especificado para pedidos de compra, inventario y pedidos de ventas. Si está utilizando una validación estricta, no podrá guardar la configuración de pedido predeterminada que no cumpla con este requisito (y se muestra un error en la barra de mensajes). 

La validación estricta se aplica a los valores en **Cantidad de pedido estándar** especificados en las fichas desplegables **Pedido de compra**, **Inventario** y **Pedidos de venta** de la pagina **Configuración de pedido predeterminada**. Cada ficha desplegable tiene su propia configuración de **Múltiplo**, que se utiliza para validar el valor **Cantidad de pedido estándar** especificado para esa ficha desplegable.

### <a name="enable-the-strict-validation-option"></a>Habilitar la opción de validación estricta

Antes de poder usar la opción de validación estricta, debe estar habilitada en su sistema. Los administradores pueden usar la página [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y habilitarla si es necesario. Aquí, la característica aparece como:

- **Módulo** - *Gestión de información de productos*
- **Nombre de la característica** - *Validación estricta en cantidades de pedido predeterminadas*

### <a name="set-the-validation-option"></a>Establecer la opción de validación

Para establecer la opción de validación:

1. Vaya a **Gestión de la información del producto \> Configuración \> Parámetros de gestión de información del producto**.
1. En la pestaña **General**, establezca **Validación en cantidades de pedido predeterminadas** en uno de los siguientes valores:
    - **Estricto**: seleccione esta opción para asegurarse de que todos los valores de **Cantidad de pedido estándar** serán un múltiplo del valor en **Múltiplo** para cada ficha desplegable (**Pedido de compra**, **Inventario** y **Pedidos de venta**).
    - **Estándar**: seleccione esta opción para usar la validación estándar (que funciona igual que cuando esta función no está habilitada).
