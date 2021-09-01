---
title: Configuración de los valores de los parámetros de gestión de costes
description: Cuando configura el módulo de costo de aterrizaje, puede definir varios conjuntos de valores comunes que estarán disponibles cuando seleccione tipos específicos de valores de parámetros de costos en otras partes de la aplicación. Este tema explica cómo establecer estos conjuntos de valores.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMCostTypeTable, ITMCostTypeGroup, ITMCostTransferGroup, ITMCostTemplateTable, ITMVolumetricDivisorTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: dada2f9a3ae13f41b7f63d1f0907002860d0717ff9d8c2453fc6f3ad123cbf78
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736752"
---
# <a name="costing-parameter-values-setup"></a>Configuración de los valores de los parámetros de gestión de costes

[!include [banner](../../includes/banner.md)]

Cuando configura el módulo **Coste de aterrizaje**, puede definir varios conjuntos de valores comunes y configuraciones relacionadas por valor. Estos valores estarán disponibles cuando seleccione tipos específicos de valores de parámetros de costos en otras partes de la aplicación. Este tema explica cómo establecer estos conjuntos de valores.

## <a name="set-up-cost-type-codes"></a>Configurar códigos de tipo de costo

Los códigos de tipo de costo determinan el tipo de costo en el que se incurre cuando las mercancías se desembarcan en el almacén o los costos de desembarque del viaje. Aunque normalmente aumentan el valor de los bienes, también se pueden utilizar para acumular importes en el libro mayor. Los ajustes del libro mayor se utilizan cuando un costo se acumula a lo largo del tiempo o durante una serie de viajes y se compensa en una sola transacción.

> [!NOTE]
> Si la tabla de tipos de costos se comparte entre entidades legales, el plan de cuentas también debe compartirse entre entidades legales. De lo contrario, las transacciones de contabilización no funcionarán correctamente.

Para configurar sus códigos de tipo de costos, vaya a **Coste de aterrizaje \> Configuración de costos \> Códigos de tipos de costos**. Puede utilizar los botones del Panel de acciones para crear nuevos códigos de tipo de costo, editar códigos existentes o eliminar un tipo de costo seleccionado.

En la tabla siguiente se describen los campos disponibles para cada código de tipo de coste.

| Campo | Descripción |
|---|---|
| Código de tipo de coste | Permite introducir un nombre para el código de tipo de coste. |
| Descripción | Especifique una descripción del código de tipo de coste. |
| Usar la tasa de envío | Establezca esta opción en *Sí* si la tasa de cambio del viaje (a veces denominada tasa de gestión) debe usarse para calcular el valor de estos costos. En este caso, se utilizará la tarifa de envío en lugar del tipo de cambio estándar predeterminado o al contado para cambiar facturas en moneda extranjera. |
| Categoría de informe | Este campo establece una categoría de informe para el tipo de costo. Los informes se pueden imprimir por categorías de informes o por tipo de costo. |
| Tipo de débito | Seleccione si el tipo de costo debe debitar el artículo, la cuenta contable o el proveedor. |
| Registro del débito | Si el campo **Tipo de débito** está configurado en *Cuenta contable*, seleccione la descripción de la publicación. |
| Cuenta de débito | Si el campo **Tipo de débito** está configurado en *Cuenta contable*, seleccione la cuenta contable para usar. |
| Tipo de crédito | Seleccione si este tipo de costo debe abonar el artículo, la cuenta contable o el proveedor. |
| Registro del crédito | Si el campo **Tipo de crédito** está configurado en *Cuenta contable*, seleccione la descripción de la publicación. |
| Cuenta de cŕedito | Si el campo **Tipo de crédito** está configurado en *Cuenta contable*, seleccione la cuenta contable para usar. |
| Cuenta de compensación | Seleccione la cuenta de compensación para el tipo de coste. Le recomendamos que especifique una cuenta de compensación separada por tipo de costo para ayudar con la conciliación. |
| Tipo de registro de coste estándar | Si utiliza el cálculo de costes estándar, seleccione la descripción de la publicación. |
| Cuenta de desviación del coste estándar | <p>Si usa el cálculo de costos estándar, la cuenta que se especifica aquí se usará para registrar cualquier variación. Esta cuenta utiliza el desglose del costo de entrega en la página **Precios de los artículos**. Este desglose se crea utilizando la rutina periódica para actualizar los precios.</p><p>Por ejemplo, el costo estándar de un artículo es $ 15,00, el FOB es $ 13,00 y el flete es $ 2,00. Cuando se recibe la factura por las existencias, el artículo se recibe en $ 15,00, pero hay una variación de precio estándar de $ 2,00 para el artículo, porque el FOB real es $ 13,00. Esta variación se contabiliza en la cuenta de variación de precio estándar que se configura en el perfil de contabilización de artículos. Debido a que el flete estimado es $ 2,00, no hay variación cuando se registra la factura de stock. Sin embargo, cuando se recibe la factura del flete, el flete es $ 2,50 por unidad. Por lo tanto, se contabiliza una variación $ 0,50 en el costo especificado. |
| Cuenta de desviación de media móvil | <p>Si usa la gestión de costes de media móvil, la cuenta que se especifica aquí se usará para registrar cualquier variación.</p><p>Por ejemplo, el flete estimado es $ 2,00. Sin embargo, cuando se recibe la factura del flete, el flete es $ 2,50 por unidad. Por lo tanto, se debe publicar una variación $ 0,50.</p><p>Cuando la opción **Publicar ajustes como variación** está configurada en *Sí* en la página **Parámetros de costo aterrizado**, todas las variaciones entre los costos de envío estimados y reales se contabilizarán en la cuenta de variación de promedio móvil que se especifica aquí. Cuando la opción **Publicar ajustes como variación** está configurada en *No*, se utilizará la funcionalidad estándar y la variación se aplicará al inventario o a la cuenta de variación de promedio móvil que se especifica aquí, según las existencias disponibles.</p> |
| Cuenta de acumulación de cargos | Seleccione la cuenta que se utiliza para acumular estimaciones de costos cuando se registra la factura de compra. Este campo se usa solo cuando la opción **Usar cuenta de acumulación de cargo de tipo de costo** está configurada en *Sí* en la ficha desplegable **Gestión de costes** en la pestaña **General** de la página **Parámetros de costo aterrizado**. |
| Cuenta de cargos | Seleccione la cuenta que se utiliza para capturar los costos de transporte de entrada que han sido facturados por un proveedor. La cantidad se registra como débito. La cuenta de compensación es la cuenta de variación de existencias. Este registro se usa solo cuando se factura un pedido de compra, si la opción **Registrar en la cuenta de gastos del libro mayor** está establecida en *Sí* en la página **Parámetros de proveedores**. |
| Cuenta de desviación | La cuenta que se utilizará para compensar las acumulaciones de cargos cuando se registre la factura de compra. Este campo se usa solo cuando la opción **Usar cuenta de acumulación de cargo de tipo de costo** está configurada en *Sí* en la ficha desplegable **Gestión de costes** en la pestaña **General** de la página **Parámetros de costo aterrizado**. |

## <a name="vendor-cost-type-groups"></a>Grupos de tipos de costes de proveedores

Los grupos de tipos de costos de proveedores ayudan a determinar cómo se encuentran y se aplican a un viaje los cargos de *costo automático*. Los proveedores que tienen costos de importación similares están vinculados. Por ejemplo, todos los proveedores de mercados emergentes pagan el mismo porcentaje de impuestos por el mismo tipo de producto que se compra en un mercado establecido.

Puede actualizar los grupos de tipos de costos de proveedores yendo a **Coste de aterrizaje \> Configuración de costos \> Grupos de tipos de costos de proveedores**. La página **Grupos de tipos de costos de proveedores** proporciona una cuadrícula que enumera todos los grupos de tipos de costos de proveedores existentes. Puede utilizar los botones del Panel de acciones para agregar, eliminar y editar filas en la cuadrícula.

En la tabla siguiente se describen los campos disponibles en cada fila de la cuadrícula.

| Campo | Descripción |
|---|---|
| Grupos de tipos de costes de proveedores | Ingrese un nombre único para el grupo de tipos de costos de proveedor (como *Mercados emergentes*). |
| Descripción | Especifique una descripción del grupo de tipo de coste de proveedor. Esta descripción puede proporcionar detalles sobre el nivel o tipo de cargo asociado con el grupo de proveedores. |

## <a name="item-cost-type-groups"></a>Grupos de tipos de costes de artículos

Los grupos de tipos de costos de artículos ayudan a determinar cómo se encuentran y se aplican a un viaje los cargos de *costo automático*. Los elementos similares están vinculados entre sí. Por ejemplo, todos los artículos que tienen una tasa de impuestos del 5 por ciento pueden pertenecer a un grupo de tipo de costo específico.

Puede actualizar los grupos de tipos de costos de artículos yendo a **Coste de aterrizaje \> Configuración de costos \> Grupos de tipos de costos de artículos**. La página **Grupos de tipos de costos de artículos** proporciona una cuadrícula que enumera todos los grupos de tipos de costos de artículos existentes. Puede utilizar los botones del Panel de acciones para agregar, eliminar y editar filas en la cuadrícula.

En la tabla siguiente se describen los campos disponibles en cada fila de la cuadrícula.

| Campo | Descripción |
|---|---|
| Grupos de tipos de costes de artículos | Ingrese un nombre único para el grupo de tipos de costos de artículo (como *arancel 5 %*). |
| Descripción | Especifique una descripción del grupo de tipo de coste de artículo. Esta descripción puede proporcionar detalles sobre el nivel o tipo de cargo asociado con el grupo de artículos. |

> [!NOTE]
> El tipo de costo del artículo está vinculado al artículo a través del campo **Grupo de tipo de costo** en la ficha desplegable **Compra** de la página **Producto lanzado** del artículo.

## <a name="transfer-order-cost-type-groups"></a>Grupos de tipos de costes de órdenes de transferencia

Los grupos de tipos de costos de órdenes de transferencia ayudan a determinar cómo se encuentran los cargos de *costo automático*. Los elementos similares están vinculados entre sí. Por ejemplo, todos los artículos que tienen una tasa de impuestos del 7 por ciento pueden pertenecer a un grupo de tipo de costo específico.

Puede actualizar los grupos de tipos de costos de órdenes de transferencia yendo a **Coste de aterrizaje \> Configuración de costos \> Grupos de tipos de costos de órdenes de transferencia**. La página **Grupos de tipos de costos de órdenes de transferencia** proporciona una cuadrícula que enumera todos los grupos de tipos de costos de órdenes de transferencia existentes. Puede utilizar los botones del Panel de acciones para agregar, eliminar y editar filas en la cuadrícula.

En la tabla siguiente se describen los ajustes disponibles en cada fila de la cuadrícula.

| Campo | Descripción |
|---|---|
| Grupos de tipos de costes de órdenes de transferencia | Ingrese un nombre único para el grupo de tipos de costos de órdenes de transferencia (como *arancel 7 %*). |
| Descripción | Especifique una descripción del grupo de tipo de coste de órdenes de transferencia. Esta descripción puede proporcionar detalles sobre el nivel o tipo de cargo asociado con el grupo de tipos de costes de órdenes de transferencia. |

> [!NOTE]
> El tipo de costo de órdenes de transferencia está vinculado al artículo a través del campo **Grupo de tipo de costo de órdenes de transferencia** en la ficha desplegable **Compra** de la página **Producto lanzado** del artículo.

## <a name="cost-templates"></a>Plantillas de coste

Utilice plantillas de costos para establecer valores predeterminados para configuraciones que los usuarios que obtienen la estimación de costos tal vez no conozcan. Las plantillas de costes pueden ayudar a reducir la complejidad en el proceso de estimación al minimizar las selecciones que los usuarios deben realizar para obtener una estimación precisa.

Para trabajar con plantillas de costos, vaya a **Coste de aterrizaje \> Configuración de costos \> Plantillas de costos**. Sobre la página **Plantillas de costos**, el panel de lista de la izquierda muestra todas las plantillas de costos actuales. Puede utilizar los botones del Panel de acciones para agregar, quitar y editar plantillas.

En la tabla siguiente se describen los ajustes disponibles para cada plantilla.

| Campo | Descripción |
|---|---|
| Plantilla de coste | Permite introducir un nombre único para la plantilla de costes. El nombre generalmente describe el factor o el multiplicador de costos de la plantilla. |
| Descripción | Especificar una descripción de la plantilla de coste. |
| Empresa de transporte | Seleccione la cuenta de proveedor de la empresa de envío para asociarla con la plantilla de costos. |
| Modo de entrega | Seleccione el modo de entrega que debe usar la plantilla de costos cuando se calcula el costo estimado de un artículo. Este campo ayudará a determinar los costos de automóviles asociados con los bienes en la estimación de costos. |
| Tipo de contenedor de envío | Seleccione el tipo de contenedor de envío para para asociarlo con la plantilla de costos. Este campo ayudará a determinar los costos de automóviles asociados con los bienes en la estimación de costos. |
| Agente de aduanas | Seleccione el agente de aduanas (proveedor) para asociarlo con la plantilla de costos. Este campo ayudará a determinar los costos de automóviles asociados con la estimación de costos. |
| Factor | Ingrese un factor para aplicar a la estimación del costo final de los bienes. Por ejemplo, para agregar un 10 por ciento al costo estimado calculado, ingrese *1,10*. |

## <a name="volumetric-divisors"></a>Divisores volumétricos

Los divisores volumétricos se utilizan para calcular el peso volumétrico. Cada empresa de envío / flete formula sus propios divisores volumétricos. Además, los divisores de una empresa suelen variar, según el modo de entrega. Por ejemplo, el aire y el mar a menudo tienen divisores muy diferentes. Una empresa también puede hacer que sus reglas sean más complejas, según el lugar desde el que envíe.

Por ejemplo, un paquete que se envía por vía aérea tiene un volumen de 3 metros cúbicos (m³). La empresa cobra por peso volumétrico y aplica un divisor volumétrico de 6. Este divisor se multiplica por el volumen para determinar el peso volumétrico. Por lo tanto, el peso volumétrico de este ejemplo es 3 × 6 = 18 kilogramos (kg).

Para configurar divisores volumétricos, vaya a **Coste de aterrizaje \> Configuración de costos \> Divisores volumétricos**. La página **Divisores volumétricos** proporciona una cuadrícula que enumera todos los divisores volumétricos existentes. Puede utilizar los botones del Panel de acciones para agregar, eliminar y editar filas en la cuadrícula.

En la tabla siguiente se describen los campos disponibles en cada fila de la cuadrícula.

| Campo | Descripción |
|---|---|
| Empresa de transporte | Seleccione la cuenta de proveedor de la empresa de envío asociada al divisor volumétrico. |
| Código de tipo de coste | Seleccione el código de tipo de costo asociado con el divisor volumétrico. Utilice este campo para colocar los tipos de costos en grupos de informes. Los informes se pueden imprimir por categorías de informes o por tipo de costo. |
| Puerto de origen | Seleccione el puerto "desde" al que se aplica el divisor volumétrico. |
| Divisor volumétrico | Introduzca el valor de divisor volumétrico que se aplica a la fila. El valor que ingrese será *multiplicado* por el volumen de cada paquete para determinar el peso volumétrico de ese paquete. |
