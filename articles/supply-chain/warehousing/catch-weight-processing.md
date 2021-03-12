---
title: Procesamiento de producto con peso capturado con la gestión de almacenes
description: Este tema describe cómo usar plantillas de trabajo y directivas de ubicación para determinar cómo y dónde se realiza el trabajo en el almacén.
author: perlynne
manager: tfehr
ms.date: 08/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCatchWeightTag, WHSCatchWeightItemHandlingPolicy, TMSLoadBuildWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-1-31
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 6ecadb06adce5a0cbf1614c7da8fc65cb801e249
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001186"
---
# <a name="catch-weight-product-processing-with-warehouse-management"></a>Procesamiento de producto con peso capturado con la gestión de almacenes

[!include [banner](../includes/banner.md)]


## <a name="feature-exposure"></a>Exposición de la función

Para usar la gestión de almacén para procesar los productos con peso capturado, debe usar una clave de configuración de la licencia para activar la funcionalidad. Vaya a **Administración del sistema \> Configuración \> Configuración de licencias**. A continuación, en la pestaña **Claves de configuración** , expanda **Comercio \> Administración del almacén y el transporte**, y seleccione la casilla para **Peso capturado para el almacén**.

> [!NOTE]
> Tanto la clave de configuración de la licencia **Administración del almacén y el transporte** y las claves de configuración de la licencia **Procesar distribución \> Peso capturado** también se deben activar. Para establecer las claves de configuración para el peso capturado, también debe activar la característica a través del espacio de trabajo **Administración de características**. La característica principal que hay que activarse es **Procesamiento de producto con peso capturado con la gestión de almacenes**. Dos características relacionadas pero opcionales que es posible que desee activar son **Cambios en el estado del inventario para productos de peso de captura** y **Use las etiquetas de peso de captura existentes al informar las órdenes de producción como terminadas**.

Después de que se vuelva a activar la clave de configuración de la licencia, al crear un producto liberado, puede seleccionar **Peso capturado**. También puede asociar el producto lanzado a un grupo de dimensiones de almacenamiento que el parámetro **Procesos de gestión de almacenes de uso** se ha seleccionado.

Para poder usar el producto en la gestión del almacén, debe hacer cierta configuración básica del producto para peso capturado:

- Defina la conversión nominal del peso entre la unidad de peso capturado (cuadro) y la unidad de inventario (kilogramo \[kg\]) como parte de una definición de conversión de unidades.
- Defina tolerancias mínimas y máximas de peso como parte de la configuración de la unidad de peso capturado.
- Configurar un grupo de la secuencia de la unidad en la unidad de peso capturado se define como la referencia de almacén inferior (SKU).
- Configurar una directiva de manipulación de artículos con peso capturado

Para obtener más información, consulte [Configuración y mantenimiento de artículos con peso capturado](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-catch-weight-items).

## <a name="transaction-adjustments"></a>Ajustes de transacciones

Dado que el peso del inventario cuando especifica un almacén puede ser diferente del peso cuando se emite el inventario fuera del almacén, el procesamiento de producto con peso capturado debe ajustar el inventario.

> [!NOTE]
> La actividad de dispositivo móvil solo activará los ajustes de la transacción si el método de desviación de peso de salida de la directiva de manipulación de artículos de peso capturado del artículo es **Permitir la desviación del peso**.

**Ejemplo 1**

Durante un proceso de producción **Notificar como terminado** , el peso de entrada de una matrícula de entidad de almacén que contiene ocho cajas de un producto con peso capturado se captura como 80,1 kilogramos. La matrícula de entidad se almacena en el área de productos finalizados y durante el proceso de almacenado, algo de peso se pierde en el aire.

Más adelante, como parte de un proceso de selección de pedido de ventas, el peso de la misma matrícula de entidad se captura como 79,8 kilogramos. Por tanto, en el sistema, dispondrá una diferencia del peso como parte del conjunto de dimensiones físico.

En este caso, el sistema ajusta automáticamente la diferencia registrando una transacción para los 0,3 kg que faltan.

**Ejemplo 2**

En su definición, un producto se configura para tolerar un peso mínimo de 8 kilogramos y un máximo de 12 kg para la unidad **Caja** de peso capturado.

Tiene dos cajas del producto y tienen un peso registrado de 16 kilogramos. Si un trabajador del almacén pesa y selecciona una de las cajas, y el peso se captura como 9 kg, la caja restante pesará 7 kilogramos. Sin embargo, dado que 7 kg por debajo del peso mínimo, el sistema realiza un ajuste automático para aumentar el peso del inventario disponible en 1 kilogramo.

Para configurar las cuentas en que estos ajustes se registrarán, vaya a **Coste la administración \> Directivas de integración contable configurados \> Registro**. A continuación, en la pestaña **Inventario** , defina las cuentas siguientes:

- Cuenta de pérdidas de peso capturado 
- Cuenta de ganancias de peso capturado 

## <a name="catch-weight-item-handling-policy"></a>Directiva de manipulación de artículos con peso capturado

El artículo con directiva de administración de peso capturado define los dos flujos principales de gestión de almacenes de los artículos: cuando el peso de los artículos se obtiene, y cómo se captura.

Puede definir cuando el peso se captura para ventas y el procesamiento del pedido de transferencia. El peso se puede capturar durante cualquiera de los siguientes procesos:

- **Selección** - El peso se captura durante las líneas iniciales del trabajo de la selección de trabajo del pedido.
- **Embalaje** - La captura peso se durante el embalaje manual. (Debe enviar los artículos a una instalación de embalaje).

Si el peso real se captura en la instalación de embalaje durante los procesos de embalaje de contenedor, no se solicitará a los trabajadores del almacén que capturen el peso durante el trabajo de selección. En su lugar, el peso medio del inventario físico se usará como el peso del inventario seleccionado que va al área de embalaje. Este concepto también se aplica a artículos de peso capturado rastreados por etiquetas. Para los elementos con seguimiento de etiqueta, estos parámetros determinan cuándo se captura la etiqueta. La etiqueta se puede capturar en el momento de la selección mediante el dispositivo móvil o durante el embalaje manual.

> [!NOTE]
> Como la opción **Embalaje** hace que el inventario se actualice con el peso medio seleccionado, esto podría desencadenar una discrepancia que tendría como resultado un ajuste de ganancia/pérdida de peso capturado o una diferencia entre el peso de inventario disponible y el peso de etiqueta de peso capturado.

Para los procesos internos de gestión de almacenes como correcciones del recuento y ajuste, puede definir si se debe capturar el peso. Si no captura, se usa el peso nominal. Otras opciones le permiten capturar el peso por unidad de peso capturado y por cantidad contable.

También puede definir cómo se captura el peso. En uno de los dos flujos principales, las etiquetas de peso capturado se siguen y se utilizan para capturar peso. En el otro flujo, etiquetas de peso capturado no se siguen.

- **Sí** El artículo utiliza etiquetas de peso capturado. Cada número de etiqueta representa una unidad de peso capturado (caja), y un peso y otra información está asociado con la etiqueta. Para los procesos de salida, se utiliza el peso que está asociado a la etiqueta.
- **No** - El artículo no utiliza etiquetas de peso capturado. Los procesos de pesado de entrada y salida se basan en el peso real que se captura durante cada proceso.

El proceso de seguir etiquetas de peso capturado se puede usar para los artículos que no cambiarán el peso durante el período de almacenado. El peso se captura sólo durante el proceso de entrada del almacén. Durante el proceso de salida, las etiquetas de peso capturado sólo se digitalizan, y los pesos que están asociados a las etiquetas se usarán para el procesamiento de salida transaccional.

Otro parámetro importante relacionado con el procesamiento de las etiquetas de peso capturado es **Método de seguimiento de dimensión de etiqueta de peso capturado**. Las etiquetas se pueden rastrear parcial o completamente. Si una etiqueta se rastrea parcialmente, se rastrean las dimensiones del producto, las dimensiones de seguimiento y el estado del inventario. Si una etiqueta se rastrea completamente, se rastrean las dimensiones del producto, las dimensiones de seguimiento y **todas** las dimensiones de almacenamiento.

Además, cuando se realiza un seguimiento de etiqueta de un artículo, hay un parámetro de **Método de captura de etiqueta de salida**. Puede establecer este parámetro para que siempre se le solicite la etiqueta en las transacciones salientes desde el dispositivo móvil. Como alternativa, puede establecer el parámetro para que solo se le soliciten las etiquetas cuando sean necesarias. Por ejemplo, hay cinco etiquetas de peso capturado en el inventario para una matrícula determinada, y ha indicado que desea elegir las cinco etiquetas de la matrícula. En este caso, si el parámetro **Método de captura de etiqueta de salida** se establece en **Solicitar la etiqueta solo cuando sea necesario**, las cinco etiquetas se seleccionan automáticamente. No tiene que escanear cada etiqueta. Si el parámetro se establece en **Solicitar siempre la etiqueta**, debe escanear cada etiqueta, incluso si se seleccionan las cinco etiquetas.

> [!NOTE]
> Como regla general, las etiquetas se capturan y actualizan solo desde los elementos del menú del dispositivo móvil. Sin embargo, hay algunos escenarios en los que las etiquetas se capturan en otro lugar (por ejemplo, desde la estación de embalaje manual). Sin embargo, en general, los elementos del menú del dispositivo móvil deben usarse para toda la actividad del almacén si se usan etiquetas.

### <a name="how-to-capture-catch-weight"></a>¿Cómo capturar el peso capturado?

**Cuando se usa el seguimiento de la etiqueta de peso capturado**, siempre se debe crear una etiqueta para cada unidad de peso capturado recibida, y cada etiqueta debe asociarse siempre a un peso.

Por ejemplo, **Caja** es la unidad de peso capturado, y usted recibe un pallet de ocho cajas. En este caso, deberán crearse ocho etiquetas únicas de peso capturado, y un peso se debe asociar a cada etiqueta. En función de la etiqueta de entrada con peso capturado, el peso de las ocho cajas puede capturarse, y el peso medio se puede distribuir a cada caja, o se puede capturar un peso único para cada caja.
Cuando use la característica **Use las etiquetas de peso de captura existentes al informar las órdenes de producción como terminadas** con el proceso habilitado a través de un elemento de menú del dispositivo móvil, el inventario se actualiza en función de la información de la etiqueta de peso de captura existente. Como resultado, la aplicación de almacén no solicita capturar los datos de la etiqueta de peso de captura como parte de un informe de producción como una operación finalizada.

**Cuando el seguimiento de etiquetas de peso capturado no se usa**, el peso se puede capturar para cada conjunto de dimensiones (por ejemplo, para cada matrícula de entidad y cada dimensión de seguimiento). Como alternativa, el peso se puede capturar en función de un nivel agregado, como cinco matrículas de entidad (pallets).

Para los métodos de captura de peso saliente, la opción **Por unidad de peso capturado** le permite especificar que la medición de peso debe realizarse para cada unidad de peso capturado (por ejemplo, por caja). La opción **Por unidad de selección** le permite especificar que el peso debe capturarse en función de la cantidad que se va a seleccionar (por ejemplo, tres cajas). Tenga en cuenta que para el proceso de selección de la línea y el de movimiento interno, el peso medio se usará si se usa la opción **No capturado**.

Se definen varios métodos de captura de peso en la directiva de manipulación de artículos de peso capturado. Cada parámetro de método de captura de peso es utilizado por varias transacciones. En la tabla siguiente se resume qué parámetros son utilizados por qué transacciones.

| Método                                     | Transacción                                |
|--------------------------------------------|--------------------------------------------|
| Método de captura de peso de salida           | Selección de ventas, selección de transferencia            |
| Método de captura de peso de selección de producción | Selección de producción, consumo de producción |
| Método de captura de peso de movimiento           | Movimiento                                   |
| Cuándo capturar la correción del peso       | Ajustes, recuento                      |
| Método de captura de peso de recuento           | Recuento                                   |
| Método de captura de peso de transferencia de almacén | Transferencia de almacén                         |

Para evitar que los procesos de selección de la gestión de almacenes capturen pesos que puedan generar ajustes de ganancias/pérdidas en los pesos capturados, puede usar el método de desviación del peso de salida. El método de variación de peso de salida se aplica durante los siguientes procesos de dispositivo móvil: selección de ventas, selección de transferencia, selección de producción, movimientos, recuento y transferencias de almacén. Puedes usar la opción **Desviación limitada del peso** si el peso del artículo de peso capturado no fluctúa durante su almacenamiento en el almacén y si no se requieren ajustes de ganancia/pérdida de peso capturado. Puede usar la opción **Permitir la desviación del peso** si el peso puede fluctuar, y si se requieren ajustes de ganancia/pérdida de peso capturado cuando se registra una fluctuación de peso.

## <a name="unsupported-scenarios"></a>Escenarios no admitidos

No todos los flujos de trabajo son compatibles con el procesamiento de producto con peso capturado en la gestión de almacenes. Actualmente se aplican las siguientes restricciones. Se aplican a todos los artículos de peso capturado, independientemente de si están etiquetados o no.

### <a name="configuring-catch-weight-products-for-warehouse-management-processes"></a>Configurar productos de peso capturado para los procesos de gestión de almacenes

- Solo el procesamiento de la fórmula se admite para los productos con peso capturado (no lista de materiales).
- Los productos con peso capturado no se pueden asociar un grupo de dimensiones de seguimiento mediante la dimensión del propietario.
- Los productos con peso capturado no se pueden usar como servicios.
- Los productos con peso capturado se pueden usar como “productos mantenidos en existencias” sólo como parte el grupo de modelos de artículos.
- Los productos con peso capturado no se pueden usar junto con la funcionalidad para seguir “Activo en proceso de ventas.”
- Los productos con peso capturado no se pueden usar junto con la funcionalidad para capturar números de serie. Por lo tanto, los productos no se pueden transferir de “en blanco” a un número de serie como parte de la selección/proceso de embalaje.
- Los productos con peso capturado no se pueden usar junto con la funcionalidad para registrar números de serie antes del consumo.
- Los productos con peso capturado con variante habilitada no se pueden usar junto con la funcionalidad para convertir unidades de medida variables.
- No se puede marcar productos de peso capturado como "kit de producto" comercial.
- Los productos con peso capturado sólo se pueden usar en un grupo de secuencias que tenga unidades de gestión de material de peso capturado y que contenga la unidad de peso capturado como la secuencia más baja.
- Para los productos con peso capturado, la unidad de inventario se puede convertir a la unidad de peso capturado si la conversión genera una cantidad nominal mayor de 1.
- La configuración de los códigos de barras para los productos con peso capturado no admite una configuración variable de peso.

### <a name="order-processing"></a>Procesamiento de pedidos

- La creación de aviso de envío por adelantado (estructuras de ASN/embalaje) no admite la información de peso.
- La cantidad del pedido debe mantenerse según la unidad de peso capturado.

### <a name="inbound-warehouse-processing"></a>Procesamiento de entradas en el almacén

- Recibir las matrículas requiere que los pesos sean asignados durante el registro, porque la información del peso no se admite como parte del aviso de envío por adelantado. Cuando se usan los procesos de la etiqueta de peso capturado, el número de etiqueta se debe asignar manualmente por unidad de peso capturado.
- El trabajo de control de calidad entrante no es compatible con los productos de peso capturado. Si está configurado, se omitirá el trabajo de control de calidad.

### <a name="inventory-and-warehouse-operations"></a>Operaciones de inventarios y almacenes

- La creación manual de pedidos de cuarentena no se admite para los productos con peso capturado.
- El movimiento manual de inventario relacionado con el trabajo abierto no se admite para los productos de peso capturado.
- La carga del número de matrícula de entidad al inicializar las existencias del almacén no se admite para los productos con peso capturado.
- Los procesos de equilibrio por lotes no son admitidos para los productos de peso capturado.
- La gestión del inventario negativo físico no se admite para los productos con peso capturado.
- El marcado de inventario no se puede usar para los productos con peso capturado.

### <a name="outbound-warehouse-processing"></a>Procesamiento de salidas en el almacén

- La funcionalidad para la selección del clúster no se admite para los productos con peso capturado.
- El procesamiento del almacén de la selección y el embalaje no se admite para los productos con peso capturado.
- Para los productos con peso capturado, el trabajo que se define en una plantilla de trabajo no se puede ejecutar automáticamente.
- Para los productos con peso capturado, el sistema no admite el procesamiento manual de estación de embalaje, donde se crea el trabajo de selección de contenedor empaquetado después de cerrar los contenedores.
- La funcionalidad para el escaneo pieza a pieza no se admite para los productos con peso capturado.

### <a name="production-processing"></a>Proceso de producción

- Para los productos con peso capturado, sólo se admiten los pedidos de lote para los productos de la fórmula.
- La funcionalidad kanban no se admite para los productos con peso capturado.
- Para los productos con peso capturado, los números de serie no se pueden registrar antes del consumo.
- La funcionalidad para la inversión de matrículas de entidad desde producción no se admite para los productos con peso capturado.
- Para los productos con peso capturado, la notificación como terminado no se puede registrar por número de serie.

### <a name="transportation-management-processing"></a>Procesado de la administración del transporte

- Los productos de peso capturado no admiten el procesado de área de trabajo de planificación de la carga.
- Las líneas de la solicitud de transporte no se admiten para los productos con peso capturado.

### <a name="other-restrictions-and-behaviors-for-catch-weight-product-processing-with-warehouse-management"></a>Otras restricciones y comportamientos para el procesamiento de productos con peso capturado con la gestión de almacenes

- Durante los procesos de la selección en los que no se pide al usuario identificar dimensiones de seguimiento, la asignación del peso se realiza en función del peso medio. Este comportamiento aparece si, por ejemplo, una combinación de dimensiones de seguimiento se usa en la misma ubicación y, después de que un usuario procese selección, sólo un valor de la dimensión de seguimiento se deja en la ubicación.
- Cuando el inventario se reserva para un producto con peso capturado que está configurado para los procesos de gestión de almacenes, la reserva se realiza en función del peso mínima definido, incluso si esta cantidad es la cantidad que se ha administrado a mano. Este comportamiento difiere del comportamiento de los artículos que no se configuran para los procesos de la gestión de almacenes. Hay una excepción a esta restricción. Para la selección de producción, cuando se selecciona la última cantidad de manipulación de un producto de peso capturado que está controlado por número de serie, se utiliza el peso real.
- Los procesos que usan el peso como parte de los cálculos de la capacidad (umbrales de la gama, descansos del máximo del trabajo, máximos de contenedor, capacidades de carga de la ubicación, etc.) no utilizan el peso real del inventario. En su lugar, los procesos se basan en el peso de administración física que se define para el producto.
- En general, la funcionalidad de Commerce no se admite para los productos de peso capturado.
- Para productos de peso capturado, el estado del inventario no se puede actualizar desde **Cambio de estado de almacén**.

### <a name="catch-weight-tags"></a>Etiquetas de peso capturado

Una etiqueta de peso capturado se puede crear mediante un proceso de la aplicación de almacén, manualmente en el formulario o mediante un proceso de la entidad de datos. Si una etiqueta de peso capturado se asocia a una línea de entrada del documento de origen, como por ejemplo una línea de pedido de compra, se registra la etiqueta. Si la línea se utiliza para el procesamiento de salida, se actualizará la etiqueta como enviada.

Además de las restricciones que se aplican actualmente para los productos de peso capturado, los productos de peso capturado etiquetados tienen otras restricciones que se aplican actualmente.

- Todas las actualizaciones manuales del inventario (es decir, las actualizaciones que no se realizan mediante un dispositivo móvil) deben incluir las actualizaciones manuales correspondientes a las etiquetas de peso capturado asociadas porque estas actualizaciones no se realizan automáticamente. Por ejemplo, los diarios de ajuste manual actualizarán el inventario, pero no las etiquetas de peso capturado asociadas.
- Debe actualizar manualmente las etiquetas de peso capturado para reflejar los movimientos de trabajo de reabastecimiento. Esto se debe a que el sistema no puede capturar pesos mientras procesa el trabajo de reabastecimiento y, por lo tanto, registra el peso promedio.
- Actualmente no se admite la recepción de una matrícula mixta para artículos de peso capturado etiquetados.
- El procesamiento de la recepción de pedidos de devolución de ventas puede registrar etiquetas de peso capturado. Sin embargo, el proceso no valida que la etiqueta devuelta sea la misma etiqueta que se envió originalmente para un pedido de ventas.
- El elemento de menú del dispositivo móvil que tiene el código de actividad de **Registrar lista de selección** no permite registrar etiquetas de peso capturado.
- Aunque los procesos de recuento son compatibles con los artículos de peso capturado etiquetados, son limitados. Por ejemplo, puede usar las opciones del dispositivo móvil para contar artículos de peso capturado etiquetados, y se usa el peso medio. Sin embargo, la transacción de recuento no actualiza automáticamente las etiquetas de peso capturado. Una vez completada la transacción de recuento hay que actualizar manualmente las etiquetas de peso capturado para que reflejen el inventario. Si los artículos que no estaban originalmente en una ubicación se cuentan como de esa ubicación, se utiliza el peso nominal.
- Actualmente la consolidación de matrículas no admite artículos de peso capturado etiquetados.
- No se admite la funcionalidad de trabajo inverso para artículos de peso capturado que tienen seguimiento de número de etiqueta.

> [!NOTE]
> La información anterior sobre las etiquetas de peso capturado solo es válida si el producto de peso capturado tiene un método de seguimiento de dimensión de etiqueta de peso capturado para hacer un seguimiento completo (es decir, si el parámetro **Método de seguimiento de dimensión de etiqueta de peso capturado** de la directiva de manipulación de artículos de peso capturado se establece en **Dimensiones del producto, dimensiones de seguimiento y todas las dimensiones de almacenamiento**). Si solo se realiza un seguimiento parcial de las etiquetas del elemento de peso capturado (es decir, si el parámetro **Método de seguimiento de dimensión de etiqueta de peso capturado** de la directiva de manipulación de artículos de peso capturado se establece en **Dimensiones del producto, dimensiones de seguimiento y estado del inventario**), se aplican restricciones adicionales. Debido a que, en este caso, se pierde visibilidad entre la etiqueta y el inventario, no se admiten algunos escenarios adicionales.
