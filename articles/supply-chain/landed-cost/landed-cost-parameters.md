---
title: Configuración de los parámetros de costo descargado
description: En este artículo se describe cómo configurar la información general y los parámetros de configuración que se utilizan en el módulo de costos de aterrizaje para la publicación, las actualizaciones de estado, las secuencias de números y el comportamiento.
author: Weijiesa
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 609403b251338b7e792f3ab624fb37a1833c919b
ms.sourcegitcommit: eb9a53d5cf10f1ada68757536d6a94b2cb00929d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725531"
---
# <a name="landed-cost-parameters-setup"></a>Configuración de los parámetros de costo descargado

[!include [banner](../../includes/banner.md)]

La página **Parámetros de costos descargados** se usa para configurar la información general y los parámetros de configuración que se utilizan en el módulo de **Costo descargado** para la publicación, las actualizaciones de estado, las secuencias de números y el comportamiento. La configuración de los parámetros se comparte entre las entidades legales y puede ser modificada por un administrador.

## <a name="open-the-landed-cost-parameters-page"></a>Abra la página de parámetros de costo de entrega

Para trabajar con los parámetros, vaya a **Coste de aterrizaje \> Configuración \> Parámetros de costo aterrizado** y luego configure los campos como se describe en las siguientes subsecciones.

![Página Parámetros de costos descargados.](media/landed-cost-parameters.png "Página Parámetros de costos descargados")

## <a name="general-tab"></a>Pestaña General

### <a name="general-fasttab"></a>Ficha desplegable General

La siguiente tabla describe los campos que están disponibles en la ficha desplegable **General** de la pestaña **Genearl** de la página **Parámetros de costos descargados**.

| Configuración | Descripción |
|---|---|
| Usar la tasa de envío | Se establece una tarifa de envío para un período definido y se utiliza para estimar los costos de los productos que utilizan varias monedas. Establezca esta opción en *Sí* para utilizar una tarifa de envío. |
| Tipo de cambio | La colección predeterminada de tipos de cambio que se utiliza para los cálculos de varias monedas para un viaje y los costos del viaje. |
| Actualizar la cantidad del pedido de compra | Seleccione lo que ocurre si un usuario cambia la cantidad en una línea de orden de compra:<ul><li>**Aceptar** - La cantidad del viaje se ajusta automáticamente.</li><li>**Advertencia** - Si la línea está unida a un viaje, se muestra una advertencia, pero se actualiza la cantidad del viaje.</li><li>**Error** - Si la línea está adjunta a un viaje, se muestra un mensaje de error y la orden de compra no se puede actualizar. Por lo tanto, la línea de pedido debe eliminarse primero del viaje.</li></ul> |
| Actualizar automáticamente el número de cajas | Cuando esta opción se establece en *Sí*, todas las cajas se agregan juntas y se muestran en los niveles de viaje y contenedor. Cuando está configurado en *No*, el número de cajas se establece inicialmente en 0 (cero) y se puede editar manualmente según sea necesario. |

### <a name="costing-fasttab"></a>Ficha desplegable Gestión de costes

La siguiente tabla describe los campos que están disponibles en la ficha desplegable **Gestión de costes** de la pestaña **Genearl** de la página **Parámetros de costos descargados**.

| Configuración | Descripción |
|---|---|
| Especificación de registro | Seleccione el ajuste de valor en el libro mayor:<ul><li>**Total** - Se contabiliza una cifra total en el libro mayor.</li><li>**Grupo de artículos** - El ajuste se especifica por grupo de artículos.</li><li>**Número de artículo** - El ajuste se especifica por artículo. Este valor proporciona la mayor cantidad de detalles.</li></ul> |
| Permitir coste cero | Establezca esta opción en *No* para mostrar un error si un usuario intenta publicar una estimación de costo para una factura de viaje o una orden de compra que no incluye un valor para el costo de viaje esperado. El mensaje de error indica que no se puede asignar un costo de 0 (cero) y la contabilización de facturas fallará. En este caso, el usuario puede actualizar manualmente la estimación (o reconfigurar el costo automático) y luego extraer el valor actualizado o eliminar el costo si no aplica.<p>Establezca esta opción en *Sí* para permitir que el costo del viaje quede en blanco. En este caso, se asignará un precio de 0 (cero) de acuerdo con el área de costo. Luego, se puede procesar una factura de costo del proveedor contra el costo de precio cero cuando se recibe el viaje.</p><p>Le recomendamos que configure la estimación en el registro de costo automático para evitar que aparezca un costo de precio cero. Aunque esta estimación no es del todo precisa, debería ser más precisa que el supuesto coste cero.</p> |
| Fecha de registro de ajuste | Cuando registra una factura de costo de viaje de Cuentas por pagar, la tabla de liquidaciones (ajustes de inventario) también se actualiza. Seleccione la fecha que se establece de forma predeterminada en la página **Seleccione los costos del viaje** mientras está en el diario de facturas:<ul><li>**Fecha de transacción** - Use la fecha de diario (fecha de registro).</li><li>**Fecha de factura de la orden de compra** - Utilice la fecha de contabilización financiera de la factura de stock (orden de compra).</li><li>**Fecha seleccionada** - El usuario puede especificar una fecha de publicación. Aunque la fecha se puede dejar en blanco, si todavía está en blanco cuando se registra la factura de costo, el usuario recibirá un error.</li></ul> |
| Usar asiento de factura de compra | Cuando esta opción se establece en *Sí*, las transacciones de acumulación de costos utilizarán el mismo número de comprobante que se utiliza para la factura de compra. Cuando está configurado en *No*, el sistema utilizará el siguiente número disponible para la secuencia numérica **Comprobante de acumulación de costes** que se configura en la pestaña **Secuencias numéricas** de la página **Parámetros de costo descargado**.<p>Esta opción tiene efecto solo cuando se factura un pedido de compra, si la opción **Registrar en la cuenta de gastos del libro mayor** está establecida en *Sí* en la pestaña **Factura** de la página **Parámetros de proveedores**.</p> |
| Bloquear registro manual en cuenta de compensación | Establezca esta opción en *Sí* para evitar la contabilización en cuentas de compensación donde la transacción no se ha vinculado a un viaje seleccionando **Funciones \> Seleccione los costos del viaje** en el Panel de acciones del diario de facturas de proveedor. Le recomendamos que configure esta opción en *Sí* para que la cuenta de viaje y compensación se pueda liquidar correctamente. |
| Usar la cuenta de acumulación de cargos del tipo de coste | Cuando esta opción se establece en *Sí*, la cuenta de acumulación de cargos que está configurada para el código de tipo de costo relevante en la página **Códigos de tipo de costo** se utilizará para acumular costos como gasto.<p>Esta opción tiene efecto solo cuando se factura un pedido de compra, si la opción **Registrar en la cuenta de gastos del libro mayor** está establecida en *Sí* en la pestaña **Factura** de la página **Parámetros de proveedores**. |
| Registrar ajustes como desviación | Cuando esta opción se establece en *Sí*, anula la funcionalidad estándar y obliga a que las transacciones de ajuste de inventario que están relacionadas con las variaciones entre los costos estimados y los costos reales se registren en una cuenta de variación.<p>Cuando esta opción se establece en *No*, las transacciones de ajuste de inventario que están relacionadas con las variaciones se manejan según la configuración del método de cálculo de costos y el código de tipo de costo. Para el costo estándar, las variaciones aún se registrarán en la cuenta de variaciones. Para el promedio ponderado móvil (WMA), las variaciones se registrarán en la cuenta de variación o en el inventario.</p><p>Esta opción tiene efecto solo cuando se factura un pedido de compra, si la opción **Registrar en la cuenta de gastos del libro mayor** está establecida en *Sí* en la pestaña **Factura** de la página **Parámetros de proveedores**.</p> |

### <a name="validation-fasttab"></a>Ficha desplegable Validación

La siguiente tabla describe los campos que están disponibles en la ficha desplegable **Validación** de la pestaña **Genearl** de la página **Parámetros de costos descargados**.

| Configuración | Descripción |
|---|---|
| Múltiples facturas de coste | Seleccione lo que ocurre si se procesa más de una factura contra un viaje, folio o contenedor por el mismo cargo misceláneo.<ul><li>**Aceptar** - El sistema debe permitir facturas de costos múltiples.</li><li>**Advertencia** - Se muestra una advertencia.</li><li>**Error** – Se muestra un mensaje de error.</li></ul> |
| Múltiples proveedores por folio | Seleccione lo que ocurre si se agregan más de las órdenes de compra de un proveedor a una publicación.<ul><li>**Aceptar** - El sistema debe permitir la acción.</li><li>**Advertencia** - Se muestra una advertencia, pero la acción aún se puede realizar.</li><li>**Error** - Se muestra un mensaje de error y se evita la acción.</li></ul><p>Su agente de aduanas o las leyes locales pueden exigir un valor específico para este campo.</p> |
| Tolerancia de varios modos de entrega | Seleccione lo que ocurre si los bienes de una orden de compra que utiliza un modo de entrega diferente al del viaje se agregan a ese viaje.<ul><li>**Aceptar** - El sistema debe permitir la acción.</li><li>**Advertencia** - Se muestra una advertencia, pero la acción aún se puede realizar.</li><li>**Error** - Se muestra un mensaje de error y se evita la acción.</li></ul> |
| Tolerancia de varios almacenes | Seleccione lo que ocurre si un viaje incluye varias líneas de pedido que deben entregarse en diferentes almacenes. Estas líneas de pedido se pueden distribuir en uno o más pedidos de compra.<ul><li>**Aceptar** - El sistema debe permitir la acción.</li><li>**Advertencia** - Se muestra una advertencia.</li><li>**Error** – Se muestra un mensaje de error.</li></ul> |
| Falta volumen | Seleccione lo que ocurre si un usuario agrega un artículo sin volumen a un viaje.<ul><li>**Aceptar** - El sistema debe aceptar el artículo.</li><li>**Advertencia** - Se muestra una advertencia.</li><li>**Error** – Se muestra un mensaje de error.</li></ul><p>Si se utilizan volúmenes para calcular y distribuir los costos, le recomendamos que seleccione *Advertencia* o *Error*.</p> |
| Proveedor de servicios sin coste de viaje | Seleccione lo que ocurre si un usuario intenta procesar una factura de un proveedor de servicios que no se ha vinculado a un viaje. <ul><li>**Aceptar** - El sistema debe permitir la acción.</li><li>**Advertencia** - Se muestra una advertencia.</li><li>**Error** – Se muestra un mensaje de error.</li></ul><p>Le recomendamos que seleccione *Advertencia*.</p> |

### <a name="defaults-fasttab"></a>Ficha desplegable Valores predeterminados

La siguiente tabla describe los campos que están disponibles en la ficha desplegable **Valores predeterminados** de la pestaña **Genearl** de la página **Parámetros de costos descargados**.

| Configuración | Descripción |
|---|---|
| Nombre del diario | Seleccione el diario predeterminado que la función *Crear diario de llegadas* debe usar. |
| Estado de viaje | Seleccione el estado que debe tener un viaje antes de que los usuarios puedan configurar un contenedor de envío de alquiler en el sistema. Esta acción suele ocurrir cuando las mercancías están en tránsito o en el muelle. |
| Plantilla de recorrido | Seleccione la plantilla de viaje predeterminada que se utilizará para los nuevos contenedores de envío de alquiler. Por lo general, seleccionará una plantilla de viaje que incluya los costos de alquiler. |
| Movimiento | Si la cantidad excedente / insuficiente de una entrega se encuentra dentro de la tolerancia definida, se procesará automáticamente un diario de movimiento. Seleccione el diario de movimiento predeterminado para usar. El campo **Cuenta de compensación** para el nombre del diario de movimiento seleccionado debe tener un valor. |
| Transferir | Cuando se procesa una entrega insuficiente, la cantidad de recepción corta se transferirá a un almacén de entrega insuficiente. Seleccione el diario de transferencia predeterminado para usar. |
| Deshabilitar pedidos de compra que no sean de viajes | Desactive la función de entrega de costo de desembarco por encima o por debajo de la tarifa para las órdenes de compra que no están asociadas a un viaje. |
| Desactivar pedidos de compra que no sean de mercancía en tránsito | Desactive la función de entrega de costo de desembarco por encima o por debajo de la tarifa para las órdenes de compra que no usan la funcionalidad de mercancía en tránsito. |
| Período de gracia de recepción en exceso de mercancía en tránsito | Especifique la cantidad de días después de la primera recepción de un contenedor de envío en los que aún se pueden completar recibos adicionales para ese contenedor de envío. |

## <a name="status-updates-tab"></a>Pestaña de actualizaciones de estado

El sistema utiliza valores de estado para indicar el estado de cada viaje. Los valores de estado de la travesía se pueden aplicar automáticamente a las travesías mediante el seguimiento de travesías o trabajos por lotes periódicos. Alternativamente, puede aplicarlos manualmente abriendo el viaje y luego seleccionando un estado en el grupo **Actualización de viaje** en la pestaña **Administrar** del Panel de acciones. 

Puede crear tantos valores de estado de viaje como quiera. Sin embargo, cuatro de ellos deben definirse como utilizados para un propósito especial en la pestaña **Actualizaciones de estado** de la página **Parámetros de costo descargado**. En la tabla siguiente se describen los campos allí disponibles.

| Configuración | Descripción |
|---|---|
| Estimado | Seleccione el estado del viaje que identifica que se ha finalizado un viaje. |
| En tránsito | Seleccione el estado del viaje que identifica que un viaje está en tránsito. |
| Listo para la gestión de costes | Seleccione el estado del viaje que identifica que un viaje está listo para la gestión de costes. Este estado se utiliza cuando todas las facturas de compra de acciones y las facturas de costo del viaje donde el campo **Crédito en el costo del viaje** está configurado como *Vendedor* han sido procesadas para el viaje. Los viajes que no superen el proceso de gestión de costes tendrán el estado *Listo para gestión de costes*.|
| Con estimación previa | Seleccione el estado del viaje que identifica un viaje está en estimación previa. Este estado se usa cuando se agrega una nueva transacción de costo a un viaje después de que ya se haya calculado el costo. Se pueden agregar nuevas transacciones de costos a un viaje previamente calculado cuando se recibe una segunda factura de flete o un cargo por estadía inesperado. Este estado se aplica automáticamente cuando se agrega un nuevo costo de viaje a un viaje con costo. |

## <a name="voyage-creator-tab"></a>Pestaña del creador de viajes

La siguiente tabla describe las secciones en la pestaña **Creador de viajes** de la página **Parámetros de costo descargado**.

| Grupo | Descripción |
|---|---|
| Tolerancias | Los campos **Tolerancia de volumen exterior** y **Tolerancia de peso exterior** definen los umbrales por encima de los cuales los bienes se consideran sobrevolumen y sobrepeso. Cuando un usuario agrega productos en la página **Editor de viajes**, si el volumen o el peso excede el valor que estableció aquí, el sistema muestra una advertencia. El valor de cada campo se expresa como un porcentaje del volumen o peso máximo que se establece para el tipo de contenedor de envío relevante. Recomendamos que el valor esté entre el 5 y el 10 por ciento del volumen o peso máximo. |
| Configuración de creación de folio | El sistema puede crear múltiples folios durante el proceso de creación del viaje. Utilice esta sección para definir cuándo se debe crear una nueva publicación. Para cada fila de esta sección, el sistema verificará la tabla y el campo especificados y creará un folio para cada valor de campo único. |

## <a name="cost-estimates-tab"></a>Pestaña de estimaciones de costes

La pestaña **Estimaciones de costes** de la página **Parámetros de costo descargado** proporciona solo un campo: **Versión de cálculo de costes predeterminada**. Este campo se aplica solo cuando el método de gestión de costes es *Gestión de costes estándar*. Seleccione la versión de cálculo de costes predeterminada que se utilizará para la tarea periódica *Actualización del precio de costo del artículo*. Es posible que deba cambiar esta configuración cada vez que comience un nuevo año financiero.

## <a name="inventory-dimensions-tab"></a>Pestaña Dimensiones de inventario

La pestaña **Dimensiones de inventario** de la página **Parámetros de costo aterrizado** se usa para controlar qué dimensiones de inventario disponibles deben mostrarse de forma predeterminada en cada página de costos de destino donde se utilizan dimensiones.

Seleccione una dimensión y luego establezca la opción **Líneas de viaje**, **Mercancías en tránsito** y/o **Coste estimado** en *Sí* para cada página donde esa dimensión debería mostrarse de forma predeterminada. Repita este paso para otras dimensiones, según sea necesario.

La configuración de esta pestaña establece las dimensiones predeterminadas para cada página designada en todas las entidades legales. Sin embargo, los usuarios que están trabajando en una de las páginas designadas pueden anular las dimensiones predeterminadas seleccionando **Inventario \> Dimensiones de la pantalla** en el Panel de acciones.

## <a name="number-sequences-tab"></a>Ficha Secuencias numéricas

La pestaña **Secuencias numéricas** de la página **Parámetros de costo aterrizado** enumera cada tipo de secuencia de números de referencia que requiere el costo de aterrizaje, pero que no se comparte entre las entidades legales. Para cada referencia de la lista, seleccione un código de secuencia numérica.


## <a name="shared-number-sequences-tab"></a>Pestaña Secuencias numéricas compartidas

La pestaña **Secuencias numéricas compartidas** de la página **Parámetros de costo aterrizado** enumera cada tipo de secuencia de números de referencia que se comparte entre las entidades jurídicas para el costo descargado. Actualmente, solo hay una secuencia numérica en la lista. Esta secuencia numérica se utiliza para la identificación del viaje.


## <a name="feature-visibility-tab"></a>Pestaña Visibilidad de funciones

El costo descargado agrega características (campos y funciones) a varias páginas de uso frecuente en Microsoft Dynamics 365 Supply Chain Management. Estas páginas incluyen páginas relacionadas con los datos maestros del proveedor, los productos lanzados, las órdenes de compra, las órdenes de transferencia y la configuración del almacén. Si está utilizando el costo de aterrizaje, debe hacer que esas funciones estén visibles en todas partes antes de poder beneficiarse de ellas. Si no está utilizando el costo de aterrizaje, puede ocultar las funciones para mantenerlas fuera del camino.

En la pestaña **Visibilidad de la función** de la página **Parámetros de costo descargado**, configure la opción **Activar** en *Sí* para hacer visibles las características de costos de aterrizaje dondequiera que estén disponibles. Establézcalo en *No* para ocultar las funciones en páginas comunes fuera del costo de lanzamiento. Sin embargo, incluso cuando la opción está configurada en *No*, el propio módulo, incluida la página **Parámetros de costo aterrizado**, permanecerá disponible para los usuarios que tengan los permisos correctos para acceder a ella.
